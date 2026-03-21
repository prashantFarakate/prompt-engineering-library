# 🧠 Prompt Engineering Library
### A practitioner's reference for AI Product Managers & Business Analysts

> Built by a BA working on GenAI products — this repo documents the prompt engineering techniques I use daily to improve LLM outputs, design better AI features, and communicate expectations to engineering teams.

---

## 📌 Why This Repo Exists

When you work on AI-enabled products, prompt engineering isn't just a developer skill — it's a **product thinking skill**. As a BA/PM, understanding *how* to instruct an LLM helps you:

- Write better **acceptance criteria** for AI features
- Identify **failure modes** before they reach production
- Collaborate effectively with ML engineers
- Evaluate whether an AI output is "good enough" for your users

This library covers the **core prompt engineering techniques** with real examples, structured templates, and notes on when (and when *not*) to use each one.

---

## 🗂️ Techniques Covered

| # | Technique | Best For | File |
|---|-----------|----------|------|
| 1 | **Role + Task + Context + Output + Style (RTCOS)** | Structured, professional outputs | [→ Read](./techniques/01-rtcos.md) |
| 2 | **ReAct (Reason + Act)** | Agentic tasks, tool use, step-by-step decisions | [→ Read](./techniques/02-react.md) |
| 3 | **Few-Shot Prompting** | Consistent formatting, classification tasks | [→ Read](./techniques/03-few-shot.md) |
| 4 | **Chain of Thought (CoT)** | Complex reasoning, analysis, debugging | [→ Read](./techniques/04-chain-of-thought.md) |
| 5 | **Zero-Shot Prompting** | Quick tasks, general instructions | [→ Read](./techniques/05-zero-shot.md) |
| 6 | **Prompt Chaining** | Multi-step workflows, document pipelines | [→ Read](./techniques/06-prompt-chaining.md) |
| 7 | **System Prompt Design** | Product-level LLM configuration | [→ Read](./techniques/07-system-prompts.md) |
| 8 | **Self-Consistency** | High-stakes decisions, reducing hallucination | [→ Read](./techniques/08-self-consistency.md) |

---

## 🗃️ BA/PM Template Library

Ready-to-use prompts for real product work:

| Template | Use Case |
|----------|----------|
| [User Story Generator](./templates/user-story-generator.md) | Generate stories from a feature brief |
| [Acceptance Criteria Writer](./templates/acceptance-criteria.md) | Write Given/When/Then criteria for AI features |
| [PRD Section Drafter](./templates/prd-drafter.md) | Draft sections of a Product Requirements Doc |
| [AI Feature Evaluator](./templates/ai-feature-evaluator.md) | Evaluate LLM output quality |
| [Stakeholder Summary](./templates/stakeholder-summary.md) | Summarise technical docs for non-technical stakeholders |

---

## 🧩 How Techniques Relate

```
Simple Task
    └── Zero-Shot ──────────────────────────────► Fast, no examples needed
    
Consistent Format Needed
    └── Few-Shot ────────────────────────────────► Show 2-3 examples

Complex Reasoning
    └── Chain of Thought ────────────────────────► Ask model to think step-by-step

Structured Professional Output
    └── RTCOS ───────────────────────────────────► Role + Task + Context + Output + Style

Agentic / Tool-Use Task
    └── ReAct ───────────────────────────────────► Reason → Act → Observe loop

Multi-Step Workflow
    └── Prompt Chaining ─────────────────────────► Output of step 1 → Input of step 2

High-Stakes / Accuracy Critical
    └── Self-Consistency ────────────────────────► Run N times, take majority answer

Product-Level LLM Setup
    └── System Prompt Design ────────────────────► Persona, boundaries, tone at model level
```

---

## 📐 My Evaluation Framework

When testing a prompt in production, I assess across 5 dimensions:

| Dimension | Question |
|-----------|----------|
| **Accuracy** | Is the output factually correct? |
| **Completeness** | Did it cover everything the user needed? |
| **Format** | Is the structure usable (JSON, markdown, bullets)? |
| **Tone** | Does it match the product's voice? |
| **Robustness** | Does it still work with unusual or edge-case inputs? |

---

## 🔖 Quick Reference — Technique Cheat Sheet

```
RTCOS     →  Role / Task / Context / Output / Style
ReAct     →  Reason + Act (loop until done)
Few-Shot  →  Example 1, Example 2 → Now do this
CoT       →  "Let's think step by step..."
Zero-Shot →  Direct instruction, no examples
Chaining  →  Prompt A output → Prompt B input
Self-Con  →  Ask 3x, pick most common answer
```

---

## 🧪 Examples From Real BA/PM Work

- [Extracting entities from invoice text](./examples/entity-extraction.md)
- [Classifying user feedback by theme](./examples/feedback-classification.md)
- [Generating test cases from acceptance criteria](./examples/test-case-generation.md)
- [Summarising a PRD for a sprint kickoff](./examples/prd-summary.md)

---

## 📚 References & Further Reading

- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [Anthropic Prompt Engineering Docs](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [DAIR.AI Prompt Engineering Guide](https://www.promptingguide.ai/)
- [Chain-of-Thought Prompting Paper (Wei et al., 2022)](https://arxiv.org/abs/2201.11903)
- [ReAct Paper (Yao et al., 2022)](https://arxiv.org/abs/2210.03629)

---

## 👤 About

Maintained by **Prashant Farakate** — Business Analyst with 5+ years in GenAI/ERP products.  
Currently transitioning to AI Product Management.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/prashant-farakate-91a162191/)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?logo=github)](https://github.com/prashantFarakate)

---

*Last updated: March 2026 | Contributions and suggestions welcome via Issues*
