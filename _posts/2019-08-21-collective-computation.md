---
layout: "post"
categories: research
permalink: /:categories/collective-computation
title: Collective computation in biological populations
date: 2019-08-21 00:00:07
featured-image: Figure1RQP.jpg
featured-image-alt: Duality
---

Ecosystems may seem unlikely substrates for sophisticated computation. But two key features make them a promising way for solving sophisticated machine learning problems based on constrained optimization. First of all, self-replication provides stable constraint enforcement. Stable coexistence requires that the environmental state satisfy a precise set of conditions, such that the population growth rates of all species are simultaneously zero. A slight deviation from this constraint will lead to exponential growth or decay of one or more population sizes, which in turn will modify the environment until these conditions are restored. Secondly, distributing the computation over a whole ecosystem provides automatic parallelization, which becomes particularly important for solving problems efficiently in high dimension. 

This intuition can be transformed into a precise mathematical duality, as my coauthors and I have recently shown {% cite mehta2019constrained %}. The duality opens some interesting horizons for thinking about ecosystems and about classic machine learning problems, suggesting new observables for field ecologists {% cite marsland2019minimum %} and new algorithms for online learning {% cite howell2019machine %}. 

But is it possible to actually use an ecosystem to perform a computation? The adaptive immune system is a natural place to start. T cells are clearly performing a collective computation to determine whether a given antigen comes from a native protein or from a pathogen. My colleagues and I have recently developed a model of immune self-tolerance that sheds new light on the nature of this computation {% cite marsland2021tregs %}.

### References

{% bibliography --cited %}