---
layout: "post"
categories: research
permalink: /:categories/thermodynamic-constraints
title: Thermodynamic constraints in living matter
date: 2019-08-21 00:00:04
featured-image: Figure1_osc_trimmed.jpg
featured-image-alt: Bound on precision
---

[Sir Arthur Eddington][eddington] famously remarked that the Second Law of Thermodynamics holds “the supreme position among the laws of Nature.” Half a century earlier, [Ludwig Boltzmann][boltzmann] had already noted that thermodynamics constrains the activity of living systems, in such a way that the Darwinian “struggle for existence” could be framed in terms of entropy. Recent progress in non-equilibrium statistical mechanics has opened up new possibilities for fleshing out these insights, determining which features of biological activity are constrained by thermodynamic laws, and what the “negative entropy” obtained in the “struggle for existence” is used for.

[One striking property][manu] of living materials is their combination of mechanical strength and rapid adaptability. This combination is essential for effective locomotion and for autonomous damage repair, and is rarely found in inanimate systems. By characterizing this qualitative observation in terms of thermodynamic constraints, I have shown how the internal chemical potential differences maintained by cellular metabolism can give biological materials their special characteristics {% cite marsland2018active %}.

Thermodynamic consistency also places general bounds on the temporal precision of physical processes at finite temperature. One might expect that these constraints would affect the design of biochemical “clocks,” such as the KaiABC system that sets the circadian rhythm in a large class of photosynthetic bacteria. I ran simulations of the KaiABC system and used published data from experiments and other biochemical clock models to determine how close they came to the thermodynamic limit. I found that the precision of these biochemical processes was always at least an order of magnitude worse than the theoretical optimum, indicating that evolution somehow failed to fully optimize this figure of merit {% cite marsland2019thermodynamic %}. Using a simplified toy model capturing the essential structure of the KaiABC system, I showed that the optimum could be achieved using a molecule with a sufficiently large number of sequentially accessed internal states, with comparable reaction rates for each internal step. This suggests that the sub-optimality of the clock precision is at least partially due to the difficulty of implementing such a large chemical cycle on a single molecule. 

Alongside these specific projects, I have also authored or contributed to several general treatments of various aspects of non-equilibrium statistical mechanics, including [a review article][review] providing an accessible introduction to some of the most important recent developments in the field {% cite marsland2015far marsland2017edge perunov2016statistical marsland2017limits %}. 

### References

{% bibliography --cited %}

[eddington]: https://en.wikiquote.org/wiki/Arthur_Eddington
[boltzmann]: https://en.wikiquote.org/wiki/Ludwig_Boltzmann
[manu]: https://web.stanford.edu/group/prakash-lab/docs/Dumont2014-MBOC.pdf
[review]: https://arxiv.org/pdf/1707.06680.pdf