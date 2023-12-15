---
layout: post
title: Order Statistics and Record Values
katex: True
---

For my first technical post, I will discuss *Order Statistics*. Order Statistics are tied intimately to *Records* or *Record Values* [1] which are particularly useful in black-box optimization settings.

For a collection of random variables (RVs) $$(X_j)_{j=1}^n$$, the $$n$$th order statistic is defined as

$$X_{(1)} := \min(X_1, X_2, ..., X_n),$$
$$X_{(n)} := \max(X_1, X_2, ..., X_n).$$

In particular, $$X_{(j)}$$ is simply another RV that represents the $$(n+1-j)$$th greatest value.

Order Statistics can be used to describe measures of central tendency such as the median or range:

$$\text{Sample Median} =
\begin{cases}
X_{(j+1)} & n = 2j + 1 \\
(X_{(j)} + X_{(j+1)})/2 & n = 2j,
\end{cases} $$

$$\text{range} = X_{(n)} - X_{(1)}.$$

A collection of *records* $$(Y_{R(k)})_{k, R(k) \in \mathbb{N}}$$ is a strictly monotone decreasing sequence of RVs that represent *improvements* over the set of all values $$\{Y_k \mid k \leq R(k)\}.$$ By definition $$Y_{R(k)} \leq Y_k$$ for any $$k \leq R(k)$$ assuming we are interested in minimization. To gain a better intuition about this concept consider the following figure.

| ![alt text](/images/Records.png) |
|:--:|
| The black dots represent realized random variables i.e., $$Y_0 = 10, Y_1 = 7, Y_2 = 7, \cdots, Y_{10} = 1/2$$, the red dots represent **records**, which are strict improvements. Further, the subscript $R(k)$ is itself a random variable, denoting the index of original value that corresponds to the $$k$$-th record. So $$Y_4 = 5$$ but $$Y_{R(5)} = 1$$ and $$R(5) = 8.$$|

The above figure was taken from my master's thesis where I studied the distributional properties of the *record improvement value* for a specific type of parametrized random search method. 