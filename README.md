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

| ID | Title | OWASP Category | Severity | Status |
|---|---|---|---|---|
| FINDING-001 | Direct Prompt Injection | LLM01 | Low | Completed |
| FINDING-002 | RAG Document Poisoning | LLM06 | — | In Progress |
| FINDING-003 | Agent Tool Abuse | LLM08 | — | Planned |
| FINDING-004 | Guardrail Bypass (Healthcare) | Guardrail Eval | — | Planned |

---

## 🧭 How to Read a Finding

Each finding is structured as:

1. **scenario.md**  
   Defines the system, architecture, and trust boundaries  

2. **evidence-log.md**  
   Contains real execution transcripts with SHA-256 integrity verification  

3. **owasp-mapping.md**  
   Classifies the finding (severity, exploitability, framework mapping)  

4. **governance-bridge.md**  
   Connects the finding to missing or incomplete risk register entries  

5. **mitigation.md**  
   Provides concrete, implementation-level remediation steps  

---

## 🔁 Cross-Repository Connection

This repository represents the **technical validation layer**.

Findings are mapped into governance artifacts in:

👉 ai-governance-risk-assessments

Flow:

```
Adversarial Testing → Evidence → OWASP Classification → Governance Gap → Remediation
```

---

## 🧩 Framework Alignment

- **OWASP LLM Top 10** — Vulnerability classification  
- **MITRE ATLAS** — Adversarial techniques and tactics  
- **NIST AI RMF** — Risk management and governance mapping  
- **ISO/IEC 42001** — AI management system controls  

---

## 📂 Folder Structure

```bash
findings/
├── 001-direct-prompt-injection/
│   ├── transcripts/
│   │   ├── 001-variant-a.txt
│   │   ├── 001-variant-b.txt
│   │   └── 001-variant-c.txt
│   ├── scenario.md
│   ├── evidence-log.md
│   ├── owasp-mapping.md
│   ├── governance-bridge.md
│   └── mitigation.md
│
├── 002-rag-document-poisoning/
│   ├── scenario.md
│   ├── evidence-log.md
│   ├── impact-analysis.md
│   ├── owasp-mapping.md
│   └── mitigation.md
│
├── 003-agent-tool-abuse/
└── 004-guardrail-bypass/
```

---

## 📌 Key Principle

AI systems do not fail only at the model level.

They fail at:
- trust boundaries  
- data flows  
- system architecture  
- missing governance controls  

This repository focuses on identifying **where systems actually break** — and translating that into decisions organizations can act on.
