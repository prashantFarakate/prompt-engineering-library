# Prompt Engineering Library
### A core prompt engineering techniques

Personal reference I maintain while working on AI products. Notes on techniques, patterns, and things I've learned from actually using these in LLM-based systems.
Just what I know, what I've tried, and what worked.


## Techniques  
**Techniques**
— [RTCOS](./techniques/01-rtcos.md) · Role + Task + Context + Output + Style — my default for structured outputs
— [ReAct](./techniques/02-react.md) · Reason → Act → Observe — mental model behind agents
— [Few-Shot](./techniques/03-few-shot.md) · Show examples before the task — go-to for classification and extraction
— [Chain of Thought](./techniques/04-chain-of-thought.md) · Ask the model to think step by step — when reasoning needs to be auditable
— [Zero-Shot](./techniques/05-zero-shot.md) · Direct instruction, no examples — always start here
— [Prompt Chaining](./techniques/06-prompt-chaining.md) · Output of step 1 → input of step 2 — how real pipelines work
— [System Prompts](./techniques/07-system-prompts.md) · Product-level model config — the BA/PM's job in an AI product
— [Self-Consistency](./techniques/08-self-consistency.md) · Run N times, take majority — for anything high-stakes

** Prompt engineering techniques - When to use what**
```
Simple task                      → Zero-Shot         → Direct instruction, no examples  
consistent format needed         → Few-Shot          → Example 1, Example 2 → Now do this
Structured Professional Output   → RTCOS             → Role + Task + Context + Output + Style
Complex Reasoning                → Chain of Thought  → Ask model to think step-by-step
Agent / tool use                 → ReAct             → Reason + Act (loop until done)
Multi-step workflow              → Prompt Chaining   → Output of step 1 → Input of step 2
Product-Level LLM Setup          → System Prompt     → Persona, boundaries, tone at model level
High-Stakes / Accuracy Critical  → Self-Consistency  → Run N times, pick majority answer
```

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

Maintained by **Prashant Farakate** — Business Analyst with 5 years in GenAI/ERP products.  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/prashant-farakate-91a162191/)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?logo=github)](https://github.com/prashantFarakate)

---
Contributions and suggestions welcome via Issues*
