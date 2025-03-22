---
title: "1-Missing Square Paradox"
description: A mathcamp problem about hiding your mistakes
date: 2024-02-01
tags:
  - Mathcamp
  - Math
---
Near this paragraph, a variant of a famous paradoxical puzzle is shown. On the left, we take two rectangles of area 60, and cut each one into two pieces. On the right, we rearrange the four pieces, and put them together into a single rectangle of area 119. How could this be?

{% image "cut-rearranged-rectangles.jpg", "rectangles cut and pieces rearranged" %}

Note: This image has been edited by labeling points for the purpose of easier explanation

a. Explain what's wrong. (Similar paradoxes can be found under names such as "Chessboard paradox" or "Missing square puzzle". It's fine to look at a source that explains such a paradox, provided you cite it — and explain it in your own words.)

b. Although two 5 × 12 rectangles cannot really be rearranged into a 7 × 17 rectangle, it is possible to take two a × b rectangles and cut them as shown in the picture above to make a c × d rectangle, with no paradox. What should the lengths a, b, c, d be (up to scaling, of course)?

c. It is also possible to take three congruent rectangles, cut each one into two pieces, and rearrange them to form a single rectangle similar to the original three. How can we do this?
Try to find an answer that lets you create a paradoxical decomposition of your own!



## Part A
At first look, the constructed rectangle looks fine. When you count, all the measures of the lines match up. But when you begin to look deeper, things fall apart. More specifically, when you look at the slopes of the line segments. 

Take segment AG, for example. According to the purple section, its slope is -2/5. But both AG and GC lie on the same line, AC, meaning AG and GC must have the same slope. According to the blue section, the slope of GC is -5/12. 

{% image "ParadoxicalSlopes.jpg", "slope paradox" %}

This is a blaring contradiction. -2/5 does not equal -5/12. But how can this be? The diagram looks fine. The reason it looks fine is because the difference is small enough to be hidden by the bold outlines of the segments. 

## Part B
So how do we make it work? Are there some values of a, b, c, and d that make everything all right? Well, we can go to where we found the contradiction: The inconstant slope of AG.

First, we will find what the slope of AG is in terms of a and b, according to the congruent purple and yellow trapezoids. Then, the slope of AC in terms of a and b, according to the pink triangle. As explained before, the slope of AC must equal the slope of AG, so we can set them equal to each other and get an algebra equation. We then solve for the ratio between "a" and "b".

It is very difficult to write out geometry problems, so here's and image:

{% image "finding-ab-ratio.jpg", "messy explanation image" %}

Now we have a ratio, we can finish the problem. It doesn't matter what "b" is, so let's set it to 1. 

If "b" is 1, "a" must be $(\sqrt{2} - 1)$

As seen in the image above, $c = (b-a)$. Substituting, $c = (2 - \sqrt{2})$

We also see in the image above that $d = (a + b)$. Substituting, $d = \sqrt{2}$

All these lengths scale linearly with "b".

Notice how these ratios make the starting two rectangles similar to the constructed one. This is why part C mentions <i>all</i> the rectangles being similar, including the constructed one. 

## Part C
Instead of creating an entirely new paradox, I will instead modify the given so it works for three rectangles. 

First, we will start with the two triangles formed form cutting one of the rectangles across a diagonal. In the original problem, they are positioned so they fit exactly into the constructed rectangle. But our new constructed rectangle will be bigger, since we are putting together three rectangles. Each side length will be about $\sqrt{3}$ times the sides of the "building blocks" rectangles. So, we will shift the triangles to fill this space.

{% image "shifted-triangles.jpg", "shifted triangle" %}

Now, like the original problem, we have two congruent trapezoids to fill. But instead of having one pice per trapezoid, we have two. 

Instead of thinking about "how will we cut each rectangle so the pieces fill the trapezoids?" we can think "how will we cut each trapezoid so the pieces fill the rectangles?"

We have two simple options: We can cut one rectangle and rearrange the pieces so one trapezoid is filled, and then repeat for the other; or we can cut each remaining rectangle into two congruent parts, take a part from both rectangles and use them to fill a trapezoid, then repeat with the two remaining parts. A third option is to cut the rectangles so there are no congruent parts and then match each piece with one from the other rectangle, but that option is complex and messy.

After some playing around, it is found that there is no way do the first option mentioned, with only one line as the slice. There may or may not be a way to do it with a more complex slice, but we want a simple solution.

Our only option left is to cut each rectangle into two congruent parts and use two of them to fill a trapezoid. If this is not possible, we must use a more complex solution. 

There are three possible resulting shapes when a rectangle is cut into two congruent parts using one line: A right triangle with legs "a" and "b"; A right trapezoid; Or a rectangle with sides a/2 and "b", or b/2 and "a".

{% image "lines-of-congruency.jpg", "lines of congruency" %}

No matter how we try to fit the right triangle described into the trapezoid, the resulting space is not any of the shapes we can use. For the a/2 by "b" rectangle, it's the same story. But, the b/2 by "a" rectangle works if we let $a+b = \sqrt{3}*b$. This means $a = b(\sqrt{3}-1)$

{% image "a-simple-fit.jpg", "the rectangle fits in the trapezoid" %}

We have one more test we need to do before we can say that this works: The two bases of the trapezoids have to add up to "b". Again, geometry problems are almost impossible to explain verbally, so heres an image:

{% image "does-it-work.jpg", "last check" %}

It worked! We were lucky. Now comes the paradox part. If we only wanted to arrange three congruent rectangles into a new similar one, we could've just set "b" to equal $\sqrt{3}*a$, rotated each rectangle 90 degrees, and set them beside each other. But the complex way we solved it makes it so we can purposely make a mistake and hide it. All we need to do is to pick a value for "b" that makes "a" be close to an integer. Setting "b" to 4 makes this happen, causing "a" to be about 2.93. Now, we just round "a" to its closest integer, which is 3. 

{% image "three-rectangle-paradox.jpg", "final solution" %}

If you look closely, you can see the diagonal isn't strait. If we picked a "b" value that made "a" even closer to an integer this would be less visible. But the simpler the better, and larger side lengths would lessen the simplicity. 

I am very curious to see other applicant's solution to this problem. It seems that there are many interesting possible solutions.