# The Architect's New Role: From System Design to System Ecology

*Part 2 of a series on how AI is transforming software engineering — and what it means for architects, developers, testers, and leaders.*

---

In the first post of this series, I argued that software engineering has reached a tipping point — not because AI writes code faster, but because that speedup is pressuring every other layer of the delivery system simultaneously. Build pipelines, code review, testing, version control, release processes — none were designed for the throughput that AI-assisted development is now generating.

If that is the systemic problem, then the architect is the person who has to solve it. Not by writing better code — the machines are handling that — but by designing the environment in which code is produced, validated, and sustained.

This is the shift I want to unpack: the architect's centre of gravity is moving from designing systems to designing system ecologies.

## What Changed

For most of my career, architecture meant making structural decisions about software. Monolith or microservices. Sync or async. SQL or document store. The architect drew boxes and lines, defined service boundaries, and ensured the system could scale, perform, and evolve.

Those decisions still matter. But they are no longer where the hardest problems live.

The hardest problems now sound like this: When should the agent use a tool versus load a skill versus spawn a subagent? How much complexity belongs in the system prompt versus external memory? Which actions require deterministic enforcement versus model discretion? How do you structure evaluation so that every change arrives with verifiable evidence? How do you manage token budgets across a multi-agent workflow without degrading quality?

These are not programming questions. They are questions about designing an environment — an ecology — in which humans, models, tools, policies, memories, and evaluators interact. The classical architectural blueprint describes a system's structure. What we need now is something more like an operating model: a living set of rules, surfaces, and feedback loops that shape how the system behaves over time.

> **[FIGURE 1: "From System Design to System Ecology"]**
> *Side-by-side: Left — classical boxes-and-lines blueprint (services, databases, APIs, queues), static, structural. Right — living network with humans, agents, tools, skills, memory layers, eval loops, approval gates, and feedback arrows. The right side is not just more complex — it is a different kind of thing. The blueprint describes; the ecology operates.*
> *Style: Left in monochrome/blueprint, right in colour with visible feedback loops.*

## Context Engineering Is the New Architecture

The most important job in building AI agents is not prompt engineering. It is context engineering — managing the whole evolving state that surrounds the model: the system prompt, tools, memory, external data, message history, and every token that accumulates during a long-running task [1].

This reframes what architects actually design. The questions are no longer "which service owns this data?" or "what is the API contract?" The questions are: Which facts live in the agent's live context versus external memory? Which capabilities are tools, which are skills, which are hooks, which are subagents? How does context age, and when does it get compacted?

The decision surface is different, and it demands a new kind of architectural discipline. The choice between tool, skill, and subagent is not stylistic — it has direct consequences for token cost, reliability, and model behaviour.

**Use a tool** when the capability is external, deterministic, or action-oriented — fetching data, executing code, calling a service. Tools need distinct purpose, clear descriptions, minimal overlap, and token-efficient outputs. When these properties are missing, the model selects tools poorly and the system degrades unpredictably.

**Use a skill** when the agent needs reusable procedural knowledge or domain guidance while remaining in control. Skills persist in context once loaded — they are for information the agent needs sometimes, not always. Overloading skills creates a recurring token cost on every turn.

**Use a subagent** when the task would pollute the main context, needs different permissions or a different model, or can run in parallel. Subagents provide context isolation that prevents side-tasks from flooding the main conversation with irrelevant tokens.

The practical consequence of getting this wrong is measurable. A production inventory management agent, after months of incremental additions, had accumulated a 400-line system prompt, 12 tools, and 3 subagents. Eval scores were degrading. The fix was architectural decomposition, not better prompting: the system prompt was shortened to 15 lines, the 12 tools were consolidated into 3 primitives (bash, read, write), business logic was moved into skills, and subagents were reduced to one where genuine context isolation was actually needed. Eval scores climbed from 62% to 92% [2]. The lesson is not that the original design was careless — it is that prompt sprawl accumulates like hidden coupling, and the remedy is architectural, not textual.

> **[FIGURE 2: "The Architect's New Decision Surface — Tool, Skill, or Subagent?"]**
> *Decision matrix: three columns (Tool / Skill / Subagent), rows (when to use, context impact, token cost pattern, example). Before/after: 400-line prompt + 12 tools → 15-line prompt + 3 primitives + 1 subagent. Eval: 62% → 92%.*

## Conway's Law Has Not Disappeared — It Has Become More Interesting

Conway's original observation — that organizations produce systems whose structures mirror their communication structures — still holds [3]. But the "communication structure" is no longer composed only of humans and teams. It now includes prompts, tool namespaces, memory layers, routing rules, evaluator loops, and approval checkpoints.

The architecture of your agent system will mirror the structure of these interactions, whether you design it intentionally or not. A poorly bounded tool namespace becomes a coordination failure between agents. An underspecified eval loop becomes a quality gap that surfaces in production. An unconstrained subagent spawning pattern becomes a cost spiral nobody owns.

In practice, the decision to introduce multiple agents has often been driven by the wrong reasons — because "multi-agent" sounds sophisticated rather than because the architecture genuinely calls for it. Multi-agent design makes sense for three specific problems: context management (tasks too large for one context window), distributed development (teams need independent agents they own), and parallelization (subtasks can run concurrently) [4]. For everything else, a single agent with the right tools and a well-designed prompt is simpler and cheaper.

When multi-agent systems do fail, the failure is almost always socio-technical. Agents duplicate work, leave gaps, or explore the wrong problem — not because the models are weak, but because the boundaries between agents were not designed with the same rigour as boundaries between services. The best agent boundaries, like the best microservice boundaries, are designed around cognitive ownership and information locality, not technical convenience [1][4].

> **[FIGURE 3: "Conway's Law Extended — Communication Structures in an Agentic Organization"]**
> *Two-panel: Left — traditional org chart mapped to system components. Right — same org, now including agents, prompts, tool namespaces, memory layers, eval loops, approval gates alongside human teams. The communication structure that shapes your architecture is no longer just humans talking to humans.*

## The 10x Stress Test — What the Architect Must Harden

I walked through the 10x stress test at a high level in Post 1. Here I want to go deeper into the specific failure points the architect must address.

**Build systems.** Hermetic builds — reproducible, self-contained, deterministically cached — become essential infrastructure, not best practice. When AI agents drive build activity, compute becomes the bottleneck rather than authoring. Weak build graphs and ad hoc scripts that were tolerable at human throughput become architectural liabilities at machine throughput. The build system must be designed from the start to be correct under high parallelism and high volume [5].

**Version control.** Branchy workflows amplify reconciliation cost when change volume multiplies. Trunk discipline, small increments, and clear ownership become more important as agents produce more changes. The "One Version" principle — eliminating long-lived development branches — is not just a cultural preference; it is a throughput control that prevents merge debt from compounding [5].

**Code review.** This is where the human bottleneck becomes acute. The economics of code generation have already shifted: it is cheap to generate large numbers of changes and easy for one agent to impose review burdens on many humans. The response must be architectural — static analysis embedded in the review tool itself, automated first-pass checking that catches resource leaks and race conditions so human reviewers can focus on architecture and intent. At scale, review latency becomes a first-class SLI, not just a process concern [5][6].

**Testing.** The question is no longer "do we have tests?" but "can the system produce trustworthy evidence fast enough to gate changes?" At 10x throughput, test compute requirements scale quadratically with codebase size. The architecture must include offline evals, trajectory analysis, online evaluation, and alerting — not as additions to a conventional CI pipeline, but as the primary quality gate [4].

The core insight: once AI makes code generation cheap, review, verification, reproducibility, and deployment governance become the real architecture. Architects who focus on agent selection and model choice while ignoring these infrastructure concerns will find that the bottleneck has simply moved.

> **[FIGURE 4: "The 10x Stress Test — Where the Architect's Priorities Shift"]**
> *Vertical pipeline: Code Generation → Build → Version Control → Code Review → Testing → Release → Production. Each stage: before-AI capacity vs after-10x capacity. Bottleneck migrates downstream. Key data: Tricorder 50K changes/day, ML edits resolve 7.5% of reviewer comments [5], quadratic dependency growth [5].*

## Tokens Are Architecture, Not Accounting

Most architects treat token cost as an operational concern — something the finance team tracks and the operations team manages. This is a mistake. Token economics is a first-class architectural constraint, as fundamental as latency or throughput in a traditional distributed system.

The reason is Amdahl's Law applied to agent workflows. Once model calls become cheap, the serial fraction — tool round trips, network waits, approval prompts, evaluator passes — dominates total latency. Parallelizing tool calls and subagent work can cut task completion time by up to 90% [1]. But the decision to parallelize, and how, is an architectural decision made at design time, not a runtime optimisation.

Token costs also vary significantly with architectural choices — not just model selection. Multi-agent systems typically consume 4x the tokens of single-agent interactions, and complex research workflows can use 15x [1]. The difference between a stateful handoff pattern and a stateless subagent pattern is 40-50% of model calls for repeated requests [4]. The difference between a well-specified tool interface and a vague one can mean the model re-invokes the wrong tool repeatedly, consuming tokens on retries.

The concrete overhead is worth knowing. A bash tool adds approximately 245 tokens per invocation. A text-editor tool adds approximately 700 tokens. Web search adds per-search charges on top of token costs [1]. These numbers seem small until you multiply by the number of agent turns in a long-horizon task.

The architectural implication: context topology — what lives inline, what becomes a skill, what is cached, what is delegated — is a token budget decision as much as a design decision. Getting it wrong wastes money and degrades performance. Getting it right is how you make multi-agent systems economically viable.

> **[FIGURE 5: "Token Economics as Architecture"]**
> *Sankey diagram: token flow through a multi-agent system. Inputs: system prompt, skills, tool definitions, tool results, message history, subagent transcripts. Show how architectural choices affect accumulation. Key callouts: 4x/15x multi-agent multiplier, 245/700-token tool overhead, 40-50% savings from stateful patterns.*

## The Harness Is the Architecture

A name has solidified for what architects are actually building in AI-native systems: **harness engineering** — designing the scaffolding (context delivery, tool interfaces, planning artifacts, verification loops, memory systems, and sandboxes) that surrounds an agent and determines whether it succeeds or fails on real tasks [7].

Every harness component exists because the model cannot do that thing alone. And the best harnesses are designed knowing that each component will eventually become unnecessary as models improve — which means the design should be modular and shedable, not monolithic.

The evidence that harness design dominates model selection is now hard to dismiss. Harness-only changes — no model swap — moved one coding agent from rank 30 to top 5 on Terminal Bench 2.0 [7]. Local models went from 2/10 to 10/10 on a SWE-bench subset purely by constraining tool access through state machine guardrails [7]. The measured finding is direct: "loop structure, not model size, is the binding constraint." Harness setup alone can swing benchmarks by 5 or more percentage points [7].

The most instructive production case is Microsoft's Azure SRE Agent, which has autonomously handled over 35,000 production incidents and reduced time-to-mitigation from 40.5 hours to 3 minutes [7]. The architectural breakthrough was not a more capable model — it was abandoning 100+ bespoke specialized tools in favour of a filesystem-based context surface. Source code, runbooks, query schemas, and past investigation notes were all exposed as files, and the agent navigated with read_file, grep, find, and shell. "Intent Met" score on novel incidents rose from 45% to 75%. A well-designed context surface outperformed specialized tooling.

The emerging role is what Martin Fowler calls "humans on the loop" — engineers who design and maintain agent environments rather than inspecting individual outputs [7]. It is closer to operating system design than to application architecture: you are building the conditions under which programs run, not the programs themselves.

## What the Role Looks Like in Practice

The AI-native architect is a designer of constraints, surfaces, and feedback loops. In practice, this means five things.

**Defining the boundary between deterministic policy and model discretion.** Which actions are enforced by hooks, middleware, permission systems, and approval gates? Which are left to model judgment? This line must be drawn deliberately — not because models are untrustworthy, but because deterministic enforcement is auditable and model discretion is not.

**Designing context topology.** What stays inline? What becomes an on-demand skill? What is summarized, stored externally, or delegated to a subagent? This is the new equivalent of data schema design — except the substrate is the model's attention, and the cost of poor design is degraded reasoning, not just slow queries.

**Embedding evaluation and observability from the start.** Not as a monitoring dashboard bolted on after launch. Evaluation loops, trace collection, experiment infrastructure, and feedback mechanisms are structural elements. If the system cannot tell you whether an agent's behaviour has drifted, the system is not production-grade.

**Managing throughput economics.** Review latency, token spend per successful task, tool-selection error rates, and prompt-compaction frequency are the new SLIs. Generation is cheap. Verification is expensive. The SLIs must reflect what is actually constrained.

**Curating ecosystem health.** A bad tool description, a lax permission policy, an under-specified eval, or a noisy context budget can each degrade the same user-facing outcome through different paths. The architect must watch for emergent degradation, adjust boundaries, and ensure the system can sustain itself as it grows. This is the gardener's work, not just the engineer's.

> **[FIGURE 6: "The Five Practices of the System Ecology Architect"]**
> *Pentagon or concentric rings: (1) Deterministic vs Model Discretion — the hard boundaries. (2) Context Topology. (3) Evaluation & Observability. (4) Throughput Economics. (5) Ecosystem Health. Each with 2-3 concrete examples. Should feel like a practical operating framework, not a theoretical model.*

## Shared Fate

In traditional distributed systems, "shared fate" describes components that fail together because they share configuration, networking, or infrastructure. In agent systems, shared fate describes something broader: when a tool description is wrong, or an eval is under-specified, or a permission boundary is too loose, the degradation propagates through every agent that touches that component. The failure has no single owner. Everyone shares its consequences.

This is why the architect's role feels different now. You are not designing a system that others will build and operate. You are designing the operating conditions under which humans and agents will collaborate — and you are responsible for the emergent outcomes of that collaboration. The system is alive. It needs a gardener as much as it needs an engineer.

---

*Next in the series: **The Developer's Identity Shift — From Writing Code to Steering Intent***

---

### Sources and References

1. Anthropic (2026). ["Building Effective Agents"](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/building-effective-agents) and ["Research System."](https://www.anthropic.com/engineering/building-research-system) — context engineering, tool design, 90.2% multi-agent gain, 80% BrowseComp variance from tokens, 90% time reduction from parallelism, tool overhead: 245-token bash, 700-token text-editor.
2. Will, Anthropic Applied AI (2026). "Tool, Skill, or Subagent." Code with Claude London, May 2026. — Inventory agent case study: 62% → 92% eval score, 400-line prompt → 15 lines.
3. Conway, M. (1968). "How Do Committees Invent?" — original formulation of Conway's law.
4. LangChain (2026). [Multi-Agent Systems guidance](https://langchain-ai.github.io/langgraph/) and performance comparisons. — three reasons for multi-agent, stateful patterns save 40-50% calls, 9K vs 15K tokens for multi-domain.
5. Winters, T. et al. (2020). *Software Engineering at Google.* O'Reilly. — monorepo, Tricorder (50K changes/day), ML edits resolve 7.5% of reviewer comments, 1B LOC coverage daily.
6. Forsgren, N. & MacVean, A. (2026). ["Build Core Skills."](https://io.google/2026/explore/workshop-4) Google I/O 2026.
7. AI Boost (2026). [Awesome Harness Engineering.](https://github.com/ai-boost/awesome-harness-engineering) — harness definition, rank 30→top 5 (LangChain), 2/10→10/10 (statewright), Azure SRE 40.5h→3min / 45%→75%, 5pt benchmark swing (Anthropic), Martin Fowler "humans on the loop."
