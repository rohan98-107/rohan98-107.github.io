
---

layout: post

title: Data Collection Complete! 

katex: True

---

The data collection phase is complete. After navigating API rate limits, extraction debugging, and the inevitable "why is chosen_laptop always null?" moments, we've successfully gathered preference trajectories from 19 LLM "people" across 18 different contextual framings. Now we want to make sense of our data.

## What We Have: 342 Preference Snapshots

Each of our 19 artificial people responded to 18 carefully designed scenarios - from "choose the best value laptop" to "pick what your future self will thank you for." Every response gives us a 6-dimensional preference vector covering price, performance, battery life, portability, build quality, and brand prestige. More importantly, we have their reasoning, their confidence levels, and the subtle linguistic markers that reveal "vibe" influences beyond pure rational analysis.

## The Classical Analysis: Understanding Preference Geometry

My plan is to try out different models of varying mathematical sophistication for how the LLMs' preferences evolve. But before diving into quantum models or advanced PDEs, we're starting with fundamental exploratory data anysis. One such key question is: which types of prompts create the most dramatic preference shifts? 

We'll be plotting actual preference trajectories - watching how our artificial decision-makers move through 6-dimensional preference space as we transition from budget-conscious framings to prestige-focused ones, from work contexts to creative scenarios. Each person's path through this space tells a story about how contextual cues reshape what we value.

## Ising Models: The Physics of Preference Interactions

Here's where I reveal my hidden interest: quantum computing. We're treating preference dimensions as interacting variables in an Ising-like system (Ising, 1925 [3]). When someone cares more about performance, how does that systematically affect their brand sensitivity? Are there coupling strengths between different preference dimensions that reveal the hidden structure of how we make choices?

The Ising model framework lets us extract these coupling coefficients directly from our trajectory data. Originally developed for magnetic systems, Ising models have found applications across social sciences, from opinion dynamics to collective behavior (Castellano et al., 2009 [4]). We're not building a predictive model - we're using a fundamentally chaotic system as a surrogate for a fundamentally chaotic process. 

## Individual Differences: Vibe Coefficients as Cognitive Signatures

Remember those random vibe coefficients we assigned each person - their susceptibility to aesthetic influences, familiarity bias, and processing fluency? Now we get to test whether these actually predict trajectory behavior. Do people with high aesthetic coefficients show more curved preference paths? Do familiarity-biased individuals gravitate toward certain regions of preference space?

This analysis bridges individual differences psychology with dynamical systems theory. Each person's vibe profile becomes a mathematical signature that potentially explains their unique patterns of preference formation. In later development we plan to use the language of entanglement and superposition to come up with a more robust way to encode "vibes". 

## Validating Psychological Phenomena

One of the most exciting aspects of this analysis is testing whether our LLM preference system reproduces known cognitive biases. Do we see loss aversion when comparing budget-constrained versus unlimited-budget framings? Are there anchoring effects where early framings bias subsequent preferences? Can we detect context-dependent preference shifts that mirror human behavioral economics findings?

If LLMs truly serve as valid proxies for human preference formation, we should see these patterns emerge naturally from our mathematical analysis.

## An Aside: Dynamic Field Theory

Before we settled on the Ising Approach, we were broadly looking at ways to use continuous mathematics to model cognitive processes. Dynamic Field Theory, developed by Gregor Schöner and others (Schöner et al., 2016 [1]), uses partial differential equations to model how neural activation patterns evolve over time. Their framework treats cognition as continuous fields that develop peaks, valleys, and stable patterns through neurally plausible dynamics.

DFT has successfully modeled spatial working memory, visual attention, and developmental changes in infant cognition (Spencer et al., 2007 [2]). The mathematical formulation - essentially reaction-diffusion equations with competitive dynamics - creates remarkably human-like behavioral patterns from simple continuous principles.

What makes our approach different is the focus on preference formation rather than spatial cognition, and the integration of individual difference parameters (our vibe coefficients) into the dynamics. We're also exploring whether discrete spin-like interactions (Ising models) capture preference coupling better than continuous field dynamics. Both approaches treat human cognition as following mathematical laws rather than pure symbolic computation, but they make different assumptions about the underlying geometric structure.