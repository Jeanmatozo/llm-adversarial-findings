# llm-adversarial-findings

**Structured adversarial finding reports for LLM, RAG, and agent systems.**

Each finding follows a four-part format: realistic organizational scenario 
→ documented evidence → framework mapping → concrete mitigation recommendation.

This is not a collection of jailbreaks. Each finding is mapped to a governance 
failure — the control that doesn't exist, the risk register entry that should 
have caught it, the architectural decision that created the exposure.

**Lab environment:** All findings are produced using the 
[AI-security-training-lab](https://github.com/Jeanmatozo/AI-security-training-lab) 
— a Docker-based red team environment with SHA-256 signed evidence pipeline.

---

## Finding Index

| ID | Title | OWASP Category | Severity | Date |
|---|---|---|---|---|
| FINDING-001 | *(Week 3 — coming)* | LLM01 | High | — |
| FINDING-002 | *(Week 4 — coming)* | LLM06 | High | — |
| FINDING-003 | *(Week 5 — coming)* | LLM08 | High | — |
| FINDING-004 | *(Week 9 — coming)* | Guardrail Eval | High | — |

---

## Framework Alignment

**OWASP LLM Top 10 · MITRE ATLAS · NIST AI RMF · ISO/IEC 42001**

---

## Folder Structure

```bash
findings/
├── 001-direct-prompt-injection/
├── 002-rag-document-poisoning/
├── 003-agent-tool-abuse/
└── 004-guardrail-bypass/
```

---

*Each finding folder contains: scenario.md · evidence-log.md · 
owasp-mapping.md · mitigation.md*
