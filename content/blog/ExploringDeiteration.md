---
title: "Deiteration Part 2: Exploring the Deiteration of Permutations"
description: In this post, we look at how the process of deiteration works for a simpler type of function, cyclic permutations. 
date: 2025-09-07
tags:
- Math
- sequences
- deiteration
---

We have this newly defined interesting operation on functions, deiteration[^1]. Time to explore it!

Before we begin exploring, we need to address some issues and annoyances we ignored in the last post. The first one to address: The reals are not only infinite, but uncountable. At the end of the last post, some functions R -> R were given, but these functions were <b>extremely</b> biased and arbitrary. They were all continuous, analytic, and mostly polynomial or rational functions. In summary, looking at a small arbitrary class of functions gives us almost no insight to the full picture. So, what do we do? We make the number of functions much smaller - finite, in fact! We will from now on restrict all functions to domains and ranges of the natural numbers 0 through n (where different ns are looked at individually). 

This restriction on the domain and range has an issue - it isn't closed, though it is quite close. Why? Well, it all comes from the pesky $+1$ in $f(f^{-1}(x)+1)$. Take, for instance, $x$ such that $f^{-1}(x) = n$. Now, we have $f(n+1)$, but $n+1$ is not in our domain! We can fix this by introducing modular arithmetic: all numbers will be taken mod $n+1$, so $f(n+1)$ now becomes $f(0)$, and 0 <i>is</i> in our domain. 

## Narrowing Our View Even Further

Finally, now, we can look at the structure of deiteration. Lets first look at how it behaves with four kinds of mappings (a mapping is a function except an input can have multiple outputs). Given in order of specificity: All Mappings, Functions, One-to-One Functions, and Cyclic Permutations[^2]. Remember, we are still restricting ourselves to this finite domain.

Image

Most non-one-to-one functions will actually stop being functions when deiterated - this is because when deiterating, we use the inverse of the function. But, only one-to-one functions are invertible.

Interestingly, any 

[^1]:
[^2]: A cyclic permutation is a function that, when repeatedly applied to some value, only comes back to that value after every other value has been reached. In other words, the graph (as in nodes + vertices) of the function would be a big loop, or "cycle". 