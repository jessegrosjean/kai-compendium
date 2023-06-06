---
title: "Sequences: Recursive to Explicit Part 1"
description: This post talks about converting a simple recursive formulas into an explicit one.
date: 2023-04-30
tags:
  - sequences
---
There are two types of sequential formulas: recursive and explicit. Recursive formulas describe the step of getting from one term to the next. They use the previous term or terms as variables[^1]. These are more simple than the explicit and are much easier to find. The downside of this type of formula is that if one wants to find the nth term of a sequence, one would have to compute the formula n times[^2], plugging in the previous term(s) in each calculation. A way to avoid this tedious process is to use an explicit formula. Explicit formulas use the term number as the variable, usually expressed as “n”. You can just plug in the term number you want and get the answer.

## A Sequence Simple yet Broad

In early middle school you probably learned about two simple types of sequences: Arithmetic and Geometric. If you don't remember, an arithmetic sequence is when you start at a given value and add a constant to get to the next value. The terms of an arithmetic sequence have a common difference. A geometric sequence is when instead of adding a constant, you multiply by one. Geometric sequences have a common ratio. Later in your education, you may have learned about Fibonacci sequences and harmonics, skipping over a simple yet broad type of sequence, a sequence combining both arithmetic and geometric.

In this sequence, to get to the next term you would multiply by a constant (we will call this constant $r$) and then add another constant, which we will call $d$. We of course need to now what value to start with. We will call this value, $a$. This sequence as an equation looks like:

$$ a_n = r(a_{n-1}) + d $$

## Breaking it Down

When we write out the first few terms with the variables $r$, $d$, and $a$, we get:

1. $a$
2. $ra + d$
3. $r^2a + rd + d$
4. $r^3a + r^2d + rd + d$
5. $...etc$

From now on, we will talk about the terms of the sequence and the terms of the terms of the sequence. To make this less confusing, when referring to the terms of the terms the word "term" will be underlined. This would be seen as "<u>term</u>". The terms in the main sequence will be referred to as normal.

Back to the problem, notice how each term has one <u>term</u> that is equal to $r^{n-1}a$. When I listed it out above, I listed it as the first <u>term</u>. We can subtract out this <u>term</u> and add it back in later. 

Now notice how all the other <u>terms</u> are divisible by $d$. We can divide out $d$ and multiply it back later. When we do this, we get the resulting sequence:

1. $0$
2. $1$
3. $r + 1$
4. $r^2 + r + 1$
5. $r^3 + r^2 + r + 1$
6. $...etc$

We will now look at each term as a sequence unto itself. In this sequence, you divide by $r$ each time. The sequence starts at $r^{n-2}$ and terminates at 1. We want to find the sum of this sequence since each term of the main sequence is the sum of the <u>terms</u> of the sub-sequence. Luckily, there is already a proven formula for the sum of a geometric sequence. This formula is:

$$\frac{a}{1 - ratio}$$
($a$ refers to the first term)

As said above, the first <u>term</u> is $r^{n-2}$. We divide by ${r}$ each time, so the ratio is $\frac{1}{r}$. Putting this into the equation we get:

$$\frac{r^{n-2}}{1 - \frac{1}{r}}$$

If we multiply both sides by $r$ we get the simpler fraction:

$$\frac{r^{n-1}}{r - 1}$$

We are almost there, but not quite. This formula finds the sum of an infinite geometric series. We want to find the sum of a series that terminates at 1. To turn this formula into one that terminates, we can just subtract all the <u>terms</u> we don't want. These terms make up another geometric series, with the same ratio but with a first <u>term</u> of $\frac{1}{r}$. We start at this <u>term</u> because it is the first <u>term</u> we don't want.

Once subtracting this series, we get:

$$\frac{r^{n-1}}{r - 1} - \frac{\frac{1}{r}}{1 - \frac{1}{r}}$$

Simplifying, we get the satisfyingly simple formula: 

$$\frac{r^{n-1} - 1}{r-1}$$

Now all we have to do is retrace our steps and put everything back together.

## Putting it all Together

The first thing we do is multiply by $d$ again, since we had divided that out. Then, we add back the <u>term</u> we took out, "$r^{n-1}a$". This gives us our final equation:

$$a_n = r^{n-1}a + d(\frac{r^{n-1} - 1}{r-1})$$

And thats it! Now we have a nice, simple formula that we can use for a broad array of sequences. We went from the formula $a_n = r(a_{n-1}) + d$ to the one above. 

[^1]: Note the difference between constants and variables. You can have letters in an expression but have them be constants. The constants define the sequence but don’t change. Variables change.
[^2]: It actually would be n-1 times since you start with a given term