# Agentic AI Learning Roadmap for Technical Project Managers

**This is a 15-step sequenced learning roadmap designed for a senior TPM who wants to master agentic AI across frameworks, SDLC, DevOps/SRE, and team leadership.** At 3–5 hours per week, the full path takes approximately 20–24 weeks. Every resource listed is free and publicly accessible — no paywalled courses, no paid certificates required. The roadmap progresses from foundational concepts through framework mastery, domain-specific applications, and culminates in governance and strategic leadership skills.

The sequencing reflects real dependency chains: you cannot evaluate agents without understanding what they are, you cannot lead agentic teams without knowing the frameworks they use, and you cannot govern AI systems without grasping their risk profiles. Each step builds on the last, but the roadmap is also designed so a senior TPM can skip or skim familiar territory.

---

## Step 1: What AI Agents Actually Are

**Description:** Understand what separates AI agents from traditional automation (RPA, scripts, workflows). This step establishes the conceptual vocabulary — autonomy, reasoning loops, tool use, planning — that every subsequent module depends on. As a TPM, you need this foundation to evaluate vendor claims, distinguish real agents from "agentwashing," and communicate architecturally with engineering teams.

**Domain tag:** Foundations

**Prerequisites:** None

**Estimated weekly sessions to complete:** 1 week (3–4 hours)

**Difficulty:** Beginner

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| Building Effective Agents — Anthropic | https://www.anthropic.com/research/building-effective-agents | Article | 1.0 |
| ReAct: Synergizing Reasoning and Acting in Language Models (Yao et al.) | https://arxiv.org/abs/2210.03629 | Paper | 1.5 |
| ReAct Prompting — DAIR.AI Prompt Engineering Guide | https://www.promptingguide.ai/techniques/react | Article | 0.5 |
| Compare AI Agents vs. RPA: Key Differences — TechTarget | https://www.techtarget.com/searchenterpriseai/tip/Compare-AI-agents-vs-RPA-Key-differences-and-overlap | Article | 0.5 |
| ReAct — Google Research Blog | https://research.google/blog/react-synergizing-reasoning-and-acting-in-language-models/ | Article | 0.3 |

**Hands-on exercise:** Create a comparison matrix for your organization: list 5 current automation workflows (CI/CD scripts, Jira automations, alerting rules, etc.) and classify each as "deterministic automation," "AI-assisted," or "potentially agentic." For each, identify what would need to change to make it truly agentic (autonomy, reasoning, tool access). Present this to a peer as a 10-minute briefing.

**Key concepts to master:**
- AI agent vs. RPA vs. traditional automation
- The ReAct loop (Reason + Act)
- Augmented LLMs: retrieval, tool use, memory
- Agent design patterns: prompt chaining, routing, orchestrator-worker, evaluator-optimizer
- Autonomy spectrum: from copilot to fully autonomous

**Pro tip:** Anthropic's "Building Effective Agents" is the single most important document in this entire roadmap. It defines the vocabulary the industry uses and was written by practitioners, not marketers. Read it first, bookmark it, and revisit it after every subsequent step — you'll understand it more deeply each time.

---

## Step 2: Prompt Engineering for TPMs

**Description:** Learn prompt engineering not for writing code, but for specifying agent behavior, evaluating prompt quality, and creating reusable templates your team can standardize on. As the person defining "what good looks like" for AI agent outputs, your ability to write clear, structured instructions directly determines agent reliability.

**Domain tag:** Foundations

**Prerequisites:** Step 1

**Estimated weekly sessions to complete:** 1–2 weeks (5–7 hours)

**Difficulty:** Beginner

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| Anthropic Prompt Engineering Overview — Official Docs | https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview | Docs | 2.0 |
| OpenAI Prompt Engineering Guide | https://platform.openai.com/docs/guides/prompt-engineering | Docs | 1.5 |
| DAIR.AI Prompt Engineering Guide (comprehensive open-source) | https://www.promptingguide.ai/ | Guide | 3.0 |
| Anthropic Interactive Prompt Engineering Tutorial (GitHub) | https://github.com/anthropics/prompt-eng-interactive-tutorial | Repo/Course | 3.0 |
| Prompt Engineering for Business Performance — Anthropic Blog | https://www.anthropic.com/news/prompt-engineering-for-business-performance | Article | 0.5 |

**Hands-on exercise:** Take a real TPM workflow — e.g., writing a sprint retrospective summary, triaging a bug report, or drafting a status update — and write three versions of a prompt to accomplish it: (1) a naive one-liner, (2) a structured prompt with role, context, constraints, and output format, (3) a chain-of-thought prompt with examples. Compare outputs. Document which techniques made the biggest difference and why.

**Key concepts to master:**
- Clarity hierarchy: role → context → task → constraints → output format
- Chain-of-thought reasoning and when to use it
- Few-shot examples and their impact on output quality
- XML tags and structured formatting for complex prompts
- Prompt templates as reusable team assets

**Pro tip:** Your job isn't to become the team's prompt engineer — it's to be the person who can evaluate whether a prompt specification is good enough to ship. Focus on learning to *read* prompts critically: Can you spot ambiguity? Missing constraints? Unstated assumptions? That skill is worth more than writing clever prompts yourself.

---

## Step 3: The Agentic Frameworks Landscape

**Description:** Survey the major agentic AI frameworks — LangChain, LangGraph, AutoGen, CrewAI, OpenAI Agents SDK, and Anthropic's tool use system — at a conceptual level. You don't need to code in each, but you need to understand their architectural philosophies, trade-offs, and when to recommend each. This is the map before the territory.

**Domain tag:** Frameworks & Tools

**Prerequisites:** Steps 1–2

**Estimated weekly sessions to complete:** 2 weeks (6–8 hours)

**Difficulty:** Beginner

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| LangChain Framework Explained — DigitalOcean | https://www.digitalocean.com/community/conceptual-articles/langchain-framework-explained | Article | 1.0 |
| CrewAI Open Source Overview | https://crewai.com/open-source | Docs | 0.5 |
| AutoGen Official Documentation | https://microsoft.github.io/autogen/stable//index.html | Docs | 2.0 |
| OpenAI Agents SDK Documentation | https://openai.github.io/openai-agents-python/ | Docs | 1.5 |
| Claude Tool Use Overview — Anthropic | https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview | Docs | 1.0 |
| Hugging Face AI Agents Course (Unit 0–1) | https://huggingface.co/learn/agents-course/en/unit0/introduction | Course | 2.0 |

**Hands-on exercise:** Build a framework comparison matrix with columns: framework name, architectural model (graph vs. conversation vs. role-based), orchestration pattern, language support, memory model, human-in-the-loop support, observability story, license, and maturity level. Fill it in from the docs. Identify which framework you'd recommend for three scenarios: (1) a single-agent customer support bot, (2) a multi-agent code review pipeline, (3) a cross-platform DevOps automation system.

**Key concepts to master:**
- Graph-based orchestration (LangGraph) vs. conversation-based (AutoGen) vs. role-based (CrewAI)
- Tool calling: function calling (OpenAI), client-side tools (Anthropic), MCP integration
- Stateful vs. stateless agent architectures
- Human-in-the-loop patterns and checkpointing
- Open-source licensing considerations (MIT, Apache 2.0, Elastic)

**Pro tip:** The framework landscape shifts fast. As of early 2026: **LangGraph** is LangChain's recommended agent framework (legacy LangChain agents are deprecated), **AutoGen** is being succeeded by the **Microsoft Agent Framework**, and the **OpenAI Assistants API** shuts down August 2026 in favor of the Responses API + Agents SDK. Don't invest deeply in deprecated approaches — focus on LangGraph, CrewAI, and the OpenAI Agents SDK as the active frontrunners.

---

## Step 4: Deep Dive — LangChain, LangGraph & Stateful Agents

**Description:** Go deeper into the LangChain ecosystem, focusing on LangGraph as the production-grade framework for building stateful, multi-step AI agents. Understand state graphs, conditional routing, checkpointing, and memory — the building blocks your engineering teams will use. A TPM who understands these concepts can scope work accurately and spot architectural risks early.

**Domain tag:** Frameworks & Tools

**Prerequisites:** Step 3

**Estimated weekly sessions to complete:** 2 weeks (6–10 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| LangChain Academy — Introduction to LangGraph Course | https://academy.langchain.com/courses/intro-to-langgraph | Course | 5.0 |
| LangGraph Official Documentation | https://docs.langchain.com/oss/python/langgraph/overview | Docs | 3.0 |
| LangGraph GitHub Repository | https://github.com/langchain-ai/langgraph | Repo | 1.0 |
| How to Build LangGraph Agents — DataCamp Tutorial | https://www.datacamp.com/tutorial/langgraph-agents | Tutorial | 1.5 |

**Hands-on exercise:** Map an existing SDLC workflow at your organization (e.g., "code commit → review → test → deploy → monitor") as a LangGraph-style state graph. Identify: (1) what each node would do, (2) where conditional edges exist (e.g., tests pass/fail), (3) where human-in-the-loop checkpoints are needed, and (4) what state needs to persist between steps. Sketch this as a diagram and present it to your engineering lead for feedback.

**Key concepts to master:**
- StateGraph: nodes, edges, conditional routing
- Durable execution and checkpointing
- Short-term memory (thread state) vs. long-term memory (cross-thread persistence)
- Human-in-the-loop interrupt patterns
- LangSmith for tracing and debugging agent runs

**Pro tip:** You don't need to write LangGraph code, but you should be able to read a LangGraph state diagram and understand what it does. Ask your engineers to present their agent architectures as graph diagrams during design reviews — this makes review tractable and catches issues like missing error handling or unbounded loops.

---

## Step 5: Deep Dive — CrewAI, AutoGen & Multi-Agent Conversation

**Description:** Explore the two leading multi-agent frameworks: CrewAI's role-based "crew" model and Microsoft's AutoGen conversation-based model. These frameworks define how multiple AI agents collaborate, delegate, and communicate — patterns you'll manage in production. Understanding their trade-offs helps you choose the right architecture for your team's use cases.

**Domain tag:** Frameworks & Tools

**Prerequisites:** Steps 3–4

**Estimated weekly sessions to complete:** 2 weeks (6–8 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| AI Agentic Design Patterns with AutoGen — DeepLearning.AI | https://learn.deeplearning.ai/courses/ai-agentic-design-patterns-with-autogen | Course | 2.0 |
| CrewAI Official Documentation | https://docs.crewai.com/ | Docs | 3.0 |
| CrewAI Examples Repository | https://github.com/crewAIInc/crewAI-examples | Repo | 2.0 |
| Microsoft Agent Framework Overview | https://learn.microsoft.com/en-us/agent-framework/overview/agent-framework-overview | Docs | 1.0 |
| OpenAI Cookbook — Agents Topic | https://cookbook.openai.com/topic/agents | Tutorials | 2.0 |

**Hands-on exercise:** Design a multi-agent system for a TPM workflow on paper. Example: a "Release Readiness Crew" with (1) a Requirements Analyst agent (checks stories vs. acceptance criteria), (2) a Test Coverage Agent (evaluates test completeness), (3) a Risk Assessor agent (flags deployment risks from change history), and (4) an Executive Summary agent (compiles a go/no-go recommendation). Define each agent's role, goal, backstory (CrewAI-style), tools it needs, and the sequential/hierarchical process flow.

**Key concepts to master:**
- Role-based agent design: role, goal, backstory (CrewAI)
- ConversableAgent, group chat, nested chats (AutoGen)
- Four agentic design patterns: Reflection, Tool Use, Planning, Multi-Agent Collaboration
- Sequential vs. hierarchical process execution
- Agent handoffs and delegation patterns (OpenAI Agents SDK)

**Pro tip:** The DeepLearning.AI course on AutoGen is only 2 hours and covers the four core agentic design patterns that appear in *every* framework. It's the highest-ROI single resource in this step. Watch it first, then explore CrewAI and the OpenAI Agents SDK through the lens of those patterns.

---

## Step 6: Multi-Agent Orchestration Patterns

**Description:** Move beyond individual frameworks to understand universal orchestration, coordination, and communication patterns for multi-agent systems. This is the architectural thinking layer — supervisor hierarchies, peer-to-peer swarms, event-driven coordination, and shared-state patterns. As a TPM, this knowledge lets you evaluate architecture proposals and anticipate failure modes.

**Domain tag:** Frameworks & Tools

**Prerequisites:** Steps 4–5

**Estimated weekly sessions to complete:** 1–2 weeks (4–6 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| The Landscape of Emerging AI Agent Architectures (Survey) | https://arxiv.org/html/2404.11584v1 | Paper | 2.0 |
| The Orchestration of Multi-Agent Systems (Survey) | https://arxiv.org/html/2601.13671v1 | Paper | 2.0 |
| Anthropic Cookbook — Agent Patterns (Reference Implementation) | https://github.com/anthropics/anthropic-cookbook/tree/main/patterns/agents | Repo | 2.0 |

**Hands-on exercise:** Audit an existing distributed system or workflow at your organization. Map it to one of the five multi-agent patterns: (1) supervisor/hierarchical, (2) peer-to-peer, (3) swarm, (4) pipeline/sequential, (5) evaluator-optimizer. Then propose how it could be re-architected with AI agents, identifying: which pattern fits best, where human oversight checkpoints belong, and what failure modes you'd need to mitigate.

**Key concepts to master:**
- Supervisor/hierarchical vs. peer-to-peer vs. swarm orchestration
- Message passing vs. shared state vs. event-driven communication
- Planning + execution separation
- Evaluator-optimizer loops for self-improvement
- Failure propagation in multi-agent chains

**Pro tip:** The Anthropic cookbook's agent patterns repo is the bridge between theory and practice — it contains working implementations of every pattern from the "Building Effective Agents" guide. Even if you don't run the code, reading the pattern descriptions alongside the implementation gives you the vocabulary to participate in architecture reviews.

---

## Step 7: Emerging Standards — MCP, A2A & the Agentic AI Foundation

**Description:** Master the emerging interoperability standards that will define how agents connect to tools (MCP), communicate with each other (A2A), and follow project-specific instructions (AGENTS.md). These standards are moving from experimental to enterprise-adopted at extraordinary speed, and a TPM who understands them can make better build-vs-buy and vendor decisions.

**Domain tag:** Frameworks & Tools

**Prerequisites:** Steps 3–6

**Estimated weekly sessions to complete:** 1–2 weeks (5–7 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| Model Context Protocol — Official Specification | https://modelcontextprotocol.io/specification/2025-11-25 | Docs | 2.0 |
| Introduction to MCP — Anthropic Skilljar Course | https://anthropic.skilljar.com/introduction-to-model-context-protocol | Course | 3.0 |
| A2A: A New Era of Agent Interoperability — Google Blog | https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/ | Article | 0.5 |
| A2A GitHub Repository (Spec + Samples) | https://github.com/a2aproject/A2A | Repo | 1.0 |
| Agentic AI Foundation — Linux Foundation Announcement | https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation | Article | 0.3 |
| What Is MCP? — Google Cloud Guide | https://cloud.google.com/discover/what-is-model-context-protocol | Article | 0.5 |

**Hands-on exercise:** Create a "standards readiness assessment" for your organization. Inventory current tool integrations (APIs, webhooks, CLIs) and classify each as: (1) already MCP-compatible, (2) could be wrapped as an MCP server easily, (3) would need significant work. Then map your inter-service communication to assess A2A applicability. Draft a one-page recommendation on which standard to adopt first and why.

**Key concepts to master:**
- MCP architecture: hosts, clients, servers; tools (model-controlled) vs. resources (app-controlled)
- A2A protocol: Agent Cards, task lifecycle, opaque agent collaboration
- AGENTS.md as project-specific agent instructions
- JSON-RPC 2.0 as the shared transport layer
- The Agentic AI Foundation (AAIF) governance model under Linux Foundation
- **10,000+** published MCP servers; adopted by OpenAI, Google, Microsoft

**Pro tip:** MCP is the "USB-C for AI" — it's rapidly becoming the universal connector between agents and tools. If your team is building any agent integrations, push for MCP-first design. It's already adopted by every major AI provider. The Anthropic Skilljar course is the most structured free learning path for MCP.

---

## Step 8: AI Agents Across the SDLC

**Description:** Understand how AI agents are transforming every phase of software development: sprint planning, code review, testing, and documentation. This is where agentic AI directly impacts your daily TPM work — from evaluating tools like GitHub Copilot Code Review and CodeRabbit to setting team expectations for AI-augmented quality gates.

**Domain tag:** AI-driven SDLC

**Prerequisites:** Steps 1–3

**Estimated weekly sessions to complete:** 2 weeks (6–8 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| State of AI Code Review Tools in 2025 — DevTools Academy | https://www.devtoolsacademy.com/blog/state-of-ai-code-review-tools-2025/ | Article | 0.75 |
| About GitHub Copilot Code Review — Official Docs | https://docs.github.com/en/copilot/concepts/agents/code-review | Docs | 0.5 |
| The Rise of Agentic AI: Transforming Software Testing — QualiZeal | https://qualizeal.com/the-rise-of-agentic-ai-transforming-software-testing-in-2025-and-beyond/ | Article | 0.75 |
| AI Code Documentation: Benefits and Top Tips — IBM Think | https://www.ibm.com/think/insights/ai-code-documentation-benefits-top-tips | Article | 0.5 |
| Using AI Tools for Backlog Refinement and Story Creation | https://agileseekers.com/blog/using-ai-tools-for-backlog-refinement-and-story-creation | Article | 0.5 |
| How AI Agents Automated Our QA: 700+ Test Coverage (Case Study) | https://openobserve.ai/blog/autonomous-qa-testing-ai-agents-claude-code/ | Article | 0.5 |
| AI Code Review Tools Benchmark — AIMultiple | https://research.aimultiple.com/ai-code-review-tools/ | Report | 0.75 |

**Hands-on exercise:** Conduct a tool evaluation for one SDLC phase at your organization. Pick either code review, testing, or documentation. Identify 3 AI tools, define 5 evaluation criteria relevant to your team (accuracy, integration difficulty, security, team adoption friction, cost), score each tool, and write a one-page recommendation memo. Include a pilot plan with success metrics and a 30-day timeline.

**Key concepts to master:**
- AI code review: PR-level bots (CodeRabbit, Copilot) vs. IDE integration vs. CLI tools
- AI testing agents: self-healing scripts, autonomous test generation, adaptive execution
- AI documentation: inline comments, API docs, architecture docs, README generation
- AI in sprint planning: capacity planning, estimation, backlog prioritization
- **Key stat**: 81% report code quality improvements from AI code review (Qodo 2025 report)

**Pro tip:** Don't try to adopt AI across all SDLC phases simultaneously. Pick the phase where your team has the most pain (usually code review or testing), run a 30-day pilot with clear metrics, and use those results to build the business case for broader adoption. Start with code review — it has the highest ROI and lowest risk.

---

## Step 9: The Agentic Development Lifecycle

**Description:** The SDLC itself is being rewritten. This step covers the "Agentic Development Lifecycle" (ADLC) — how development processes, team structures, and agile ceremonies change when AI agents are active participants. This is strategic TPM territory: rethinking how you plan, estimate, review, and ship software.

**Domain tag:** AI-driven SDLC

**Prerequisites:** Steps 1, 8

**Estimated weekly sessions to complete:** 1–2 weeks (4–6 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| Preparing Your Team for the Agentic SDLC — ThoughtWorks | https://www.thoughtworks.com/en-us/insights/articles/preparing-your-team-for-agentic-software-development-life-cycle | Article | 0.75 |
| From Prompts to Production: Playbook for Agentic Development — InfoQ | https://www.infoq.com/articles/prompts-to-production-playbook-for-agentic-development/ | Article | 1.0 |
| Agentic Development Lifecycle Explained — EPAM | https://www.epam.com/insights/ai/blogs/agentic-development-lifecycle-explained | Article | 0.75 |
| An AI-Led SDLC with Azure and GitHub — Microsoft Tech Community | https://techcommunity.microsoft.com/blog/appsonazureblog/an-ai-led-sdlc-building-an-end-to-end-agentic-software-development-lifecycle-wit/4491896 | Article | 1.0 |
| Does AI Make the Agile Manifesto Obsolete? — InfoQ | https://www.infoq.com/news/2026/02/ai-agile-manifesto-debate/ | Article | 0.5 |

**Hands-on exercise:** Draft an "Agentic SDLC Transition Plan" for your team. Define: (1) current SDLC phase and pain points, (2) which agent touchpoints to introduce first, (3) how sprint ceremonies change (planning with AI estimation, reviews of AI-generated code, retros analyzing token usage), (4) new definition of done that includes AI output review criteria, and (5) a 90-day rollout timeline with success metrics.

**Key concepts to master:**
- ADLC: continuous learning vs. static deployment assumption
- Engineers evolving from creators to governors of AI output
- New roles: knowledge architects, agentic architects, agent reliability engineers
- Prompt/tool/policy versioning as Infrastructure-as-Code
- **Key debate**: 95% still find Agile relevant (Forrester), but ceremonies need adaptation
- ISO/IEC 5338 framework for AI system lifecycle

**Pro tip:** The ThoughtWorks article is the most strategically important resource in this step. It frames the cultural transformation honestly — engineers become governors, not just builders. If you read one thing, read that. Then use the EPAM article's ADLC framework (from 1,000+ deployments) to structure your team's transition.

---

## Step 10: AIOps and Intelligent Observability

**Description:** Understand how AI transforms operations monitoring — from threshold-based alerts to intelligent anomaly detection, event correlation, and predictive alerting. As a TPM overseeing SRE/DevOps teams, you need to distinguish AIOps hype from reality and know where AI genuinely reduces MTTR and on-call burden.

**Domain tag:** DevOps & SRE

**Prerequisites:** Steps 1–2

**Estimated weekly sessions to complete:** 1–2 weeks (5–7 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| What Is AIOps? Definition, Examples, and Use Cases — Coursera | https://www.coursera.org/articles/aiops | Article | 0.5 |
| From Alert Fatigue to Agent-Assisted Intelligent Observability — InfoQ | https://www.infoq.com/articles/agent-assisted-intelligent-observability/ | Article | 0.75 |
| AI-Powered Observability: Picking Up Where AIOps Failed — The New Stack | https://thenewstack.io/ai-powered-observability-picking-up-where-aiops-failed/ | Article | 0.5 |
| SRE Report: Have AIOps Predictions Held Up? — The New Stack | https://thenewstack.io/sre-report-retrospectives-have-aiops-predictions-held-up/ | Article | 0.5 |
| Introducing Bits AI SRE, Your AI On-Call Teammate — Datadog | https://www.datadoghq.com/blog/bits-ai-sre/ | Article | 0.5 |
| Google SRE Workbook: Implementing SLOs | https://sre.google/workbook/implementing-slos/ | Book Chapter | 1.5 |
| MCP-Powered Agentic AI in DevOps — DevOps.com | https://devops.com/mcp-powered-agentic-ai-in-devops-building-secure-scalable-multi-agent-pipelines-for-autonomous-sre-and-observability/ | Article | 0.5 |

**Hands-on exercise:** Audit your current monitoring and alerting setup. Map each alert category to the AIOps capability that could improve it: anomaly detection (for noisy metrics), event correlation (for cascading failures), noise reduction (for alert fatigue), root cause analysis (for slow triage). Quantify the current on-call burden (alerts/week, MTTR, false positive rate) and estimate the potential improvement from AI-enhanced observability. Present this as a business case.

**Key concepts to master:**
- AIOps three types: domain-agnostic, domain-centric, DIY (Gartner taxonomy)
- AI-enhanced observability vs. "AIOps" — starting from observability, not AI
- SLOs, SLIs, error budgets — the foundation AI enhances
- Event correlation, anomaly detection, noise reduction
- **Reality check**: gap between leadership perception and practitioner experience with AIOps

**Pro tip:** The New Stack's "Have AIOps Predictions Held Up?" article is the most honest resource here — it uses real survey data to show where AIOps delivers and where it doesn't. Read it before your vendor meetings. The gap between marketing claims and field reality is significant, and a TPM who knows the data has better negotiating leverage.

---

## Step 11: AI-Powered Incident Management and Remediation

**Description:** Go deeper into AI's role in the incident lifecycle — detection, triage, communication, diagnosis, remediation, and post-mortems — plus autonomous remediation and self-healing systems. This step covers the operational frontier: AI agents that don't just alert you, but fix the problem.

**Domain tag:** DevOps & SRE

**Prerequisites:** Step 10

**Estimated weekly sessions to complete:** 1–2 weeks (5–7 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| AI Agents in Operations: Transforming the Incident Lifecycle — PagerDuty | https://www.pagerduty.com/blog/ai/transforming-the-incident-lifecycle-with-ai-agents/ | Article | 0.75 |
| AI in Incident Response: How Automation Improves MTTR — Rootly | https://webflow.rootly.com/blog/ai-in-incident-response-how-automation-improves-mttr | Article | 0.5 |
| AI in Incident Management — PagerDuty University (Free Course) | https://university.pagerduty.com/ai-in-incident-management | Course | 1.5 |
| AI-Powered CI/CD Pipelines: A Practical Playbook — TechBuddies | https://www.techbuddies.io/2025/12/06/ai-powered-ci-cd-pipelines-a-practical-playbook-for-sre-devops/ | Article | 1.0 |
| Autonomous SRE Agent: Implementation Guide — Jeeva.ai | https://www.jeeva.ai/blog/24-7-autonomous-devops-ai-sre-agent-implementation-plan | Article | 1.0 |
| Agentic AI in Observability Platforms: Autonomous SRE — DevOps.com | https://devops.com/agentic-ai-in-observability-platforms-empowering-autonomous-sre/ | Article | 0.5 |
| AI and ML in DevOps: Transforming CI/CD Pipelines — DevOps.com | https://devops.com/ai-and-ml-in-devops-transforming-ci-cd-pipelines-into-intelligent-autonomous-workflows/ | Article | 0.75 |

**Hands-on exercise:** Design an "AI-Assisted Incident Response Playbook" for your team. For your top 3 incident types (by frequency), define: (1) what an AI agent could do autonomously (noise reduction, initial triage, context gathering), (2) where human approval checkpoints must exist (remediation actions, customer communications), (3) what data the AI needs access to (logs, metrics, runbooks, topology), and (4) success metrics (MTTR reduction target, false positive rate). Include a crawl-walk-run adoption plan.

**Key concepts to master:**
- AI across the incident lifecycle: detect → triage → mobilize → diagnose → resolve
- Autonomous remediation maturity: diagnostics → multi-step fixes → self-healing
- AI in CI/CD: change risk scoring, canary analysis, intelligent rollback
- Runbook automation as the foundation for AI remediation
- **Key stat**: MTTR reduction from 20 min to under 3 min for K8s pod failures (PagerDuty + Rundeck case study)
- **Key stat**: Enterprises achieving **3x faster MTTR** and **30% cost savings** on SRE headcount

**Pro tip:** Start with AI-assisted diagnostics, not autonomous remediation. The crawl-walk-run approach matters enormously here because the blast radius of an AI making wrong operational decisions is far higher than wrong code review comments. PagerDuty University's free course structures this progression well.

---

## Step 12: Evaluating and Observing AI Agents

**Description:** Learn how to measure whether AI agents actually work — evaluation frameworks, benchmarks, tracing, and observability. This is the TPM's quality gate: without evals and observability, you're deploying hope, not software. This step covers both pre-deployment testing and production monitoring of agent behavior.

**Domain tag:** Governance & Leadership

**Prerequisites:** Steps 3–5

**Estimated weekly sessions to complete:** 2 weeks (6–8 hours)

**Difficulty:** Intermediate

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| What is an LLM Evaluation Framework? — Evidently AI | https://www.evidentlyai.com/blog/llm-evaluation-framework | Article | 1.5 |
| Building an LLM Evaluation Framework — Datadog | https://www.datadoghq.com/blog/llm-evaluation-framework-best-practices/ | Article | 1.0 |
| Agent Observability and Tracing — Arize AI | https://arize.com/ai-agents/agent-observability/ | Article | 1.5 |
| Arize Phoenix — Open-Source AI Observability (GitHub) | https://github.com/Arize-ai/phoenix | Repo/Docs | 2.0 |
| 8 LLM Observability Tools to Monitor AI Agents — LangChain | https://www.langchain.com/articles/llm-observability-tools | Article | 1.0 |
| HuggingFace Evaluation Guidebook | https://huggingface.co/spaces/OpenEvals/evaluation-guidebook | Guide | 1.5 |

**Hands-on exercise:** Define an evaluation framework for an AI agent your team is building or considering. Specify: (1) 5 evaluation metrics mapped to business outcomes (accuracy, latency, cost per invocation, hallucination rate, user satisfaction), (2) the eval methodology for each (automated benchmark, LLM-as-judge, human review), (3) pass/fail thresholds, (4) regression testing cadence, and (5) production monitoring dashboards needed. Present this as a "Quality Charter for AI Agents."

**Key concepts to master:**
- Three eval methods: code-based, LLM-as-judge, human-in-the-loop
- Pre-release evals vs. production monitoring — different tools, different cadence
- Agent tracing: spans, traces, tool call logging, decision paths
- Open-source observability: Arize Phoenix, Langfuse (both OpenTelemetry-compatible)
- Commercial observability: LangSmith, Datadog LLM Monitoring, Braintrust
- Faithfulness evaluations, needle-in-the-haystack tests, hallucination detection

**Pro tip:** The single most impactful thing a TPM can do is require eval suites before any agent ships to production. Treat agent evals like you treat unit tests — no green CI, no deploy. Push for this as a non-negotiable quality gate. Arize Phoenix is free, open-source, and production-ready — a good starting point if your team doesn't have observability yet.

---

## Step 13: Risk Management and Security for AI Agents

**Description:** Understand the unique risk profile of AI agents — prompt injection, excessive agency, cascading failures, hallucination-driven actions, and multi-agent trust boundaries. This step covers the OWASP Top 10 for LLMs and for Agentic Applications, the NIST AI Risk Management Framework, and practical guardrails. For a TPM, this is about building the risk register before something breaks in production.

**Domain tag:** Governance & Leadership

**Prerequisites:** Steps 1, 12

**Estimated weekly sessions to complete:** 2 weeks (6–8 hours)

**Difficulty:** Advanced

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| OWASP Top 10 for Large Language Model Applications (2025) | https://owasp.org/www-project-top-10-for-large-language-model-applications/ | Framework | 2.0 |
| OWASP Top 10 for Agentic Applications (2026) | https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/ | Framework | 1.5 |
| NIST AI Risk Management Framework (AI RMF 1.0) | https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf | Framework (PDF) | 3.0 |
| OWASP Top 10 Agents & AI Vulnerabilities Cheat Sheet — Alex Ewerlöf | https://blog.alexewerlof.com/p/owasp-top-10-ai-llm-agents | Article | 1.5 |
| NIST AI 600-1 — Generative AI Profile | https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf | Framework (PDF) | 2.0 |

**Hands-on exercise:** Build an "AI Agent Risk Register" for your organization. For each of the OWASP Top 10 for Agentic Applications (cascading failures, tool misuse, inter-agent trust, etc.): (1) assess likelihood (high/medium/low) for your systems, (2) assess impact, (3) define a mitigation strategy, (4) assign an owner, and (5) define a monitoring approach. Include guardrail recommendations (input validation, output filtering, rate limiting, human approval gates). Present this to your security team for review.

**Key concepts to master:**
- OWASP LLM Top 10: prompt injection, excessive agency, supply chain vulnerabilities
- OWASP Agentic Top 10: cascading failures, tool misuse, inter-agent trust violations
- NIST AI RMF four functions: Govern, Map, Measure, Manage
- Guardrails: input validation, output filtering, rate limiting, sandboxing
- Zero Trust architecture for agent-to-agent communication
- Circuit breakers and fallback patterns for agent failure

**Pro tip:** The OWASP Top 10 for Agentic Applications (released December 2025) is the most TPM-relevant security resource that exists. It was built by 100+ experts specifically for autonomous AI systems. Print it, laminate it, bring it to every architecture review. The Alex Ewerlöf cheat sheet is the most accessible walkthrough — start there, then reference the official docs.

---

## Step 14: Leading Teams That Build Agentic Systems

**Description:** Learn how team structures, sprint ceremonies, velocity metrics, and role definitions change when AI agents are both tools and team members. This is the leadership capstone for day-to-day TPM work: redesigning your operating model for a world where half the code is AI-generated and agents handle entire workflow segments.

**Domain tag:** Governance & Leadership

**Prerequisites:** Steps 8–9, 12

**Estimated weekly sessions to complete:** 1–2 weeks (5–7 hours)

**Difficulty:** Advanced

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| AI Augmented Scrum Framework — Scrum.org | https://www.scrum.org/resources/blog/ai-augmented-scrum-framework-when-half-your-team-autonomous-agents | Article | 1.0 |
| How to Do Sprint Planning When Half Your Team Are AI Agents — Scrum.org | https://www.scrum.org/resources/blog/how-do-sprint-planning-when-half-your-team-are-ai-agents | Article | 1.0 |
| The AI Development Team of the Future — HatchWorks | https://hatchworks.com/blog/gendd/ai-development-team-of-the-future/ | Article | 1.5 |
| AI Will Transform the TPM Role — ServiceNow | https://www.servicenow.com/workflow/learn/ai-transform-technical-project-manager-role.html | Report | 0.5 |
| The AI-Augmented Software Team Operating Model — Argos Infotech | https://www.argosinfotech.com/2026/02/05/the-ai-augmented-software-team-how-our-operating-model-changed-in-2025/ | Case Study | 0.75 |
| Setup an AI-Powered Scrum Team — Scrum.org | https://www.scrum.org/resources/blog/setup-ai-powered-scrum-team-quick-start-guide | Guide | 1.0 |

**Hands-on exercise:** Redesign your team's operating model on paper. Define: (1) which existing roles evolve (e.g., developers → agent orchestrators, QA → AI output validators), (2) what new roles are needed (AI integration lead, prompt specialist), (3) how sprint planning changes (token budgets as capacity, AI-assigned work attribution), (4) how you'll measure velocity when AI generates 10x more code but humans review bottleneck, and (5) what your "agent backlog" looks like (agent improvement tasks alongside feature work). Pilot one ceremony change in your next sprint.

**Key concepts to master:**
- Developers as "Agent Orchestrators" — shifting from creating to governing
- Token budget as capacity planning metric alongside story points
- Human-in-the-loop bottleneck: AI generates fast, human review is the constraint
- GenDD pod model: 3–5 person teams amplified by AI agents
- Agent backlog: treating agent improvement as first-class product work
- **Key stat**: AI will save TPMs **13.4 hours/week** — 10.2 from non-agentic AI, 3.2 from agentic (ServiceNow/Pearson 2025)

**Pro tip:** The biggest mistake TPMs make is treating AI agents as productivity tools while keeping the same team structure. The Scrum.org articles show that ceremonies themselves need redesign — Sprint Reviews must include accountability for AI outputs, and Retrospectives should analyze token logs. Start by changing one ceremony in your next sprint and measure the impact.

---

## Step 15: Enterprise Governance, Compliance, and Strategic Roadmapping

**Description:** The capstone step: building an enterprise AI governance program that spans responsible AI principles, audit trails, regulatory compliance (EU AI Act, NIST), and strategic adoption planning. This is where you synthesize everything into an actionable organizational strategy — the deliverable your leadership expects from a senior TPM who "knows AI."

**Domain tag:** Governance & Leadership

**Prerequisites:** Steps 12–14

**Estimated weekly sessions to complete:** 2 weeks (6–10 hours)

**Difficulty:** Advanced

**Free Resources:**

| Title | URL | Type | Est. Hours |
|-------|-----|------|------------|
| Embrace Responsible AI Principles and Practices — Microsoft Learn | https://learn.microsoft.com/en-us/training/modules/embrace-responsible-ai-principles-practices/ | Course | 1.5 |
| EU AI Act Explorer — artificialintelligenceact.eu | https://artificialintelligenceact.eu/ | Reference | 2.0 |
| NIST AI RMF Playbook & Resource Center | https://airc.nist.gov/airmf-resources/airmf/ | Framework | 2.0 |
| AI Agent Compliance & Governance: Audit Trails — Galileo AI | https://galileo.ai/blog/ai-agent-compliance-governance-audit-trails-risk-management | Article | 1.5 |
| Auditability in AI: Traces, References, and Human Oversight — Cobbai | https://cobbai.com/blog/ai-audit-trails-support | Article | 1.0 |
| Responsible AI: Applying AI Principles with Google Cloud — Google Skills | https://www.skills.google/course_templates/388 | Course | 2.0 |
| The State of AI 2025 — McKinsey (Free Summary) | https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai | Report | 1.0 |

**Hands-on exercise:** Draft a complete "AI Agent Governance Charter" for your organization. Include: (1) responsible AI principles (adapted from Microsoft/Google frameworks to your context), (2) risk classification system for agents (based on autonomy level and blast radius), (3) approval gates for deploying new agents (eval requirements, security review, compliance sign-off), (4) audit trail requirements (what to log, retention policy, access controls), (5) incident response procedures for agent failures, and (6) a quarterly review cadence. Present this to your leadership team as a formal proposal.

**Key concepts to master:**
- Responsible AI six principles: fairness, reliability, privacy, inclusiveness, transparency, accountability
- EU AI Act risk tiers and compliance timeline (high-risk systems deadline: August 2026)
- NIST AI RMF implementation: Govern → Map → Measure → Manage
- Audit trail design: immutable storage, cryptographic hashing, granularity decisions
- Governance drift: when system behavior changes without governance catching it
- **Enterprise reality**: 62% experimenting with agentic AI, but only **2% fully scaled** (Capgemini); **40%+ projects will fail** by 2027 (Gartner)

**Pro tip:** Governance is your competitive advantage as a TPM. While engineers focus on building, you're the one who ensures agents are auditable, compliant, and trustworthy. The Gartner prediction that 40%+ of agentic AI projects will be canceled by 2027 is primarily due to inadequate governance and unclear ROI — not technical failure. The TPM who builds the governance framework is the one who keeps the project alive.

---

## Supplementary: Ongoing Learning Resources

For continuous learning beyond the 15-step roadmap, these free channels and courses provide ongoing coverage of the fast-moving agentic AI landscape:

**Recommended YouTube Channels:**
- **LangChain** (https://www.youtube.com/@LangChain) — LangGraph tutorials, agent orchestration
- **DeepLearning.AI** (https://www.youtube.com/@Deeplearningai) — Andrew Ng's structured AI courses
- **AI Explained** (https://www.youtube.com/@aiexplained-official) — Research analysis, model comparison
- **IBM Technology** (https://www.youtube.com/@IBMTechnology) — Beginner-friendly enterprise AI concepts
- **Fireship** (https://www.youtube.com/@Fireship) — Concise 10-minute tech explainers

**Recommended Free Courses for Deeper Dives:**
- Hugging Face AI Agents Course (https://huggingface.co/learn/agents-course/en/unit0/introduction) — 15–20 hrs, free with certificate
- Microsoft AI Agents for Beginners — 12 lessons (https://microsoft.github.io/ai-agents-for-beginners/) — free, open-source
- LangChain Academy full catalog (https://academy.langchain.com/) — free courses on LangGraph, evaluations, and more
- Vanderbilt "Agentic AI: A Primer for Leaders" on Coursera (https://www.coursera.org/learn/agentic-ai) — free to audit, leadership-focused

**Community Reference Roadmap:**
- roadmap.sh AI Agents Roadmap (https://roadmap.sh/ai-agents) — interactive visual learning path, community-maintained

---

## Roadmap Summary Table

| Step | Title | Domain | Difficulty | Weeks | Prerequisites |
|------|-------|--------|------------|-------|---------------|
| 1 | What AI Agents Actually Are | Foundations | Beginner | 1 | None |
| 2 | Prompt Engineering for TPMs | Foundations | Beginner | 1–2 | Step 1 |
| 3 | The Agentic Frameworks Landscape | Frameworks & Tools | Beginner | 2 | Steps 1–2 |
| 4 | Deep Dive: LangChain & LangGraph | Frameworks & Tools | Intermediate | 2 | Step 3 |
| 5 | Deep Dive: CrewAI, AutoGen & Multi-Agent Conversation | Frameworks & Tools | Intermediate | 2 | Steps 3–4 |
| 6 | Multi-Agent Orchestration Patterns | Frameworks & Tools | Intermediate | 1–2 | Steps 4–5 |
| 7 | Emerging Standards: MCP, A2A & the AAIF | Frameworks & Tools | Intermediate | 1–2 | Steps 3–6 |
| 8 | AI Agents Across the SDLC | AI-driven SDLC | Intermediate | 2 | Steps 1–3 |
| 9 | The Agentic Development Lifecycle | AI-driven SDLC | Intermediate | 1–2 | Steps 1, 8 |
| 10 | AIOps and Intelligent Observability | DevOps & SRE | Intermediate | 1–2 | Steps 1–2 |
| 11 | AI-Powered Incident Management & Remediation | DevOps & SRE | Intermediate | 1–2 | Step 10 |
| 12 | Evaluating and Observing AI Agents | Governance & Leadership | Intermediate | 2 | Steps 3–5 |
| 13 | Risk Management and Security for AI Agents | Governance & Leadership | Advanced | 2 | Steps 1, 12 |
| 14 | Leading Teams That Build Agentic Systems | Governance & Leadership | Advanced | 1–2 | Steps 8–9, 12 |
| 15 | Enterprise Governance, Compliance & Strategy | Governance & Leadership | Advanced | 2 | Steps 12–14 |

**Total estimated duration: 20–26 weeks at 3–5 hours/week (~80–110 hours of focused learning)**

Steps 8–11 can be pursued in parallel with Steps 4–7 for TPMs who want to accelerate the DevOps/SRE and SDLC tracks while still working through frameworks. The foundations track (Steps 1–3) should always be completed first.