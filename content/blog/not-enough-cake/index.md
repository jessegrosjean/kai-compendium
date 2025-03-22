---
title: "4-Not Enough Cake!"
description: A problem about finding a clean method to distribute cake fairly.
date: 2024-02-14
tags:
  - Mathcamp
---
## The Question
Eleven Mathcampers decided to bake a rainbow unicorn sprinkle cake with 10 slices. Unfortunately they cannot split up the slices into smaller pieces, because they do not want to risk upsetting the unicorn. Each Mathcamper wants a slice of the cake (but not more, because Mathcampers aren't greedy). Each Mathcamper helped bake the cake to some extent. The Mathcampers have been assigned fractions x<sub>1</sub>, x<sub>2</sub>,. . ., x<sub>11</sub> representing their share of the credit in baking the cake, where 0 < x<sub>i</sub> < 1/10 for each i, and x<sub>1</sub> + x<sub>2</sub> + . . . + x<sub>11</sub> = 1.

a. How can you randomly distribute the slices of cake such that the i<sup>th</sup> Mathcamper has a probability of exactly 10x<sub>i</sub> of getting a slice of cake?

b. Generalize your solution to distribute k slices to n campers, for all k and n with n > k ≥ 1. As before, the Mathcampers have been assigned fractions x<sub>1</sub>, x<sub>2</sub>,. . ., x<sub>n</sub> representing their share of the credit in baking the cake, where 0 < x<sub>i</sub> < 1/k for each i, and x<sub>1</sub> + . . . + x<sub>n</sub> = 1; for each i, you want the i<sup>th</sup> Mathcamper to have a probability of exactly kx<sub>i</sub> of getting a slice of cake.

c. Suppose that, in the setup of part b, you do not know the value of k (the number of slices). Instead, you will put the Mathcampers in a random order, according to some strategy, and then serve slices of cake in that order until the cake runs out. Is there a way to do this so that for each i, the ith Mathcamper will have a probability of exactly kx<sub>i</sub> of getting a slice of cake — no matter what k turns out to be? You may still assume that we have 0 < x<sub>i</sub> < 1/k for all i, and x<sub>1</sub> + . . . + x<sub>n</sub> = 1.

## Part A
There is exactly one less camper than cake slices, so instead of picking who gets cake, we can pick one person who <i>doesn't</i> get cake. Since we want every camper to have a 10x<sub>i</sub> chance of getting cake, we want every camper to have a 1 - 10x<sub>i</sub> chance of not getting cake. A simple way of doing this is by slicing a circle into 11 sections, each section being a (1 - 10x<sub>i</sub>)<sup>th</sup> of the circle. Then, we pick a random point on the circle. This works because $\sum_{i=1}^{11}(1 - 10x_i) = 11 - 10\sum_{i=1}^{11}x_i$. As defined above, $\sum_{i=1}^{11}x_i = 1$, so $11 - 10\sum_{i=1}^{11}x_i = 11 - 10 = 1$ Since all the parts add up to one, it is possible to slice the circle as such.

## Part B
When we try to make our method in Part A work for any "n" and "k", we quickly run into problems. The most obvious way to generalize this method is to just repeat it n - k times, the number of campers who won't get cake. But now we run into the problem of picking the same camper twice. 

Since now there can be more than one camper who doesn't get cake, there is no point in thinking about it in terms of who doesn't get cake. It's simpler to make the sections x<sub>i</sub> in size and give the cake to the people who are picked. This change would also mean we would repeat the "picking" process k times, not n - k.

Okay, so to solve the problem of picking a camper twice, what if we remove the campers after they are picked? We instantly would run into a huge mess, because each time a camper is removed, the probabilities are messed up. If we try to tackle this problem, the method becomes extremely complex and messy. 

So what's a different way we can guarantee not choosing the same camper twice? What if, instead of randomizing the next point, we rotated our point a z<sup>th</sup> of the circle? This "z" would be large enough to insure we made it to a new sector, but small enough so to not end up looping back around and landing on the old sector once more. 

To insure we make it to a new sector, "z" must be larger than the largest x<sub>i</sub>, the size of the largest sector. To not end up looping on ourself, the portion of the circle we have "hopped" after the entire process must be less than 1. The total distance we hop is equal to z*(k-1)[^1]. Dividing both sides, we get z < 1/(k-1). So, to satisfy our requirements stated, z can be any value for which (the greatest x<sub>i</sub>) < z < 1/(k-1).

Now we have a "hopping distance," z, that ensures we don't pick the same sector twice. But does this method preserve the probabilities of each camper getting cake? Yes. The sector that the random point has to land on to cause the next point to be in the wanted sector is just the wanted sector rotated z around the circle. Hopping k number of times makes k "good" sectors, causing the total "good" area to be kx<sub>i</sub>, which is the probability we want. I am aware that my wording is terrible here, so here is a diagram:

{% image "sectorofpersona.jpeg", "Wheel of Cake" %}

Unlike my wording, this solution is so nice, clean, and simple! Before I thought of this solution, I was for a long time playing with the removal of those chosen. This lead to a lot of messy functional algebra, so messy that I don't want to try to explain. But once I gave up trying to find a method using mathematical formulas and rules, and instead looked to creative and abstract solutions, it became much easier and lead me to this beautiful answer. That is what I love about math. I believe that a solution is not a true solution unless it is simple, clean, and you <i>truly</i> understand it. You have to be able to visualize how it works, able to explain <i>why</i> it works. A messy solution is just another question, sometimes even a more complex one.

## Part C
Luckily, our solution also happens to work for part c, where we don't know what "k" is. In our solution, we do use the variable "k" twice, so we have to make 2 small changes:

First, I have to admit that the bounds I put earlier on "z" are not correct. "z" can be equal to x<sub>i</sub>. This is because the only times we run into problems with this value of z is when one of our "hops" lands on the exact point that marks the boundary between the largest sector and another sector. Since we have a finite number of points we are choosing each time, and since we are choosing from an infinite number of points, the probability that we land on this specific point is 0% (That is if this question is in an analog universe, but that's a different topic). Anyways, this means we can set "z" to be x<sub>i</sub>, getting rid of the variable "k".

Next, we have to decide how many times we "hop" without using the variable "k". This can be done by accepting the depressing reality that no matter what placement you are in, if you are behind the k<sup>th</sup> person, you get no cake. The ordering of the people after this placement has as much meaning as life does without cake. Since we know that we will only run into problems after we have hopped more than "k" times, we can just continue hopping until we pick someone we have already picked. 


[^1]: k-1 is the number of times we "hop". This is because for every slice past the first slice, we take a "hop". 