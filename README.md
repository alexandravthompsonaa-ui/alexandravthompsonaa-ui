# Zemin He

**Python / AI engineer.** I build agent systems that have to survive contact with production — not demos.

For the past year I was the only developer at a mid-sized apparel e-commerce company (~90 storefronts). I built and operated a ReAct agent platform with 37 tools that eight departments use daily, along with the publishing, automation and data systems around it. Everything below came out of that: each control exists because something went wrong first.

---

## Selected work

### [agent-governance-layer](https://github.com/alexandravthompsonaa-ui/agent-governance-layer)

The layer that decides whether an agent's tool call may touch a real business system.

- Four risk tiers, per-tool, declared once
- Three gates: permission → data scope → approval level
- Approval state machine: no self-approval, arguments hashed and re-verified at execution, atomic claim, TTL
- Direct and indirect prompt-injection defense (tool results treated as untrusted data)
- Execution sandbox for code-running tools

`159 tests passing` · Python · no third-party runtime dependencies

### [hybrid-rag-retrieval](https://github.com/alexandravthompsonaa-ui/hybrid-rag-retrieval)

Dense retrieval fails on house terms — internal names have no semantic neighbourhood, so they rank below documents that merely talk about something nearby. This merges exact-term recall (with CJK character n-grams) into the dense score, and refuses to answer when the evidence is weak.

`15 tests passing` · Python · runnable comparison included

### [visual-alignment](https://github.com/alexandravthompsonaa-ui/visual-alignment)

Gap localization in an image pair, combining classical CV (template / edge / gradient matching) with a CBAM-residual CNN and a learned fusion layer. Built to run on CPU within a latency budget, with an honest confidence output.

`>93% within 5px` (CNN + fusion) vs `38.4%` (classical only) · Python · PyTorch · FastAPI · Docker

---

## How I work

- **A guardrail, not a reminder.** If a failure can recur, the fix belongs in code that cannot forget — not in a checklist. The scope-confinement bug in the governance repo is the clearest example: the gateway writes the authorized scope into the arguments instead of trusting the caller to pass it.
- **State the gap.** Every README above has a "what is missing" section. Evaluation is the one I care most about: I have tests for correctness, not for whether the agent is *effective*.
- **Small and running beats large and planned.** One year, one developer, eight departments in production.

---

## Background

- BSc, Hunan Agricultural University (2021–2025) — not a CS degree; learned systems programming on demand
- Python: FastAPI, asyncio, PyTorch, OpenCV
- LLM engineering: ReAct loops, tool calling, RAG, prompt-injection defense
- Chinese (native), English (working — reading and writing comfortably, live discussion takes a moment)

**Contact:** 3243444839@qq.com
