---
layout: post
title: Finding An Identity for 1 Hiding in Square Root 
collection: math
---
<!-- DEPRECATED BECAUSE YOU DID THE ANALYSIS WRONG, MISSED DIVIDE BY 0 -->
I love math. BC Calculus was my favorite high school memory, that and making 7 threes in a varsity basketball game to give my team a chance to win a game we had no business winning. While solving some math-related LeetCode questions, I stumbled upon one [asking us to implement](1) $\sqrt(x)$. Naturally, my first instinct as a trained physicist was to go to the MacLaurin series for the function, with the idea being that I would calculate the function to sufficient depth using this means. However, instead I found something unexpected.

The MacLaurin series for a function $f(x)$ is given by,

$$
f(x) = \sum_{n=0}^{\infty}\frac{f^{n}(0)}
$$

<!-- REFERENCES -->
[1]: https://leetcode.com/problems/sqrtx/