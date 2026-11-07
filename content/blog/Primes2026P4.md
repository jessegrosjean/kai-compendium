---
title: "Primes USA 2026 Problem 4: Probability"
description: 
date: 2025-10-19
tags:
  - Math
  - PrimesUSA
---

## The Problem
Let S be a circle in R2. Independently and uniformly at random, select b blue
points and r red points on S, where b, r ∈N and min{b, r}≥3. Let P denote the intersection of the convex
hull of the blue points with the convex hull of the red points. Let p be the number of vertices of P (set p = 0
if P is the empty set). Compute the expected value of p.

Let's unpack what this is saying:

1. We choose a number of red and blue points randomly on a circle. r means the number of red points, and b means the number of blue points.
2. We connect the red and blue points to themselves to create polygons inscribed in the circle
3. Finally, we take the region contained in both polygons, and call it P.

{insert diagram of these steps}

And the question is asking, what is the expected value of the number of vertices of P? (Given r and b)

## Reframing and Abstracting
The first thing to consider is what are these vertices? The only two ways to get a vertex from the intersection, P, of two polygons are:

1. From when a vertex of one polygon is contained within the other (including the boundary), resulting in this vertex also being a vertex of P.
2. From when edges of the polygons intersect, resulting in this intersection point becoming a vertex of P.

{diagram of possibilities}

Possibility one occurs with probability zero in this setup. Since both polygons are inscribed within the circle, the only way to have a vertex of one contained within the other is if this vertex is a common vertex. But we are picking a finite number of points from an infinite set - so with probability 1, the points are distinct. Since this event has probability zero and does not result in P having an infinite number of vertices, it does not effect the expected value.

So, the only way we have to worry about is through the intersection of edges. 

Notice how a n-gon inscribed in a circle partitions the circle into n+1 convex regions - n regions bounded by an arc of the circle and an edge of the polygon, and one center region which is the interior of the polygon. Let this polygon be the polygon formed by , w.l.o.g., the red points.

{diagram}

Now, consider the edges of the blue polygon. If both vertices (endpoints of the edge) are within the same region, then the entire edge is within this region, meaning it intersects with the red edges zero times. But if they are in different regions, the edge must intersect with the red polygon twice: once to go from one outer region to the center region, and then once more to go from the center region to the second outer region.

{diagram}

This means that the number of intersections is precisely twice the number of pairs of adjacent blue vertices with red vertices in between them. Yet also notice that this number of such pairs is exactly the number of "consecutive runs" of red vertices, in the string you would get by reading off the vertices as red or blue in order (and defining the first and last as adjacent). A consecutive run refers to entirely red substrings where extending the string in either direction would include a blue vertex. 

{diagram}

To find the average number of such substrings, we will determine the probability of having a string with n of these substrings and then use a weighted sum.

## New Question
Our new question is: 
Given a cyclic string made up of b "b"s and r "r"s, what is the probability of having n consecutive runs of "b"s? 

To make the counting easier, we will consider different rotations and reflections as distinct.

First, start with only "r"s. Consider the r spaces between these "r"s. Having n consecutive runs of "b"s is equivalent to having exactly n of these spaces contain at least one "b". The number of ways to choose these spaces is simply nCr(r, n).

Now we have the task of partitioning the "b"s into n distinct boxes. Using a standard stars-and-bars argument, the number of ways to do this is nCr(b, n).

Combining these ideas, we have that the number of ways to have n consecutive substrings is   nCr(r, n) * nCr(b,n). Yet this is false, since we made an assumption: we assumed that the circle was oriented such that the "top" was an "r". To account for this, we must realize that r/()
