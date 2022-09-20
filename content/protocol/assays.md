---
title: "Assaying mAbs"
last: "2022-09-15T09:30:00-04:00"
---

Once an mAb is cloned into expression vectors (heavy and light chain vectors), the next steps include (**i**) cell transfection for protein production; (**ii**) protein purification & quality assessment; (**iii**) reactivity analyses; and (**iv**) functional analyses.
The aforementioned steps can be done in a week.

| Procedure | Description | Duration
| :-------- | :---------- | --------
| Transfection | -- | 3 -- 4 days
| Purification | -- | 1 day
| Quality assessment | -- | 1 day (same-day as purification)
| Reactivity analyses | -- | 1 day
| Functional analyses | -- | 1 -- 2 days

##### Transfection

It is often recommended to use suspension HEK293 cell line[^293sus] (e.g. 293F and Expi293) for their fast growth rate and more viable cells at a high cell density, which positively impact protein yield from transfection.
Generally for testing, I typically start with a small-scale transfection of 25 mL culture volume.
Once the protein passed all quality assessments, a large-scale transfection (200 mL) will follow.
This approach is mostly to save cost; failure at large-scale transfection is costly in term of reagent consumption[^expicost].
Since antibody is fairly stable[^abstability], the culture duration can go as long as 5 days.
However, 48--72 hours of transfection would yield plenty of antibody already.

For Expi293 cell line, the recommended transfection reagent is ExpiFectamine transfection kit.
However, many labs have tried other transfection reagents on Expi293 including PEI[^peiprice].
There is no special recommendation for transfection other than to follow manufacturer's recommended protocol.
At the end of transfection, collect culture supernatant by centrifugation and incubate the clarified supernatant in protein G[^proteing] resin overnight at 4 °C, shaking.

##### Purification

The next day, the resin:supernatant mixture is collected and washed with cold PBS.
This is usually done by using gravity-flow or spin columns.
As for the elution step, glycine-HCl (pH 3[^glyph]) is used to elute antibody from protein G resin and this is typically done in fractions (~500 µL), then tested for presence of protein with 20% Protein Assay (Bio-Rad cat. # 5000001).
Fractions with confirmed protein presence are then pooled, buffer-exchanged with PBS, and concentrated by using centrifugal filter[^amiconfilter].

##### Quality Assessment and Reactivity Analyses

- SDS-PAGE
- HPLC
- Nanodrop
- ELISA

##### Functional Analyses

- Neutralization
- Epitope testing

<!-- Footnotes -->

[^293sus]: Requires rotating shaker to be fitted inside a 37 °C cell culture incubator.

[^expicost]: I use Expi293<sup>TM</sup> for their superior yield. However, the reagents (culture medium and transfection reagent) are stupidly expensive. Performing side-by-side comparison between Expi293 and HEK293T (adherent) is difficult because the recommended transfection density at the same culture volume is different. 10 mL of HEK293T vs. 10 mL of Expi293 is not directly comparable, and often Expi293 would give 2--3x more protein yield simply because there are more cells and they grow faster.

[^abstability]: It has to circulate in your body, which runs at 37 °C for 24/7/365 (366 for leap year), that speaks a lot about its stability.

[^peiprice]: "Efficient and inexpensive transient expression of multispecific multivalent antibodies in Expi293 cells", [Xiaotian T. Fang et al. 2017](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5603040/) (*Biological Procedures Online*). To quote them, "*In this protocol, Expi293 cells are transfected instead with PEI (which costs **1/1000** as much as ExpiFectamine)*"

[^proteing]: Protein G is an immunoglobulin-binding protein. It is used to specifically pull IgG (all subclasses, most common hosts including human and mouse) from variety of sources, including culture supernatant (for protein purification) and from blood serum/plasma (for IgG enrichment). A shorter incubation period is possible, but I tend to do it overnight.

[^glyph]: Once the protein is confirmed (brown -> blue on 20% Protein Assay), neutralize with 1.5 M Tris (pH 8.8) at 1:20 ratio, i.e. 25 µL for each 500 µL fraction.

[^amiconfilter]: For example, Millipore-Sigma Amicon filter. Spin it really, really fast (4,000 -- 13,000 x g). You may need to experiment how long to let it run, depending on how concentrate you want your final protein solution to be at.
