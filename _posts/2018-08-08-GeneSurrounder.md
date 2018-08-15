---
published: true
title: "GeneSurrounder: Network-based identification of disease genes"
---

New technologies have made it possible to probe complex diseases and identify
genes for precision medicine. These technologies yield large datasets that
require advanced algorithms to extract useful information. Since genes interact
with one another, we seek specific genes that have an effect on the whole
system. However, existing tools either neglect interactions between genes, or
yield “pathway-level” results that are difficult to target. There is therefore a
need for algorithms that can precisely identify genes for treatment while taking
into account the interaction network.



To fill this gap, we present GeneSurrounder, a new algorithm that ranks genes
based on the evidence that they are sources of disruption on the network of
interacting genes. Since the effects of a “disruptive” source gene would
propagate outward in the interaction network, we find these genes by searching
for a telltale pattern of attenuating and correlated biological signal in the
data. We apply GeneSurrounder to three distinct ovarian cancer datasets and
demonstrate that the results are more reproducible than competing techniques. We
also find that our method is able to identify genes known to impact ovarian
cancer. These results suggest that GeneSurrounder is able to reproducibly detect
specific therapeutic gene targets.







