# The Architect's New Role: From System Design to System Ecology

*Part 2 of a series on how AI is transforming software engineering — and what it means for architects, developers, testers, and leaders.*

---

In the first post of this series, I argued that software engineering has reached a tipping point — not because AI writes code faster, but because that speedup is pressuring every other layer of the delivery system simultaneously. Build pipelines, code review, testing, version control, release processes — none were designed for the throughput that AI-assisted development is now generating.

If that is the systemic problem, then the architect is the person who has to solve it. Not by writing better code — the machines are handling that — but by designing the environment in which code is produced, validated, and sustained.

This is the shift I want to unpack: the architect's centre of gravity is moving from designing systems to designing system ecologies.

## What Changed

For most of my career, architecture meant making structural decisions about software. Monolith or microservices. Sync or async messaging. SQL or document store. Which frameworks, which protocols, which deployment topology. The architect drew boxes and lines, defined service boundaries, wrote canonical designs, and ensured the system could scale, perform, and evolve.

Those decisions still matter. But they are no longer where the hardest architectural problems live.

The hardest problems now sound like this: When should the model use a tool versus load a skill versus spawn a subagent? How much complexity belongs in the system prompt versus external memory? Which actions require deterministic enforcement versus soft guidance? How do you structure evaluation so that every change arrives with verifiable evidence? How do you manage token budgets across a multi-agent workflow without degrading quality?

These are not programming questions. They are not even traditional system design questions. They are questions about designing an environment — an ecology — in which humans, models, tools, policies, memories, and evaluators interact.

> **[FIGURE 1: "From System Design to System Ecology"]**
> *Visual type: Side-by-side comparison. Left: "Classical Architecture" showing boxes-and-lines diagram (services, databases, APIs, queues) — static, structural. Right: "System Ecology" showing a living network with humans, agents, tools, skills, memory layers, eval loops, approval gates, and feedback arrows — dynamic, interactive.*
> *The visual should make clear that the right side is not just "more complex" — it is a fundamentally different kind of thing. The classical diagram is a blueprint. The ecology diagram is an operating environment.*
> *Style: Architectural, clean. Left side in monochrome/blueprint style. Right side in color with visible feedback loops and interaction patterns.*

## Context Engineering Is the New Architecture

Anthropic's engineering team frames the core challenge explicitly: the most important job in building AI agents is not prompt engineering. It is context engineering — managing the whole evolving state that surrounds the model. That includes the system prompt, yes, but also tools, memory, external data, message history, and every token that accumulates during a long-running task.

This is architectural work. The architect now decides questions such as: Which facts live in the agent's live context versus external memory? Which capabilities are exposed as tools, which are packaged as reusable skills, which are enforced through deterministic hooks, and which are delegated to subagents with separate permissions or cheaper models?

The decision surface has changed. The classic architecture decision record asked about service boundaries and data stores. The AI-first ADR asks:

- **Use a tool** when the capability is external, deterministic, or action-oriented — fetching data, executing code, calling a service, taking a real-world step. Both Anthropic and LangChain emphasize that tools need distinct purpose, clear descriptions, minimal overlap, and token-efficient outputs. Otherwise the model will choose poorly.

- **Use a skill** when the agent needs reusable procedural knowledge or domain guidance while staying in control of the conversation. Skills provide reference content, conventions, or step-by-step procedures that persist in context once loaded. They are for information the model needs some of the time, not all of the time.

- **Use a subagent** when the task would pollute the main context, needs different permissions or a different model, or can be explored in parallel. Subagents isolate context, preventing a side-task from flooding the main conversation with irrelevant tokens.

This is not a taxonomy for its own sake. It is a design discipline. Will, from Anthropic's Applied AI team, demonstrated this at Code with Claude London with a concrete case study: an inventory management agent whose system prompt had grown to 400 lines, with 12 tools and 3 subagents bolted on over time. Eval scores were degrading. The fix was not better prompting — it was architectural decomposition. They shortened the system prompt to 15 lines, replaced business logic with skills for progressive disclosure, consolidated 12 tools down to 3 primitive capabilities (bash, read, write), and kept only one subagent where genuine context isolation was needed. Eval scores climbed from 62% to 92%. Token usage dropped dramatically because the agent could write and execute code instead of consuming entire datasets into its context window.

The lesson is clear: prompt sprawl behaves like hidden coupling. Anthropic warns against hardcoding brittle logic into prompts or stuffing them with laundry lists of edge cases. Their own Claude Code best-practices guide calls out the over-specified CLAUDE.md as a failure pattern — important rules get lost in the noise, and every unnecessary line is a recurring token cost across turns.

> **[FIGURE 2: "The Architect's New Decision Surface — Tool, Skill, or Subagent?"]**
> *Visual type: Decision flowchart or decision matrix. Three columns: Tool / Skill / Subagent. Rows: When to use, What it does, Context impact, Token cost pattern, Example.*
> *Key decision triggers: "Is it external/deterministic?" → Tool. "Is it reusable knowledge needed sometimes?" → Skill. "Would it pollute the main context or need different permissions?" → Subagent.*
> *Include the before/after from Will's inventory agent case: 400-line prompt + 12 tools + 3 subagents → 15-line prompt + 3 primitives + skills + 1 subagent. Eval: 62% → 92%.*
> *Style: Clean decision diagram. Practical, not theoretical — the reader should be able to use this to evaluate their own agent architecture.*

## Conway's Law in an Agentic World

Conway's law has not disappeared. It has become more interesting.

The original observation — that organizations build technologies mirroring their communication structures — still holds. But in the AI-first era, the "communication structure" no longer consists only of humans and teams. It also includes prompts, tool namespaces, memory layers, routing rules, evaluator loops, and approval checkpoints. The architecture of your agent system will mirror the structure of these interactions, whether you design it intentionally or not.

LangChain's multi-agent guidance makes this concrete. They observe that developers turn to multi-agent systems for three reasons: context management, distributed development, and parallelization. But they also warn that not every complex task requires a multi-agent design — often a single agent with the right tools and prompt is enough. That is a modern Conway's law point: boundaries should exist where they improve cognition, ownership, or throughput, not because "multi-agent" sounds advanced.

Anthropic's research system illustrates how quickly those boundaries become socio-technical. Their lead agent had to be taught how to delegate. Each subagent needed an objective, an output format, guidance on tools and sources, and clear task boundaries. Without that structure, agents duplicated work, left gaps, or explored the wrong problem. And they observed emergent behaviour: small changes to the lead agent's prompt could unpredictably alter subagent behaviour. The best prompts were not strict instruction lists but frameworks for labour division, effort budgets, and collaboration.

This is why the architect's role is becoming ecological. The system's important properties now emerge from interactions among humans, models, prompts, evaluators, and external systems. You cannot predict them by examining any single component. You can only understand them by observing the ecology as a whole.

> **[FIGURE 3: "Conway's Law Extended — Communication Structures in an Agentic Organization"]**
> *Visual type: Two-panel diagram. Left: "Traditional Conway's Law" — org chart with teams mapped to system components (Team A → Service A, Team B → Service B). Right: "Agentic Conway's Law" — same org but now the communication structure includes agents, prompts, tool namespaces, memory layers, eval loops, and approval gates alongside human teams.*
> *The point: the "communication structure" that shapes your architecture is no longer just humans talking to humans. It includes every interaction channel between humans, agents, tools, and policies.*
> *Style: Conceptual, clean. The right panel should feel notably more complex but not chaotic — it should feel like a richer, more interconnected version of the same principle.*

## The 10x Stress Test — What Breaks First

In the previous post, I walked through the 10x stress test at a high level. Here I want to go deeper into what the architect specifically needs to worry about, drawing on what Google has already learned at extreme scale.

**Build systems fail first if they are not hermetic.** Google's build philosophy emphasizes speed and correctness together, not as a trade-off. Remote caching works only if builds are reproducible. Distributed builds require self-describing environments, self-contained build steps, and deterministic outputs. Google runs millions of builds and millions of test cases per day, with many artefacts served from cache rather than rebuilt. In an AI-heavy environment, a weak build graph or ad hoc scripts become architectural liabilities because compute, not authoring, becomes the bottleneck.

**Version control breaks under branch proliferation.** Google's "One Version" rule and near-elimination of long-lived branches are throughput controls. They reduce choice, merge friction, and divergence. If agents produce many more changes, branchy workflows amplify reconciliation cost. Trunk discipline, clear ownership, and small increments become more important, not less.

**Code review becomes the hard human bottleneck.** Google's Large-Scale Changes chapter observed that as change-generation tooling improved, it became much cheaper to generate large numbers of changes and easier for one engineer to impose burdens on many reviewers. That is an almost exact description of the AI era. Google's response: embed code review into Critique, integrate Tricorder static analysis directly into the diff (analyzing over 50,000 changes per day), deploy AutoCommenter to tens of thousands of developers, and add ML-suggested edits that now resolve 7.5% of reviewer comments — projected to save hundreds of thousands of engineer-hours annually.

Anthropic's practices point to the same conclusion from the agent side: unattended work should be followed by an adversarial review subagent in a fresh context. The agent should always have a way to verify its own work through tests or outputs. Review becomes partly automated, partly delegated, and tightly linked to evidence.

**Testing must produce trustworthy evidence fast enough to gate changes.** At 10x throughput, the challenge is no longer "do we have tests?" but "can the system cheaply produce trustworthy evidence fast enough?" LangChain's reference CI/CD pipeline adds offline evals, end-to-end runs, trajectory analysis, online evaluation, and alerting on top of conventional tests. Google expects every change to include tests, blocks changes without them, and computes coverage for one billion lines of code daily.

The main insight: once AI makes code generation cheap, review, verification, reproducibility, and deployment governance become the real architecture.

> **[FIGURE 4: "The 10x Stress Test — Architect's View"]**
> *Visual type: Vertical pipeline diagram showing the full delivery chain (Code Generation → Build → Version Control → Code Review → Testing → Release → Production). Each stage has a "Before AI" capacity indicator and an "After 10x" capacity indicator showing where bottlenecks form.*
> *Key annotations at each stage with specific data: Build (hermetic builds, cache-dependent), VCS (One Version rule, trunk discipline), Code Review (Tricorder: 50K changes/day, AutoCommenter, ML edits: 7.5% of comments), Testing (1B LOC coverage daily at Google), Release (green-head promotion, quality gates).*
> *The visual should make clear that the bottleneck migrates downstream from code generation into every subsequent stage.*
> *Style: Engineering blueprint. Each stage as a pipe with capacity indicators (green → amber → red).*

## Tokens Are Architecture, Not Accounting

Here is a shift that most architects have not internalized yet: token economics is now a first-class architectural concern.

Anthropic's production research system found that token usage alone explained 80% of the variance in their BrowseComp benchmark performance. Multi-agent systems typically used around 4x the tokens of single chat interactions, and around 15x for complex multi-agent research runs. Those systems were economically viable only when the task value justified the spend. But they also outperformed single-agent setups by 90.2% on breadth-first research evaluations — a useful reminder that token spend sometimes buys genuinely better outcomes.

The costs are concrete. Anthropic's pricing documentation lists tool overhead explicitly: a 245-token overhead for the bash tool and a 700-token overhead for the text-editor tool on Claude 4.x, plus per-search charges for web search. Skill content stays in context across turns, making every unnecessary line a recurring cost. Prompt caching can amortize some of this, but cache validity is sensitive to changes in tool definitions and system settings.

This creates real architectural trade-offs. LangChain's performance comparisons show that stateful patterns like handoffs and skills save 40-50% of model calls relative to stateless subagents for repeated requests. But for multi-domain requests, subagents and routers can use parallel execution and context isolation to process roughly 9K tokens versus 15K for skills, despite making more model calls. The architectural choice is not "fewest calls always wins." It is "choose the pattern whose call graph and context pattern best match the workload."

An Amdahl's-Law lens is useful here. Once models get faster or cheaper, the serial fraction dominates overall latency: tool round trips, network waits, approval prompts, evaluator passes, handoff overhead. Anthropic's research team reports that adding parallel subagents and parallel tool calls cut research time by up to 90%. The architect's question is no longer "which model is faster?" It is "what fraction of this task is still serial, and how do I redesign the ecology to parallelize or bypass it?"

> **[FIGURE 5: "Token Economics as Architecture"]**
> *Visual type: Sankey diagram or flow chart showing token flow through a multi-agent system. Inputs: system prompt, skills loaded, tool definitions, tool results, message history, subagent transcripts. Show how tokens accumulate across turns and how architectural choices (skills vs subagents, code execution vs direct tool calls, prompt caching) affect total token consumption.*
> *Key data callouts: "Multi-agent: ~4x tokens of chat, ~15x for complex runs" (Anthropic), "Bash tool: 245-token overhead, Text editor: 700-token" (Anthropic pricing), "Stateful patterns save 40-50% calls vs stateless subagents" (LangChain).*
> *Style: Data visualization showing flow and accumulation. The reader should see where tokens pile up and where architectural choices can reduce them.*

## The Harness Is the Architecture

A name has emerged for what architects are actually building when they design AI-native systems: **harness engineering** — the discipline of designing the scaffolding (context delivery, tool interfaces, planning artifacts, verification loops, memory systems, and sandboxes) that surrounds an agent and determines whether it succeeds or fails on real tasks.

Every component of a harness exists because the model cannot do that thing alone. And the best harnesses are designed knowing that each component will eventually become unnecessary as models improve. That design horizon is what distinguishes harness engineering from mere prompt engineering.

The Microsoft Azure SRE Agent provides the most compelling production evidence for this framing. The system has autonomously handled over 35,000 production incidents, reducing time-to-mitigation from 40.5 hours to 3 minutes. The architectural key was not a better model — it was a better harness. The team replaced over 100 bespoke specialized tools with a filesystem-based context engineering approach: source code, runbooks, query schemas, and past investigation notes were all exposed as files, and the agent navigated using read_file, grep, find, and shell. The "Intent Met" score on novel incidents rose from 45% to 75%. Specialized tooling lost to a well-designed context surface.

Martin Fowler characterizes the emerging role as "humans on the loop" — architects and engineers who design and maintain agent environments rather than inspecting individual outputs. This is distinct from prompt engineering and from traditional system design. It is closer to operating system design: you are building the environment in which programs run.

## What the Role Looks Like in Practice

The emerging architect is becoming a designer of constraints, surfaces, and feedback loops. In practice, that means five things:

**First, defining the boundary between deterministic policy and model discretion.** Which actions are enforced by hooks, middleware, permission systems, human approval gates, and classifier-based safety checks? Which are left to the model's judgment? Anthropic's hooks and auto mode, LangChain's human-in-the-loop middleware — these are the architect's tools for drawing the line between what the model decides and what the system enforces.

**Second, designing context topology.** What stays inline in the conversation? What becomes a skill loaded on demand? What is summarized to save tokens? What is stored in external memory? What is delegated to an isolated subagent? This is the new equivalent of database schema design — except the substrate is the model's attention, and the cost of getting it wrong is degraded reasoning, not just slow queries.

**Third, embedding evaluation and observability into the architecture from the start.** Not as an afterthought. Not as a monitoring dashboard bolted on after launch. Evaluation loops, trace collection, experiment infrastructure, and feedback mechanisms are structural elements of the system. LangSmith's lifecycle spans tracing, experiments, offline evaluation, online monitoring, deployment, and feedback. Anthropic's telemetry can attribute cost and tokens by model, subagent, skill, or tool.

**Fourth, managing throughput economics.** The architect now tracks review latency, token spend per successful task, tool-selection error rates, prompt-compaction frequency, and the fraction of changes that arrive with verifiable evidence. These are the new SLIs for a system where generation is cheap and verification is expensive.

**Fifth, curating system ecology health.** This is the broadest and most important responsibility. The architect is no longer only drawing boxes and lines. The architect is tuning an evolving ecosystem of humans, agents, tools, and policies — watching for emergent behaviour, adjusting boundaries, and ensuring that the system can sustain itself as it grows. A bad tool description, a lax permission policy, an under-specified eval, a noisy context budget — any of these can degrade the same user-facing outcome. The architecture is a web of shared operational fate.

> **[FIGURE 6: "The Five Practices of the System Ecology Architect"]**
> *Visual type: Concentric rings or pentagon diagram showing the five architectural practices: (1) Deterministic vs Model Discretion (innermost — the hard boundaries), (2) Context Topology, (3) Evaluation & Observability, (4) Throughput Economics, (5) System Ecology Health (outermost — the living environment).*
> *Each ring/vertex should have 2-3 concrete examples: (1) hooks, approval gates, classifier checks; (2) skills, subagents, memory layers, summarization; (3) evals, traces, experiments, feedback loops; (4) token budgets, cost attribution, review latency SLIs; (5) emergent behavior monitoring, shared fate, boundary adjustment.*
> *Style: Clean, layered. Should feel like a maturity model or operating framework the reader can actually adopt.*

## Shared Fate in Agent Systems

Google SRE coined the term "shared fate" to describe how components grouped by configuration, shard placement, or networking fail together. Google Cloud uses it more broadly to describe ongoing partnerships that improve outcomes together rather than dividing responsibility transactionally.

In agent systems, shared fate maps onto the relationship among architect, platform team, tool owners, security team, and product team. A bad tool description, a lax permission policy, an under-specified eval, or a noisy context budget can all degrade the same user-facing outcome. Nobody owns the failure individually. Everyone shares its consequences.

This is why the architect's role feels different now. You are not just designing a system that other people will build. You are designing the operating conditions under which humans and agents will collaborate — and you are responsible for the emergent outcomes of that collaboration. The system is alive, and it needs a gardener as much as it needs an engineer.

---

*Next in the series: **The Developer's Identity Shift — From Writing Code to Steering Intent***

---

### Sources and References

**Conference Talks**
- Adam Bender, ["Software Engineering at the Tipping Point,"](https://io.google/2026/explore/workshop-2) Google I/O 2026 — [YouTube](https://www.youtube.com/watch?v=2n41YjR5QfU)
- Nicole Forsgren and Andrew MacVean, ["Build Core Skills to Thrive as an AI-Era Developer,"](https://io.google/2026/explore/workshop-4) Google I/O 2026
- Will (Anthropic Applied AI), ["Tool, Skill, or Subagent: Decomposing an Agent That Outgrew Its Prompt,"](https://claude.com/code-with-claude/) Code with Claude London (May 19, 2026)
- Harrison Chase, ["The Agent Development Lifecycle,"](https://interrupt.langchain.com/) LangChain Interrupt 2026 (May 13-14, 2026)

**Anthropic Documentation and Research**
- Anthropic, ["Building Effective Agents"](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/building-effective-agents) — context engineering, tool design, decomposition patterns (orchestrator-worker, evaluator-optimizer)
- Anthropic, ["Research System"](https://www.anthropic.com/engineering/building-research-system) — lead agent delegation, emergent behaviour, multi-agent outperformed single-agent by 90.2%, token usage explained 80% of BrowseComp variance, parallel subagents cut research time by up to 90%
- Anthropic, Claude Code documentation — hooks, skills, subagents, auto mode, telemetry, CLAUDE.md best practices
- Anthropic, Pricing documentation — tool overhead: 245-token bash, 700-token text-editor on Claude 4.x

**Google Engineering**
- Titus Winters et al., *Software Engineering at Google* (O'Reilly, 2020) — monorepo, trunk-based development, Large-Scale Changes, Critique, Tricorder (50,000+ changes/day), code coverage for 1B LOC daily
- Google, AutoCommenter and ML-suggested edits — deployed to tens of thousands of developers; ML edits resolve 7.5% of reviewer comments
- Google SRE / Google Cloud — shared fate concept

**LangChain**
- LangChain, [Multi-Agent Systems guidance](https://langchain-ai.github.io/langgraph/) — when to use subagents vs skills vs routers; context management, distributed development, parallelization
- LangChain, Performance comparisons — stateful patterns save 40-50% calls; subagents process ~9K vs ~15K tokens for multi-domain requests
- LangSmith, CI/CD reference pipeline — offline evals, trajectory analysis, online evaluation, quality-gated deployment

**Thoughtworks**
- ["Spec-Driven Development,"](https://www.thoughtworks.com/en-us/insights/blog/agile-engineering-practices/spec-driven-development-unpacking-2025-new-engineering-practices) Thoughtworks (Dec 2025)
- ["Codebase Cognitive Debt,"](https://www.thoughtworks.com/radar/techniques/codebase-cognitive-debt) Thoughtworks Technology Radar (April 2026) — architectural fitness functions as countermeasure

**Other**
- Melvin Conway, "How Do Committees Invent?" (1968) — original formulation of Conway's law
- ACM Ethics Committee — sociotechnical systems framework
