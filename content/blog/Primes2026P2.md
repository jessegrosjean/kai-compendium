---
title: "Primes USA 2026 Problem 2: Abstract Algebra"
description: 
date: 2025-11-29
tags:
  - Math
  - PrimesUSA
---

## The Problem

## Some Computations
For ease of notation, detonate some element g in G as (x, y, z) corresponding to the matrix (1 x z, 0 1 y, 0 0 1). Lets compute (x, y, z) * (a, b, c) for arbitrary x,y,z,a,b,c in Fp. We do this by converting the elements into their matrices and then multiplying. We get:

(1) (a+x) (c+xb+z)
(0)  (1)   (b+y)
(0)  (0)    (1)

which corresponds to (a+x, b+y, c+xb+z). So, (x, y, z) * (a, b, c) = (a+x, b+y, c+xb+z)

Now we can easily compute what an inverse should be. The identity corresponds to the identity matrix which corresponds to (0, 0, 0). This implies that for element A = (x, y, z) and A^-1 = (a, b, c)

(a+x, b+y, c+xb+z) = (0,0,0)

-> a = -x  b = -y  c = -z-x(-y) = xy-z

So A^-1 = (-x, -y, xy-z)

## Part a
A commutator of a group is the subgroup consisting of all elements [g, h] = g^-1h^-1gh. Let g = (x, y, z) and h = (a, b, c). So we have:

g = (x, y, z)
h = (a, b, c)
g^-1 = (-x. -y, xy-z)
h^-1 = (-a, -b, ab-c)

gh = (a+x, b+y, c+xb+z) so h^-1gh = (-a+a+x, -b+b+y, c+xb+z-a(b+y)+ab-c) = (x, y, xb+z-ay)

And g^-1(h^-1gh) = (-x+x, -y+y, xb+z-ay - xy + xy - z) = (0, 0, xb-ay).

Given any number n in Fp, one can choose a, b, x, y s.t. xb-ay = n. So, the commutator is merely the subgroup with elements in the form (0, 0, n) where n is any number in Fp. 

A center of a group is the commutative subgroup of all elements that commute with every other element. This implies that for any c in center C, cg = gc for all g in G.

Call g = (x, y, z) and c = (i, j, k).

Now, gc = (x+i, y+j, z+xj+k) and cg = (i+x, j+y, k+iy+z). Trivially x+i = i+x and y+j = j+y. But, z+xj+k must equal z+iy+k for all (x, y, z). This simplifies to xj-yi = 0 for all (x, y) in FpxFp. This is equivalent to saying that (i, j) is linearly dependent to all vectors (x, y) which is true iff (i, j) = (0,0). So, the center of G is precisely the elements in the form (0, 0, n) for n in Fp - exactly the same set of elements as the commutator. 

## Part b
Conjecture: The subgroups defined by 

We will know if we have found all maximal subgroups if we prove that:

1. The subgroups we have cover the entire group - as in, every element is in at least one of these subgroups
2. The subgroups are actually subgroups
3. The subgroups are maximal - if we add any new element to one of the subgroups and use it as a generator, we will generate the entire group.

Conditions two and three are obviously needed. Condition one is not actually necessary - there could exist elements in G contained in now maximal subgroup, but it is sufficient and turns out to be true.

