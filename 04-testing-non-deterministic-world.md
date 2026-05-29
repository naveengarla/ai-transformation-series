# Testing in a Non-Deterministic World: The Death of Expected Output

*Part 4 of a series on how AI is transforming software engineering — and what it means for architects, developers, testers, and leaders.*

---

In the previous posts, I examined how AI is migrating the bottleneck from code generation to verification, how the architect's role is shifting to system ecology, and how the developer's identity is evolving from writing code to steering intent. All three posts converge on the same conclusion: the hardest problem in AI-native software engineering is not producing code — it is knowing whether the code is correct.

This post is about what that means for testing.

The testing practices that most organizations rely on — unit tests with deterministic assertions, integration tests with fixed expected outputs, the testing pyramid, the green-check-means-ship mentality — were designed for a world where humans wrote code deliberately, understood what they wrote, and could predict what it should do. That world is ending. And the testing discipline must evolve with it.

## The Verification Bottleneck

The shift is already measurable. The 2025 DORA Report introduced "rework rate" as a fifth core metric — tracking how often teams push unplanned fixes to production — specifically because AI-generated code is creating a quality gap that the original four metrics could not capture [5]. The New Stack reported that while AI promised to eliminate developer toil, it has created a new form of it: developers now spend more time reviewing unreliable AI code than they saved generating it [17].

Fiona Fung's team at Anthropic identified verification as the primary bottleneck almost immediately after adopting AI-native workflows [3]. Coding is no longer the slow part. What is slow is confirming correctness — that the output matches intent, does not introduce regressions, integrates cleanly, and behaves as expected under edge cases the AI may not have considered.

This is not a marginal adjustment to existing testing practices. It is a structural shift in what testing means.

> **[FIGURE 1: "The Verification Bottleneck"]**
> *Visual type: Hourglass or funnel. Top (wide): Code generation — fast, cheap, abundant. Narrow middle: Verification — slow, expensive, human-dependent. Bottom (wide): Production — where unverified code causes incidents. The bottleneck is at verification, not generation.*
> *Key data callout: DORA introduced "rework rate" as 5th metric to capture this gap.*
> *Style: Clean, conceptual. The narrowness of the verification layer should be visually striking.*

## Why Traditional Testing Breaks

Traditional software testing rests on a deterministic assumption: given the same input, the same code produces the same output. You write a test that asserts `add(2, 3) == 5`, and if it passes, you have confidence. The assertion is binary. The expectation is fixed. The result is reproducible.

AI-generated code introduces three problems that break this model.

**First, the author does not understand the code.** When a developer writes code by hand, the tests reflect their mental model of what the code should do. When AI generates code, the developer may not have a mental model at all. AI-generated tests can include incorrect assumptions, hallucinations, incomplete coverage, or brittle logic that looks plausible but tests the wrong thing. As one practitioner put it: "Your AI-generated tests are lying to you" — they pass, they cover lines, and they verify nothing meaningful.

**Second, non-deterministic outputs require non-deterministic evaluation.** Agents and LLM-powered systems can produce different output from the same input. Traditional assertions (`assertEqual`, `assertTrue`) cannot handle acceptable variation ranges. Testing AI-driven components requires assessing response stability across varied inputs, hallucination risk, and behavioral consistency — none of which fit cleanly into a pass/fail binary.

**Third, the volume overwhelms the verification surface.** A 76% increase in output per developer and a 33% increase in average PR size (State of AI Coding 2025) means the verification surface is expanding faster than the verification capacity. Google's internal data shows dependency graphs grow quadratically with codebase size [1] [12]. At ten times more code, the test compute requirement may be a hundred times larger — and agents amplify this further by running tests continuously as their own feedback mechanism.

> **[FIGURE 2: "Three Breaks in the Traditional Testing Model"]**
> *Visual type: Three-column comparison. Column headers: "Traditional Testing" / "What AI Breaks" / "What's Needed Instead." Rows: (1) Author understands code → Author may not understand code → Comprehension verification required. (2) Deterministic output → Non-deterministic output → Probabilistic assertions and variation ranges. (3) Human-speed volume → Machine-speed volume → Statistical validation and selective execution.*
> *Style: Clean comparison table rendered as a visual. Each "break" should feel like a crack in a foundation.*

## The Circular Review Problem

There is a deeper structural problem that an arXiv paper from March 2026 articulates clearly: when AI generates both the code and the tests, and AI also reviews the result, the system is checking code against itself, not against intent [arXiv:2603.25773].

Without an external reference — a specification, a human-verified acceptance criterion, a deterministic contract — both the generating and reviewing agents reason from the same artefact, share the same training distribution, and exhibit correlated failures. The review becomes structurally circular. This is why spec-driven development, discussed in Post 3, is not just a workflow preference. It is a testing prerequisite. Without externalized intent, there is nothing independent to verify against.

Open-source maintainers are already feeling this. The New Stack reported in April 2026 that maintainers are "drowning in AI-generated pull requests" — verbose changes with nonsensical descriptions, contributions that submitters cannot explain when questioned, and code that looks plausible on the surface but crumbles under review. This is not a future risk. It is happening now.

## Eval-Driven Development: A New Testing Paradigm

The response emerging from the leading AI engineering teams is eval-driven development (EDD) — a practice that treats evaluations as the primary engine of the development cycle, not an afterthought.

Anthropic's guide to agent evals provides the clearest framework. They distinguish two types of evaluations that serve different purposes:

**Capability evals** ask: "What can this agent do well?" They should start at a low pass rate, targeting tasks the agent currently struggles with. They give teams what Anthropic calls "a clear hill to climb." As teams improve the agent, the pass rate rises. When it plateaus at a high level, the eval has done its job.

**Regression evals** ask: "Does the agent still handle all the tasks it used to?" These should maintain a nearly 100% pass rate. A decline signals that a recent change broke something. As capability evals graduate to high pass rates, they can be promoted into the regression suite.

The hill-climbing metaphor is deliberate. You run your evals, get a baseline score, make changes to the agent's architecture — system prompt, tools, skills, context topology — and rerun the evals. If the score improves, you climb. If it regresses, you investigate. This is not traditional test-then-ship. It is an iterative optimization loop that is structurally different from the deterministic green/red of conventional CI.

Will, from Anthropic's Applied AI team, demonstrated this concretely at Code with Claude London. His inventory management agent had 12 eval tasks across five grader types — some deterministic (token count, latency), some non-deterministic (personality, tone, output quality via LLM-as-judge). He ran evals, triaged failures with Claude Code, made architectural changes (skills instead of long prompts, primitive tools instead of custom ones, one subagent instead of three), and reran. Eval scores climbed from 62% to 92%.

The most mature teams do not just eval before go-live. They eval every commit, every context change, every conversation. As Red Hat's engineering team puts it: eval-driven development is the AI equivalent of test-driven development — except the assertions are probabilistic, the graders are hybrid, and the iteration cycle never ends.

> **[FIGURE 3: "The Eval-Driven Development Loop"]**
> *Visual type: Circular/iterative diagram. Steps: Define evals (capability + regression) → Run baseline → Make changes (prompt, tools, skills, architecture) → Rerun evals → Analyze results → Hill-climb or investigate regressions → Repeat.*
> *Annotate with Anthropic's framework: capability evals start low and climb; regression evals stay high or signal breakage. Show "graduation" arrow from capability to regression when pass rate stabilizes.*
> *Key data callout: Will's case study — 62% → 92% through architectural changes, not model changes.*
> *Style: Iterative loop, not linear pipeline. This is the key visual difference from traditional CI/CD.*

## Mutation Testing: AI Makes It Urgent and Cheap

If AI-generated tests are potentially lying about coverage, how do you verify the tests themselves?

Mutation testing — the practice of deliberately introducing small faults ("mutants") into code and checking whether existing tests catch them — has been known for decades but rarely adopted at scale because generating mutations was expensive and running them was slow.

AI changes both sides of that equation. AI makes it cheap to generate intelligent mutations. And AI makes it urgent, because AI is now generating the tests that mutation testing was designed to evaluate.

Thoughtworks placed mutation testing back on their Technology Radar in 2026, recognizing its renewed relevance. Meta presented work at FSE 2025 demonstrating LLM-powered mutation testing at scale — across Facebook, Instagram, WhatsApp, and wearables platforms. Out of thousands of mutants and hundreds of generated tests, privacy engineers accepted 73% of the tests produced by the system.

A practitioner case study illustrates the gap mutation testing reveals: a file with 20 test methods and apparently solid line coverage scored only 70% on mutation testing. Three surviving mutants exposed tests that were not checking for required sections in output, not verifying behaviour when a feature gate was disabled, and not testing boundary conditions at critical thresholds. These are not obscure edge cases. They are the kinds of bugs that cause production incidents.

The complementary approach is property-based testing combined with controlled inputs. A Monte Carlo simulation engine in the same study scored 100% — every mutant was killed — because the test suite combined deterministic tests with exact expected outputs and property-based tests asserting invariants like ordering constraints and monotonicity.

> **[FIGURE 4: "Mutation Testing — Verifying the Verifiers"]**
> *Visual type: Process flow. Original code → AI introduces mutations (small deliberate faults) → Run existing test suite → Did tests catch the mutation? If yes: test is strong (mutant killed). If no: test is weak (mutant survived) — gap in coverage exposed.*
> *Include data callout: "20 test methods, solid line coverage → mutation score only 70%. Three surviving mutants = three production incident risks."*
> *Style: Diagnostic flow. The point is that line coverage is misleading; mutation testing reveals actual test quality.*

## The Scaling Problem: From Boolean to Statistical

Adam Bender raised a problem at Google I/O 2026 that most testing strategies are not prepared for: what happens when you have a million tests and the actual reliability of the infrastructure to run them is in question? [1]

Today, shipping software requires every test to pass — a conjunction of Booleans. All green means ship. Any red means stop. This works when the test suite is small enough to be deterministic and fast enough to run completely.

At ten times the throughput, with AI agents generating changes and running tests continuously, the conjunction of Booleans breaks down. Some tests will be flaky not because the code is wrong but because the test infrastructure cannot reliably execute a million tests. The question becomes: which tests should I run? And how confident do I need to be?

This is a shift from Boolean validation to statistical validation — from "all tests pass" to "the probability of a regression in this change is below an acceptable threshold." Google already operates this way for some large-scale changes, using statistical methods to decide which tests to run and how to interpret their results.

For most organizations, this shift is still ahead. But it is coming, because the alternative — running every test for every change at machine speed — is computationally and economically unsustainable.

## Multi-Agent Verification

Single-model verification has fundamental limitations. Sun et al. (2025) found that single LLMs produce factually incorrect diagnostic conclusions in 50% of real-world microservice incident analyses. Raw distributed log dumps overwhelm context windows, leading models to hallucinate plausible but wrong root causes.

OTelBench — a January 2026 benchmark evaluating frontier LLMs on real-world OpenTelemetry instrumentation — revealed a stark performance gap: the best model scored 80.9% on standard coding benchmarks but only 29% on production-grade instrumentation tasks. No model completed instrumentation in Swift, Ruby, or Java.

The response is multi-agent verification. TrioXpert deploys three specialized agents — one for numeric telemetry, one for textual log patterns, one for historical change events — that cross-validate outcomes. This architecture improved root-cause incident localization by 163% and anomaly detection by 57% over single-LLM approaches.

Anthropic's practices reflect the same principle: unattended work should be followed by an adversarial review subagent in a fresh context. The agent that wrote the code should not be the same agent that reviews it — just as the developer who wrote the code should not be the only reviewer.

> **[FIGURE 5: "Multi-Agent Verification Architecture"]**
> *Visual type: Three parallel agents feeding into a cross-validation layer. Agent 1: Numeric telemetry analysis. Agent 2: Textual log pattern analysis. Agent 3: Historical change event analysis. All three feed into a cross-validation consensus layer that produces a verified diagnosis.*
> *Key data callout: "+163% root-cause localization, +57% anomaly detection vs single-LLM" (TrioXpert).*
> *Also show the adversarial review pattern: Writing agent → Fresh-context review agent → Verified output.*
> *Style: Architecture diagram. Clean, showing separation of concerns and cross-validation.*

## What Production-Scale CI Recovery Looks Like

ClickHouse runs 20 to 80 million tests across approximately 600 commits and 300 pull requests per day. Their CI was accumulating roughly 200 failing test findings per day — a backlog the team could not keep up with. Their policy: never mute flaky tests, never retry. Every failure must be investigated.

In January and February 2026, CTO Alexey Milovidov submitted approximately 700 pull requests fixing tests and CI infrastructure with AI agent assistance. The result: approximately 200 findings per day collapsed to 3–5 per 10 million test runs. The team now also runs two autonomous agents that continuously open PRs and find edge cases. [27]

His assessment: *"This single use case justifies the entire investment."*

And his most important insight for testing teams: **"The headroom in agent-assisted work is in your CI, not in the prompt."** Better prompts improve code generation marginally. A rigorous, well-instrumented test infrastructure improves everything — it gives agents the feedback they need to verify their own work, catches the cases humans miss, and creates the evidence base that makes review trustworthy.

This is the practical expression of the verification bottleneck thesis. The constraint is not writing code. It is having fast, comprehensive, trustworthy signal about whether the code is correct. Invest in CI infrastructure with at least as much urgency as you invest in AI tooling.

## Recommendations for Testing Teams

### Start with evals, not tests
If your system involves AI agents, build evaluation pipelines before conventional test suites. Define capability evals that give you a hill to climb and regression evals that catch drift. Source eval cases from real failures, not synthetic scenarios.

### Adopt mutation testing for AI-generated code
Use AI to generate mutations cheaply and at scale. Treat mutation score as the real quality metric, not line coverage. Line coverage tells you what code was executed; mutation testing tells you whether your tests would catch real bugs.

### Externalize intent before testing
Specs, requirement files, acceptance criteria — these must exist as machine-readable artifacts independent of the code. Without them, AI-generated tests verify code against itself, which is structurally circular.

### Prepare for statistical validation
Begin benchmarking your test infrastructure's throughput ceiling. Identify which tests are most predictive of real regressions. Start building the capability to make risk-based test selection decisions, because running everything for every change will not scale.

### Deploy adversarial review
Do not let the same agent — or the same context window — both generate and verify. Use fresh-context review agents, multi-agent cross-validation, or human-in-the-loop checkpoints for high-risk changes.

### Track rework rate
Adopt DORA's fifth metric. If your rework rate is rising, your verification pipeline is not keeping up with your generation pipeline, regardless of what your line coverage dashboard says.

---

*Next in the series: **Leadership in the AI-Native Org — You Can't Mandate T-Shaped in a Broken System***

---

### Sources and References

**Conference Talks**
1. Bender, A. (2026). "Software Engineering at the Tipping Point." Google I/O 2026. [YouTube](https://www.youtube.com/watch?v=2n41YjR5QfU)
2. Forsgren, N. & MacVean, A. (2026). "Build Core Skills to Thrive as an AI-Era Developer." [Google I/O 2026](https://io.google/2026/explore/workshop-4).
3. Fung, F. (2026). "Running an AI-Native Engineering Org." [Code with Claude](https://claude.com/code-with-claude/session/sf-running-an-ai-native-engineering-org), Anthropic.
4. Will, Anthropic Applied AI (2026). "Tool, Skill, or Subagent: Decomposing an Agent That Outgrew Its Prompt." Code with Claude London.

**Research and Reports**
5. DORA Team (2025). *State of AI-Assisted Software Development.* [dora.dev](https://dora.dev/insights/balancing-ai-tensions/). Rework rate introduced as 5th metric.
6. Anthropic (2026). ["Demystifying Evals for AI Agents."](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents) — capability evals, regression evals, hill climbing.
7. InfoQ (2026). ["Meta Applies Mutation Testing with LLM to Improve Compliance Coverage."](https://www.infoq.com/news/2026/01/meta-llm-mutation-testing/) Meta at FSE 2025, 73% test acceptance rate.
8. InfoQ (2026). ["Evaluating AI Agents in Practice: Benchmarks, Frameworks, and Lessons Learned."](https://www.infoq.com/articles/evaluating-ai-agents-lessons-learned/)
9. InfoQ (2026). ["Docker's Cagent Brings Deterministic Testing to AI Agents."](https://www.infoq.com/news/2026/01/cagent-testing/)
10. arXiv (2026). "The Specification as Quality Gate: Three Hypotheses on AI-Assisted Code Review." arXiv:2603.25773. — Circular review problem.
11. Sun et al. (2025). Single LLMs produce incorrect diagnoses in 50% of microservice incidents.
12. Winters, T. et al. (2020). *Software Engineering at Google.* O'Reilly. — Quadratic dependency growth, test coverage for 1B LOC daily.

**Industry Analysis**
13. The New Stack (2026). ["The AI Verification Bottleneck: Developer Toil Isn't Shrinking."](https://thenewstack.io/the-ai-verification-bottleneck-developer-toil-isnt-shrinking/)
14. The New Stack (2026). ["Open Source Maintainers Are Drowning in AI-Generated Pull Requests."](https://thenewstack.io/ai-generated-code-crisis/)
15. The New Stack (2025). ["Is AI Creating a New Code Review Bottleneck for Senior Engineers?"](https://thenewstack.io/is-ai-creating-a-new-code-review-bottleneck-for-senior-engineers/)
16. Applitools (2026). ["AI Testing in 2026: Why Signal, Trust, and Intentional Choices Matter."](https://applitools.com/blog/ai-testing-strategy-in-2026/)
17. Medium (2026). ["Your AI-Generated Tests Are Lying to You."](https://singhpr.medium.com/your-ai-generated-tests-are-lying-to-you-and-what-to-do-about-it-57fb0e5f2783)
18. Red Hat (2026). ["Eval-Driven Development: Build and Evaluate Reliable AI Agents."](https://developers.redhat.com/articles/2026/03/23/eval-driven-development-build-evaluate-ai-agents)
19. Thoughtworks (2026). ["Codebase Cognitive Debt."](https://www.thoughtworks.com/radar/techniques/codebase-cognitive-debt) Technology Radar, April 2026. — Mutation testing revival.
20. LangChain (2026). [*State of Agent Engineering.*](https://www.langchain.com/state-of-agent-engineering) — 52.4% run offline evals, 37.3% online evals.
21. Milovidov, A. (2026). ["What ClickHouse Learned from a Year of Coding with AI Agents."](https://thenewstack.io/clickhouse-ai-coding-agents/) The New Stack, May 24, 2026. — 700 PRs, 200 findings/day → 3–5 per 10M test runs; "headroom is in your CI, not the prompt."
