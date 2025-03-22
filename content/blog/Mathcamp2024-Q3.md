---
title: "3-Paradoxes: Number Theorists, Analysts, and Logicians"
description: A Mathcamp 2024 problem about yes-or-no paradoxes.
date: 2024-02-03
tags:
  - Mathcamp
  - Math
---
Remember this curious fact you may not have known about mathematicians: when asked a yes-or-no question, number theorists will always tell the truth, while analysts will always lie. Be careful: if you ask someone a yes-or-no question, and they cannot answer either "yes" or "no" to it, then the universe explodes in paradox. For example, this happens if you ask an number theorist, "Is your answer to this question 'no'?"

a. What yes-or-no question can be asked to both a number theorist and an analyst to cause the universe to explode in both cases?

b. To try to prevent the universe from exploding in paradox, logicians have decided to act as paradox detectors. When you ask a logician a yes-or-no question, the logician will answer "yes" if asking the question to a number theorist would cause the universe to explode, and "no" otherwise. For example, if you ask a logician, "Is your answer to this question 'no'?" the logician will answer "yes".

What yes-or-no question can be asked to a logician to cause the universe to explode?

## Introduction
To my knowledge[^1], all paradoxical questions stem from self-reference[^2]. These questions require you to know the answer to find the answer. This may seem like all self-referencing questions are paradoxical, but this is not the case. Self-referencing yes-or-no questions, which from now on we will call SBQs[^3], can either have one right answer, two right answers, or be a paradox (having no right answer). We can determine what type an SBQ is (and if there is one, the correct answer) through trial and error. First, we assume the answer is "yes", and what that entails. Then we do the same for "no". If an answer leads to error, we know that answer is not an option.

## Part A
To find a question that answers part A, we can realize that a number analyst is just a number theorist, but the meanings of "yes" and "no" are switched. Using the example given, "Is your answer to this question 'no'?" is paradoxical when asked to a number theorist. Switching out "no" for "yes" we get the question "is your answer to this question 'yes'?". This is a paradox if asked to a number analyst. Now we can do something clever: since a number analyst's answer and a number theorist's answer are always swapped, we can replace the "yes" and "no" in the questions with a new question. The correct answer of this question needs to be "no". Let use the question "are number analysts truthful?" 

Putting these two questions together, we get our final question:

"Is your answer to this question the same as your answer to the question 'are number analysts truthful'?"

Doing the logic out yourself, you can see that this creates a paradox for both number analysts and number theorists.

## Part B
Part B is a little harder, but a lot more fun (Part A was really fun as well). To create a paradox with a logician, we must make sure that the logician cannot answer either "yes" or "no". Let's start with "no".

If a logician answers "no", then they are saying that if asked to a number theorist, there is no paradox. So, to prevent the logician from saying "no" we must make it so if the logician answers "no" it creates a paradox for the number theorist.

To make sure the logician can't answer "yes", we must make it so there is no paradox for the number theorist if the logician's answer is "yes".

So, we want the question to be paradoxical to a number theorist <i>only</i> if the logician answers "no". By using the same trick used in Part A, we can make this work. We can replace the "no" in "is your answer to this question 'no'?" with "the logicians answer to this question". By changing the wording we can get a simpler question with the same meaning:

"Would a logician's answer to this question be the same as your answer?"

Checking our answer:

If the logician answers "no" then the question is simplified to "is 'no' your answer?", which is just "is your answer to this question 'no'?" but with different wording. As stated in the given, this creates a paradox if asked to a number theorist, proving the logician's answer of "no" wrong.

If the logician answers "yes" then the the question is simplified to "is your answer to this question 'yes'?" When asked to a number theorist, both "yes" and "no" are correct, leading to no paradox. Since there is no paradox, the logician's answer of "yes" is wrong.

We did it! It's such a clean, simple looking question that we found. Who knew it could be so dangerous? And complicated! I continuously kept proving in my head that it works, but it took me a long time to be able to think it through clearly. I love this problem so much. I love how confused it makes me, but how simple it is. I'm very curious how others answered this question.


[^1]: This is the only idea that did not come directly from me, it came from prior knowledge. Where exactly, I forget, but I know that its a common idea. (The other ideas have been found by others, of course, but I thought of them independently).
[^2]: By self reference, I mean specifically referencing the answer to the question.
[^3]: Self-referencing boolean question