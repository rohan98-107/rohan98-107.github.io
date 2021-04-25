---
layout: post
title: Order Statistics and Record Values
katex: True
---

This will be my first technical post. Part of the reason I made this blog was to further explore any interesting relationships between my current thesis research and other topics in mathematical OR. One such concept that I felt made the cut was that of *Order Statistics*.

For a collection of random variables (RVs) $$(X_j)_{j=1}^n$$, the $n$th order statistic is defined as

$$X_{(1)} := \min(X_1, X_2, \hdots, X_n),$$
$$X_{(n)} := \max(X_1, X_2, \hdots, X_n).$$

In particular, $X_{(j)}$ is simply another RV that represents the $(n+1)-j$th greatest value. 
