---
title: "Projects"
date: 2025-03-22T12:42:47-04:00
draft: false
---

## Using LLMs as Economic Agents.

See code files here [(my git hub)](https://github.com/jarichey/EconAgents)

Here I use LLMs as economic agents in a few scenarios to test their ability to be used in (hopefully) larger simulations. Full paper is pending, but here are some pretty cool results. 

1. First I show that you can determine their 'utility' function indirectly (i.e. 'steer' their behavior) with a custom prompt giving them a 'personality'. In this simulation I randomly create agents with random mixes of characteristics and have them play the dictator game - they offer some percent of $100 to another unknown player and if they other player accepts they both keep the money, if the other player refuses, they both get nothing. The left shows four random people and their distribution of what they offer to keep, the middle shows distribution of cross-player T-stats testing equivalence of the mean over many simulations, and the right shows a snippet of some regressions - here just highlighting how political leaning affects the agents' average response. Pretty cool!

{{< threeimg
    src1="/images/Dictator_DollarsToKeep.PNG" alt1="Image 1" width1="500" caption1="Ex's of Dist. Offers"
    src2="/images/Dictator_CrossAveTStat.PNG" alt2="Image 2" width2="500" caption2="Dist. of Cross-T-Stats"
    src3="/images/Dictator_RegSnip.PNG" alt3="Image 3" width3="600" caption3="Snippet of Regs"
>}}

2. Here I test loss aversion with a simple experiment where you either give an agent (again with random mix of characteristics) a ticket and have another offer to buy, or tell them another agent has it and they can offer a price to sell. A perfectly rational agent would tend to stop offering to buy at the same price they start accepting offers to sell - because that is above the price they value the ticket. But, LLMs seem to be much like people and display loss aversion - they start refusing to buy long before they start accepting to sell. Except this guy below! He looks incredibly rational! And when we check his profile we see he is... an economist! Sometimes research is more than expected!

{{< img src="/images/LossAverse_Economist.PNG" alt="Economist" width="500" caption="Economist looks quite rational!" >}}

3. Finally I show that agents can interact and reach a simple equilibrium in a simple supply and demand set up. So each agent only knows there are other agents out there, some sellers and some buyers, and they know the set of their values or costs of the good and the offers or bids if there are any. They go in random order one by one either making offer/bid or accepting an existing one. And we see over time they consistantly reach the theoretical equilibrium once some bidding has played out. Moreover it seems that in the 'second round' that the convergence is smoother for some instances. So first panel is the hypothetical supply and demand curves and equilibrium based on the actual distribution of values and costs the agents have, and the second panel is the evolution of sell prices for multiple runs. In the second set of lines in the second panel we have convergence where the agents know of the previous round's outcomes. Pretty cool!

{{< img src="/images/SnD_Graph.PNG" alt="SnD" width="800" caption="Equilibrium Convergence!" >}}