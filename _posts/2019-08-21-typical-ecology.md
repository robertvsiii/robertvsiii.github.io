---
layout: "post"
categories: research
permalink: /:categories/typical-ecology
title: Statistical physics approaches to community ecology
date: 2019-08-21 00:00:06
featured-image: Fig1_scheme_trimmed-01.jpg
featured-image-alt: Random Interactions
---

Microbial ecosystems manifest one of the main technical obstacles to predictive modeling of biological systems, which arises from their extreme heterogeneity. The standard methods of statistical mechanics produce powerful and robust predictions about the behavior of large collections of functionally identical particles, which are easily extended to mixtures of a few different kinds of components. But in most biological systems, the number of distinct types of components is unmanageably large, whether we are considering the [20,000 different genes in the human genome][genome], or the [20,000 distinct metabolites][kegg-stats] involved in biochemical networks. Microbial ecosystems reproduce this same difficulty on a bigger length scale, with hundreds to thousands of coexisting “species” in a given natural community. The development of inexpensive DNA sequencing has made these systems an attractive setting for developing and testing new theoretical methods for overcoming this hurdle. Highly diverse microbial communities can be readily found on any plant leaf, pond droplet, or grain of soil, and sequencing technology makes it possible to determine which species are present there and in what abundance.

My colleagues and I have been adapting [methods from the physics of disordered materials][cavity] to this new setting, deriving predictions about the diversity, composition and sensitivity of heterogeneous communities based on summary statistics about consumption preferences and byproduct secretion in the regional species pool. The key assumption behind these methods is that the parameters characterizing each species can be modeled as independent random variables drawn from a given probability distribution. This seems like an extreme assumption, given how much specific structure is already known about microbial behavior. But we have shown that at sufficiently high levels of diversity, the strong interactions between specific pairs of organisms based on known mechanisms can be overwhelmed by the sheer number of weak, uncharacterized interactions with all the other species in the system {% cite cui2019diverse %}. 

To check our calculations and facilitate hypothesis generation, I have also been developing [a Python package][community-simulator] for rapidly simulating diverse microbial ecosystems with randomly sampled parameters {% cite marsland2019community %}. Using this package, I have shown that the robust patterns observed in large-scale surveys of microbial diversity (such as the Human Microbiome Project and Earth Microbiome Project) reflect the “typical” structure of diverse communities {% cite marsland2019minimal %}. 

I have also used this software to study some novel ecological phenomena that can arise in self-sufficient microbial ecosystems {% cite marsland2019available %}. Since microbes generically produce usable byproducts whenever they consume an energy source, they can autonomously generate a complex chemical environment that supports a diverse community even when only a single energy source is supplied externally. This differs from the standard case considered in macroscopic ecology, where environmental conditions are either fixed or modified only through consumption. By performing simulations of this extreme case of a fully self-generated environment, I identified a transition in community structure as a function of the supply rate of the externally provided resource. At high supply rates, the community-level metabolic network percolates, and all possible byproducts are produced at sufficiently high concentrations to significantly contribute to the growth of some set of species. The scaling of diversity with the number of supplied resources in this regime agrees with analytic predictions obtained for “typical” communities. But at low supply rates, only species that directly consume the externally supplied resource can survive, and the resulting low-diversity state no longer satisfies the assumptions for calculating “typical” community properties. 

### References

{% bibliography --cited %}

[genome]: https://en.wikipedia.org/wiki/Human_genome
[kegg-stats]: https://www.genome.jp/kegg/docs/statistics.html
[cavity]: https://iopscience.iop.org/article/10.1088/1742-5468/aab04e/meta
[community-simulator]: https://github.com/Emergent-Behaviors-in-Biology/community-simulator