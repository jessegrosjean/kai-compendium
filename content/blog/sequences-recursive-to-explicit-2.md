---
title: "Sequences: Recursive to Explicit Part 2"
description: This post builds upon the previous formula and adds another variable and constant to the recursive sequence.
date: 2023-05-10
tags:
  - sequences
---
In the [last post](/blog/sequences-recursive-to-explicit-1) we found an explicit formula for the general recursive sequence:

$$a_n = r(a_{n-1}) + d$$

In this post we will add to this recursive formula so to describe a larger variety of sequences. The new sequence will be:

$$a_n = r(a_{n-1}) + x(n-1) + d$$

As you can see, we added the term $x(n-1)$ to the equation. $x$ will be a constant, and $n$ represents the term number.

As we did in the previous post, we will start with finding the first few terms so to visualize it better. Once we do this, we see the sequence:

1. $(a)$

2. $(ra + d) + (x)$

3. $(r^2a + rd + d) + (rx + 2x)$

4. $(r^3a + r^2d + rd + d) + (r^2x + 2rx + 3x)$

5. ...

(Remember, $a$ represents the first term in the sequence)

As you can see, I grouped the <u>terms</u>[^1] of the terms into two groups. One of the groups is the exact same sequence as the one in the post before. This is very convenient because we have already found the formula for this sequence. We can forget about these <u>terms</u> and then add the formula we already know to the formula we will derive for the remaining <u>terms</u> and get a formula for the whole thing.

It makes sense that this sequence is unaffected by the modification of adding $x(n-1)$ because the way we are expressing the terms is through the addition of monomials[^2], so addition won’t affect the separability of the previous sequence.

Taking out the sequence from the previous post greatly simplifies the sequence. The sequence that we are left with is:

1. $0$
2. $x$
3. $rx + 2x$
4. $r^2x + 2rx + 3x$
5. $r^3x + 2r^2x + 3rx + 4x$
6. ...

All these <u>terms</u> are divisible by $x$, so we can divide that out and multiply it back in later. We now have the sequence:

1. $0$
2. $1$
3. $r + 2$
4. $r^2 + 2r + 3$
5. $r^3 + 2r^2 + 3r + 4$
6. ...

Now, we have to do something interesting. In the sequence made by the <u>terms</u>, each <u>term</u> is made up of a coefficient and r to the something. The exponent of r decrease by one from one term to the next. This is a geometric sequence, and we know the formula for the sum. It would be easy, but the coefficients are in the way. 

To get rid of the coefficients, we can expand each <u>term</u> into a sum of multiple monomials, each with a coefficient of one. For instance, instead of thinking of a <u>term</u> as $3r$ we would view it as $r + r + r$.

Lets use this method to fully expand a term. In our example, we will use the 6th term.

<table>
  <tr>
    <td>$r^4$</td>
    <td>$r^3$</td> 
    <td>$r^2$</td>
    <td>$r$</td>
    <td>$1$</td>
  </tr>
  <tr>
    <td></td>
    <td>$r^3$</td> 
    <td>$r^2$</td>
    <td>$r$</td>
    <td>$1$</td>
  </tr>
  <tr>
    <td></td>
    <td></td> 
    <td>$r^2$</td>
    <td>$r$</td>
    <td>$1$</td>
  </tr>
  <tr>
    <td></td>
    <td></td> 
    <td></td>
    <td>$r$</td>
    <td>$1$</td>
  </tr>
  <tr>
    <td></td>
    <td></td> 
    <td></td>
    <td></td>
    <td>$1$</td>
  </tr>
</table>

The sum of each column in the table represent a <u>term</u> in the sequence. But instead of looking at it in columns, we can look at it in rows. Each row represents a sum of a geometric sequence. The sum of these sums is equal to the term. A.k.a. the sum of all the boxes in the table is equal to the 6th term.

These sequences looks very similar to ones we saw in the last post. The only difference are the first terms. Going back to previous post we can see that the sum of each individual row is:

$$\frac{ra - 1}{r - 1}$$
Where $a$ is the first term and $r$ is the inverse of the common ratio, which in this case is the same as our $r$.

The first term in each sequence is $r^{n-1-row}$. This is because the first term in the sequence is $r^{n-1}$, and each row represents a decrease in the exponent by one. So, the first term in the first row is $r^{n-1-1}$, the first term in the second row is $r^{n-1-2}$, and so on. If we put these rows in the formula and add them we get[^3]:

$$\frac{(r^{n-1} - 1) + (r^{n-2} - 1) + (r^{n-3} - 1)...ect}{r-1}$$

Since all the sums have the denominator of $r-1$ we can forget about that for now and divide by it later. Now, all that is left is the numerator. Notice how the numerator is made up of $-1$s and $r$ terms. If we group each $-1$ in the together, we get $-n$. Now notice how what we have left is a geometric sequence. If we put this sequence into our known formula, we get:

$$\frac{r^{n} - 1}{r-1}$$


## Putting It Back Together
Now, we get to put it back together. First, we add back the $-n$ that we took out earlier. Then, we divide by $r-1$ because we took that out earlier too. Next, we multiply by $x$ because we took that out earlier too. Finally, we add back the sequence we took out earlier. This gives us the final formula:

$$a_n = x(\frac{\frac{r^{n} - 1}{r-1} - n}{r-1}) + r^{n-1}a + d(\frac{r^{n-1} - 1}{r-1})$$

[^1]: As in the previous post, when we refer to the <u>terms</u> of the terms, we will underline the word "term" so to minimize confusion.
[^2]: A monomial is an expression that has a single non-zero term. For example, $3x$ is a monomial, but $(3x+2)$ is not.
[^3]: Remember, we start at $r^{n-1}$ and not $r^{n-2}$ (which is the first term) because in the formula above we multiply the first term by $r$. 