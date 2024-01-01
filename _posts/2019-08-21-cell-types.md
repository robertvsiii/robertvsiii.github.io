---
layout: "post"
categories: research
permalink: /:categories/cell-types
title: Mathematical tools for improving stem cell protocols
date: 2019-08-21 00:00:02
featured-image: projections.png
featured-image-alt: Projections
---

Induced pluripotent stem cells (iPSC’s) have generated considerable excitement for the future of regenerative medicine. Since these cells can be generated directly from readily accessible somatic patient cells, they can be used to grow new tissues and eventually organs with no risk of immune rejection. Coaxing the cells to differentiate into the desired tissue remains a major challenge, and the development of effective protocols is hampered by the fact that the success or failure of a given attempt is difficult to determine until the cells are delivered to a host. 

Information about the cell type is already encoded in the gene expression levels as soon as the protocol is complete, however, and my colleagues have developed [a reliable method][lap] for extracting this, based on the linear algebra of non-orthogonal projections. I have recently completed a project with [Laertis Ikonomou][laertis] and his colleagues at the BU Center for Regenerative Medicine, using this method to help develop protocols for generating lung cells {% cite ikonomou2020vivo %}. 

### References

{% bibliography --cited %}

[laertis]: https://ikonomoulab.com/
[lap]: https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003734
