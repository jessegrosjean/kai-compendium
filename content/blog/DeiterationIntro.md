---
title: "An Introduction to Deiteration"
description: Going from a recursive formula to an explicit one can be very difficult, but going the other way is a lot easier.
date: 2025-01-25
tags:
- Math
- sequences
---

The previous posts[^1] looked at a few examples of converting from a recursive sequence to an explicit one. These were useful for getting a idea of what these conversions were like, but were not useful at all for looking at how iteration[^2] behaves as a whole. Now, two years later, I have the tools to explore this bigger question.

It turns out that going the other way, explicit to recursive, is actually pretty easy: It has a very nice simple formula. 

## The Formula

To find this formula, realize that a recursive function adds one to the term number: It takes an input of the current term and outputs the next term, which has a term number of one greater. An explicit function takes a term number and outputs the term.

Letting g(x) be the recursive function for a sequence, and letting f(x) be the explicit, we get that:

$$g(f(x)) = f(x+1)$$

In this equation, x represents the term number. We input f(x), which is the xth-term, into g(x), and get the "x+1"th term.

$x$ is just a variable, so we can replace it with anything we want[^3], as long as we replace it everywhere. If we replace $x$ with $f^{-1}(x)$ we get a new equation:

$$g(f(f^{-1}(x))) = f(f^{-1}(x) + 1)$$

The $f(x)$ and $f^{-1}(x)$ cancel out, giving a final equation:

$$g(x) = f(f^{-1}(x)+1)$$

This equation is extremely simple and also powerful. Remember, $g(x)$ is the recursive function for the sequence and $f(x)$ is the explicit function, so this equation expresses the recursive function solely using the explicit function. This is the opposite of iteration, which is going from recursive to explicit. We will call going the other way "deiteration". Lets try out this "deiteration" equation using some examples!

## Examples

Let the explicit function be 2x. This means our sequence is

$$0, 2, 4, 6, 8, 10, 12 ...$$

Obviously, the recursive function for this sequence is $x+2$. To get from one term to the next term, you just add 2. 

Plugging 2x into our equation, we get:

$$g(x) = 2(\frac{x}{2} + 1)$$

simplifying results in the equation

$$g(x) = x+2$$

This is the result we expected. It works![^4]

## ...What About Going the Other Way?

Our main goal is to find methods of converting from a recursive function to an explicit one. So, all we have to do is solve for f(x) in terms of g(x) using our equation, right? Then we can plug in g(x) and vwa-la, we've found the explicit function! Well, not really. First of all, it is important to note that a recursive function iterated may result in many different explicit functions depending on the 0th term. The 0th term is the original value that you apply the recursive function to: It is easy to see why we need to know this value if we want to define a sequence.

If we only know the recursive function, and not the initial value, we don't have anywhere to start. A recursive function takes a term and inputs the next term, but we can't do that if we don't have a term to input. So, we need to introduce a new variable, a<sub>0</sub>[^5], representing the initial value of our sequence. 

But even if we introduce this new variable (say hi a<sub>0</sub>!) we still run into issues: We can only find discrete values of our explicit function. This is because the explicit function takes an input of the term number, but the term number has to be a positive integer[^6]. For instance, there is no such thing as the 2.73rd number in a sequence. To get around this and make our explicit function continuous, we'ed have to do something like defining an entire initial interval, say I<sub>0</sub>, instead of only an initial value.  

Still, even if we do that it is impossible for our solution to be "easy". This is because it has been proven that for some systems, the most efficient way to find the nth term is to use the recursive function n-times. Although this does not mean there aren't explicit formulas for these sequences, it shows that these formulas would be insanely complicated and computationally ineffective if they do in fact exist.

## But the Pigeon Housing Crisis!!

Going back a few paragraphs: We showed that recursive functions map to multiple functions when iterated, depending on the initial value. But, when deiterated, each explicit function maps to just one recursive function. Does this mean there are more explicit functions than recursive ones? No - this can not be the case. A function is not by nature "explicit" or "recursive": It depends on what sequence is being talked about. For instance, 2x is the explicit function of the sequence $0, 2, 4, 6, 8...$ but is also the recursive function of the sequence $1, 2, 4, 8, 16, 32...$.

What solves the problem of this apparent violation of the pigeonhole principle is the fact that we use $f^{-1}(x)$ when deiterating. By using this, we have assumed that $f(x)$ is a bijection[^7]. So yes, a bijection deiterated results in just one function, but a non-invertible function may output multiple functions when deiterated.

## So What is Next?

Although going from deiteration to iteration isn't as direct and easy as hoped, we still can maybe use the simple process deiteration to understand iteration a little better. In the following posts, we will look at deiteration and iteration as a system, exploring how they behave. 

[^1]: Click [here](/blog/sequences-recursive-to-explicit-1) for the first, [here](/blog/sequences-recursive-to-explicit-2) for the second.
[^2]: Converting from recursive to explicit
[^3]: If we ignore potential domain and range issues
[^4]: This equation already was known before I found it, but I did find it independently, about 4-5 years ago. 
[^5]: This variable is actually a lot like the +C you see in integrals. Actually, iteration and deiteration are very much like integrals and derivatives in many ways: Iteration generally adds complexity and needs this a<sub>0</sub> factor, and deiteration generally takes away complexity. When you look at what we are doing from a dynamical systems perspective, this connection goes even further. This is a very long footnote, so see [this](/blog/DynamicsDC) article if you want to learn more.
[^6]: Well, we could pretty easily define it to negative values as well by applying the inverse of the recursive function, if the recursive function is invertible. But, still, only discrete integer values would work.
[^7]: One-to-one, invertible, whatever you want to call it. Each output has only one corresponding input. 