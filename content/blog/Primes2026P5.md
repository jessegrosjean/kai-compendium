---
title: "Primes USA 2026 Problem 5: Number Theory"
description: 
date: 2025-11-28
tags:
  - Math
  - PrimesUSA
---

## The Problem

## Part a
To prove that every such sequence is finite, we will prove that the sequence is strictly increasing and then prove that the sequence never "skips over" a multiple of n.

gcd(a,b) is defined as always being a positive integer, so x_k + gcd(xk, n) > x_k -> x_(k+1) > x_k -> the sequence is strictly increasing. 

The second part is proving the sequence never "skips over" a multiple of n - as in, there does not exist an x_j and a k s.t. x_j < kn < x_j+1. For sake of contradiction, assume true. x_(j+1) = x_j + gcd(x_j, n) so x_j < kn < x_(j+1) -> 0 < kn - x_j < gcd(x_j, n). kn is divisible by gcd(x_j, n) since n is by definition divisible by gcd(x_j, n) and likewise x_j is divisible by gcd(x_j, n). So, kn - x_j must be divisible by gcd(x_j, n) -> kn - x_j = m*gcd(x_j, n) for some integer m. Dividing everything by gcd(x_j, n) we get that: 0 < m < 1, but m is an integer and there exist no integers between 0 and 1 noninclusive. Contradiction.

These two facts show that T(n, x0) must be finite because consider the first multiple of n that is greater than x0. Since we are dealing with integers, there must be a finite number of integers between x0 and the multiple of n. The sequence is strictly increasing, so every term must be greater than or equal to x0 and there can be no repeated values. Yet since the sequence must not "skip over" the multiple of n and terminates once it reaches it, no term may be greater than the multiple of n. This leaves a finite number of values to distinctly assign to the terms - by pigeonhole, the number of terms must be finite.

## Part b
To put bounds on T(n, x0) we will realize that when the sequence gains a common factor with n we can reduce the sequence by this factor. 

If both n and some x_k are divisible by some "a" then gcd(n, x_k) must also be divisible by this "s" and so "s" must be a factor of x_k + gcd(n, x_k) = x_(k+1). By induction, this implies that all terms after x_k must also be divisible by "s". 

Let's reduce everything and divide all these terms by "s", getting a new sequence which will be called A, with terms a_i. Our recursive equation for this new sequence is now x_j/s + gcd(n, x_k)/s = x_(j+1)/s. x_j/s and x_(j+1)/s are a_(j-k) and a_(j-k+1) respectively. gcd(n, x_j)/s is equal to gcd(n/s, x_j/s) = gcd(n/s, a_j-k). So, we have: a_i + gcd(n/s, a_i) = a_(i+1) - exactly the same recurrence relation for X(n, x_0) except n -> n/s and x_0 -> a_0 = x_k/s. So, this new sequence is X(n/s, x_k/s), and T() of this sequence = T(n/s, x_k/s). But T(n, x_0) is simply the number of terms before reaching x_k, k, plus the length of the rest of the sequence before reaching n, which is T(n/s, x_k/s). 

So, T(n, x_0) = T(n/s, x_k/s) + k for all k in N with any s s.t. s | x_k and s | n. 

This is so helpful because for each (not necessarily distinct) prime factor p of n, we can apply this fact by using this prime factor as "s" and picking x_k to be the first term s.t. p | x_k. 

The maximum k can be is p-1 - 