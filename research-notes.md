# Research Notes & Bookmarks — AI Transformation Blog Series

*Last updated: 2026-05-28*
*Purpose: Persistent research reference spanning sessions. Contains verified sources, key data points, and material allocated to specific posts.*

---

## Source Transcripts (User-Provided)

These are full transcripts the user collected and shared. Stored in `C:\Users\nge2kor\Downloads\`.

| File | Speaker(s) | Event | Date | Key Topics |
|---|---|---|---|---|
| `Build core skills to thrive as an AI-era developer.txt` | Andrew MacVean, Nicole Forsgren (Google Developer Intelligence) | Google I/O 2026 | May 19-20, 2026 | T-shaped engineer, 5 AI-native patterns, shift-left on intent, spec-driven dev, orchestrating agent teams, cognitive overload, leadership |
| `Software engineering at the tipping point.txt` | Adam Bender (Google) | Google I/O 2026 | May 19-20, 2026 | Software ecology, socio-technical systems, Conway's law, shared fate, 10x moment, system thinking, cascading failures |
| `A fireside chat on the evolution of the developer craft.txt` | Addy Osmani, Ciera Jaspan, Aja Hammerly, Richard Seroter (Google) | Google I/O 2026 | May 19-20, 2026 | Redefining senior engineers, cognitive surrender, de-skilling vs reskilling, adversarial mentoring, spec-driven dev |
| `Running an AI-native engineering org.txt` | Fiona Fung (Anthropic, Dir. of Engineering, Claude Code) | Code with Claude SF | May 6, 2026 | Bottleneck shift, rewritten team norms, code review changes, managers as ICs, dog-fooding, verification as new bottleneck |
| `Tool, skill, or subagent Decomposing an agent that outgrew its prompt.txt` | Will (Anthropic Applied AI) | Code with Claude London | May 19, 2026 | Agent decomposition, eval-driven dev, skills vs tools vs subagents, progressive disclosure, hill climbing on evals |
| `Defining the agentic AI era.txt` | Logan Kilpatrick, Koray Kavukcuoglu, Liz Reid, Jeff Dean, Josh Woodward (Google) | Google I/O 2026 | May 19-20, 2026 | Gemini 3.5, full-stack AI, agents in Search, Spark, role blurring, asynchronous work, future interfaces |
| `The Future of AI Agents What Will Interrupt 2027 Look Like.txt` | Harrison Chase (LangChain) | Interrupt 2026 | May 13-14, 2026 | Future agent types, voice, sandboxes, open models, agent identity/auth, continual learning, Fleet |
| `The Agent Development Lifecycle Build, Test, Deploy, Monitor.txt` | Harrison Chase, Ankush Gola (LangChain) | Interrupt 2026 | May 13-14, 2026 | Agent dev lifecycle, deep agents, LangSmith, evals, SmithDB, context management, governance |
| `Building agents with real-world reasoning.txt` | Ken Nevarez, Caio Moreira (Google Maps Platform) | Google I/O 2026 | May 19-20, 2026 | Grounding LLMs, MCP servers, multi-agent orchestrator architecture, Maps Grounding Lite |

---

## Verified Key Data Points

### METR Randomized Controlled Trial (2025)
- Developers expected AI to speed them up by **+24%**
- After task completion, perceived speedup: **+20%**
- Actual measured performance: **-19% slower**
- **39-percentage-point metacognitive gap**
- Source: METR (https://metr.org/)
- **Used in:** Post 1

### DORA 2025 Report (~5,000 tech professionals)
- 90% of developers use AI tools at work (up from 76% prior year)
- Median AI usage: 2 hours/day (~25% of workday)
- 80%+ believe AI increased productivity; 30% report little trust in AI-generated code
- AI improves: individual effectiveness, organizational performance, code quality, delivery throughput, team performance
- AI worsens: **software delivery instability**
- **"Rework rate" introduced as 5th DORA metric** (unplanned fixes to production)
- 7 AI Capabilities for success: clear AI policy (**451% adoption increase**), dedicated learning time (**131% adoption increase**), strong version control, small batches, quality platforms, AI-accessible data, user-centric focus
- Key quote: "AI doesn't fix a team; it amplifies what's already there."
- Source: https://dora.dev/insights/balancing-ai-tensions/
- **Used in:** Post 1

### Faros AI Study (2025, 10,000+ developers, 1,255 teams)
- High-adoption AI teams: **+21% more tasks**, **+98% more PRs merged**
- PR size grew by **+154%**
- Review times spiked by **+91%**
- Software bugs rose by **+9%**
- Organizational delivery throughput: **flat**
- Source: https://www.faros.ai/blog/key-takeaways-from-the-dora-report-2025
- **Used in:** Post 1

### GitClear Longitudinal Data (2021-2025)
- Code churn within 2-week window: **3.3% baseline → 7.1%** with AI tools
- AI-generated code rewritten/discarded at **>2x the historical rate**
- **Used in:** Post 1

### Google AI Code Generation
- **75% of new Google code** is AI-generated (Sundar Pichai, Google Cloud Next 2026)
- Up from 25% in early 2024, 50% in late 2025
- Source: https://www.techspot.com/news/112152-google-ai-now-generates-75-new-code-up.html
- Also: Snap Inc. 65%, Meta targeting 65% of engineers using AI for 75%+ of committed code
- **Used in:** Post 1

### Amdahl's Law Applied to SDLC (Bain & Company)
- Writing and testing code: **25-35% of total SDLC**
- Maximum theoretical speedup with infinite coding speed: **~1.4x**
- Non-coding portion actually EXPANDS with faster code gen (more review, debugging, integration)
- **Used in:** Post 1

### Workforce Impact
- Junior developer hiring collapsed by **40%** in companies with AI tools
- AI/ML engineers average **$206,000** salary, **56% premium**
- "SaaSocalypse" early 2026: **$285B erased** in software market value
- Seat-based SaaS fell from 21% to 15% of market; hybrid consumption models grew to 41%
- Stanford: employment rates among younger software developers **plummeted 20%** since late 2022
- **Allocated to:** Post 5 (Leadership)

### OTelBench (January 2026)
- Best model: 80.9% on standard coding benchmarks vs **29% on real-world instrumentation**
- No model completed instrumentation in Swift, Ruby, or Java
- Sun et al. (2025): single LLMs produce **factually incorrect diagnoses in 50%** of microservice incidents
- TrioXpert multi-agent validation: **+163% root-cause localization**, **+57% anomaly detection**
- **Allocated to:** Post 4 (Testing)

### Geoffrey Litt's "Comprehension Quizzes"
- During code review, reviewers must pass automated quiz on control flow and edge cases before approval
- Introduces intentional pause to verify human comprehension
- **Allocated to:** Post 3 (Developer) or Post 4 (Testing)

---

## Verified Sources — Bookmarks by Category

### Conference Talks (Primary Sources)

| Title | URL | Speaker | Event |
|---|---|---|---|
| Software Engineering at the Tipping Point | https://io.google/2026/explore/workshop-2 | Adam Bender | Google I/O 2026 |
| (YouTube) | https://www.youtube.com/watch?v=2n41YjR5QfU | | |
| Build Core Skills to Thrive as an AI-Era Developer | https://io.google/2026/explore/workshop-4 | Forsgren, MacVean | Google I/O 2026 |
| A Fireside Chat on the Developer Craft | https://io.google/2026/explore/workshop-5 | Osmani, Jaspan, Hammerly | Google I/O 2026 |
| Running an AI-Native Engineering Org | https://claude.com/code-with-claude/session/sf-running-an-ai-native-engineering-org | Fiona Fung | Code with Claude SF |

### Research Papers

| Title | URL | Author(s) | Date |
|---|---|---|---|
| From Technical Debt to Cognitive and Intent Debt (Triple Debt Model) | https://arxiv.org/abs/2603.22106 | Margaret-Anne Storey (U. of Victoria) | March-April 2026 |
| Professional Software Developers Don't Vibe, They Control | https://arxiv.org/pdf/2512.14012 | (multiple) | Dec 2025 |
| Beyond Human-Readable: Rethinking SE Conventions for Agentic Dev | https://arxiv.org/pdf/2604.07502 | (multiple) | April 2026 |
| Thinking — Fast, Slow, and Artificial: The Rise of Cognitive Surrender | Wharton School Research Paper | Shaw, S. D. and Nave, G. | 2026 |

### Thoughtworks

| Title | URL | Date | Key Insight |
|---|---|---|---|
| The 2025 DORA Report: Engineering Leadership Perspective | https://www.thoughtworks.com/insights/articles/the-dora-report-2025--a-thoughtworks-perspective | Feb 2026 | "AI engineering waste" concept |
| Codebase Cognitive Debt (Technology Radar) | https://www.thoughtworks.com/radar/techniques/codebase-cognitive-debt | April 2026 | On Radar as critical concern; fitness functions, cognitive load tracking |
| Spec-Driven Development | https://www.thoughtworks.com/en-us/insights/blog/agile-engineering-practices/spec-driven-development-unpacking-2025-new-engineering-practices | Dec 2025 | SDD as formal emerging practice |
| The Cognitive Demands of AI Novelty | https://www.thoughtworks.com/en-us/insights/blog/generative-ai/cognitive-demands-ai-novelty | April 2026 | "Current cognitive demand isn't sustainable" |
| Do Developers Need to Think Less with AI? | https://www.thoughtworks.com/en-us/insights/blog/generative-ai/do-developers-need-think-less-ai | July 2025 | AI increasing cognitive load, not reducing it |
| Preparing Your Team for the Agentic SDLC | https://www.thoughtworks.com/en-us/insights/articles/preparing-your-team-for-agentic-software-development-life-cycle | March 2026 | New roles: knowledge architects, agent reliability engineers |
| AI and Software Delivery (Looking Glass 2026) | https://www.thoughtworks.com/en-us/insights/looking-glass/looking-glass-2026/AI-and-software-delivery | 2026 | DORA metrics may become less relevant; KPIs need redefinition |
| The Future of Software Dev: AI Speed, Human Judgment | https://www.thoughtworks.com/en-us/insights/articles/the-future-of-software-development-AI-speed-human-judgment | Nov 2025 | Central paradox: tools promising reduced cognitive load require more disciplined thinking |
| AI-First Software Engineering (Perspectives) | https://www.thoughtworks.com/en-us/perspectives/edition36-ai-first-software-engineering/article | 2025-2026 | Benefits too narrowly defined; should enhance entire processes |
| Software Engineering Skills, Jobs and Careers in the AI Era | https://www.thoughtworks.com/insights/articles/software-engineering-skills-jobs-careers-ai-era | Dec 2025 | Role evolution, PM-engineering relationship renegotiation |
| Reflections on the Future of SE Retreat | https://www.thoughtworks.com/insights/articles/reflections-future-software-engineering-retreat | Feb 2026 | Margaret-Anne Storey's cognitive debt discussed at retreat |
| DORA Metrics (Technology Radar) | https://www.thoughtworks.com/en-us/radar/techniques/dora-metrics | April 2026 | 5th metric (rework rate); "measuring by LOC is misleading" |
| Podcast: AI-Assisted Software Dev — Inside DORA Report | https://www.thoughtworks.com/en-us/insights/podcasts/technology-podcasts/ai-assisted-software-development-2025-inside-dora-report | Dec 2025 | "You can increase throughput but destroy your product" |

### Other Key Sources

| Title | URL | Author | Date |
|---|---|---|---|
| Cognitive Surrender (blog) | https://addyosmani.com/blog/cognitive-surrender/ | Addy Osmani | May 2026 |
| Don't Outsource the Learning (blog) | https://addyosmani.com/blog/dont-outsource-learning/ | Addy Osmani | May 2026 |
| The Best Code is No Code At All | https://blog.codinghorror.com/the-best-code-is-no-code-at-all/ | Jeff Atwood | May 2007 |
| Google 75% AI code stat | https://www.techspot.com/news/112152-google-ai-now-generates-75-new-code-up.html | TechSpot (Pichai) | 2026 |
| Martin Fowler on Triple Debt | https://martinfowler.com/fragments/2026-04-02.html | Martin Fowler | April 2026 |
| Simon Willison on Cognitive Debt | https://simonwillison.net/2026/Feb/15/cognitive-debt/ | Simon Willison | Feb 2026 |

---

## Material Allocation by Post

### Post 1: The Big Picture — "Software Engineering's Tipping Point" [WRITTEN]
- METR RCT (perception gap)
- DORA 2025 (amplifier, instability, rework rate, 451%/131% stats)
- Faros AI (PR size, review time, bugs)
- GitClear (code churn)
- Amdahl's Law / Bain (25-35% coding portion)
- Storey Triple Debt Model
- Thoughtworks: AI engineering waste, cognitive debt on Radar, spec-driven dev, cognitive demand unsustainable
- Google 75% stat, Jevons paradox
- Fiona Fung (bottleneck shift, TDD, competing prototypes)
- Adam Bender (10x moment, software ecology, systems thinking)

### Post 2: The Architect's New Role [WRITTEN]
- **Deep research report received:** `C:\Users\nge2kor\Downloads\deep-research-report (2).md`
- Adam Bender: socio-technical systems, Conway's law, shared fate, emergent properties, LSCs
- Will (Anthropic): agent decomposition, tools vs skills vs subagents, progressive disclosure, system prompt management
- Forsgren/MacVean: designing environments not vibe coding, agent orchestration
- Thoughtworks: spec-driven development (deeper dive), preparing teams for agentic SDLC
- Thoughtworks: architectural fitness functions as countermeasure
- Jeff Dean: Amdahl's law on tool latency, tools designed for human frequency
- Google fireside: Antigravity SDK, full-stack AI approach
- arXiv: "Beyond Human-Readable: Rethinking SE Conventions for Agentic Era"
- **NEW from deep research:**
  - Context engineering as the core architectural discipline (Anthropic: managing whole evolving state, not just prompts)
  - Hooks/skills/subagents as architectural primitives with clear decision rules
  - Prompt sprawl as hidden coupling (Anthropic warns against over-specified CLAUDE.md)
  - Token economics as architecture: multi-agent uses ~4x tokens of chat, ~15x for multi-agent runs; token usage explained 80% of BrowseComp variance
  - Tool overhead is concrete: 245-token bash tool, 700-token text-editor tool for Claude 4.x
  - Stateful patterns (handoffs/skills) save 40-50% calls vs stateless subagents for repeat requests
  - Google: Tricorder analyses 50,000+ changes/day; AutoCommenter deployed to tens of thousands; ML edits resolve 7.5% of reviewer comments
  - Anthropic research system: lead agent taught to delegate; emergent behaviour from small prompt changes; effort budgets and collaboration frameworks > strict instruction lists
  - Anthropic multi-agent: outperformed single-agent by 90.2% on breadth-first research eval
  - Parallel subagents + parallel tool calls cut research time by up to 90%
  - ETH Zurich counterpoint on AGENTS.md (already captured)
  - Conway's law extended: communication structure now includes prompts, tool namespaces, memory layers, routing rules, evaluator loops
  - The 5 practices of the emerging architect: (1) deterministic vs model discretion boundaries, (2) context topology, (3) evaluation/observability as architecture, (4) throughput economics, (5) system ecology health

### Post 3: The Developer's Identity Shift [WRITTEN]
- **Deep research report received:** `C:\Users\nge2kor\Downloads\AI Era Developer Identity Shift.md`
- **NEW from deep research:**
  - DORA "Builder Mindsets" framework: Founder, Optimizer, Accelerator, Learner — task-based states replacing static role personas (https://dora.dev/insights/builder-mindset/)
  - Annie Vella (Distinguished Engineer): occupational identity threat research — "Am I still a software engineer if I don't write the code?" (https://annievella.com/posts/the-software-engineering-identity-crisis/)
  - Osmani "Orchestration Tax": developer as GIL (Global Interpreter Lock) of their agent fleet; starting agents is frictionless, closing the loop is expensive (https://addyosmani.com/blog/orchestration-tax/)
  - GitHub Spec Kit: formal SDD workflow — /specify → /plan → /tasks → /implement; constitution.md as non-negotiable constraints (https://developer.microsoft.com/blog/spec-driven-development-spec-kit)
  - MCP as "USB-C port for AI applications" — standardized tool/data connections
  - Practitioner community friction: Reddit vibe coding debates — "expensive debugging with extra steps," "10x crap developer" if no architecture knowledge, cultural panic and hostility toward non-traditional builders
  - 27-year game dev veteran comparing AI transition to assembly → compiler transition
  - SDD markdown ecosystem: CLAUDE.md, SPEC.md, DESIGN.md, constitution.md — living transactive memory
  - Job crafting as identity preservation: Resist (niche domains), Adapt (embrace orchestration), Balance (AI for toil, hands-on for complex challenges)
- Forsgren/MacVean: T-shaped engineer, 5 patterns, shift-left on intent
- Osmani: cognitive surrender, cognitive debt, comprehension debt
- Osmani: Don't Outsource the Learning (MIT EEG study, CHI 2026 anchoring study)
- Jaspan/Osmani/Hammerly fireside: reskilling, de-skilling syntax, adversarial mentoring, innovation budget
- Shaw & Nave (Wharton): "Thinking — Fast, Slow, and Artificial"
- Thoughtworks: "Do developers need to think less with AI?"
- Geoffrey Litt: Comprehension Quizzes
- arXiv: "Professional Software Developers Don't Vibe, They Control"

### Post 4: Testing in a Non-Deterministic World [NOT YET WRITTEN]
- OTelBench (80.9% vs 29% real-world gap)
- Sun et al.: 50% incorrect diagnoses from single LLMs
- TrioXpert multi-agent validation (+163% root-cause, +57% anomaly detection)
- DORA: rework rate as 5th metric
- Bender: quadratic dependency graph growth, test compute explosion, conjunction of Booleans
- Fung: verification as new bottleneck, shift-left automation
- Will (Anthropic): eval-driven development, hill climbing on evals, deterministic vs non-deterministic graders
- Harrison Chase: evals at center of agent dev lifecycle
- Thoughtworks: DORA metrics on Radar, mutation testing revival
- Thoughtworks: Looking Glass 2026 — DORA metrics may need redefinition

### Post 5: Leadership in the AI-Native Org [NOT YET WRITTEN]
- Fung: managers as ICs, flat orgs, explicit permission to kill processes, team makeup (creative builders + deep system expertise)
- Forsgren/MacVean: leadership recommendations (redefine productivity, protect productive struggle, psychological safety)
- Workforce data: junior hiring -40%, $206K AI/ML salary, Stanford employment data
- SaaSocalypse: $285B erased, pricing model shift
- DORA: 7 AI Capabilities Model (detailed)
- Forsgren & Noda: Frictionless DevEx methodology
- Thoughtworks: preparing teams for agentic SDLC, new roles (knowledge architects, agent reliability engineers)
- Thoughtworks: "AI-first SE" — benefits too narrowly defined, should enhance entire processes
- Thoughtworks: SE skills, jobs and careers in AI era — PM-engineering renegotiation

### Post 6: Emerging AI Tech [NOT YET WRITTEN]
- Harrison Chase: agent dev lifecycle, deep agents, continual learning (model/harness/context layers), open models, sandboxes, LangSmith
- Will (Anthropic): Claude Managed Agents, skills vs tools vs subagents, callable agents, code execution as universal tool
- Google fireside: Antigravity SDK, Gemini 3.5, Spark (24/7 agent)
- Google Maps: Grounding Lite, MCP servers, multi-agent orchestrator
- Forsgren/MacVean: agent teams (planner-orchestrator-coder), 3-5 agent sweet spot, TensorFlow migration example
- Thoughtworks: Looking Glass 2026 — AIOps, self-healing, AI and software delivery

### Post 7: The 2030 Developer Ecosystem [NOT YET WRITTEN]
- Jeff Dean: bespoke software, long-running agents, tool latency as new bottleneck
- Bender: software ecology metaphor (managing forests not trees), 2030 will feel like 2001 does to us
- Harrison Chase: future agent types (long-horizon vs customer-experience), voice, agent identity
- Google fireside: personalized interfaces, voice-native, "every person has 30 virtual interns"
- Bender: everyone's a builder consequences, junior developer speedrun, human attention as scarcest resource
- Thoughtworks: DORA metrics redefinition, KPIs for agent-human tandem

---

## Deep Research Prompts (Provided to User)

Seven prompts were given to the user for deep research on each post topic. The user has returned research for Post 1; remaining prompts are pending.

### Stack Overflow 2025 Developer Survey
- 44% frustrated with "AI solutions almost right, but not quite"
- 30% say debugging AI-generated code is more time-consuming than writing it
- 46% distrust AI tool accuracy (InfoQ/DORA cross-reference)
- Only **3% report "high trust"** in AI-generated output
- **Used in:** Post 1

### Anthropic Skill Mastery Study (2026)
- Developers using AI assistance scored **17% lower** on comprehension tests for new libraries
- Those using AI for **conceptual inquiry** scored **65%+**
- Those **delegating code generation** scored **below 40%**
- Productivity gains were **not statistically significant**
- Source: https://www.infoq.com/news/2026/02/ai-coding-skill-formation/
- **Used in:** Post 1

### Spotify AI Agent Data
- AI agents generated **1,500+ merged PRs** in fleet management system
- **60-90% time savings** on large migrations
- Source: https://thenewstack.io/in-2026-ai-is-merging-with-platform-engineering-are-you-ready/
- **Allocated to:** Post 2 (Architect) or Post 6 (Emerging Tech) — concrete success case for agent-driven migrations

### OpenAI Codex GitHub Activity
- Created **400,000+ PRs** in open-source GitHub repos in less than 2 months since May 2025 release
- Source: arXiv "The Rise of AI Teammates in SE 3.0"
- **Allocated to:** Post 6 (Emerging Tech)

### Enterprise AI Spending vs Maturity Gap
- Some organizations allocating up to **8% of total revenue** to AI tools for internal productivity
- Only **1% consider themselves "mature"** in AI deployment (2025 AI at Work report)
- Source: https://thenewstack.io/developer-productivity-in-2025-more-ai-but-mixed-results/
- **Allocated to:** Post 5 (Leadership)

### DORA ROI Report (2026.01)
- Published ~May 14, 2026 by Google Cloud DORA team
- Practical financial framework for calculating AI ROI in software development
- Includes interactive calculator with conservative/realistic/optimistic scenarios
- Complements the September 2025 AI Capabilities Model
- Source: https://www.infoq.com/news/2026/05/dora-roi-ai-assisted-dev-report/
- **Allocated to:** Post 5 (Leadership)

### ETH Zurich on AGENTS.md Files
- Despite widespread recommendations, ETH Zurich paper concludes AGENTS.md files may often **hinder** AI coding agents
- Recommends omitting LLM-generated context files; limiting human-written instructions to non-inferable details
- Source: https://www.infoq.com/news/2026/03/agents-context-file-value-review/
- **Allocated to:** Post 2 (Architect) or Post 3 (Developer) — important counterpoint to spec-driven development narrative

---

## The New Stack — Bookmarks

| Title | URL | Date | Key Insight |
|---|---|---|---|
| This Simple Infrastructure Gap Is Holding Back AI Productivity | https://thenewstack.io/this-simple-infrastructure-gap-is-holding-back-ai-productivity/ | Feb 2026 | Time saved in coding absorbed downstream at unchanged bottleneck; DORA: -1.5% throughput, -7.2% stability |
| Developer Productivity in 2025: More AI, but Mixed Results | https://thenewstack.io/developer-productivity-in-2025-more-ai-but-mixed-results/ | Jan 2025 | Only 1% of companies "mature" in AI; 8% revenue spent on AI tools; developers still cite tech debt as top impediment |
| 3 Ways Enterprises Can Scale AI Gains in 2026 | https://thenewstack.io/3-ways-enterprises-can-scale-ai-gains-in-2026/ | Jan 2026 | Scaling beyond early experiments |
| In 2026, AI Is Merging With Platform Engineering | https://thenewstack.io/in-2026-ai-is-merging-with-platform-engineering-are-you-ready/ | Feb 2026 | Spotify 1,500+ agent PRs; 60-90% time savings on migrations; platform engineering convergence |
| AI Has Won: DORA Study Shows Universal Dev Adoption | https://thenewstack.io/ai-has-won-googles-dora-study-shows-universal-dev-adoption/ | Jan 2026 | 2 hours/day with AI; "We won't need to ask about AI adoption in the future" |
| AI Use Cases That Actually Fix Engineering Bottlenecks | https://thenewstack.io/ai-use-cases-that-actually-fix-engineering-bottlenecks/ | Jan 2026 | "If writing code was never the bottleneck, organizations need to look elsewhere" |
| Throwing AI at Developers Won't Fix Their Problems | https://thenewstack.io/throwing-ai-at-developers-wont-fix-their-problems/ | Jul 2025 | Developers cite tech debt and documentation as top impediments; more AI spending doesn't fix that |
| How IDPs Balance Productivity and Control in the AI Era | https://thenewstack.io/how-idps-balance-productivity-and-control-in-the-ai-era/ | Nov 2025 | Agentic AI requires control/compliance mechanisms; IDP role |
| Agentic IDEs: Next Frontier in Intelligent Coding | https://thenewstack.io/agentic-ides-next-frontier-in-intelligent-coding/ | Apr 2025 | Evolution of IDEs to agentic systems |

## InfoQ — Bookmarks

| Title | URL | Date | Key Insight |
|---|---|---|---|
| AI Is Amplifying SE Performance, Says DORA 2025 | https://www.infoq.com/news/2026/03/ai-dora-report/ | Mar 2026 | AI multiplies existing conditions; 5,000 respondents + 100hrs qualitative interviews |
| DORA Report Finds AI Is Amplifier, Trust Remains Low | https://www.infoq.com/news/2025/09/dora-state-of-ai-in-dev-2025/ | Sep 2025 | 46% distrust AI accuracy; only 3% "high trust" |
| New DORA Report: Engineering Foundations Drive AI ROI | https://www.infoq.com/news/2026/05/dora-roi-ai-assisted-dev-report/ | May 2026 | Financial framework + interactive calculator for AI ROI |
| Where Do Humans Fit in AI-Assisted Software Dev? | https://www.infoq.com/news/2026/03/mf-aiassisted-dev/ | Mar 2026 | 84% using/planning AI; trade-offs in maintainability and tech debt |
| AI in the Trenches: Virtual Panel | https://www.infoq.com/articles/ai-developers-rewriting-software-process/ | Jan 2026 | "Vanity metrics spike with AI; real productivity shows in stability, incidents, code churn" |
| Anthropic Study: AI Reduces Skill Mastery by 17% | https://www.infoq.com/news/2026/02/ai-coding-skill-formation/ | Feb 2026 | 17% lower comprehension; conceptual inquiry (65%+) vs delegation (below 40%) |
| New Research Reassesses AGENTS.md Files | https://www.infoq.com/news/2026/03/agents-context-file-value-review/ | Mar 2026 | ETH Zurich: context files may hinder agents; recommend limiting to non-inferable details |
| Platform Engineering for AI: Scaling Agents at LinkedIn | https://www.infoq.com/podcasts/platform-engineering-scaling-agents/ | Dec 2025 | "We cannot have every team build their own mini-agent platform" |
| Exploring Impact of GenAI on SE and Career Paths | https://www.infoq.com/podcasts/generative-ai-impact-software-engineering/ | 2025 | Fear of job loss exaggerated; learn to use AI effectively |
| Cloud and DevOps Trends Report 2025 | https://www.infoq.com/podcasts/cloud-devops-trends-2025/ | Oct 2025 | "AI can raise cognitive load even as it promises relief" |

---

## Big Tech Open-Source Releases & Strategic Signals (Researched 2026-05-29)

### Microsoft
- **Agent Framework 1.0** (April 7, 2026): Merged AutoGen + Semantic Kernel. GA for Python and .NET. 5 orchestration patterns (sequential, concurrent, handoff, group chat, Magentic-One). 7 model providers (Foundry, Azure OpenAI, OpenAI, Claude, Bedrock, Gemini, Ollama). MCP + A2A + OpenTelemetry native. Declarative agents via YAML. [Blog](https://devblogs.microsoft.com/agent-framework/microsoft-agent-framework-version-1-0/) | [Learn](https://learn.microsoft.com/en-us/agent-framework/overview/)
- **Agent Governance Toolkit** (April 2, 2026): 7-package system (Python, TS, Rust, Go, .NET). Agent OS (policy engine, p99 <0.1ms), Agent Compliance (EU AI Act, HIPAA, SOC2 mapping), Agent Marketplace (Ed25519 signing, trust-tiered gating), Agent Lightning (RL governance). MIT license. [Blog](https://opensource.microsoft.com/blog/2026/04/02/introducing-the-agent-governance-toolkit-open-source-runtime-security-for-ai-agents/)
- **RAMPART & Clarity** (May 2026): AI Red Team security tools. RAMPART: continuous adversarial testing built on PyRIT, slots into CI/CD pipeline. Clarity: structured design review. [Coverage](https://www.helpnetsecurity.com/2026/05/21/microsoft-open-sources-tools-for-designing-and-testing-ai-agents/)
- **Phi-4 family**: Phi-4-reasoning-vision-15B (March 2026, edge-deployable), Phi-4-multimodal 5.6B (speech+vision+text unified)
- **Playwright MCP**: Web browsing for agents via MCP server. Ready-to-use example in AutoGen repo.
- **MarkItDown MCP**: Document parsing (PDF, DOCX) to markdown for agent consumption.
- **Power Platform Canvas Authoring MCP** (May 14, 2026): Natural-language app migration.
- **Strategic signal**: Microsoft is betting on GOVERNANCE as the differentiator. While others focus on agent capability, Microsoft is building the compliance/security/policy layer. Early adopters: KPMG (audit), BMW (vehicle telemetry).

### Google
- **ADK 2.0** (2026): Python, TypeScript, Go. Workflow Runtime (graph-based execution), Task API (structured agent-to-agent delegation). Native A2A. ~17.8K GitHub stars, 3.3M monthly downloads. Bi-weekly release cadence. [Python](https://github.com/google/adk-python) | [JS](https://github.com/google/adk-js) | [Go](https://github.com/google/adk-go)
- **Gemma 4** (April 2026): 2B to 31B sizes, Apache 2.0. 31B scores 84.3% GPQA Diamond. Consumer/IoT-optimized. Best open-weight for local/edge.
- **Gemini CLI**: Open-source terminal agent under Apache 2.0.
- **TPU 8t/8i** (May 2026): Training + inference split chips. Virgo network: 134K TPUs in single fabric, 1M+ across sites.
- **Antigravity 2.0 + CLI**: Agentic development environment with subagent orchestration, built-in security.
- **Strategic signal**: Google is betting on VERTICAL INTEGRATION (hardware → model → framework → platform) and CROSS-FRAMEWORK INTEROPERABILITY via A2A. 50+ partners (Salesforce, ServiceNow) can invoke ADK agents.

### AWS
- **Strands Agents SDK**: Model-driven agent SDK with native Bedrock integration.
- **Bedrock AgentCore**: Managed infrastructure for agents — compliance, scaling, monitoring built-in.
- **Trainium2**: Custom training chip focused on cost efficiency vs NVIDIA GPUs.
- **Strategic signal**: AWS is betting on MANAGED INFRASTRUCTURE — less on the framework layer, more on making agents enterprise-deployable at scale with compliance out of the box.

### Anthropic
- **Claude Agent SDK** (renamed from Claude Code SDK): The agent harness powering Claude Code, exposed as a library. 7,098+ GitHub stars, MIT license. Structured outputs, fallback model handling, extended context beta. [Repo](https://github.com/anthropics/claude-agent-sdk-python)
- **Claude Code**: GA. Terminal-based agentic coding. Hooks, skills, subagents, telemetry via OpenTelemetry. Background tasks via GitHub Actions. VS Code + JetBrains integrations. Plugin ecosystem. [Repo](https://github.com/anthropics/claude-code)
- **Claude Managed Agents**: Self-hosted sandboxes (Cloudflare, Daytona, Modal, Vercel). Outcomes (rubric-based grading, +10pts on hardest tasks). Private MCP server support.
- **MCP**: Contributed to AAIF. 110M+ monthly SDK downloads. 10,000+ active servers.
- **Strategic signal**: Anthropic is betting on DEVELOPER EXPERIENCE + CONTEXT ENGINEERING. Claude Code as the reference agent, Agent SDK as the build-your-own toolkit, MCP as the universal connector. "Claude Code has become far more than a coding tool — it powers almost all of their major agent loops."

### Agentic AI Foundation (AAIF) — The Governance Layer
- **Founded**: December 2025, under Linux Foundation.
- **Founding projects**: MCP (Anthropic), goose (Block), AGENTS.md (OpenAI).
- **Platinum members (8)**: AWS, Anthropic, Block, Bloomberg, Cloudflare, Google, Microsoft, OpenAI.
- **Gold members (19+)**: Adyen, Arcade.dev, Cisco, Datadog, Docker, Ericsson, IBM, JetBrains, Okta, Oracle, Salesforce, SAP, Shopify, Snowflake, Temporal, Twilio, etc.
- **Growth**: 170+ members in <4 months. MCP: 110M+ monthly SDK downloads. A2A: v1.0, 150+ supporting orgs. AGENTS.md: 60,000+ projects.
- **Protocol stack**: MCP (tool connectivity) + A2A (agent coordination) + ACP (community-driven agent communication) — all under Linux Foundation.
- **Events**: Global MCP Dev Summits in Mumbai, Seoul, Shanghai, Tokyo, Toronto, Nairobi throughout 2026.
- **Future**: By 2027, bridges and unified SDKs. By 2028+, potential A2A/ACP convergence; MCP remains distinct tool layer. Formal ISO/IETF standardization possible.
- [AAIF site](https://aaif.io/) | [Linux Foundation announcement](https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation)

### Community & Ecosystem Signals
- **GitHub**: 4.3M AI-related repositories (178% YoY jump in LLM-focused projects). OpenClaw: 0 → 210K stars in days.
- **Top repos by stars (2026)**: AutoGPT (182K), n8n (162K), OpenClaw (210K+), Dify, RAGFlow (70K+), LangGraph (32.3K).
- **Self-hosting renaissance**: OpenClaw, Open WebUI, RAGFlow, Dify all built for privacy-first, on-premise deployment.
- **Terminal-first AI**: Claude Code, Gemini CLI, Codex CLI — shift away from browser-based AI toward tools in the dev environment.
- **Multi-tool stack norm**: $30/month (Copilot Pro + Claude Code Pro) most common senior engineer configuration.
- **Cursor**: $1.2B ARR. Claude: $2.5B annualized run rate.
- **Consolidation**: Google acqui-hired Windsurf ($2.4B), Cognition acquired rest ($250M), Sourcegraph spun out Amp.
- **OWASP Top 10 for Agentic Applications** (Dec 2025): First formal taxonomy of agent-specific risks.
- **Regulation**: EU AI Act high-risk obligations take effect August 2026. Colorado AI Act enforceable June 2026.

### Trendshift.io — 360-Day AI Trending Analysis (Researched 2026-05-29)

**Key Trendshift pages to bookmark:**
- [trendshift.io/topics/ai-agent](https://trendshift.io/topics/ai-agent) — Live AI agent repo rankings
- [trendshift.io/topics/mcp](https://trendshift.io/topics/mcp) — MCP ecosystem repos
- [trendshift.io/topics/ai-coding](https://trendshift.io/topics/ai-coding) — Coding assistant repos
- [trendshift.io/topics/self-hosted](https://trendshift.io/topics/self-hosted) — Self-hosting repos
- [trendshift.io/topics/ai-skills](https://trendshift.io/topics/ai-skills) — Skills/config repos
- [trendshift.io/repository-engagements](https://trendshift.io/repository-engagements) — Monthly star velocity
- [trendshift.io/insights](https://trendshift.io/insights) — Monthly topic distribution
- [trendshift.io/github-trending-repositories](https://trendshift.io/github-trending-repositories) — Full trending history archive
- [ossinsight.io/trending/ai](https://ossinsight.io/trending/ai) — Real-time from 10.5B GitHub events

**Why Trendshift is valuable:** Unlike GitHub's black-box trending, Trendshift uses a consistent scoring algorithm + maintains a full historical archive. The `?trending-range=360` view shows what sustained traction over the past year, not just one viral week.

**Past-year topic star totals (Trendshift, trending-range=1):**

| Rank | Topic | Stars (past year) | Signal |
|---|---|---|---|
| 1 | #AI agent | 65.1K | Dominant category |
| 2 | #AI coding assistant | 24.6K | Strong, maturing |
| 3 | #AI skills | 20.6K | New category — exploding |
| 4 | #Self-hosted | 16.3K | Privacy/sovereignty trend |
| 5 | #AI workflow | 12.4K | Automation mainstream |
| 6 | #Workflow automation | 11.9K | Adjacent to AI workflow |
| 7 | #Curated list | 10.7K | Developers curating knowledge |
| 8 | #MCP | 9.8K | Protocol ecosystem growing |
| 9 | #AI memory | 8.2K | Memory layer becoming standard |
| 10 | #Web scraping | 7.2K | Browser automation signal |

**Top repos by total stars (360-day sustained traction):**

| Repository | Stars | Category | Key insight |
|---|---|---|---|
| **Langflow** | ~147K | Visual agent builder | Top AI agent repo; drag-drop for RAG + multi-agent |
| **Dify** | ~138K | Production AI platform | RAG + 100+ LLMs + MCP + observability |
| **Open WebUI** | ~124K+ | Self-hosted AI interface | 270M+ Docker downloads; backbone of local AI |
| **Browser-use** | ~92K | Web automation | Vision + DOM; MIT license; AI web browsing |
| **Mem0** | ~52K | Agent memory layer | Persistent memory = what separates toy from prod agent |
| **Flowise** | ~51K | Visual agent builder | Drag-drop agent creation, low barrier |
| **vLLM** | ~68K | LLM inference engine | Fastest-growing by contributors; PagedAttention |
| **LangGraph** | ~34.5K | Stateful agent framework | 34.5M monthly downloads; enterprise leader |

**Monthly velocity (May 2026 — trendshift/repository-engagements):**
- mattpocock/skills: **54,658 new stars in May 2026**
- multica-ai/andrej-karpathy-skills: **50,341 new stars in May 2026**
- Top topics this month: #AI agent (43.8K), #AI coding assistant (22.6K), #AI skills (18.6K), #Self-hosted (10.6K), #MCP (4.5K)

**Five trend signals unique to Trendshift data:**

1. **#AI skills is a new category that doesn't exist in traditional taxonomies** — CLAUDE.md files, agent.md configs, personal AI stacks. 20.6K stars past year. This is the "spec-driven development" trend made visible in GitHub star data.

2. **Browser automation is mainstream** — Browser-use at 92K stars. Web browsing is no longer a specialist agent capability; it is table-stakes infrastructure.

3. **Memory is the missing primitive** — Mem0 at 52K. The rise of #AI memory (8.2K topic stars) signals that developers have moved past "chatbot" toward "agent that remembers." This is the context engineering / intent debt problem in open-source form.

4. **Self-hosting is a 16.3K-star-per-year trend** — Not niche. Privacy, sovereignty, cost. Dify, Open WebUI, Ollama, RAGFlow all thriving here.

5. **MCP ecosystem is accelerating** — 9.8K topic stars, 97M→110M SDK downloads, 10K+ active servers. The protocol won. Now it is infrastructure.

**Notable MCP ecosystem repos (trendshift/topics/mcp):**
- MCP server security scanner (vulnerability detection)
- Self-extending MCP server (one tool that creates other tools)
- Rust-native Office document processing MCP (Excel/Word/PPT, sub-ms)
- Immich photo management via MCP
- Indian stock research MCP (live Screener.in data → Claude as equity analyst)

### GitHub Trending AI — Top Repos & Ecosystem Signals (Researched 2026-05-29)

**Tracking sources:**
- [OSSInsight Trending AI](https://ossinsight.io/trending/ai) — Real-time rankings from 10.5B+ GitHub events
- [ByteBytego Top AI Repos](https://blog.bytebytego.com/p/top-ai-github-repositories-in-2026)
- [Fungies.io Top 20 Agent Frameworks](https://fungies.io/top-github-repositories-ai-agent-frameworks-2026/)
- GitHub Octoverse 2025: 4.3M AI repos, 178% YoY jump in LLM-focused projects

**Top repos by stars (mid-2026):**

| Repository | Stars | Category | Signal |
|---|---|---|---|
| OpenClaw | ~210K+ | Open-source AI | Fastest-growing ever — 9K → 60K in days |
| AutoGPT | ~167K | Autonomous agents | Platform for deploying agent fleets at scale |
| Karpathy CLAUDE.md | ~156K | AI coding workflow | Personal AI config files are a category now |
| Langflow | ~146K | Visual agent builder | Low-code agent building is mainstream |
| Dify | ~136K | Visual agent builder | RAG + agent orchestration + MCP integration |
| Open WebUI | ~124K+ | Self-hosted AI interface | 282M downloads — self-hosting is back |
| n8n | ~162K | Workflow automation | Native AI + MCP client/server |
| ComfyUI | ~106K | Image generation | Visual workflow for media AI |
| vLLM | ~68K | Inference engine | De facto standard for serving LLMs |
| RAGFlow | ~70K+ | RAG platform | Grounded, traceable enterprise knowledge |
| Mem0 | ~52K | Agent memory | Memory layer for production agents |
| Flowise | ~51K | Visual agent builder | Drag-and-drop agent creation |
| LangGraph | ~32.3K | Agent framework | Enterprise-grade stateful orchestration |

**Five macro trends from GitHub data:**

1. **Visual/Low-code agent builders dominate top stars** — 3 of top 5 repos (Langflow, Dify, Flowise) are visual builders. "Everyone's a builder" is manifesting in star counts.

2. **Personal AI stacks are a category** — garrytan/gstack (50K stars in 16 days), Karpathy CLAUDE.md (156K stars), mattpocock/skills (10K). Developers are sharing their personal agent configurations as open source. This validates spec-driven development and context engineering as mainstream.

3. **Self-hosting renaissance** — OpenClaw, Open WebUI (282M downloads), Ollama, RAGFlow, Dify — all built for on-premise, privacy-first deployment. Sovereignty is not just a government concern; it is a developer concern.

4. **Rust is becoming the agent infrastructure language** — 16x increase in star velocity for Rust AI tools (25/day in 2023 → 404/day in 2026). Four categories: Agent OS/Runtime (~38%), CLI Tools (~26%), Browser Automation (~20%), Model Tooling (~16%). When agents have root access, memory safety is non-optional.

5. **Multi-agent systems, not single chatbots** — Every top repo is a system of specialized workers. The "talk to one model, get one answer" era is quietly being replaced by "a team of agents collaborating."

**Weekly velocity signals (May 2026):**
- claude-context (semantic code search MCP server): 10.6K stars/week
- codegraph: 14.1K new stars in one week
- ~290K aggregate stars across top 10 trending, 73K new in 7 days
- Dominant theme: infrastructure for AI agents in production — memory, context, local execution

### Distribution to Articles
- **Post 1 (Tipping Point)**: AAIF formation as evidence of industry recognizing the systemic challenge. Regulation timeline (EU AI Act Aug 2026).
- **Post 2 (Architect)**: Microsoft Agent Framework declarative agents (YAML), Anthropic Agent SDK as reference architecture, ADK Task API for structured delegation, governance toolkit as new architectural primitive.
- **Post 5 (Leadership)**: Agent Governance Toolkit (EU AI Act compliance mapping), OWASP Top 10 for Agentic Apps, regulation timeline, KPMG/BMW early adopters.
- **Post 6 (Emerging Tech)**: ALL of this — enriches every layer. Microsoft's governance bet, Google's vertical integration, AWS managed infra, Anthropic's dev experience, AAIF standards, coding agent market ($1.2B Cursor, $2.5B Claude), framework comparison update, protocol convergence.
- **Post 7 (2030 Vision)**: AAIF trajectory (ISO/IETF by 2028+), self-hosting renaissance, terminal-first shift, agent market $7.84B → $52.62B by 2030.

---

## Notes

- **Name correction:** Fiona Fung (not "Fiona Fun"). Title: Director of Engineering for Claude Code, Anthropic.
- **Event year:** All Google I/O talks are from 2026, not 2025.
- **Google 75% stat:** Sundar Pichai, Google Cloud Next 2026 (not I/O). The transcript from MacVean says "3/4 of all code" which references the same internal data.
- **Jeff Atwood:** The exact phrasing "software is a liability" comes from *Software Engineering at Google* (the book). Atwood's version is "the best code is no code at all" (Coding Horror, May 2007).
