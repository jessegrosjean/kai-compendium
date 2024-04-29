---
title: "2-Mathcamp boxes"
description: A mathcamp problem
date: 2024-02-02
tags:
  - Mathcamp
  - Math
---
## The Problem
Kayla has two red boxes, two green boxes, and two blue boxes. Each of the six boxes contains a secret number. Kayla hands the boxes to Leo and asks him to write the letters A, a, B, b, C, and c, on the boxes. We will write #A, #a, #B, #b, #C, and #c to refer to the secret numbers inside these boxes.
From there, the boxes go to Maya, who opens the boxes and reports the differences #A−#a, #B−#b, and #C−#c, (in that order). Next, the boxes go to Nathan, who opens the boxes and reports the sum of the numbers in the red boxes, the sum of the numbers in the green boxes, and the sum of the numbers in the blue boxes (in that order). The resealed boxes, along with Maya's and Nathan's reports, are then handed back to Kayla, who must determine the numbers in each of the boxes.

Kayla expected Leo to label same-color boxes with the same letter, which would have made it easy for Kayla to figure the numbers: for example, knowing #A−#a from Maya and #A+#a from Nathan, Kayla could solve for #A and #a. However, to Kayla's surprise, Leo is color blind, so his labeling had nothing to do with the colors.

a. For which of the labelings that Leo used is it still possible for Kayla to determine the six secret numbers? (Kayla can see which colors have which labels on them.)
b. Generalize your answer to a problem with 2n boxes of n different colors, labeled with n different uppercase and lowercase letters.

## Solution
No matter what labeling leo uses, we know three constant equations:

#A-#a = x
#B-#b = y
#C-#c = z

Doing algebra we get:

#A = #a + x
#B = #b + y
#C = #c + z

Since we have solved for #A, #B, and #C, we can forget that those variables exist. Whenever they show up, we can just substitute them for their lowercase plus a constant. Now, we just have to solve for the lowercases.

From Nathan's report, we get three more equations, each in the form of two of the six variables being added to get a new constant. But if we substitute the capital variables, we get three equations in this form with only lowercase variables. We get rid of the extra constants through algebra. For example, if we had:

#A + #b = X
#a + x + #b = X
#a + #b = X-x
"X-x" is just a new constant.

From prior knowledge about algebra, a system of equations with "n" variables can only be solved for all variables when there are at least "n" unique equations. We have 3 variables and 3 equations, but these equations aren't necessarily unique. For instance, say that box C and box b are the same color, and box B and box c are the same color. Substituting for lowercase variables, we get:

#c + #b = constant
#b + #c = constant

These equation are practically the same. To ensure that labelings don't have "repeated" equations, there must not be two color groupings that have the same base letters, ignoring capitalization. This is also the case for any number of boxes.

