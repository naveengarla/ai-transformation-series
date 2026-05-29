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

## Notes

- **Name correction:** Fiona Fung (not "Fiona Fun"). Title: Director of Engineering for Claude Code, Anthropic.
- **Event year:** All Google I/O talks are from 2026, not 2025.
- **Google 75% stat:** Sundar Pichai, Google Cloud Next 2026 (not I/O). The transcript from MacVean says "3/4 of all code" which references the same internal data.
- **Jeff Atwood:** The exact phrasing "software is a liability" comes from *Software Engineering at Google* (the book). Atwood's version is "the best code is no code at all" (Coding Horror, May 2007).
