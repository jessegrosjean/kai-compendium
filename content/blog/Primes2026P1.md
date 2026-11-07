---
title: "Primes USA 2026 Problem 1: Analysis"
description: 
date: 2025-11-28
tags:
  - Math
  - PrimesUSA
---

## The Problem
Determine all positive real p for which there exists cp ∈ R with the following property: for any continuously differentiable real-valued function f on [−1, 1] with f (1) > f (−1) and |f′(s)|≤1 for all s ∈(−1, 1), there exists s0 ∈(−1, 1) with f′(s0) > 0 such that:

                   |f(s)−f(s0)|≤cp|s−s0|^(1/p) for all s ∈(−1, 1).


## Sufficiency
It's easy to see that for any such s, s0 |f(s) - f(s0)| ≤ |s-s0|. We are given that for s in (-1, 1) |f'(s)| ≤ 1. Since the slope is locally always less than or equal to one, the average slope must also be less than or equal to one. More formally, applying the mean value theorem to any interval [a, b] subset [-1, 1] gives exists c s.t. f'(c) = (f(b)-f(a))/(b-a). Since |f'(c)| must be ≤ 1, we get that |(f(b)-f(a))/(b-a)| ≤ 1 -> |f(b)- f(a)| ≤ |b-a|. Letting s = b and s0 = a, this is precisely |f(s) - f(s0)| ≤ |s-s0|, which was our claim.

Because of this inequality, we know that if |s - s0| ≤cp|s−s0|^(1/p), then |f(s)−f(s0)|≤cp|s−s0|^(1/p). p is given to be greater than zero, and |s-s0| must be positive. If we assume s noteqaul s0, we may divide both sides by |s-s0|^(1/p), obtaining: 

|s-s0|^(p-1)/p ≤ cp.

Let's clean this up further: s and s0 are both contained within the interval (-1, 1) which has length 2, so |s-s0| < 2, and trivially 0 < |s-s0| (not ≤, for we assumed s notequal s0). Call |s-s0| "x", which we know must be in (0, 2).

Now, call (p-1)/p "m". 

Our question has reduced to: For what m does there exist a cp s.t. for all x in (0,2) x^m ≤ cp.

Important: this is not an if-or-only-if, merely an implies. The ps that work for this are guaranteed to work for the actual question, but not vice versa. We will deal with the other direction later, as well as the case where s=s0.

If m>=0, x^m is an increasing function for x>0. x^m d/dx = mx^(m-1). x>0, so x^(m-1) > 0, and m>=0, so m * x^(m-1) >= 0 -> x^m d/dx >= 0. 

Since x^m is increasing, sup(x^m) 0 < x < 2 = sup(x)^m 0 < x < 2 = 2^m. By definition of supremum, -> 2^m >= x^m for all x in (0,2). So if we set cp to equal 2^m, we have found a cp that works.

We have shown that if m>0, there does exist a cp s.t. for all x in (0,2) x^m <= cp. 
m>= 0 -> (p-1)/p >= 0. p is given to be >0, so (p-1)/p >= 0 -> p >= 1.

So, in total, we have shown that there does exists a cp that satisfies the conditions of the problem if p >=1. 

## Necessity
Now, assume p < 1. For our counterexample, we will use the function f(x) = x over the interval [-1, 1]. We will also pick an s notequalto s0.

Since f(s0) = s0 and f(s) = s, we once more have |s-s0| <= cp|s-s0|^1/p. Again we may divide by |s-s0|^1/p and get |s-s0|^(p-1)/p <= cp. Yet 0 < p < 1, so (p-1)/p < 0. This means that
|s-s0|^(p-1)/p = 1/|s-s0|^k, where k is a positive real number (more precisely, |(p-1)/p|). But s may be picked such that |s-s0| is arbitrarily close to 0, meaning 1/|s-s0|^k may be arbitrarily large. This implies that for the function f(x) = x and 0 < p < 1, there exists no cp such that |f(s)−f(s0)|≤cp|s−s0|^(1/p) for all s ∈(−1, 1). We have found a counterexample for p<1, so p must be greater than or equal to 1.

## Loose Ends
We still have two loose ends to tie up.

1: In the sufficiency proof, we have unjustifiably assumed that s does not equal s0, so we must prove that the statement still holds if this is the case. This is simple: if s = s0, f(s) = f(s0) -> |f(s) - f(s0)| = 0. |s-s0| is also 0, and 0^1/p for any positive real p is 0. cp * 0 is 0 for any cp, so the expression simplifies to 0 <= 0, which is true.

2: We have assumed that there always exists an s0 in (-1, 1) such that f'(s0) > 0. But this must be the case, since we are given that f(1) > f(-1). If f was a decreasing function on this interval, then f(a) <= f(b) for a>=b. Yet letting a = 1 and b = -1, we see that this implies f(1) <= f(-1). Contradiction.

## Conclusion
We have shown that for the statement to hold, p must be greater than or equal to 1, and we have also shown that the statement does hold if p is greater than or equal to 1. Having completed both sufficiency and necessity, we have finally proven that:

For positively valued real number p, for any continuously differentiable real-valued function f on [−1, 1] with f (1) > f (−1) and |f′(s)|≤1 for all s ∈(−1, 1), there exists s0 ∈(−1, 1) with f′(s0) > 0 such that:

                   |f(s)−f(s0)|≤cp|s−s0|^(1/p) for all s ∈(−1, 1).

iff p>=1. 