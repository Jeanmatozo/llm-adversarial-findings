# Governance Bridge — Finding 001: Direct Prompt Injection

---

## Purpose

This document connects the adversarial finding (direct prompt injection testing) to the governance layer defined in:

→ ai-governance-risk-assessments/assessments/001-financial-llm/risk-register-v1.md

The objective is to determine:

- Which risk register entry should have captured this risk  
- Whether the risk was explicitly defined or implicitly covered  
- What governance gap exists based on this test  

---

## Finding Summary

- Finding ID: 001-direct-prompt-injection  
- OWASP Category: LLM01 — Prompt Injection  
- Test Result: All attack variants resisted (Pass)  
- Residual Risk: Low (for direct prompt injection only)  

The system demonstrated strong resistance to direct prompt injection attempts under controlled conditions.

---

## Expected Risk Coverage (Repo 1)

### Relevant Risk Categories

This finding should map to:

- Integrity Risk — model behavior manipulated by adversarial input  
- Confidentiality Risk — potential exposure of system prompt or restricted data  

---

## Risk Register Cross-Reference

### Closest Matching Entry (Expected)

If your risk register includes a similar entry, it should resemble:

Risk Name: Prompt Injection / Instruction Override  

Description:  
The LLM may follow adversarial user instructions that override system-level constraints, leading to unauthorized behavior or disclosure of sensitive information.

---

## Gap Assessment

### Case 1 — If this risk EXISTS in the register

If a prompt injection–type risk already exists:

- Governance alignment is present  
- Risk identification is correct  

However, a gap still exists:

The risk is identified, but no validation mechanism (testing control) is explicitly defined to confirm whether the control is effective.

---

### Case 2 — If this risk DOES NOT exist

Then this represents a missing governance entry.

---

## Missing Risk Register Entry (Add This)

Risk Name: Prompt Injection / Instruction Override  

Description:  
The AI system may be manipulated through adversarial user input (prompt injection) to override system instructions, bypass policy constraints, or disclose sensitive information such as system prompts or internal data.

Likelihood: 3  
Impact: 4  
Inherent Risk Score: 12  

Risk Owner: AI Governance / Security Team  

Current Controls:
- System prompt defining behavioral constraints  
- Model-level safety alignment  

Control Gaps:
- No documented adversarial testing for prompt injection  
- No continuous monitoring of prompt injection attempts  
- No incident response defined for successful injection  

Recommended Controls:
- Implement structured prompt injection testing (red teaming)  
- Maintain test cases for regression validation  
- Log and monitor suspicious prompt patterns  
- Define escalation workflow for injection attempts  

---

## Key Governance Insight

A risk is not fully governed unless it is both documented and tested.

In this case:

- The system is technically resilient  
- Governance maturity depends on whether that resilience is:
  - validated regularly  
  - monitored in production  
  - tied to incident response  

---

## Control Gap (Governance Level)

### Gap Title

Lack of Formalized Adversarial Testing as a Governance Control

### Gap Description

While the system resisted prompt injection in this test, there is no evidence that:

- prompt injection testing is part of a repeatable process  
- results are tracked over time  
- regressions would be detected after system changes  

This creates a governance risk where future vulnerabilities may be introduced without detection.

---

## Bridge to NIST AI RMF

This gap maps to:

- MANAGE 1.1 — AI risks are not continuously monitored and validated  
- MANAGE 2.3 — No defined response process for adversarial AI incidents  

---

## Why This Matters

This cross-reference connects:

- technical testing (repo2)  
to  
- governance decision-making (repo1)  

It demonstrates:

- risk identification  
- validation of controls  
- identification of governance gaps  
- translation into actionable improvements  

---

## Conclusion

The prompt injection risk should exist within the governance risk register.

If it does not, it represents a missing risk entry.

If it does, the remaining gap is:

lack of formalized, repeatable adversarial testing and monitoring as a control

This ensures risks are not only documented, but empirically validated and continuously managed.
