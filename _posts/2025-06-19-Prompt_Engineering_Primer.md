---
layout: post
title: A Primer on Prompt Engineering
katex: true
---
Prompt engineering is the difference between getting useful data from LLMs and getting garbage. Since I'm using LLMs as proxies for mathematically modeling preferences, I needed to study some of the current state-of-the-art prompting techniques.

## The Basic Structure

Good research prompts follow a consistent template:

```
[ROLE] You are [specific persona]
[CONTEXT] [The decision scenario]
[TASK] [What you want them to do]
[CONSTRAINTS] [How to format the response]
[FORMAT] [Expected output structure]
```

This structure works because LLMs perform better with clear role definition, explicit context, and structured output requirements.

## Key Techniques I'm Using

**Scenario-Based Prompting:** Instead of abstract questions, embed decisions in realistic situations. "You're at Best Buy comparing laptops" feels more natural than "Evaluate these laptop options."

**Dual-System Elicitation:** Ask for both analytical reasoning AND gut reactions. Questions like "What factors mattered most?" (System 2) and "Was there anything that just felt right?" (System 1) extract different types of cognitive processing.

**Chain-of-Thought Reasoning:** Based on Wei et al. [1], explicitly asking models to "think through this decision" before answering improves response quality and makes reasoning more extractable.

**Few-Shot Prompting:** Though I'm not using it at all yet, Brown et al. [2] showed that providing 2-3 examples of desired response format significantly improves output consistency.

**Consistent Output Format:** Always request the same rating structure so you can extract quantitative data.

**Role Consistency:** Keep the persona constant across experimental conditions. Only vary the decision context, not the fundamental role or capabilities of the responder.

## What Doesn't Work

**Abstract Instructions:** "Choose rationally" or "Be objective" don't actually change LLM behavior much.

**Too Many Constraints:** Overloading prompts with instructions reduces response quality. Pick 3-4 key requirements max.

**Inconsistent Framing:** If you change both the scenario AND the response format between trials, you can't isolate what's driving preference changes.

**Zero-Shot vs Few-Shot Trade-offs:** Zhou et al. [3] found that while few-shot examples improve consistency, they can also bias responses toward the example patterns, which is problematic for preference research where you want authentic variation.

## Research Applications

For preference modeling, prompts need to elicit both explicit preferences (rating scales) and implicit preference markers (aesthetic language, confidence indicators, emotional responses). The challenge is making this feel natural rather than like filling out a survey.

The goal isn't just getting LLMs to follow instructions - it's getting them to exhibit human-like cognitive patterns that you can study mathematically.

**Useful Resources:**

- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [Anthropic Prompting Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)

## References

[1] Wei, J., Wang, X., Schuurmans, D., Bosma, M., Xia, F., Chi, E., ... & Zhou, D. (2022). Chain-of-thought prompting elicits reasoning in large language models. Advances in Neural Information Processing Systems, 35, 24824-24837.

[2] Brown, T., Mann, B., Ryder, N., Subbiah, M., Kaplan, J. D., Dhariwal, P., ... & Amodei, D. (2020). Language models are few-shot learners. Advances in Neural Information Processing Systems, 33, 1877-1901.

[3] Zhou, Y., Muresanu, A. I., Han, Z., Paster, K., Pitis, S., Chan, H., & Ba, J. (2022). Large language models are human-level prompt engineers. arXiv preprint arXiv:2211.01910.