# Prompt Engineering — Cheat Sheet

**When to use what**
```
Simple task            → Zero-Shot
Need consistent format → Few-Shot
Structured doc output  → RTCOS
Reasoning matters      → Chain of Thought
Agent / tool use       → ReAct
Multi-step pipeline    → Prompt Chaining
Building a product     → System Prompt
Accuracy critical      → Self-Consistency
```

---

**Zero-Shot** — direct instruction, no examples. Start here always.
```
Classify this ticket as Bug / Feature Request / Configuration:
"Invoice dates show MM/DD but we're a UK company"
```

**Few-Shot** — show 2–4 examples, model learns the pattern.
```
Input: "can't upload PDF over 5MB"   → Output: Bug
Input: "add dark mode to dashboard"  → Output: Feature Request
Input: "how do I change currency?"   → Output: Configuration

Input: "wrong vendor name extracted" → Output:
```

**RTCOS** — structured prompt with 5 components. Best for consistent, professional outputs.
```
ROLE:    You are a BA with expertise in AI document processing
TASK:    Write a user story for invoice anomaly detection
CONTEXT: B2B SaaS · Finance Manager reviews 100 invoices/day
OUTPUT:  As a / I want / So that + 3 Given/When/Then ACs
STYLE:   Concise · plain English · for dev team backlog
```

**Chain of Thought** — ask model to reason before answering. Use when the logic matters as much as the output.
```
Which feature should we build first? Think step by step.
Consider: user impact, effort, business risk, strategic value.
```

**ReAct** — Reason → Act → Observe loop. The pattern behind agents.
```
THOUGHT: I need to check if this vendor exists in the approved list
ACTION:  Query vendor database for "Infosys BPM"
OBSERVE: Found — risk level: low, avg invoice: ₹1.2L
THOUGHT: Amount is 2× average — flag for review
ANSWER:  Invoice flagged as anomaly
```

**Prompt Chaining** — output of step 1 becomes input of step 2. How real pipelines work.
```
Step 1 → Extract fields from invoice text → JSON
Step 2 → Validate JSON (missing fields, date logic, amount mismatch)
Step 3 → Generate plain-English summary for Finance Manager
```

**System Prompt** — product-level model config. Set once, applies to all users.
```
You are an invoice review assistant for FinanceFlow.
Help Finance Managers review extracted invoice data.
Never fabricate invoice fields — say "not extracted" if missing.
If asked outside scope: "Please contact support for help with that."
Tone: professional, concise.
Context: {{user_role}} · {{company_name}}
```

**Self-Consistency** — run the same prompt N times, take majority answer. For high-stakes outputs.
```
Run 5×: "Is this invoice amount anomalous for this vendor?"
Result: YES · YES · NO · YES · YES  →  Majority = YES → flag it
```

---

**BA/PM quick reference**

| Task | Technique |
|------|-----------|
| User stories / ACs | RTCOS |
| Ticket classification | Few-Shot |
| Feature prioritisation | Chain of Thought |
| Entity extraction | Few-Shot |
| Agent behaviour spec | ReAct |
| AI output evaluation | Self-Consistency |
| PRD stakeholder summary | Zero-Shot |

---

← [README](./README.md)
