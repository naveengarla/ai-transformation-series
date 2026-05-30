# The Architect's New Role: From System Design to System Ecology

*Part 2 of a series on how AI is transforming software engineering — and what it means for architects, developers, testers, and leaders.*

---

There is a question I now ask every architect I work with: if you replaced your development team with AI agents tomorrow, what would break first? Not in the code — in the system around the code. The build pipelines. The review process. The release governance. The way context flows between tools. Most architects cannot answer it, because they have never had to think about their engineering ecosystem as a designed system. It has always been a collection of practices and tools that accumulated over time.

That reckoning has arrived.

## The Job Has Changed

For most of software engineering history, the architect's job was to design the structure of the software: the services, the data stores, the interfaces between them. Get the boundaries right, and the system would scale, perform, and evolve. The architect drew boxes and lines. Other people filled in the boxes.

That job still exists. But it is no longer where the hardest architectural problems live.

The hardest problems now are environmental, not structural. They are questions like: How much complexity should live in the agent's active context versus external memory? When does a capability belong in a tool versus a skill versus a subagent? Where is the line between what the model decides and what the system enforces deterministically? How does evaluation fit into the architecture — not as a testing phase, but as a structural feedback loop that operates continuously? How do you design for token cost the same way you design for latency?

These are not programming questions, and they are not traditional system design questions. They are questions about designing an operating environment — the conditions under which AI agents, humans, tools, data, and policies interact. The classical architecture diagram describes what a system *is*. What we need now is something that describes what a system *does over time*: a living operating model, not a static blueprint.

> **[FIGURE 1: "From System Design to System Ecology"]**
> *Two diagrams side by side. Left: classical boxes-and-lines architecture — static, structural, describes what exists. Right: a living network of agents, tools, memory layers, approval gates, eval loops, and feedback arrows — dynamic, describes how the system behaves over time. The point is not complexity; it is a different kind of thing entirely.*

## The New Design Surface

The most consequential architectural decision in an AI-native system is not which model you choose. It is how you shape the context that surrounds the model at every step of every task.

Context is the medium in which the model reasons. Every token in the context window influences the output. Every token outside it is invisible. The architect's job is to curate that window — deciding what must be present, what can be retrieved on demand, what should be enforced through code rather than through instruction, and what should be isolated in a separate agent entirely.

This gives rise to a decision framework that has no equivalent in classical architecture. A capability can live in four places, and the choice has consequences for cost, reliability, and model behaviour:

A **tool** is the right choice when the capability is external and deterministic — fetching data, executing code, calling an API, taking a real-world action. Tools should have a single clear purpose, minimal overlap with other tools, and token-efficient outputs. When these properties are absent, the model selects tools erratically and the system becomes unpredictable.

A **skill** belongs when the agent needs reusable knowledge or procedural guidance that it uses sometimes but not always — style conventions, domain rules, step-by-step procedures. Skills are loaded on demand and persist in context. The cost of a poorly scoped skill is that it adds tokens on every turn where it is present, whether the agent needs it or not.

A **subagent** is correct when a task would pollute the main conversation with irrelevant tokens, needs different permissions or a cheaper model, or can genuinely run in parallel. Subagents provide context isolation — but they add coordination overhead, and that overhead is only worth paying when the isolation genuinely matters.

A **hook or policy** is the right choice when the action must be enforced deterministically, regardless of what the model decides. Some constraints cannot be trusted to model judgment. They must be implemented in code.

The practical cost of getting this wrong is concrete. A production agent that had accumulated a 400-line system prompt, twelve tools, and three subagents over several months of development showed progressively degrading evaluation scores. The fix was architectural decomposition: a 15-line system prompt, three primitive capabilities, skills for progressive context loading, and a single subagent where isolation was genuinely required. Evaluation scores rose from 62% to 92% [2]. The lesson is not that the original design was careless — it is that context sprawl accumulates like hidden coupling, invisible until it degrades the system.

> **[FIGURE 2: "The Architect's Context Topology Decision"]**
> *Decision framework showing the four placement options (Tool / Skill / Subagent / Hook-Policy) with when to use each, the context impact, and the cost pattern. Before/after: 400-line prompt + 12 tools → 15-line prompt + 3 primitives. Eval: 62% → 92%.*

## Conway's Law Has Become More Dangerous

In 1968, Melvin Conway observed that organizations produce systems whose structures mirror their communication structures. This principle has never been more relevant — or more treacherous.

In an AI-native engineering organization, the "communication structure" is no longer composed only of humans and teams. It now includes the shape of your prompts, the namespace of your tools, the boundaries between agents, the rules governing what each agent can access, the memory layers that persist between sessions, and the evaluation loops that provide feedback. Every one of these is an architectural choice. And if you do not make those choices deliberately, Conway's law will make them for you — producing agent systems whose failure modes mirror your organizational dysfunctions.

The failure pattern is recognizable. Agents in a poorly designed multi-agent system duplicate work, leave gaps at handoff boundaries, or explore the wrong problem — not because the models are weak, but because the boundaries between agents were drawn for the wrong reasons. Multi-agent design is justified by three specific needs: context management (the task exceeds one context window), distributed development (teams need independent ownership), and parallelization (subtasks can genuinely run concurrently) [4]. When organizations introduce multiple agents because the architecture sounds sophisticated, they pay the coordination cost without getting the isolation benefit.

The deeper implication is this: in a multi-agent system, the system's important properties emerge from interactions among agents, tools, evaluators, and humans. You cannot predict them by examining any single component. You can only understand them by watching the ecology as a whole. This is why the architect's job is becoming ecological. You are not designing components. You are designing a system that evolves.

> **[FIGURE 3: "Conway's Law Extended"]**
> *Left: traditional org chart mapped to system components. Right: same org, but the communication structure now includes agents, prompts, tool namespaces, memory layers, eval loops, and approval gates. The system mirrors not just how teams relate, but how every interaction channel is designed.*

## What Breaks at 10x

I introduced the 10x stress test in the first post: what happens when AI increases development throughput by an order of magnitude? Here I want to be specific about what the architect must harden.

**The build system.** When AI agents drive build activity, compute — not authoring — becomes the bottleneck. Hermetic builds, reproducible outputs, and aggressive caching are no longer engineering hygiene; they are architectural requirements. A weak build graph that was tolerable at human throughput becomes a liability at machine throughput, because agents trigger far more builds per unit of time than developers do, and they do not slow down when the queue backs up.

**Version control discipline.** Branching strategies designed for human-paced development amplify merge debt when change volume multiplies. Trunk discipline — small increments, no long-lived branches, clear ownership — becomes a throughput control, not a cultural preference. The engineering cost of reconciling diverged branches scales non-linearly with branch age. AI agents do not wait for the merge to settle before generating the next change.

**Code review.** This is where the human bottleneck crystallizes. The asymmetry is stark: AI makes it cheap to generate large volumes of change, but review remains constrained by human cognitive bandwidth. The architectural response is to embed automated first-pass analysis directly into the review workflow — catching resource leaks, race conditions, and coverage gaps before a human sees the diff. Google's Tricorder analyses over 50,000 changes per day [5]; automated review assists resolve 7.5% of all reviewer comments [5]. The lesson for architects is that review capacity is a system constraint that must be engineered, not assumed.

**Testing.** At 10x throughput, test compute requirements scale quadratically with codebase size. The question is no longer whether you have tests — it is whether the test infrastructure can produce trustworthy evidence fast enough to gate the change rate. This demands eval pipelines, trajectory analysis, and online evaluation as structural elements of the delivery system, not additions to a conventional CI pipeline.

When AI makes code generation cheap, verification becomes the scarcest resource. The architect who optimizes for code generation while ignoring these downstream constraints has simply moved the bottleneck, not removed it.

> **[FIGURE 4: "Where the Bottleneck Migrates"]**
> *Vertical delivery pipeline (Code Generation → Build → VCS → Code Review → Testing → Release → Production). Before-AI capacity vs after-10x capacity at each stage. The bottleneck migrates downstream. Key data: Tricorder 50K changes/day, quadratic dependency growth, 7.5% automated review resolution.*

## Token Economics Is Architecture

Most architects treat token cost as an operational concern. This is a category error.

Token economics is a first-class architectural constraint — as fundamental as latency or throughput in any distributed system. The decisions that shape token consumption are made at design time: which information stays in the active context, which is retrieved on demand, which is cached, which is delegated. Changing these decisions after deployment requires rearchitecting the system.

The numbers matter. Multi-agent systems typically consume four times the tokens of single-agent interactions. Complex research workflows can consume fifteen times as much [1]. The overhead from a single tool invocation is not free: a bash tool adds approximately 245 tokens, a text-editor tool adds approximately 700 [1]. A skill that stays in context across turns adds its token cost on every turn, whether the agent needs it or not. A poorly scoped system prompt that loads everything at initialization pays that cost for the lifetime of every session.

The Amdahl's Law perspective is useful here. Once model calls get cheaper and faster, the serial fraction of the workflow dominates: tool round trips, approval waits, evaluator passes, handoff latency. Designing for parallelism — parallel tool calls, parallel subagents where the tasks are genuinely independent — is an architectural decision that can reduce task completion time by up to 90% [1]. This is not a configuration option; it is a structural choice made when the system is designed.

Context topology — what lives inline, what is cached, what is retrieved on demand — is a token budget allocation. Getting it right is how you make multi-agent systems economically viable. Getting it wrong is how you burn engineering budget and degrade model performance simultaneously.

> **[FIGURE 5: "Token Economics as Architecture"]**
> *Sankey diagram showing token flow through a multi-agent system: system prompt, skills, tool definitions, tool results, message history, subagent transcripts. Show how architectural choices (skill vs subagent, cached vs inline, code execution vs direct tool call) affect total accumulation. Key numbers: 4x/15x multipliers, 245/700-token tool overhead, 40-50% call savings from stateful patterns.*

## Harness Engineering: The Discipline That Names All of This

The discipline of designing the scaffolding around AI agents now has a name: harness engineering — the practice of building the context delivery, tool interfaces, planning artifacts, verification loops, memory systems, and sandboxes that determine whether an agent succeeds or fails on real tasks [7].

The framing is clarifying. Every component of a harness exists because the model cannot do that thing alone. And the best harnesses are designed knowing that those components will eventually become unnecessary as models improve — which means the design should be modular, auditable, and shedable, not monolithic.

The evidence that harness design dominates model selection is now hard to dispute. Harness-only changes — no model swap — moved a coding agent from rank 30 to top 5 on a competitive benchmark [7]. Constraining an agent's tool access through state machine guardrails moved local model performance from 2/10 to 10/10 on a held-out evaluation set [7]. The pattern is consistent enough to state as a principle: for most real-world tasks, loop structure and context discipline are the binding constraints, not model capability.

The most instructive production case is a major cloud provider's site reliability engineering system, which has autonomously handled over 35,000 production incidents and reduced time-to-mitigation from 40.5 hours to 3 minutes [7]. The architectural breakthrough was not a more capable model. It was abandoning over 100 bespoke specialized tools in favour of a filesystem-based context surface — exposing source code, runbooks, query schemas, and past investigation notes as files that the agent navigates with standard shell commands. Specialized tooling lost to a well-designed context surface. "Intent Met" score on novel incidents rose from 45% to 75% [7].

The architect who designs agent systems is no longer primarily a system designer. They are a harness engineer — building the operating environment in which models work. It is closer to designing an operating system than an application: you are creating the conditions under which programs run, not the programs themselves.

## Five Practices of the System Ecology Architect

In practice, this translates to five architectural responsibilities that do not exist in the classical role.

**Drawing the determinism boundary.** Some constraints must be enforced by code — not because the model is incompetent, but because compliance, safety, and auditability require deterministic guarantees. The architect decides which actions go through hooks, middleware, and approval gates, and which are left to model judgment. This line must be drawn explicitly and defended actively as the system evolves.

**Designing context topology.** What lives inline in every conversation? What becomes a skill, loaded on demand? What is summarized and discarded? What is stored in external memory across sessions? What is isolated in a subagent? These decisions shape the model's reasoning quality and the system's operating cost simultaneously. They require the same rigour as data schema design, because the cost of getting them wrong compounds across every interaction.

**Making evaluation structural.** Observability and evaluation are not monitoring tools bolted on after launch. They are architectural elements that must be present at system design. If you cannot tell whether an agent's behaviour has drifted from its intended policy, the system is not production-grade — regardless of how well it performed during testing. Trace collection, experiment infrastructure, and feedback loops are part of the architecture, not additions to it.

**Managing throughput economics.** Token spend per successful task, tool-selection error rates, review latency, and prompt-compaction frequency are the new system SLIs. In a world where generation is cheap and verification is expensive, the metrics that matter are not the metrics that tracked the old bottleneck.

**Curating ecosystem health.** A bad tool description, an under-specified eval, a lax permission boundary, or a noisy context budget can each degrade the same user-facing outcome through different causal paths. The architect must watch for emergent degradation, adjust boundaries, and ensure the ecosystem can sustain itself as it grows. This is the ongoing work — not a design decision made once, but a responsibility held continuously.

> **[FIGURE 6: "The Five Practices of the System Ecology Architect"]**
> *Pentagon diagram with the five practices at each vertex. Each annotated with 2-3 concrete examples. Should read as a practical operating framework — something an architect can use to audit whether their current role addresses all five dimensions.*

## The Gardener and the Engineer

Traditional software systems, once built, are relatively stable. You design them, build them, and then operate them. The architect's job is mostly done at design time.

Agent systems are different. They evolve as models improve, as workloads shift, as new tools appear and old assumptions expire. A harness component that was essential six months ago may be unnecessary today. A context topology that was optimal for one class of tasks may fail for another. The ecology drifts.

This is why the architect of an AI-native system needs to be a gardener as much as an engineer. You are not designing a system and then handing it over to operations. You are designing the operating conditions under which humans and agents will collaborate — and you remain responsible for the emergent outcomes of that collaboration over time. The system is alive. It needs continuous tending, not just initial construction.

The architect who understands this is not threatened by AI. They are doing the most interesting work in the field — designing environments that make intelligence useful, reliable, and trustworthy at scale.

---

*Next in the series: **The Developer's Identity Shift — From Writing Code to Steering Intent***

---

### References

1. Anthropic (2026). [Building Effective Agents](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/building-effective-agents) and [Research System](https://www.anthropic.com/engineering/building-research-system). Multi-agent token multipliers (4x/15x), 90% time reduction from parallelism, tool overhead (245/700 tokens), 80% BrowseComp variance from tokens.
2. Will, Anthropic Applied AI (2026). "Tool, Skill, or Subagent." Code with Claude London. Inventory agent: 62% → 92% eval score via architectural decomposition.
3. Conway, M. (1968). "How Do Committees Invent?" *Datamation.*
4. LangChain (2026). [LangGraph multi-agent guidance](https://langchain-ai.github.io/langgraph/). Three justifications for multi-agent; stateful patterns save 40-50% calls; 9K vs 15K tokens for multi-domain requests.
5. Winters, T., Manshreck, T. & Wright, H. (2020). *Software Engineering at Google.* O'Reilly. Tricorder (50K+ changes/day), ML review assists (7.5% of comments), quadratic dependency growth.
6. Bender, A. (2026). ["Software Engineering at the Tipping Point."](https://io.google/2026/explore/workshop-2) Google I/O 2026.
7. AI Boost (2026). [Awesome Harness Engineering](https://github.com/ai-boost/awesome-harness-engineering). Harness definition; rank 30 → top 5 (LangChain, no model swap); 2/10 → 10/10 (statewright, state machine constraints); SRE agent 40.5h → 3 min, 45% → 75% Intent Met (Microsoft); ±5pt benchmark swing from harness setup (Anthropic); Martin Fowler "humans on the loop."
