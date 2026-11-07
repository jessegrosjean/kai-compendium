---
title: "The Interesting Dynamics of (x+y)/(x-y)"
description: A brief exploration of an interesting sequence.
date: 2025-04-06
tags:
  - Dynamical Systems
  - Math
---

## Introduction
My research on "deiteration," which is explained in this(link) series, led me on many tangents. One of these tangents was the exploration of recursive formulas that depended on the two previous terms, not just one. An example of this is the well known Fibonacci sequence $x_{n} = x_{n-2} + x_{n-1}$, where $x_{n-2}$ is two terms ago, and $x_{n-1}$ is the previous term. $x_n$ is the current, new term. 

When randomly putting formulas like these into Desmos to see their behavior, I ran into a very interesting formula $(x_{n-2} + x_{n-1})/(x_{n-2} - x_{n-1})$. For ease of notation, from now on $x$ will refer to two terms ago ($x_{n-2}$), and $y$ will refer to one term ago ($x_{n-1}$).

The most obvious interesting aspect of $(x+y)/(x-y)$ iterated is the "semi-chaoticness" of it. 