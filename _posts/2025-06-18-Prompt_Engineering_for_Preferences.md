---
layout: post
title: Psychology-Informed Prompting
katex: true
---
When I started thinking about using LLMs as proxies for human behavior, I quickly realized that the quality of my experimental data would live or die by one thing: **how I ask the questions**. Traditional psychology experiments control for environmental variables, participant selection, and task design. In computational behavioral science, your "environment" is the prompt, your "participants" are LLM instances, and your "task design" becomes the infantile art of prompt engineering.

But here's the thing: most prompt engineering advice is written for people trying to get ChatGPT to write better emails or summarize documents. Nobody talks about prompt engineering for _scientific discovery_. How do you systematically elicit cognitive biases from an artificial system? How do you design prompts that reveal the mathematical structure of decision-making?

That's what this post is about.

## The Psychology Behind the Prompts

Before deciding how I wanted to perturb my prompts throughout the experiment, I needed to understand how exactly to measure preference. So I needed to do a little bit of homework on psychology. Turns out, decades of research have identified systematic ways that context influences decision-making.

**Framing Effects** (Tversky & Kahneman, 1981 [1]) show that identical choices presented differently yield different decisions. The classic example: describing a medical treatment as "90% survival rate" vs "10% mortality rate" changes patient choices, even though the information is mathematically identical. This told me I needed systematic prompt variations that change _how_ I present the choices, not _what_ choices are available.

**Context-Dependent Preferences** (Bettman et al., 1998 [2]) demonstrate that the same person will weight attributes differently depending on the decision context. Someone choosing a car for "daily commuting" vs "weekend adventure trips" will prioritize completely different features. This gave me the idea for context-based framings: e.g., a laptop for "creative work" vs "business meetings" vs "travel" should elicit different preference patterns if LLMs truly mirror human cognition.

**Social Identity Effects** (Berger & Heath, 2007 [3]) show that choices often signal identity and social belonging. People don't just buy products; they buy representations of who they want to be seen as. This motivated my emotional framings around "professional image" and "earning respect from colleagues."

But the most crucial insight came from **Prospect Theory** (Kahneman & Tversky, 1979 [4]). Humans don't evaluate choices in isolation - they evaluate them relative to reference points that can be manipulated. This is why I included constraint-based framings: "budget is no object" vs "tight budget" should shift the entire preference landscape by changing the reference point.

## Neuroscience of Preference Construction

Here's where it gets really interesting. Recent neuroscience research (Izuma et al., 2010 [5]; Voigt et al., 2022 [6]) shows that preferences aren't stable neural representations we retrieve from memory. Instead, they're _constructed on the fly_ during the decision process itself.

This was a revelation for my experimental design. If human preferences are dynamically constructed rather than retrieved, then LLMs (which also construct responses dynamically based on context) might be surprisingly good proxies for studying preference formation. The key is designing prompts that trigger this construction process in systematic ways.

The neuroscience also explains why I organized framings into distinct categories. Different brain networks handle different types of decision factors:

- **Value-based decisions** primarily engage the ventromedial prefrontal cortex (vmPFC)
- **Social considerations** activate the medial prefrontal cortex and temporoparietal junction
- **Temporal planning** engages the dorsolateral prefrontal cortex
- **Constraint processing** involves the anterior cingulate cortex

By systematically varying prompt framings across these cognitive dimensions, I'm essentially probing different "neural circuits" in whatever distributed computation the LLM uses for decision-making.

## State-of-the-Art Prompt Engineering Meets Experimental Psychology

Current prompt engineering best practices (White et al., 2023 [7]; Zhou et al., 2023 [8]) emphasize techniques like chain-of-thought reasoning, few-shot learning, and systematic prompt structure. But most of this work focuses on _accuracy_ and _consistency_ - getting the model to produce reliably correct outputs.

For preference research, I need something different: **controlled variability**. I want the LLM to give different answers to systematically different prompts, and I need those differences to be interpretable and measurable.

This led me to design what I call "**Systematic Cognitive Probing**" - a prompt engineering approach specifically for behavioral research:

### Template Structure for Preference Elicitation

```
[ROLE] You are [specific decision-maker persona]
[CONTEXT] [Systematic framing variation - this is where the magic happens]
[TASK] [Identical choice task across all conditions]
[CONSTRAINTS] [Force explicit preference revelation]
[FORMAT] [Structured output for quantitative analysis]
```

The magic is in the `[CONTEXT]` section. While traditional prompt engineering tries to eliminate context effects as "noise," I'm systematically _manipulating_ context to study how it changes decision patterns.

### Laptop Choice 

Given the six categorical ways to influence decision-making, I wanted to keep the actual choice relatively discrete so as not to introduce too much noise in the result itself. I will have the LLM choose between a fixed number of laptops and measure how its preference changes over time. More concretely: 

|Framing Category|Laptop Examples|
|---|---|
|**Value-Based**|"best value for money" vs "maximize performance per dollar"|
|**Context-Based**|"laptop for creative work" vs "laptop for business presentations"|
|**Emotional**|"reflects your professional image" vs "earns respect from colleagues"|
|**Constraint-Based**|"unlimited budget" vs "tight budget constraints"|
|**Comparative**|"stand out from everyone else" vs "similar to successful people"|
|**Temporal**|"needs for next 3 years" vs "immediate purchase decision"|

## The Mathematical Payoff

Now let's talk math. Each category should produce **mathematically distinct preference trajectories** through the 6-dimensional attribute space (price, performance, battery, portability, build quality, brand prestige).

If LLMs truly learned human-like cognitive patterns, I should see:

- Constraint framings creating **discontinuous jumps** in preference vectors
- Emotional framings **rotating** the preference space toward social attributes
- Temporal framings creating **systematic drift** toward durability factors
- Context framings producing **clustered preference regions**

This adds an entirely new dimension to prompt engineering that I am super excited to learn and share with you all! 
## References

[1] Tversky, A., & Kahneman, D. (1981). The framing of decisions and the psychology of choice. Science, 211(4481), 453-458.

[2] Bettman, J. R., Luce, M. F., & Payne, J. W. (1998). Constructive consumer choice processes. Journal of Consumer Research, 25(3), 187-217.

[3] Berger, J., & Heath, C. (2007). Where consumers diverge from others: Identity signaling and product domains. Journal of Consumer Research, 34(2), 121-134.

[4] Kahneman, D., & Tversky, A. (1979). Prospect theory: An analysis of decision under risk. Econometrica, 47(2), 263-292.

[5] Izuma, K., Matsumoto, M., Murayama, K., Samejima, K., Sadato, N., & Matsumoto, K. (2010). Neural correlates of cognitive dissonance and choice-induced preference change. Proceedings of the National Academy of Sciences, 107(51), 22014-22019.

[6] Voigt, K., Murawski, C., Speer, S., & Bode, S. (2022). Where do our preferences come from? How hard decisions shape our preferences. Frontiers in Behavioral Neuroscience, 16, 956307.

[7] White, J., Fu, Q., Hays, S., Sandborn, M., Olea, C., Gilbert, H., ... & Schmidt, D. C. (2023). A prompt pattern catalog to enhance prompt engineering with ChatGPT. arXiv preprint arXiv:2302.11382.

[8] Zhou, Y., Muresanu, A. I., Han, Z., Paster, K., Pitis, S., Chan, H., & Ba, J. (2023). Large language models are human-level prompt engineers. arXiv preprint arXiv:2211.01910.