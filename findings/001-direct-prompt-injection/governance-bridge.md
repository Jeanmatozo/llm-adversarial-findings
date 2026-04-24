# Governance Bridge — Finding 001: Direct Prompt Injection

---

## Purpose

This document connects the adversarial finding (direct prompt injection testing) to the governance layer defined in:

→ `ai-governance-risk-assessments/assessments/001-financial-llm/risk-register-v1.md`

The objective is to determine:

- Which **risk register entry should have captured this risk**
- Whether the risk was **explicitly defined or implicitly covered**
- What **governance gap exists** based on this test

---

## Finding Summary

- **Finding ID:** 001-direct-prompt-injection  
- **OWASP Category:** LLM01 — Prompt Injection  
- **Test Result:** All attack variants resisted (Pass)  
- **Residual Risk:** Low (for direct prompt injection only)  

The system demonstrated strong resistance to direct prompt injection attempts under controlled conditions.

---

## Expected Risk Coverage (Repo 1)

### Relevant Risk Category

This finding should map to the following governance risk category:

- **Integrity Risk** — model behavior can be manipulated by adversarial input  
- **Confidentiality Risk** — exposure of system prompt or restricted internal data  

---

## Risk Register Cross-Reference

### Closest Matching Entry (Expected)

If your `risk-register-v1.md` includes something similar, it should resemble:

> **Risk Name:** Prompt Injection / Instruction Override  
> **Description:** The LLM may follow adversarial user instructions that override system-level constraints, leading to unauthorized behavior or disclosure of sensitive information.

---

## Gap Assessment

### ❗ Case 1 — If this risk EXISTS in your register

If a prompt injection–type risk already exists:

✔ Governance alignment is present  
✔ Risk identification is correct  

However:

### Gap Still Exists

> The risk is identified, but **no validation mechanism (testing control)** is explicitly defined to confirm whether the control is effective.

---

### ❗ Case 2 — If this risk DOES NOT exist

Then this is a **missing governance entry**.

---

## Missing Risk Register Entry (Add This)

```markdown
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
