---
title: "Sequences: Recursive to Explicit"
description: This post talks about converting some simple recursive formulas into explicit ones.
date: 2023-04-30
tags:
  - another tag
---
There are two types of sequence formulas: recursive and explicit. Recursive formulas describe the step of getting from one term to the next. They use the previous term or terms as variables[^1]. These are more simple than the explicit and are much easier to find. The downside of this type of formula is that if one wants to find the nth term of a sequence, one would have to compute the formula n times[^2], plugging in the previous term(s) in each calculation. A way to avoid this tedious process is to use an explicit formula. Explicit formulas use the term number as the variable, usually expressed as “n”. You can just plug in the term number you want and get the answer.

## A Sequence Simple yet Broad

In early middle school you probally learned about two simple types of sequenes: Arithmatic and Geometric. If you don't remember, an arithmatic sequence is when you start at a given value and add a constant to get to the next value. The terms of an arithmatic sequence have a common differnce. A geometric sequence is when instead of adding a constant, you multiply by one. Geometic sequences have a common ratio. Later in your education, you may have learned about fibonachi sequences and harmonics, skipping over a simple yet broad type of sequence, a sequence combining both arithmatic and geometric.

In this sequence, to get to the next term you would multiply by a constant (we will call this constant "r") and then add another constant, which we will call "d". 

[^1]: Note the difference between constants and variables. You can have letters in an expression but have them be constants. The constants define the sequence but don’t change. Variables change.
[^2]: It actually would be n-1 times since you start with a given term