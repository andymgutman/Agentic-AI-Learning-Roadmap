# Agentic AI Framework Comparison Matrix

> Step 3 · Agentic AI Learning Roadmap for TPMs

Survey of major agentic AI frameworks — architectural models, trade-offs, and scenario recommendations.

**Architectural model key:** `Graph-based` · `Conversation-based` · `Role-based` · `Tool-use / MCP`  
**Maturity:** rated 1–5 (5 = highest)

---

## Framework Comparison

| Framework | Vendor | Architectural Model | Orchestration Pattern | Language Support | Memory Model | Human-in-the-Loop | Observability | License | Maturity |
|-----------|--------|--------------------|-----------------------|-----------------|--------------|-------------------|---------------|---------|----------|
| **LangGraph** | LangChain | Graph-based | State graph w/ conditional edges | Python, JS/TS | Thread state (short-term) + persistent store (long-term) | Native interrupt/resume checkpointing | LangSmith (first-party); OpenTelemetry-compatible | MIT | ●●●●○ 4/5 |
| **CrewAI** | CrewAI Inc. | Role-based | Sequential or hierarchical crews | Python | Agent-level short-term + optional long-term RAG | Limited — supports human input tasks in flow | CrewAI+ platform (paid); minimal OSS observability | MIT | ●●●○○ 3/5 |
| **AutoGen** | Microsoft | Conversation-based | ConversableAgents + GroupChat | Python (.NET in preview) | Message history in context; external via tools | UserProxy agent pattern; nested chat flows | AutoGen Studio UI; transitioning to Agent Framework | CC BY-NC 4.0 / MIT | ●●●○○ 3/5 |
| **OpenAI Agents SDK** | OpenAI | Conversation-based | Agents + handoffs + guardrails | Python, JS/TS | Thread-level persistence via API; external stores | Approval hooks on tool calls; tracing API | OpenAI Traces dashboard (built-in); Datadog integration | MIT | ●●●○○ 3/5 |
| **Anthropic Tool Use** | Anthropic | Tool-use / MCP | Client-orchestrated + MCP servers | Python, JS/TS, any HTTP | Conversation turns; extended context window | Client controls all loop iterations | Via third-party (Arize Phoenix, LangSmith); no first-party dashboard | Proprietary API (MIT SDKs) | ●●●●○ 4/5 |
| **LangChain (legacy)** | LangChain | Graph-based | LCEL chains + legacy agents | Python, JS/TS | BufferMemory, VectorStore; largely replaced by LangGraph | Limited in legacy agents; use LangGraph instead | LangSmith | MIT | ●●○○○ 2/5 |

---

## Framework Details

### LangGraph
**Status:** Active — recommended LangChain path  
**Tags:** Production-grade · Stateful · Multi-agent · Durable execution · Active 2026

LangGraph models agents as directed state graphs — nodes represent actions, edges define transitions. Ideal for complex, multi-step workflows with branching logic and durable execution. Replaces legacy LangChain agents (deprecated). Strong human-in-the-loop story via checkpoints.

---

### CrewAI
**Status:** Active & growing  
**Tags:** Multi-agent · Role-based · Collaboration · Python-only · Active 2026

CrewAI organizes agents into "crews" of roles with defined goals and backstories — closest to how human teams operate. Great for multi-agent collaboration pipelines. Sequential and hierarchical process modes. Python-only with strong developer ergonomics.

---

### AutoGen
**Status:** Transitioning → Microsoft Agent Framework  
**Tags:** Multi-agent · Group chat · Transitioning · Research-friendly

AutoGen structures multi-agent interaction as conversations between ConversableAgents. GroupChat enables N-way agent dialogue. Being superseded by Microsoft Agent Framework. Covers the four agentic design patterns: Reflection, Tool Use, Planning, Multi-Agent Collaboration.

---

### OpenAI Agents SDK
**Status:** Active — Assistants API retiring Aug 2026  
**Tags:** First-party OpenAI · Handoffs · Guardrails · Active 2026 · Assistants deprecated

OpenAI's official framework for building agents with handoffs, guardrails, and structured tool calling. First-class support for Responses API (replacing Assistants). Traces are built into the platform — no separate observability setup needed.

---

### Anthropic Tool Use
**Status:** Active — MCP expanding rapidly (10,000+ servers)  
**Tags:** MCP-native · Interoperable · Client-orchestrated · Any language via HTTP

Claude's native tool use is client-orchestrated: the model decides which tools to call, the client executes them and returns results. MCP extends this with a universal server protocol adopted by all major AI vendors. Flexible and interoperable — not a "framework" per se, but the substrate many frameworks build on.

---

### LangChain (legacy)
**Status:** Deprecated for agents — use LangGraph  
**Tags:** Deprecated for agents · LCEL still valid · Use LangGraph instead

The original LangChain "AgentExecutor" and legacy agent patterns are deprecated. New projects should use LangGraph. LangChain LCEL chains remain valid for simple pipelines. Understanding this context helps you steer teams away from legacy approaches.

---

## Scenario Recommendations

### Scenario 1 — Single-agent customer support bot

**Recommended: OpenAI Agents SDK**  
Alt: Anthropic Tool Use + MCP

Single-agent pipelines with guardrails and structured tool calls map naturally to the Agents SDK. Built-in tracing, handoff patterns (to human agents), and guardrails reduce boilerplate. Fastest path to production for a focused use case.

---

### Scenario 2 — Multi-agent code review pipeline

**Recommended: LangGraph**  
Alt: CrewAI for simpler role-based setup

Code review is a multi-step stateful workflow: fetch PR → analyze → run checks → summarize → post comment. LangGraph's state graph + conditional edges + checkpointing handle the branching (pass/fail, human approval) and durable execution natively.

---

### Scenario 3 — Cross-platform DevOps automation

**Recommended: Anthropic Tool Use + MCP**  
Alt: LangGraph with MCP tools

DevOps systems span Datadog, PagerDuty, GitHub, Kubernetes, and more. MCP's universal connector model lets each tool expose itself as an MCP server without framework lock-in. With 10,000+ published MCP servers, coverage is deep and growing fast.
