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

### Trendshift Top-100 Scraped (30-Day Window, 2026-05-29) — via Playwright MCP

Full list scraped from: https://trendshift.io/github-trending-repositories?trending-range=30&trending-limit=100

**Note:** Initial scrape got repo names correct but star counts were wrong (DOM bleeding). User provided accurate full data below.

**Accurate Top-100 with stars, descriptions, tags (30-day trending frequency):**

| Rank | Repo | Stars | Forks | Trending Days | Description | Tags |
|---|---|---|---|---|---|---|
| 1 | colbymchenry/codegraph | 32.7k | 2k | 11 | Pre-indexed code knowledge graph for Claude Code — fewer tokens, fewer tool calls, 100% local | #AI coding assistant |
| 2 | tinyhumansai/openhuman | 29.7k | 2.8k | 10 | Your Personal AI super intelligence. Private, Simple and extremely powerful | #AI agent #AI memory #Digital human |
| 3 | Lum1104/Understand-Anything | 43.7k | 3.5k | 9 | Turn any code/KB into interactive knowledge graph. Works with Claude Code, Codex, Cursor, Copilot, Gemini CLI | #AI coding assistant #AI skills |
| 4 | anthropics/claude-plugins-official | 28.6k | 3.1k | 6 | Official Anthropic-managed directory of high quality Claude Code Plugins | #Curated list |
| 5 | Hmbown/CodeWhale | 36.3k | 3.1k | 6 | Coding agent for DeepSeek models that runs in your terminal | #AI agent #AI coding assistant |
| 6 | TauricResearch/TradingAgents | 80.7k | 15.7k | 5 | Multi-Agents LLM Financial Trading Framework | #AI agent #Fintech |
| 7 | ruvnet/ruflo | 56.5k | 6.4k | 5 | Leading agent orchestration platform for Claude. Multi-agent swarms, RAG, native Claude Code/Codex integration | #AI agent #AI workflow #Workflow automation |
| 8 | ruvnet/RuView | 68.2k | 9k | 5 | WiFi signals → real-time spatial intelligence, vital sign monitoring, presence detection | — |
| 9 | anthropics/financial-services | 28.7k | 4.1k | 5 | (Anthropic financial services repo) | #AI agent #MCP #Fintech |
| 10 | oven-sh/bun | 93.1k | 4.7k | 4 | JavaScript runtime, bundler, test runner, package manager | #Bundler |
| 11 | harry0703/MoneyPrinterTurbo | 68.6k | 9.9k | 3 | Generate short videos with one click using AI LLM | #AI video generation |
| 12 | bytedance/UI-TARS-desktop | 35.7k | 3.6k | 3 | Open-Source Multimodal AI Agent Stack | #AI agent |
| 13 | warpdotdev/warp | 60.8k | 4.8k | 2 | Agentic development environment, born out of the terminal | #AI agent #AI coding assistant |
| 14 | obra/superpowers | **212.1k** | 18.8k | **11** | Agentic skills framework & software development methodology that works | #AI agent #AI coding assistant #AI skills |
| 15 | CloakHQ/CloakBrowser | 22.3k | 1.8k | 8 | Stealth Chromium that passes every bot detection test. Drop-in Playwright replacement | #Headless browser #Web scraping |
| 16 | rohitg00/agentmemory | 19.6k | 1.6k | 8 | **#1 Persistent memory for AI coding agents** based on real-world benchmarks | #AI agent #AI coding assistant #AI memory #MCP |
| 17 | rohitg00/ai-engineering-from-scratch | 24.3k | 3.9k | 7 | Learn it. Build it. Ship it for others | #AI agent #Programming examples |
| 18 | affaan-m/ECC | **198.3k** | 30.5k | 6 | Agent harness performance optimization: Skills, instincts, memory, security for Claude Code, Codex, Opencode, Cursor | #AI agent #AI coding assistant #AI skills |
| 19 | K-Dense-AI/scientific-agent-skills | 26.5k | 2.7k | 6 | Agent Skills for research, science, engineering, analysis, finance and writing | #AI agent #AI skills |
| 20 | soxoj/maigret | 30.9k | 2.2k | 5 | OSINT: collect dossier on person from 3000+ sites | #Web scraping |
| 21 | HKUDS/CLI-Anything | 41.3k | 3.9k | 5 | Making ALL Software Agent-Native | #AI agent #Workflow automation |
| 22 | addyosmani/agent-skills | 46.9k | 5.2k | 5 | Production-grade engineering skills for AI coding agents | #AI agent #AI coding assistant #AI skills |
| 23 | anthropics/knowledge-work-plugins | 17.9k | 2.1k | 4 | Plugins for knowledge workers in Claude Cowork | #AI agent #AI workflow |
| 24 | Imbad0202/academic-research-skills | 23.7k | 2k | 4 | Academic Research Skills: research → write → review → revise → finalize | #AI agent #AI workflow #Workflow automation |
| 25 | microsoft/markitdown | 128.4k | 8.8k | 2 | Python tool for converting files and office docs to Markdown | #Document processing |
| 26 | mattpocock/skills | **111k** | 9.8k | 8 | Skills for Real Engineers. Straight from my .claude directory | #AI skills |
| 27 | multica-ai/andrej-karpathy-skills | **161.4k** | 16.5k | 7 | A single CLAUDE.md file to improve Claude Code behavior, derived from Karpathy's LLM coding pitfall observations | — |
| 28 | browserbase/skills | 3.5k | 236 | 7 | Browserbase's official agent skills to access the web | #AI agent |
| 29 | hardikpandya/stop-slop | 6.6k | 477 | 6 | A skill file for removing AI tells from prose | #AI skills |
| 30 | PriorLabs/TabPFN | 7.2k | 710 | 5 | Foundation Model for Tabular Data | — |
| 31 | Leonxlnx/taste-skill | 27.2k | 1.9k | 5 | Gives your AI good taste. Stops AI from generating boring generic slop | #AI agent #AI skills |
| 32 | virattt/dexter | 26.7k | 3.3k | 3 | Autonomous agent for deep financial research | #AI agent #Fintech |
| 33 | yikart/AiToEarn | 17.1k | 2.7k | 3 | Let's use AI to Earn! | #AI agent #Workflow automation |
| 34 | EveryInc/compound-engineering-plugin | 17.9k | 1.4k | 2 | Official Compound Engineering plugin for Claude Code, Codex, Cursor | #AI agent #AI coding assistant |
| 35 | z-lab/dflash | 4.8k | 342 | 2 | Block Diffusion for Flash Speculative Decoding | #AI infrastructure |
| 36 | calcom/cal.diy | 44.8k | 13.7k | 1 | Scheduling infrastructure for absolutely everyone | #Workflow automation #Self-hosted |
| 37 | datawhalechina/hello-agents | 54.6k | 6.7k | 5 | 《从零开始构建智能体》 — Agent tutorial from scratch | #AI agent #Programming examples |
| 38 | supertone-inc/supertonic | 11k | 1.1k | 5 | Lightning-Fast On-Device Multilingual TTS via ONNX | #Text to speech |
| 39 | 1jehuang/jcode | 6.7k | 762 | 5 | Coding Agent Harness | #AI agent #AI coding assistant |
| 40 | docusealco/docuseal | 17k | 1.6k | 4 | Open source DocuSign alternative | #Document processing #Self-hosted |
| 41 | twentyhq/twenty | 48.2k | 6.8k | 4 | Open alternative to Salesforce, designed for AI | — |
| 42 | dotnet/skills | 3.2k | 236 | 4 | Skills to assist AI coding agents with .NET and C# | #AI agent #AI coding assistant #AI skills |
| 43 | playcanvas/supersplat | 8.8k | 951 | 3 | 3D Gaussian Splat Editor | — |
| 44 | apernet/hysteria | 21.7k | 2.2k | 2 | Lightning fast censorship resistant proxy | #Proxy |
| 45 | InsForge/InsForge | 10.8k | 935 | 2 | All-in-one open-source backend for agentic coding: DB, auth, storage, compute, hosting, AI gateway | #AI agent #AI coding assistant |
| 46 | Anil-matcha/Open-Generative-AI | 17.4k | 2.9k | 2 | Free AI image & video generation studio, 200+ models. Self-hosted, MIT licensed | #AI image generation #AI video generation #Self-hosted |
| 47 | decolua/9router | 15.1k | 2.3k | 5 | Unlimited FREE AI coding. Connect to 40+ providers. Auto-fallback, **RTK -40% tokens**, never hit limits | #AI coding assistant #AI infrastructure |
| 48 | mukul975/Anthropic-Cybersecurity-Skills | 11.8k | 1.3k | 5 | 754 cybersecurity skills for AI agents. MITRE ATT&CK, NIST CSF 2.0, ATLAS, D3FEND, NIST AI RMF. 26 domains | #AI agent #AI skills |
| 49 | LearningCircuit/local-deep-research | 8.2k | 724 | 4 | ~95% SimpleQA. Supports local+cloud LLMs. 10+ search engines. Everything Local & Encrypted | #Local LLM #RAG #Self-hosted |
| 50 | ChromeDevTools/chrome-devtools-mcp | 42.3k | 2.7k | 4 | Chrome DevTools for coding agents | #AI agent #AI coding assistant #MCP |
| 51 | influxdata/telegraf | 17.6k | 5.8k | 3 | Metrics/logs collection agent | #Monitoring |
| 52 | Flowseal/zapret-discord-youtube | 28.6k | 2.2k | 3 | (Censorship bypass proxy) | #Proxy |
| 53 | HKUDS/AI-Trader | 19k | 2.9k | 3 | 100% Fully-Automated Agent-Native Trading | #AI agent #Fintech |
| 54 | Fincept-Corporation/FinceptTerminal | 24.5k | 3.4k | 3 | Finance terminal: market analytics, investment research, economic data | #Fintech |
| 55 | bwya77/vscode-dark-islands | 8.6k | 267 | 3 | VSCode theme | — |
| 56 | datawhalechina/easy-vibe | 15.2k | 1.5k | 3 | vibe coding 2026 — step by step coding course for beginners | #AI coding assistant |
| 57 | AIDC-AI/Pixelle-Video | 20.5k | 2.9k | 2 | AI Fully Automated Short Video Engine | #AI video generation #Text to speech |
| 58 | anthropics/claude-code | **127.8k** | 20.8k | 1 | Claude Code — agentic coding tool in terminal | #AI agent #AI coding assistant |
| 59 | craft-ai-agents/craft-agents-oss | 6.2k | 840 | 1 | (Craft AI agents open source) | #AI agent |
| 60 | shiyu-coder/Kronos | 27.2k | 4.7k | 5 | Foundation Model for Language of Financial Markets | #Fintech |
| 61 | DigitalPlatDev/FreeDomain | 171.4k | 3.3k | 4 | DigitalPlat FreeDomain: Free Domain For Everyone | — |
| 62 | millionco/react-doctor | 11.5k | 371 | 3 | Your agent writes bad React. This catches it | #AI coding assistant |
| 63 | ggml-org/llama.cpp | 113.9k | 18.2k | 2 | LLM inference in C/C++ | #Local LLM #Self-hosted |
| 64 | BigBodyCobain/Shadowbroker | 8.9k | 1.4k | 2 | OSINT: track jets, spy satellites, seismic events in one interface | #Data visualization #Self-hosted #Monitoring |
| 65 | qbittorrent/qBittorrent | 37.8k | 4.7k | 1 | qBittorrent client | — |
| 66 | public-apis/public-apis | 438.3k | 48k | 1 | Collective list of free APIs | #Curated list |
| 67 | LadybirdBrowser/ladybird | 63.7k | 3.1k | 1 | Truly independent web browser | — |
| 68 | anonfaded/FadCam | 2.5k | 190 | 1 | Open-source Android multimedia recorder | — |
| 69 | rowboatlabs/rowboat | 14.7k | 1.5k | 1 | Open-source AI coworker, with memory | #AI agent #AI memory #Local LLM |
| 70 | earendil-works/pi | 57.3k | 6.9k | 1 | AI agent toolkit: coding agent CLI, unified LLM API, TUI & web UI, Slack bot, vLLM pods | #AI agent #AI coding assistant |
| 71 | jundot/omlx | 15.5k | 1.3k | 1 | LLM inference with continuous batching & SSD caching for Apple Silicon — macOS menu bar | #AI infrastructure #Local LLM #Self-hosted |
| 72 | mksglu/context-mode | 16k | 1.2k | 1 | Context window optimization for AI coding agents. **98% reduction**. 15 platforms | #MCP |
| 73 | byoungd/English-level-up-tips | 49k | 5k | 3 | English learning guide | #Curated list |
| 74 | czlonkowski/n8n-mcp | 21.4k | 3.5k | 3 | MCP for Claude Desktop/Code/Windsurf/Cursor to build n8n workflows | #AI workflow #MCP #Workflow automation |
| 75 | can1357/oh-my-pi | 8.4k | 688 | 3 | AI Coding agent for terminal: hash-anchored edits, optimized tool harness, LSP, Python, browser, subagents | #AI agent #AI coding assistant |
| 76 | cocoindex-io/cocoindex | 10.1k | 801 | 2 | Incremental engine for long horizon agents | #AI infrastructure |
| 77 | anthropics/skills | 143.4k | 17k | 2 | Public repository for Agent Skills | #AI agent #AI skills |
| 78 | Alishahryar1/free-claude-code | 30.9k | 4.7k | 2 | Use claude-code for free in terminal/VSCode/Discord like OpenClaw (voice supported) | #AI coding assistant #Local LLM #Proxy |
| 79 | tech-leads-club/agent-skills | 4.5k | 393 | 2 | Secure, validated skill registry for professional AI coding agents. Extends Antigravity, Claude Code, Cursor, Copilot | #AI agent #AI coding assistant #AI skills |
| 80 | manaflow-ai/cmux | 20.3k | 1.5k | 2 | Ghostty-based macOS terminal with vertical tabs and notifications for AI coding agents | #AI agent #AI coding assistant |
| 81 | rmyndharis/OpenWA | 6.9k | 1.4k | 2 | Free Open Source Self-Hosted WhatsApp API Gateway | #Self-hosted |
| 82 | roboflow/supervision | 39.8k | 3.6k | 1 | Reusable computer vision tools | #Computer vision |
| 83 | ShareX/ShareX | 37.9k | 3.8k | 1 | Screen capture & recording | — |
| 84 | simstudioai/sim | 28.7k | 3.6k | 1 | Build, deploy, orchestrate AI agents — central intelligence layer for AI workforce | #AI agent #AI workflow #Self-hosted |
| 85 | VectifyAI/PageIndex | 32.4k | 2.8k | 1 | Document Index for Vectorless, Reasoning-based RAG | #RAG #Document processing |
| 86 | p-e-w/heretic | 22.4k | 2.3k | 1 | Fully automatic censorship removal for language models | #NLP |
| 87 | cursor/plugins | 1.1k | 101 | 1 | Cursor plugin specification and official plugins | #AI agent |
| 88 | awslabs/aidlc-workflows | 2.5k | 413 | 1 | AI-Driven Life Cycle adaptive workflow steering rules for AI coding agents | #AI agent #AI workflow #AI coding assistant |
| 89 | msitarzewski/agency-agents | 106.1k | 17.5k | 6 | Complete AI agency: frontend wizards to Reddit ninjas, whimsy injectors. Each agent has personality, processes, deliverables | #AI agent |
| 90 | jwasham/coding-interview-university | 348k | 83k | 3 | Complete CS study plan to become software engineer | #Programming examples #Curated list |
| 91 | rasbt/LLMs-from-scratch | 96.3k | 14.7k | 3 | Implement ChatGPT-like LLM in PyTorch from scratch | #NLP #Programming examples |
| 92 | odoo/odoo | 51.8k | 32.6k | 2 | Open Source Apps To Grow Your Business | — |
| 93 | danielmiessler/Personal_AI_Infrastructure | 14.5k | 2.1k | 1 | Agentic AI Infrastructure for magnifying HUMAN capabilities | #AI agent #AI infrastructure |
| 94 | rtk-ai/rtk | 56.2k | 3.4k | 1 | CLI proxy that **reduces LLM token consumption by 60-90%** on common dev commands. Single Rust binary, zero deps | #AI infrastructure #Proxy |
| 95 | masterking32/MasterDnsVPN | 4.4k | 448 | 1 | Advanced DNS tunneling VPN for censorship bypass | #Proxy |
| 96 | run-llama/liteparse | 6.6k | 419 | 1 | Fast, helpful, open-source document parser | #Document processing |
| 97 | vercel-labs/open-agents | 5.6k | 725 | 1 | Open source template for building cloud agents | #AI agent #AI workflow |
| 98 | NirDiamant/agents-towards-production | 20.6k | 2.7k | 1 | End-to-end code-first tutorials for production-grade GenAI agents | #AI agent #Programming examples |
| 99 | multica-ai/multica | 34.2k | 4.1k | 3 | Open-source managed agents platform. Turn coding agents into real teammates — assign tasks, track progress, compound skills | #AI agent #Self-hosted |
| 100 | jellyfin/jellyfin | 52.7k | 4.9k | 2 | Free Software Media System | #Self-hosted |

**Raw repo list (ranked 1–100):**
1. NVlabs/Eagle ← NOTE: this was a DOM bleed artefact from initial scrape; actual #1 is colbymchenry/codegraph
2. colbymchenry/codegraph ← `#AI coding assistant`
3. tinyhumansai/openhuman ← `#AI agent #AI memory #Digital human`
4. Lum1104/Understand-Anything ← `#AI coding assistant #AI skills`
5. anthropics/claude-plugins-official
6. Hmbown/CodeWhale
7. TauricResearch/TradingAgents
8. ruvnet/ruflo
9. ruvnet/RuView
10. anthropics/financial-services
11. oven-sh/bun
12. harry0703/MoneyPrinterTurbo
13. bytedance/UI-TARS-desktop
14. warpdotdev/warp
15. obra/superpowers
16. CloakHQ/CloakBrowser
17. rohitg00/agentmemory ← `#AI memory`
18. rohitg00/ai-engineering-from-scratch
19. affaan-m/ECC
20. K-Dense-AI/scientific-agent-skills ← `#AI skills`
21. soxoj/maigret
22. HKUDS/CLI-Anything
23. addyosmani/agent-skills ← `#AI skills`
24. anthropics/knowledge-work-plugins
25. Imbad0202/academic-research-skills ← `#AI skills`
26. microsoft/markitdown
27. mattpocock/skills ← `#AI skills`
28. multica-ai/andrej-karpathy-skills ← `#AI skills`
29. browserbase/skills ← `#AI skills`
30. hardikpandya/stop-slop
31. PriorLabs/TabPFN
32. Leonxlnx/taste-skill ← `#AI skills`
33. virattt/dexter
34. yikart/AiToEarn
35. EveryInc/compound-engineering-plugin
36. z-lab/dflash
37. calcom/cal.diy
38. datawhalechina/hello-agents ← `#AI agent`
39. supertone-inc/supertonic
40. 1jehuang/jcode
41. docusealco/docuseal
42. twentyhq/twenty
43. dotnet/skills ← `#AI skills`
44. playcanvas/supersplat
45. apernet/hysteria
46. InsForge/InsForge
47. Anil-matcha/Open-Generative-AI
48. decolua/9router
49. mukul975/Anthropic-Cybersecurity-Skills ← `#AI skills`
50. LearningCircuit/local-deep-research
51. ChromeDevTools/chrome-devtools-mcp ← `#MCP`
52. influxdata/telegraf
53. Flowseal/zapret-discord-youtube
54. HKUDS/AI-Trader
55. Fincept-Corporation/FinceptTerminal
56. bwya77/vscode-dark-islands
57. datawhalechina/easy-vibe
58. AIDC-AI/Pixelle-Video
59. anthropics/claude-code ← flagship
60. craft-ai-agents/craft-agents-oss
61. shiyu-coder/Kronos
62. DigitalPlatDev/FreeDomain
63. millionco/react-doctor
64. ggml-org/llama.cpp ← inference engine
65. BigBodyCobain/Shadowbroker
66. qbittorrent/qBittorrent
67. public-apis/public-apis
68. LadybirdBrowser/ladybird
69. anonfaded/FadCam
70. rowboatlabs/rowboat ← `#AI agent`
71. earendil-works/pi
72. jundot/omlx
73. mksglu/context-mode
74. byoungd/English-level-up-tips
75. czlonkowski/n8n-mcp ← `#MCP`
76. can1357/oh-my-pi
77. cocoindex-io/cocoindex
78. anthropics/skills ← `#AI skills`
79. Alishahryar1/free-claude-code
80. tech-leads-club/agent-skills ← `#AI skills`
81. manaflow-ai/cmux
82. rmyndharis/OpenWA
83. roboflow/supervision
84. ShareX/ShareX
85. simstudioai/sim
86. VectifyAI/PageIndex
87. p-e-w/heretic
88. cursor/plugins
89. awslabs/aidlc-workflows ← AWS
90. msitarzewski/agency-agents
91. jwasham/coding-interview-university
92. rasbt/LLMs-from-scratch
93. odoo/odoo
94. danielmiessler/Personal_AI_Infrastructure
95. rtk-ai/rtk
96. masterking32/MasterDnsVPN
97. run-llama/liteparse
98. vercel-labs/open-agents
99. NirDiamant/agents-towards-production
100. multica-ai/multica

**Key pattern analysis (30-day window) — UPDATED with accurate data:**

**DAILY TRENDING TOPIC STARS (sidebar data):**
1. #AI agent — 23k stars/day
2. #AI coding assistant — 10.7k
3. #AI skills — 10.2k ← 3rd place in DAILY velocity
4. #Curated list — 5k
5. #Self-hosted — 4.6k
6. #AI workflow — 3.7k
7. #AI video generation — 3.6k
8. #MCP — 2.5k
9. #AI infrastructure — 1.9k

**1. Skills repos are the breakout category** — 11+ of 100 repos are `/skills` or agent config files:
mattpocock/skills, multica-ai/andrej-karpathy-skills, browserbase/skills, addyosmani/agent-skills, K-Dense-AI/scientific-agent-skills, academic-research-skills, Leonxlnx/taste-skill, dotnet/skills, anthropics/skills, tech-leads-club/agent-skills, mukul975/Anthropic-Cybersecurity-Skills
→ Validates Post 3 thesis: structured intent files are a new open-source asset class

**2. Anthropic ecosystem dominates** — 5 direct Anthropic repos in top 100:
anthropics/claude-plugins-official (#5), anthropics/financial-services (#10), anthropics/knowledge-work-plugins (#24), anthropics/claude-code (#59), anthropics/skills (#78)
→ Validates Post 6: Claude Code as the platform, not just a tool

**3. colbymchenry/codegraph is #2** — "Pre-indexed code knowledge graph for Claude Code — fewer tokens, fewer tool calls, 100% local"
→ This is actually the codegraph MCP we use in this very project! Strong signal: context/token efficiency is a top developer concern

**4. Memory is its own category** — rohitg00/agentmemory (#17), tinyhumansai/openhuman (#3 with #AI memory tag)
→ Validates Post 2/3: memory as architectural primitive

**5. MCP tooling appearing** — ChromeDevTools/chrome-devtools-mcp (#51), czlonkowski/n8n-mcp (#75)
→ MCP ecosystem building out from dev tools (Chrome DevTools → n8n workflow automation)

**6. Non-AI repos still in top 100** — bun (#11), warp (#14), qbittorrent (#66), public-apis (#67), Ladybird (#68)
→ GitHub trending is not purely AI — developers are still building infrastructure and general tools

**7. AWS appearing** — awslabs/aidlc-workflows (#89)
→ Hyperscalers now releasing agent workflow tools as open source

**3. Token/cost optimization is an URGENT developer problem** — multiple repos explicitly solving it:
- colbymchenry/codegraph (#1): "fewer tokens, fewer tool calls, 100% local"
- decolua/9router (#47): "RTK -40% tokens, never hit limits"
- rtk-ai/rtk (#94): "reduces LLM token consumption by **60-90%**" — single Rust binary
- mksglu/context-mode (#72): "**98% reduction** in tool output, 15 platforms" — MCP-based
→ This validates the architecture thesis: token economics is now a first-class constraint

**4. Agent harness optimization is its own category:**
- affaan-m/ECC (#18, 198.3k stars!): "The agent harness performance optimization system. Skills, instincts, memory, security"
- obra/superpowers (#14, 212.1k stars!): "Agentic skills framework & software development methodology that works"
→ The two highest-starred repos by absolute count are about IMPROVING how agents run — not new agent features

**5. Fintech is the dominant enterprise vertical** — 6 repos in top 100:
- TauricResearch/TradingAgents (#6, 80.7k): Multi-agent financial trading
- anthropics/financial-services (#9, 28.7k): Anthropic's finance vertical
- virattt/dexter (#32): Autonomous financial research agent
- HKUDS/AI-Trader (#53): "100% Fully-Automated Agent-Native Trading"
- Fincept-Corporation/FinceptTerminal (#54): Finance analytics terminal
- shiyu-coder/Kronos (#60): Foundation Model for Financial Markets
→ Finance is where agents are already deployed in production at scale

**6. "Free AI coding" is a movement** — cost resistance is real:
- decolua/9router (#47): "Unlimited FREE AI coding. 40+ providers"
- Alishahryar1/free-claude-code (#78, 30.9k): "Use claude-code for free like OpenClaw"
→ Token costs are creating demand for workarounds; pricing model disruption is real

**7. Anthropic owns a remarkable cluster** — 6 repos in top 100:
- anthropics/claude-plugins-official (#4, 28.6k)
- anthropics/financial-services (#9, 28.7k)
- anthropics/knowledge-work-plugins (#23, 17.9k)
- anthropics/claude-code (#58, 127.8k)
- anthropics/skills (#77, 143.4k)
→ Anthropic is building a platform ecosystem, not just a model

**8. MCP has a visible ecosystem** — 5 repos explicitly tagged #MCP:
- rohitg00/agentmemory (#16): MCP-connected memory
- anthropics/financial-services (#9): Finance via MCP
- ChromeDevTools/chrome-devtools-mcp (#50, 42.3k): Chrome DevTools for agents
- mksglu/context-mode (#72): Context optimization via MCP
- czlonkowski/n8n-mcp (#74, 21.4k): n8n workflow builder via MCP
→ MCP is becoming the integration layer for real tools (Chrome, n8n, memory) not just toy examples

**9. Cybersecurity skills are a domain:**
- mukul975/Anthropic-Cybersecurity-Skills (#48, 11.8k): 754 skills mapped to MITRE ATT&CK, NIST CSF 2.0, ATLAS, D3FEND, NIST AI RMF

**10. New interesting repos to investigate:**
- InsForge/InsForge (#45): "all-in-one open-source backend for agentic coding — DB, auth, storage, compute, hosting, AI gateway"
- cocoindex-io/cocoindex (#76): "Incremental engine for long horizon agents"
- msitarzewski/agency-agents (#89, 106.1k): "Complete AI agency — each agent has personality, processes, deliverables"
- multica-ai/multica (#99): "Open-source managed agents platform — turn coding agents into real teammates"
- millionco/react-doctor (#62): "Your agent writes bad React. This catches it" ← verification tooling
- LearningCircuit/local-deep-research (#49): "~95% on SimpleQA, fully local, encrypted"

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

## Awesome Harness Engineering — github.com/ai-boost/awesome-harness-engineering (Scraped 2026-05-30)

**Source:** https://github.com/ai-boost/awesome-harness-engineering
Curated list for AI agent harness engineering: tools, patterns, evals, memory, MCP, permissions, observability, orchestration.

### Definition
> "Harness engineering is the discipline of designing the scaffolding — context delivery, tool interfaces, planning artifacts, verification loops, memory systems, and sandboxes — that surrounds an AI agent and determines whether it succeeds or fails on real tasks. Every component here exists because the model can't do it alone — and the best harnesses are designed knowing those components will become unnecessary as models improve."

### Canonical Quotes
- **GitHub Copilot team:** "The model is the engine, the harness is the car."
- **Martin Fowler's "humans on the loop"** — harness engineers who design and maintain agent environments, not inspect individual outputs
- **Thoughtworks / Kulkarni:** "The better the models are, the thinner the harness needs to be."

### Five Harness Primitives (LangChain)
Filesystem (durable state + collaboration surface) · Code execution · Sandbox (isolation + verification) · Memory (cross-session persistence) · Context management (compaction against "context rot")
**Co-evolution warning:** Models trained with specific harnesses can become overfitted to those designs.

### Hard Data Points

| Finding | Data | Source |
|---|---|---|
| Harness-only rank improvement (no model swap) | **Rank 30 → Top 5**, Terminal Bench 2.0 | LangChain |
| State machine constraints on local models | **2/10 → 10/10** SWE-bench subset | statewright |
| Azure SRE Agent incident resolution | **40.5 hours → 3 minutes** (35K+ incidents) | Microsoft |
| Azure SRE "Intent Met" score, 100+ tools → filesystem | **45% → 75%** on novel incidents | Microsoft |
| Harness setup benchmark swing | **±5+ percentage points** | Anthropic 2026 Trends |
| Negative examples in SKILL.md routing | **73% → 85%** routing accuracy | OpenAI |
| AutoHarness (learned constraints) vs frontier | Gemini-2.5-Flash + AutoHarness **> GPT-5.2-High** | Google DeepMind |
| AdaptOrch topology selection vs model selection | **+12–23% performance** | Feb 2026 paper |
| Claude Code compaction: token reduction | **84%** in 100-turn eval | Anthropic |
| context-mode MCP (tool output interception) | **77% token reduction, 76% wall time reduction** | context-mode |
| Confucius Code Agent (CCA) SWE-Bench-Pro | **59% Resolve@1** (beats commercial baselines) | Meta/Harvard |

### Anthropic Claude Code Postmortem
Three harness-level changes caused visible quality regressions:
1. Default reasoning-effort downgrade
2. Caching bug that dropped thinking history from stale sessions
3. Overly aggressive verbosity-limiting system prompt
→ Minor harness adjustments (prompt wording, cache headers, default parameters) compound into visible regressions

### Distribution to Articles
- **Post 2 (Architect):** Harness IS the architecture. Azure SRE case study, five primitives, Martin Fowler "humans on the loop", co-evolution warning, rank 30→top 5 harness-only
- **Post 3 (Developer):** Level 2→3 = harness engineering as developer skill. "Engine/car" quote. 5pt benchmark swing
- **Post 4 (Testing):** statewright (2/10→10/10), LLM Readiness Harness CI gates, verification loop patterns
- **Post 6 (Emerging Tech):** Add "Harness Engineering" as named section. Full definition, primitives, data table, Azure SRE
- **Post 7 (2030 Vision):** "Components will become unnecessary as models improve" — the trajectory

---

## Cursor Developer Habits Report — Spring 2026 (Scraped 2026-05-29)

**Source:** https://cursor.com/insights — "The Cursor Developer Habits Report, Spring 2026"
Based on aggregated Cursor product and engineering data: agent usage, token consumption, accepted AI diffs, merged PR activity.

### Developer Acceleration (Hard Data)

**Code volume:**
- Lines added/dev/week: Jan 2025: **3.6K** → May 2026: **8.6K** (2.4x in 16 months)
- Lines added per PR (p75): Jan 2025: **125** → May 2026: **345** (2.75x)
- Mega PRs (≥1,000 lines changed): Jan 2025: **8%** → May 2026: **13.8%** (nearly 2x)

**Agent depth:**
- Mean tool calls per session: March 2026: **113** → May 2026: **145** (+28% in 2 months)

**Code survival:**
- AI-generated code surviving 60 minutes: Jan 2026: **76%** → May 2026: **81%** (rising quality signal)

### The Power User Gap (Key Finding for Posts 1, 3, 5)

- AI usage concentration: Gini 0.77 for AI lines, 0.75 for spend — highly concentrated among top users
- **P99 developers produce 46x more lines than median** and merge **15x more PRs than median**
- P90 vs p50: 10x more lines, 4x more PRs
- Median developer (p50): ~712 lines/week. P90: ~8,800 lines/week
- Gap is **widening absolutely** even as Gini stays flat — top developers pulling further away in absolute terms

### The Rise of Context (Key Finding for Posts 1, 2, 6)

- Input/output token ratio: Jan 2026: **4.5x** → May 2026: **~11-13x** (2.5x increase in 5 months)
- Input tokens now **>91%** of input-output volume (was 82% in Jan 2026)
- Input tokens now **69.5%** of price-equivalent cost (was 47.5% in Jan 2026)
- **Cache-read tokens dominate ALL token activity: ~90%** of total tokens are cache reads
- Cache reads 90x larger than actual output tokens
- Implication: context engineering and prompt caching are now the dominant cost levers, not output generation

### Model Economics (CursorBench 3.1 — Internal Benchmark)

**Cost per agent request:**
- Opus 4.7: $1.57 (most expensive)
- Opus 4.6: $0.86
- GPT-5.5: $0.81
- GPT-5.4: $0.46
- Sonnet 4.6: $0.44
- GPT-5.3 Codex: $0.30
- Composer 2.5: $0.18 (cheapest)
- **Range: 9x from cheapest to most expensive**

**Cost per accepted line (efficiency measure):**
- Opus 4.6: 1.19¢ (highest cost per accepted line)
- GPT-5.5: 1.09¢
- Sonnet 4.6: 0.54¢
- Composer 2.5: 0.18¢
- **Range: 7x — smaller than request cost gap (9x), suggesting expensive models produce more code per request**

**CursorBench 3.1 score vs cost (frontier frontier):**
- Composer 2.5: **63.2% at $0.55** — best value on the frontier
- Opus 4.7 Max: 64.8% at $11.02 — highest performance but 20x the cost
- GPT-5.5 High: **62.6% at $3.59** — strong mid-tier
- Sonnet 4.6 Max: 49% at $3.09 — lowest frontier score
- Key: **Composer 2.5 matches frontier models at 5-10% of the cost**

### The Shift to Automation (Key Finding for Posts 5, 6, 7)

- Changes accepted **without manual review**: Jan 2026: **7%** → May 2026: **38%** (5.4x in 5 months)
- Security review is emerging as leading automation use case
- Cursor SDK runs showing early demand for programmable agent infrastructure

### Google TPU Architecture (ByteByteGo Infographic Notes)
**Source:** ByteByteGo "What is Google's TPU?" infographic (shared by user)

**TPU 8t (Training chip):**
- SparseCore Advantage: offloads data-dependent collectives, eliminates zero-op bottlenecks
- MXU overlap and balanced scaling; native FP4 (4-bit)
- Virgo Network: multi-layer, high-radix switches, flat 2-layer, up to 4x DC bandwidth
- Faster storage: TPUDirect RDMA, NIC bypass CPU/DRAM, IOT Lustre direct storage

**TPU 8i (Inference chip):**
- 7th Gen SRAM: 3x more SRAM on-chip vs prior gen, less core idle
- CAE (Collectives Acceleration Engine): replaces 4x SparseCores, 5x lower collective latency, accelerates decode & chain-of-thought
- Boardify ICI topology: high-radix, up to 1,152 chips, 50% lower latency (all-to-all)

**Common spine:** Both use Axion ARM-based hosts, 4th-gen liquid cooling, Pallas/MOSAIC/PyTorch software stack, native FP4

### Distribution to Articles
- **Post 1:** Power user gap (46x/15x) validates amplifier thesis with real data. Context shift validates "engineering is not programming."
- **Post 3:** Developer acceleration data (8.6K lines/week, 2.4x). Power user gap (46x). 38% auto-accept rate validates shift to autonomy.
- **Post 5:** Power user gap widens — Gini stable but absolute inequality growing. Leaders must invest in enabling top developers AND protecting median developers.
- **Post 6:** Model economics table (CursorBench 3.1), cache tokens (90% of all tokens), context shift, Composer 2.5 as value leader, GPU/TPU architecture details.
- **Post 7:** 38% auto-acceptance, automation spreading — the shift to Level 3 autonomy is already visible in data.

## Enterprise Agentic AI Infrastructure Deep Research (May 2026)

**Source:** Deep Research Report — "The State of Enterprise Agentic AI Infrastructure: Frameworks, Memory, Runtime, and Observability in 2026"

### Key Data Points Not Currently in Post 6

**Frameworks:**
- LangGraph: 27,100 monthly technical search queries as of early 2026 (developer mindshare metric)
- Microsoft Agent Framework 1.0 (GA April 2026): Unified AutoGen + Semantic Kernel; LTS for .NET AND Python; AutoGen placed into maintenance mode
- MCP: 97M monthly SDK downloads within one year of launch (previously noted as 110M — use higher number)
- MCP transports: stdio for local/single-machine; Streamable HTTP (HTTPS + SSE) for distributed enterprise
- MCP security: OAuth 2.0 + OpenID Connect natively; TLS encryption; agent never handles raw credentials
- MCP bidirectional primitive: `sampling/createMessage` — allows downstream MCP server to request LLM completion from host (essential for recursive workflows)
- N×M integration problem: 50 tools × 5 LLMs = 250 custom API wrappers → eliminated by MCP

**Memory Architecture (Critical — currently thin in Post 6):**
- Four-tiered cognitive map:
  1. Working Memory — active context window only
  2. Episodic Memory — time-stamped observation-action-outcome tuples (e.g., "Tuesday 10AM: user rejected email for being too formal")
  3. Semantic Memory — durable generalized facts and user preferences
  4. Procedural Memory — operational guidelines, system prompts, tool-use workflows
- GENESIS framework: bidirectional episodic ↔ semantic; consolidation step merges conflicting facts autonomously
- Multi-factor retrieval scoring: `final_score = α × cosine_similarity + β × recency_decay + γ × importance_rating`
- Importance rating assigned at encoding time (1-10 scale); peanut allergy = 10, weather comment = 1
- Mem0 benchmarks vs full-context: **+26% accuracy, 91% lower p95 latency, 90% token reduction**
- Mem0 Graph Variant (Mem0ᵍ): **68.4% accuracy on multi-hop reasoning tasks**
- Letta/MemGPT: uses only 6.5% of context window (~2,093 of 32,000 tokens) for working memory; rest paged to external storage
- Zep: temporal knowledge graph tracking how entities/relationships evolve over time

**Runtimes:**
- Temporal: each step wrapped as Activity in stateful Workflow; exponential backoff on failure; HITL via Signal primitive — workflow can suspend for days/weeks without active compute
- MicroVM providers: Blaxel (sub-25ms resume speeds, hardware-enforced isolation via Firecracker), E2B (coding-agent focused, 24hr session cap)
- gVisor approach (Modal): userspace kernel interception vs dedicated kernel — slower resume, needs warm pools
- Multi-tenancy: Silo (isolated, expensive) / Pool (shared, unsafe) / Bridge = modern standard. Amazon Bedrock AgentCore uses session-isolated microVMs per tenant

**Observability:**
- OTel GenAI semantic conventions: `gen_ai.system`, `gen_ai.request.model`, `gen_ai.usage.input_tokens`, prompt contents, tool invocation arguments, finish reasons
- Maxim AI: integrates production monitoring + simulation + evaluation; trace-to-dataset capability (convert production failure to simulation dataset instantly)
- LangSmith: annotation queues for non-technical domain experts; deep LangGraph coupling
- Arize Phoenix: ML-grade evaluation, OTel compatible, RAG pipeline visualization
- Langfuse: self-hosted tracing + prompt management version control

**Anti-Patterns (New section for Post 6):**
1. **Monolithic Mega-Prompt** — hundreds of instructions in one system prompt overwhelms attention; fix: narrow specialized agents orchestrated by state machine
2. **Agent-as-Business-Process Fallacy** — replacing deterministic business logic with black-box agent; fix: agents at edges to parse unstructured data, deterministic core
3. **Invisible State Management** — relying on raw conversation history for multi-day tasks without external persistence
4. **Uncontrolled Recursion** — reflection quality diminishes sharply after 2-3 cycles; need hard computational limits
5. **Voice Collapse/Transcript Drift** — agents hallucinate policies under peak load; symptom of poor memory + no online evaluation gates
6. **Agent Sprawl** — dozens of agents without ownership/credentials/escalation paths; governance must be day-1, not retrofit

**GraphRAG result:** 63% reduction in enterprise ticket resolution times (vs flat vector RAG)

---

## Thoughtworks Deep Research Agent — Healthcare/Pharma (Arc of AI Conference 2026)

**Speaker:** Sarang Kulkarni, Thoughtworks
**Context:** Multi-agent research systems for healthcare and pharmaceutical R&D

**Key Facts:**
- Drug development cost: **$2.6B** to bring new drug to market
- Half of research studies conducted without prior evidence — knowledge exists but access is broken
- Evolution: RAG chatbot → Agentic RAG → **Agentic RAG++** (deep research system)

**Architecture of Agentic RAG++:**
- Clarification loop → Research loop (think/plan/execute/reflect/adjust) → Writing loop (write/reflect/redraft)
- Tools: RAG tool (weighted hybrid search, 20 context chunks, re-ranker → 7 refined chunks) + text2sql tool (feeds SQL errors back to LLM)
- Reflection step: data reflection + **process reflection** (is the process complete?) + **Draft Writing Loop** (catches synthesis gaps between research and writing)

**Named Problems/Solutions:**
- **Context anxiety** — too much context degrades agent performance
- **Long-horizon task fragmentation** — decisions break between steps; fix: explicit think-act loop (think → plan → inspect → update)
- Anthropic's "think" tool for formalizing reasoning pause
- **Incomplete data → poor self-evaluation** — reflection loop helps

**Harness Engineering Key Insight:**
> "Since AI Agents are basically the combination of model and harness, the better the models are, the thinner the harness needs to be."
> Goal: shift from prompt engineering to automated execution through tools, memory systems, validation checks, constraints, and feedback loops.

**Distribution:** Post 6 (memory architecture, runtime, observability, anti-patterns), Post 4 (eval-driven development), Post 2 (architect - harness engineering concept)

## ClickHouse: A Year of AI Coding Agents in Production (May 2026)

**Source:** ["What ClickHouse Learned from a Year of Coding with AI Agents"](https://thenewstack.io/clickhouse-ai-coding-agents/)
The New Stack, May 24, 2026. By Alexey Milovidov, CTO, ClickHouse.
Context: ClickHouse is a major open-source analytics database with a very large C++ codebase (~600 commits/day, 300 PRs/day, 20-80M CI tests/day).

### The Three Levels of AI-Assisted Coding (Taxonomy)
1. **Level 1: Copy-paste from chat** — Still useful for exploration; compared to agents, obsolete.
2. **Level 2: Agents in your CLI or IDE** — Agent reads codebase, runs commands, edits files, builds, tests, commits. Hand-hold for hard tasks, let run for routine ones. This is most day-to-day work.
3. **Level 3: Autonomous agents in isolated environments** — Multi-agent feedback loops, spec-driven development, orchestrated multi-agent setups. A few examples in production but tooling still maturing. "Results from long autonomous loops can be dubious."

### The Inflection Point
- **Before Claude Opus 4.5 (pre-Nov 2025):** Agents were toys on large C++ codebases. Half the ClickHouse team had never seriously used an agent at their October 2025 offsite.
- **Claude Opus 4.5 (November 2025):** Milovidov began giving it small over-specified C++ tasks → bug investigation from CI logs → small features. It exceeded expectations every time.
- **Quote:** "Since Opus 4.5, agents have been usable for daily work on a large C++ codebase. 2025 was the year of the tools. 2026 should be the year of productivity gains."

### Hard Metrics (Real Production Data)
- **Flaky test fixing:** CI runs 20-80M tests across ~600 commits/300 PRs/day. Before: ~200 findings/day, impossible to keep up. After 2 months with agents (Jan-Feb 2026): Milovidov submitted ~**700 PRs** fixing tests and CI infrastructure. Result: **~200 findings/day → 3-5 per 10M test runs**. Two autonomous agents now open PRs and find edge cases continuously.
- **Merge conflicts:** Agents resolve nearly 100% better than humans. "Reviewing code somebody else wrote is much harder than reviewing code you just wrote."
- **Bug investigation:** One hard concurrency bug that defeated 3 human attempts was fixed by Opus 4.6 in a one-line change, after ~1 hour of reasoning, with full explanation and tests.

### What Works vs What Doesn't
**Works well:**
- Boilerplate and integrations (repetitive build-system changes, config edits across many files)
- Merge conflict resolution (near 100% win rate)
- Code review (custom bot on top of Copilot CLI; human reviewers now focus on architecture, bot catches resource leaks, race conditions, corner cases)
- Fixing flaky tests — single best use case justifying the entire investment
- Bug investigation (with experienced engineer guiding; dangerous with junior engineers)

**Dangerous:**
- Bug investigation with inexperienced engineers — agents produce plausible-but-wrong hypotheses that less experienced engineers follow confidently

### Seven Practical Recommendations
1. **Treat AI as a tool of thought, not a replacement for thinking.** Extension of your editor, not your engineering judgment.
2. **It is a multiplier.** Strong engineers get sharper. Weaker engineers cause more damage. No shortcut around understanding the problem.
3. **Start small, raise expectations gradually.** Skeptics who jump to large complex tasks reconfirm their skepticism.
4. **Always validate.** More tests, more fuzzing, more randomization. **"The headroom in agent-assisted work is in your CI, not in the prompt."**
5. **Use the latest models, keep at least two providers handy.** Model providers experience downtime, sometimes daily. Switch between Claude Code, Codex CLI, and others.
6. **Save guidance to CLAUDE.md/AGENTS.md, but keep it short.** Long instruction files get ignored. Avoid telling the model what NOT to do — that often has the opposite effect.
7. **Be specific.** Which files, which functions, which approach. Preserves your engineering skill in the process.

### Distribution to Articles
- **Post 1 (Tipping Point):** Amplifier quote — "Strong engineers get sharper with agents. Weaker engineers cause more damage." Hard validation of the DORA amplifier finding.
- **Post 3 (Developer Identity):** Three-level taxonomy, CLAUDE.md guidance, "tool of thought not replacement for thinking."
- **Post 4 (Testing):** The CI story is extraordinary — 200 findings/day → 3-5 per 10M runs with 700 PRs. Real verification bottleneck data.
- **Post 6 (Emerging Tech):** Full case study — inflection point, three levels, what works/doesn't, 700 PRs metric.

## Security — AI Agent Supply Chain Attack Surface (Researched 2026-05-29)

**Source:** ["There is no accountability": AI coding agents are installing packages no one owns](https://thenewstack.io/aikido-ai-agents-security/)
The New Stack, May 27, 2026. Interview with Willem Delbare, CEO/CTO, Aikido Security.

### Core Problem
When a human developer installs a package there is at least implicit accountability. When an AI agent acts autonomously — installing packages, pulling dependencies, adding tools — **there is no accountability unless someone has deliberately assumed ownership.** Most enterprises have no policy, no visibility, and no one accountable.

Marketing, sales, and product teams are now using AI agents without realising packages and agent skills are being installed in their local environments. Security teams have no control, no visibility, and no way to identify affected machines after an incident.

### The Attack Surface Is Escalating Fast
- **Aikido Intel** detects ~100,000 malicious packages/day using dual-LLM pipeline + human review
- **In 12 months:** went from single-package compromises → self-replicating worms → **full CI/CD pipeline hijacks chaining across registries**
- AI has lowered the barrier to entry and increased attack velocity: work that required a skilled hacker for hours can now be dispatched to AI agents
- "$8 ChatGPT subscription" is enough to write sophisticated supply chain malware

### Key Vendors in the AI Agent Security Space (May 2026)

| Vendor | Approach | Notable |
|---|---|---|
| **Aikido Security** | Endpoint agent — inspects packages, plugins, IDE/browser extensions before install; blocks malware; 48-hour install hold; MCP server coverage | Aikido Infinite: continuous AI pen testing |
| **Socket** | Real-time detection/blocking of malicious open source packages | $60M Series C at $1B valuation; identified malicious Axios dependency in 6 minutes |
| **Endor Labs** | AURI: Skills plugin + MCP server + CLI detecting vulnerabilities in real time within Cursor/Claude Code | Launched March 2026 |
| **Chainguard** | Hardened minimal container images + curated package repos — securing before code is written | Infrastructure-layer approach |
| **Snyk** | Audited ~4,000 agent skills — **>⅓ contained at least one security flaw** | First comprehensive audit of skills ecosystem |
| **Arcjet** | Runtime enforcement inside agentic workflows: prompt injection + PII blocking | |
| **Mobb Security** | AI agent skill supply chain vulnerabilities | |

### Snyk Skills Audit Finding
**More than one-third of nearly 4,000 scanned agent skills contained at least one security flaw.** This is the skills ecosystem — the CLAUDE.md files, agent.md, and skill registries that developers are sharing at 100k+ stars on GitHub. The attack surface is not theoretical.

### Aikido's Shared Responsibility Model
- Security team sets guardrails (policies, thresholds, approved ecosystems)
- Developer moves freely within them
- Agent operates inside that envelope
- Same model as human developers — just now enforced at the install layer

### Technical Detail: 48-Hour Install Block
- Targets the window where most malicious packages are caught
- Configurable per ecosystem (npm = 48hrs makes sense; Maven Central with GPG signing = may not need it)
- Packages/groups can be whitelisted; one-off approvals available
- Falls back to last approved version, not blocked entirely

### Coverage in Aikido Endpoint (May 2026)
- Models/platforms: Gemini, OpenAI, GitHub Copilot, xAI, MCP Servers, Claude Code, skills.sh
- Skill marketplaces: skills.sh and VS Code Marketplace
- Covers: packages, plugins, IDE extensions, browser extensions, AI models, AI agents

### Distribution to Articles
- **Post 6 (Emerging Tech) — Layer 7 Security section:** This entire finding belongs here. The "no accountability" gap, the 100K malicious packages/day, the Snyk audit (>⅓ of skills have flaws), and the emerging vendor landscape should all go into Post 6's governance/security layer.
- **Post 9 (if written) or Post 6:** The skills security finding directly intersects with Post 3's thesis about skills files as a new open-source asset — they're also a new attack surface.
- **Post 5 (Leadership):** "No one has made the decision, and no one owns the risk" — this is a Deming-principle failure at the organizational level. Leaders need explicit AI security ownership.

## Notes

- **Name correction:** Fiona Fung (not "Fiona Fun"). Title: Director of Engineering for Claude Code, Anthropic.
- **Event year:** All Google I/O talks are from 2026, not 2025.
- **Google 75% stat:** Sundar Pichai, Google Cloud Next 2026 (not I/O). The transcript from MacVean says "3/4 of all code" which references the same internal data.
- **Jeff Atwood:** The exact phrasing "software is a liability" comes from *Software Engineering at Google* (the book). Atwood's version is "the best code is no code at all" (Coding Horror, May 2007).
