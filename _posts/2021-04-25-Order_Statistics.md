---
layout: post
title: Order Statistics and Record Values
katex: True
---

This will be my first technical post. Part of the reason I made this blog was to further explore any interesting relationships between my current thesis research and other topics in mathematical OR. One such concept that I felt made the cut was that of *Order Statistics*.

For a collection of random variables (RVs) $$(X_j)_{j=1}^n$$, the $$n$$th order statistic is defined as

$$X_{(1)} := \min(X_1, X_2, ..., X_n),$$

$$X_{(n)} := \max(X_1, X_2, ..., X_n).$$

In particular, $$X_{(j)}$$ is simply another RV that represents the $$(n+1-j)$$th greatest value.

So why do order statistics matter? For starters, we can use them to formalize measures of central tendency like the median and range. In particular,

$$\text{Sample Median} = \begin{cases}
X_{(j+1)} & n = 2j + 1 \\
\frac{X_{(j)} + X_{(j+1)}}{2} & n = 2j
\end{cases}$$

$$\text{range} = X_{(n)} = X_{(1)}$$

these definitions allow the robust use of these measures for scaling operations.
