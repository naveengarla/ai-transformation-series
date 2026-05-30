# Emerging AI Tech Every Stakeholder Should Know: The New Stack

*Part 6 of a series on how AI is transforming software engineering — and what it means for architects, developers, testers, and leaders.*

---

Most organizations are making AI technology decisions at the wrong layer.

The conversation in most engineering teams focuses on models — which LLM to use, whether GPT or Claude or Gemini is better for a given task, whether open-source models have closed the gap with frontier providers. These are real decisions with real trade-offs. But they are not where the most consequential choices live. The AI engineering stack has seven layers, and decisions made at one layer constrain and shape everything above it. The architects, developers, and leaders who understand the full stack make better decisions at every layer. Those who see only the model layer are optimizing a small fraction of the system.

This post is a practitioner's map of the stack — what each layer does, what matters at each level, and how the layers connect.

> **[FIGURE 1: "The AI-Native Engineering Stack — Seven Layers"]**
> *Vertical stack from bottom to top: Accelerated Compute / Cloud & Inference / Foundation Models / Agent Frameworks / Protocols & Standards / Developer Tooling / Application & Governance. Each layer labeled with key players and the primary decision at that layer. Show how decisions cascade downward — model choice is constrained by inference infrastructure; framework choice is constrained by protocol support; application design is constrained by framework capabilities.*

## Layer 1: Accelerated Compute

The hardware layer is the foundation everything else runs on, and it has bifurcated.

The fundamental split in 2026 is between training hardware and inference hardware — and the optimization targets are now different enough that NVIDIA has released two distinct architectures for the first time. Training chips optimize for maximum throughput on large matrix operations. Inference chips optimize for decode latency and the ability to serve many concurrent requests efficiently. This distinction matters because the model that a team deploys was trained on infrastructure quite different from the infrastructure that serves it.

Within inference-oriented hardware, the performance hierarchy in mid-2026 runs roughly: custom silicon (Groq's LPUs, Cerebras wafer-scale engines) for maximum throughput on specific workloads, NVIDIA B200 and H200 for general-purpose production workloads at scale, and consumer-grade GPUs (M-series Apple Silicon, RTX 5090) for local and edge deployment. The B200 delivers approximately three times lower cost-per-token than the H200 for FP4-optimized serving — a meaningful economics shift for organizations at scale [1].

The practitioner-relevant insight is this: inference hardware choice directly determines what model sizes are economically viable and at what latency. An organization that designs agents assuming frontier model access at all steps will face a very different cost structure than one that routes intelligently across model tiers. Hardware constrains economics, and economics constrain architecture.

## Layer 2: Cloud and Inference Infrastructure

The inference market has consolidated around philosophies rather than providers.

At the hyperscaler level, the major cloud providers have each committed to building AI infrastructure at a scale that was inconceivable five years ago — millions of GPUs in a single provider's fleet, specialized AI networking fabrics connecting compute nodes, inference gateways that can provision hundreds of agent sandboxes per second. These numbers matter for enterprise deployments that need reliability guarantees and compliance posture more than raw cost optimization.

At the specialized inference provider level, the market has split into three value propositions. Speed-first providers (Groq, Cerebras) are the right choice when latency is the dominant constraint — voice agents, real-time user interactions, streaming workflows. Reliability-first providers (Fireworks AI) lead on uptime and structured output accuracy. Breadth-first providers (Together AI) offer the largest model catalog for teams that need access to multiple open-source models without managing deployment infrastructure. The practical cost spread across providers for the same model is approximately 9x — selecting the right provider for a given use case matters as much as model selection [2].

The architecture decision with the highest practical leverage is multi-provider routing: directing latency-critical traffic to the fastest provider, structured output generation to the most reliable, and batch processing to the cheapest. Teams that implement this pattern consistently outperform single-provider architectures on both cost and reliability.

## Layer 3: Foundation Models

The most significant development in the model layer over the past eighteen months is the collapse of the performance gap between open-source and proprietary models. The MMLU benchmark gap between the best open-weight model and the best frontier model narrowed from 17.5 percentage points to 0.3 in a single year [3]. The gap has not fully closed, but it has narrowed enough that the decision framework has changed entirely.

For most enterprise use cases, the relevant question is no longer "open or closed?" — it is "what is the right model for this specific task at this price point?" Real-world agent session data across millions of developer interactions shows that request costs vary approximately 9x across model families, and cost per accepted line of code varies approximately 7x [4]. The best-value position on the cost-quality frontier — a model achieving frontier-competitive benchmark scores at roughly 5-10% of the per-request cost of the most expensive options — is held by mid-tier models, not by either extreme [4].

The dominant production pattern is multi-model routing: cheap, fast models for classification, routing, and high-volume simple tasks; frontier models for hard reasoning where the quality difference justifies the cost; specialized small models for embeddings, structured extraction, and domain-specific tasks. Single-model architectures are appropriate for prototyping. Production systems that run cost-effectively at scale use routing.

**Model economics (CursorBench 3.1, based on real agent sessions) [4]:**

| Tier | Cost/Request | Benchmark Score | Value Position |
|---|---|---|---|
| Frontier (max) | ~$1.57 | 64.8% | Highest capability |
| Frontier (standard) | ~$0.44–0.81 | 49–63% | Standard production |
| Mid-tier | ~$0.18 | 63.2% | Best cost-quality ratio |

> **[FIGURE 2: "The Cost-Quality Frontier"]**
> *Scatter plot: X-axis = cost per task, Y-axis = benchmark score. Show the frontier curve and where different models sit. Key insight: the best value is not at the frontier — mid-tier models match frontier performance at fraction of the cost. Mark the "Composer 2.5" equivalent position explicitly.*

## Layer 4: Agent Frameworks and Harnesses

The framework layer is where the most consequential architectural choices in AI-native development are made — and where the most common mistakes occur.

The key insight from production deployments is that framework choice moves benchmark performance by up to 30 percentage points on identical models [5]. Harness-only changes, with no model swap, moved a coding agent from rank 30 to top 5 on Terminal Bench 2.0 [6]. The model is the engine; the harness is the car. Most organizations are spending their time arguing about the engine while the car is poorly designed.

The five major frameworks in production use have converged on four orchestration patterns: graph-based state machines (LangGraph, Microsoft Agent Framework), role-based multi-agent crews (CrewAI), explicit handoff chains (OpenAI Agents SDK), and hierarchical agent trees with cross-framework interoperability (Google ADK). Each pattern is genuinely appropriate for specific use cases and genuinely wrong for others. Graph-based is the right choice for compliance-bound workflows that require audit trails, checkpointing, and deterministic edge routing. Role-based is the fastest path to a working prototype. Handoff chains are cleanest for linear agent pipelines. Hierarchical is the right choice when you need to coordinate agents built on different frameworks.

The consolidation event that matters most for enterprise teams: Microsoft merged its two major frameworks into a unified Agent Framework 1.0 (GA April 2026) [5]. Organizations running AutoGen or Semantic Kernel should treat migration as a near-term priority rather than an optional future consideration.

What every framework provides, and what distinguishes mature harnesses from fragile ones, is the scaffold around the model call: durable execution state, human-in-the-loop control points, context management across long sessions, tool interfaces with proper error signaling, and observability hooks. The five primitives of any agent harness are filesystem (durable state and collaboration surface), code execution (autonomous problem-solving), sandbox (isolation and verification), memory (cross-session persistence), and context management (compaction against context rot) [6]. Frameworks that address all five provide the foundation for production deployment. Frameworks that address only some require supplementation.

## Layer 5: Protocols and Standards

The protocol landscape resolved faster than most observers expected.

The Model Context Protocol (MCP) — an open standard for connecting agents to external tools, data, and APIs, now under Linux Foundation governance — has achieved functional ubiquity. Over 110 million monthly SDK downloads, 10,000+ active server implementations, support across every major framework. The protocol's core value is eliminating the N×M integration problem: instead of writing custom connectors for each combination of agent framework and external system, MCP provides a single standard that both sides implement once.

The production evidence for MCP's value is concrete. A major cloud provider's site reliability engineering system replaced over 100 bespoke specialized tools with a filesystem-based MCP surface — source code, runbooks, query schemas, and incident history exposed as files navigable with standard shell commands. The "Intent Met" score on novel incidents rose from 45% to 75% [6]. The lesson: a well-designed MCP context surface outperforms specialized tooling, because LLMs are trained to navigate file structures and the standardization reduces the tool selection errors that degrade multi-tool agent performance.

A2A (Agent-to-Agent protocol) complements MCP by addressing multi-agent coordination rather than tool connectivity. MCP handles how an agent connects to tools and data. A2A handles how agents discover, delegate to, and coordinate with other agents. The two-layer model — MCP for tool connectivity, A2A for agent coordination — is the reference architecture for multi-agent production systems in 2026.

The practical guidance: start with built-in primitives. Add custom MCP integrations when you have tools that multiple clients need to access through a standardized, governed interface. Do not build MCP servers for every integration — that path leads to tool sprawl that confuses models and multiplies maintenance burden.

## Layer 6: Developer Tooling

The developer tooling layer has exploded into a multi-tool ecosystem that most developers are still figuring out how to compose.

The AI coding tools market now has seven serious contenders across four categories: CLI agents (Claude Code, Codex CLI, Gemini CLI) for deep, multi-file, multi-session work; dedicated AI-native IDEs (Cursor, Windsurf, Kiro) that embed agent capabilities into the editing environment; IDE extensions (GitHub Copilot, Cline, Continue) that add agent capabilities to existing editors; and cloud agent platforms (Devin, Jules, OpenHands) for fully autonomous development tasks. The typical power-user stack in 2026 is a CLI agent for deep work plus a Copilot-style extension for inline completions — complementary, not redundant.

Real-world performance data from millions of agent sessions reveals the pattern of what works: models that read more context before generating code consistently outperform models that generate quickly with less context [4]. The input-to-output token ratio in production agent sessions rose from 4.5x in January 2026 to over 11x by May 2026 [4]. Cache-read tokens now account for approximately 90% of total token consumption in mature agent workflows [4] — the agent is overwhelmingly reusing prior context rather than processing it from scratch. This context shift has favorable economics: input tokens cost less than output tokens, and cache reads cost far less than both.

For observability and evaluation, the tooling has matured into three tiers. LangSmith provides deep LangGraph integration with annotation queues for non-technical reviewers. Arize Phoenix and Langfuse serve teams that require full data sovereignty through self-hosted, open-source deployment. Braintrust and DeepEval provide developer-friendly eval pipelines for teams focused on eval-driven development. Only 52.4% of organizations run offline evaluations; only 37.3% run online evaluations [7]. The gap between these numbers and 100% represents the verification deficit that surfaces as delivery instability — the same pattern documented in the DORA data.

## Layer 7: Application, Governance, and Security

The application and governance layer is where most organizations are weakest relative to their ambitions.

**Memory architecture.** Early agent memory relied on context stuffing — loading everything into a single large context window. This fails at scale because relevant signals get buried and the model loses coherence. Production memory in 2026 follows a four-tier cognitive architecture: working memory (the active context window), episodic memory (time-stamped event records), semantic memory (durable generalized facts), and procedural memory (operating guidelines and workflows) [8]. The practical implementations — Mem0 for lightweight deployments (26% accuracy improvement, 91% latency reduction, 90% token reduction vs full-context [8]), Letta for long-horizon autonomous agents, Zep for temporal knowledge graphs — provide managed memory that most teams should adopt rather than build.

**Durable execution.** Agent workflows fail in ways that traditional error handling cannot address: a three-minute, multi-dollar reasoning sequence should not restart from scratch because of a transient network error. Temporal and similar durable execution platforms wrap every agent step as a recoverable activity, serialize state automatically on failure, and resume transparently after recovery. Human-in-the-loop oversight — agent workflows that must pause for hours or days awaiting human approval before proceeding — requires this infrastructure.

**Security.** The accountability gap in AI-native development is real and growing. When AI agents autonomously install packages, pull dependencies, and configure systems, there is no natural owner for those decisions unless the organization creates one deliberately. Commercial security infrastructure (Aikido, Socket, Endor Labs, Chainguard) is now available to address agent-specific attack surfaces — supply chain compromise via malicious packages, prompt injection, privilege escalation in poorly sandboxed environments. More than a third of agent skills scanned in a comprehensive 2026 audit contained at least one security flaw [9]. The OWASP Top 10 for Agentic Applications provides the formal taxonomy of agent-specific risks and the starting point for any security programme.

**What production looks like.** The realistic deployment picture comes from the agents already operating at scale. An SRE agent handling over 35,000 production incidents autonomously, reducing time-to-mitigation from 40 hours to 3 minutes [6]. Autonomous CI agents continuously filing pull requests to address regressions, collapsing a 200-per-day failure backlog to single digits [10]. Multi-agent trading systems operating in financial markets. These are not demonstrations. They are the systems that prove which architectural patterns are durable under production load.

## What the Open-Source Community Reveals

GitHub star counts over the past 30 days are the clearest real-time signal of where practitioner attention is going. The top-trending repository by sustained frequency is a pre-indexed code knowledge graph that exists for one reason: to reduce tokens and tool calls in agent workflows [11]. Three of the next five most-trending repositories are tools that cut token consumption by 40-90% through different mechanisms [11]. The developer community is voting with its attention: the acute pain is not capability — it is cost and reliability. The architectural investments that address those pains are the ones accumulating tens of thousands of stars per week.

The second signal is the explosion of skills repositories — CLAUDE.md files, agent.md configurations, domain-specific skill registries — which now represent the third-fastest-growing category on GitHub by daily star velocity [11]. The community has independently converged on spec-driven development as the practice, and is sharing the artifacts that make it work. The Karpathy-derived skills file accumulated 161,000 stars from a single markdown document [11]. Well-designed intent files are as valuable to the community as well-designed code.

## What Every Stakeholder Should Take Away

**For architects:** Token economics is a first-class architectural constraint — as important as latency. Context topology (what stays inline, what becomes a skill, what is cached, what is delegated) shapes both cost and reasoning quality. Multi-model routing across the full provider landscape, designed at the architecture level, beats single-provider optimization.

**For developers:** The multi-tool stack is the norm and the right investment is in context quality and evaluation depth, not more tools. The 90% cache read share in production sessions means the developer who designs excellent, stable context is building compound advantage that accumulates.

**For testers:** The observability gap — 52% offline evals, 37% online — is the most actionable number in this post. Building evaluation pipelines early compounds. Every agent change validated against a solid eval baseline is a change whose consequences are understood.

**For leaders:** Model selection is a downstream decision. The seven organizational capabilities that determine whether AI adoption produces benefits or instability (DORA [7]) are upstream. Invest there first.

---

*Next in the series: **What It All Means — The 2030 Developer Ecosystem***

---

### References

1. NVIDIA (2026). B200 Blackwell specs; H200 specs. Spheron pricing data. B200: ~3x lower cost-per-token than H200 for FP4-optimized serving.
2. Digital Applied (2026). ["AI Inference Providers: Q2 2026 Pricing Matrix."](https://www.digitalapplied.com/blog/ai-inference-providers-pricing-matrix-q2-2026) Groq, Fireworks, Together: cost, latency, uptime comparison.
3. MindStudio (2026). ["Best Open-Source LLMs for Agentic Coding."](https://www.mindstudio.ai/blog/best-open-source-llms-agentic-coding-2026) MMLU gap: 17.5 → 0.3 points.
4. Cursor (2026). [The Cursor Developer Habits Report — Spring 2026.](https://cursor.com/insights) Model economics, input/output ratio (4.5x→13x), cache dominance (90%), lines/week data.
5. Uvik (2026). ["Agentic AI Frameworks 2026."](https://uvik.net/blog/agentic-ai-frameworks/) Framework comparison; 30pt benchmark swing from framework choice; Microsoft Agent Framework 1.0 GA.
6. AI Boost (2026). [Awesome Harness Engineering.](https://github.com/ai-boost/awesome-harness-engineering) Harness engineering definition; five primitives; rank 30→top 5 (no model swap); Azure SRE 40.5h→3min, 45%→75% Intent Met.
7. DORA (2025). [State of AI-Assisted Software Development.](https://dora.dev/insights/balancing-ai-tensions/) Eval adoption: 52.4% offline, 37.3% online; seven AI capabilities.
8. Enterprise Agentic AI Infrastructure Report (2026). Four-tier memory model; Mem0 benchmarks (+26% accuracy, 91% latency, 90% token reduction); Letta 6.5% working context model.
9. Snyk (2026); Taft, D. K. ["There is no accountability."](https://thenewstack.io/aikido-ai-agents-security/) The New Stack, May 2026. Aikido, Socket, Endor Labs, Chainguard; >⅓ of 4,000 skills with security flaws; OWASP Top 10 for Agentic Applications (Dec 2025).
10. Milovidov, A. (2026). ["What ClickHouse Learned."](https://thenewstack.io/clickhouse-ai-coding-agents/) The New Stack. CI: 200 findings/day → 3-5 per 10M runs.
11. Trendshift (2026). [Top-100 GitHub Trending Repositories — 30-day window.](https://trendshift.io/github-trending-repositories?trending-range=30&trending-limit=100) colbymchenry/codegraph (#1 by frequency); token-reduction tools; karpathy-skills (161K stars).
