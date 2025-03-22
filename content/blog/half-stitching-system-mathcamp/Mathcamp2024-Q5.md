---
title: "5-Half-stitching system"
description: A mathcamp problem about exploring a new system and creating theorems from postulates. 
date: 2024-02-18
tags:
  - Mathcamp
  - Math
---
## The Problem
"Stitching halves" is a form of embroidery which makes images out of diagonal stitches in a square grid. Our images will all be created from a single thread, which alternates traveling in straight lines (called stitches) along the front and the back of the grid:

1. The front of the grid is where the image is formed. Here, each stitch goes from a point (x,y) either to (x+1,y+1) or (x−1,y−1). We say that we stitch a square if a stitch on the front follows its diagonal (from top right to bottom left or from bottom left to top right).

2. The back of the grid is not part of the image. Here, each stitch can follow any straight line — but it must travel a positive distance, because if you end a stitch where it started, it will unravel.

This problem is about minimizing the total length of thread needed to stitch a given pattern.

## General Rules
This problem presents a system where there is no simple analogy that can be made to other mathematical systems we know well. We only know the base postulates, but solving these problems with only these postulates is like fumbling around in the dark, hoping to find solutions through trial-and-error. Of course, our human brain would subconsciously find some theorems to help us, but it would be hard to <i>prove</i> that the thread length needed for the method found is the actual minimum. So instead of immediately solving the problems, we should work on finding some helpful theorems. 

1. The Minimum Minimum[^1]: On the front side, each stitch is $\sqrt{2}$ in length. The minimal length of each stitch on the backside is 1, since (as implied in the given) we must always end and come up at integer points, and the smallest positive distance between two integer points is 1. So, if we have “x” stitches, the minimum minimum thread length is $x(\sqrt{2}+1)-1$. We subtract one because at the end we don’t need to do another backstitch[^2]. This theorem shows that if the minimum is the minimum minimum, all the backstitches have to go to one of the 4 orthogonal points around where the thread "when down". 

2. Full Loop: If a stitching method of one iteration of the pattern starts in the same place it ends but shifted one iteration, the stitching method works for the entire pattern. Full loops can consist of smaller full loops. A full loop that acts as one iteration of the overall pattern is defined as a "full iteration".

3. Point Completion: Define "point" as a point where at least one stitch either starts or ends. For each stitch touching this point, there must be one backstitch starting or ending at the point. <b>The converse is also true.</b>

4. Resetter: Some of the patterns given have a section that's missing from the last iteration. Actually, all patterns have this because the final backstitch is not needed.

5. Beginning rewrite: Sometimes there is a piece missing from the beginning iteration, kind of like the resetter. This missing part can affect the iteration a lot, so the first iteration (if not complete) thread length can just be found independency. Remember that it must end at the start of the first "full iteration". 

6. Final Length: The final length of a pattern is the thread length needed for each "full iteration" times "n-1" (n being the number of iterations). Then, subtract the thread length of the resetter. Add the length of the beginning rewrite. (If there is no piece missing from the beginning, then it is just the length of a "full iteration" and it cancels out the "-1" in "n-1"). 

## Part A
As you can see in the image below, it is possible to stich any full rectangle with the minimum minimum thread length. There are m*n stitches in an "m" by "n" rectangle, so the minimum thread length needed is $mn(\sqrt{2}+1)-1$

{% image "Mathcamp pictures-10.jpg", "Image" %}

## Part B
If using only backstitches of length one, there is only one point that can connect to the very top of each "tooth." This allows us to see that if this pattern has the minimum minimum thread length, then:

{% image "Mathcamp pictures-12.jpg", "Image" %}

Having proved that the full iterations cannot be the minimum, we can test for the next minimum minimum: All backstitches are of length 1 except for one that is $\sqrt{2}$. A stitching method for this pattern that does this is shown below:

{% image "Mathcamp pictures-14.jpg", "Image" %}

This method has a beginning rewrite. Each full iteration is length $4\sqrt{2}+2$, the beginning rewrite is of length $2\sqrt{2}+2$, and the resetter is of length $\sqrt{2}$. The final length is $(n-1)(4\sqrt{2}+2) + 2\sqrt{2}+2 - \sqrt{2}$. Simplifying we get:
$$n(4\sqrt{2}+2) - 3\sqrt{2}$$

## Part C
As you can see below, the minimum minimum thread length works for this "tall teeth" pattern. Each full iteration is of length $4(\sqrt{2} + 1)$, and the resetter is of length $\sqrt{2} + 1$. So, the total thread length needed is $4n(\sqrt{2}+1) - \sqrt{2} - 1$, or $(4n-1)(\sqrt{2} + 1)$

{% image "Mathcamp pictures-11.jpg", "Image" %}

## Part D
We can use the exact same method as we did in Part B to determine if this has the minimum minimum thread length. We get the same exact results, meaning we can't get the minimum minimum.

{% image "Mathcamp pictures-13.jpg", "Image" %}

Also like in Part B, there is a stitching method that lets us get the second to least minimum:

{% image "Mathcamp pictures-15.jpg", "Image" %}

The length of a full iteration is $7\sqrt{2}+5$, the length of the beginning rewrite is $2\sqrt{2}+2$ and the resetter length is $\sqrt{2}$. So the final length is $$n(7\sqrt{2}+5)-6\sqrt{2}-3$$

## Part E
I have already given some general theorems about this system, but here is one final one about the maximum minimum.

If the design fits in a "m" by "n" rectangle, then the average backstitch can not be larger than $\sqrt{m^2+n^2}$. This is because the largest possible backstitch is the length of the diagonal of rectangle mn (Which is $\sqrt{m^2 + n^2}$). With "x" stitches, there are "x-1" backstitches, so the total backstitch length will be the average times "x-1". The total length of the stitches on the front will be $x\sqrt{2}$. So, if a design with "x" stitches fits in a "m" by "n" rectangle, then the total thread length cannot be greater than $(x-1)\sqrt{m^2+n^2} + x\sqrt{2}$

I'm aware this bound is not very tight and better bounds can be easily found. I want to spend so much more time working on this problem but I have no time left. 

[^1]: The smallest thread length a pattern can have
[^2]: This pattern has the minimum resetter, "1".
