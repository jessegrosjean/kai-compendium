---
title: "Nash Equilibrium: An Alternative Thought"
description: I do not know much game theory, but have been slightly discontent whenever I think about the prisoner's dilemma, or some equivalent problem. In problems like these, a nash equilibrium is reached but it is not the optimal outcome. This post explores unconventional ways of thinking about these problems.
date: 2025-08-10
tags:
  - Game Theory
  - Math
---

## The Prisoner's Dilemma
It is likely you have already heard of the Prisoner's Dilemma before. But in case you haven't, or you need a refresher, here's the setup of an equivalent problem (with no prisoners involved, sadly):

Two gather's are getting pears from a tree. If they cooperate, they gather a total of 6 pears before nightfall and split them evenly. If they fight, they each only manage to gather one pear. But, if one cooperates and the other betrays them, the betrayer steals all the pears, getting 6 while the one who cooperated gets none.

I am aware that word problems are horrendous, so here's a table that represents the game:

<table>
  <tr>
    <td></td>
    <td>cooperate</td> 
    <td>fight</td>
  </tr>
  <tr>
    <td></td>
    <td>cooperate</td> 
    <td>3, 3</td>
    <td>0, 6</td>
  </tr>
   <tr>
    <td></td>
    <td>fight</td> 
    <td>6, 0</td>
    <td>1, 1</td>
  </tr>
</table>

What is the optimal strategy? Game theory says that the best strategy is to fight. This may seem unintuitive since them both cooperating gives a better outcome than them both fighting. Game theory though gives a strong argument:

Consider the possibility that your opponent's strategy is to fight. In this case, it is obviously better for you to fight as well: getting 1 pear is better than getting none.

If, alternatively, your opponent's strategy is to cooperate, your best strategy is still to fight: If you cooperate, you get 3, but fighting gives you 6. 

Solved, right?

## An Argument Otherwise

The solution above never assumes anything about how the opponent will act. If this must be maintained, then I don't think there's any reasonable way to argue for any other strategy. But, if assumptions can be made, then there is something tricky we can do: We can assume that the other player is a <b>rational agent</b>.

Def: A <b>rational agent</b> is a player who will always make the optimal move.

If we are assuming the opponent is playing by the optimal strategy, we can make a <b>very</b> important corollary: we know that the opponent will have the same strategy as us. We also are playing by the optimal strategy. 

