---
title: "Monoclonal Antibody Cloning with SLIC"
last: "2022-09-15T09:30:00-04:00"
---

*Sequence and ligation independent cloning* (SLIC) is one of homology-based cloning methods[^hom].
The conventional restriction/ligation-based cloning requires insert and vector digested with matching restriction enzymes[^ddg] and then ligated *in vitro* with T4 DNA ligase before transforming ligated plasmid into competent *E. coli*.
Homology-based cloning allows construction of plasmid without being restricted[^rest] by compatible cut sites between vector and insert.
Tiller et al. 2008[^tiller] described an important advance in the field of human B cell immunology by outlining the protocol for antibody cloning.
Recently, Gieselmann et al. 2021[^gieselmann] described an improved antibody cloning method utilizing SLIC approach for cloning antibody into expression vectors.

This page outlines steps to construct monoclonal antibody expression vectors (heavy and light chains) by using published antibody sequences, adapted from Gieselmann et al. 2021.

##### Publicly Available Antibody Sequence

<!-- 
- Typical size of the inserts, and associated cost
-->

Something here

##### AbVec Features

AbVec empty plasmids are available on Addgene.

| AbVec       | Addgene #                  | REases               | Size (bp)
| :----       | ---------                  | ----                 | :-------
| Heavy, IgG1 | AbVec2.0-IGHG1; 80795      | EcoRI-HF / SalI-HF   | --
| Light, κ    | AbVec1.1-IGKC; 80796       | EcoRI-HF / BsiWI-HF  | --
| Light, λ    | AbVec1.1-IGLC2-XhoI; 99575 | EcoRI-HF / XhoI      | --

Note that AbVec plasmids listed here are for expressing human IgG1 antibody isotype.
For other isotypes and hosts, consider using [InvivoGen pFUSE plasmid system](https://www.invivogen.com/pfuse).

**AbVec2.0-IGHG1** includes heavy chain constant heavy (CH) region starting from amino acid sequence `STKGPSVFPLAP`[^heavych1].
It does not include signal peptide, thus VH insert has to include suitable signal peptide sequence.
A double-digestion with **EcoRI-HF** & **SalI-HF** linearizes this heavy chain plasmid before VH insertion by SLIC.
On a VH insert, include 5' upstream homology `aactgcacctcggttctatcgattgaattc` (before signal peptide) and 3' downstream homology `tcgaccaagggcccaagcgtcttccccctggcaccc`.

<!-- Image example -->

Similarly, **AbVec1.1-IGKC** does not include signal peptide.
A double-digestion with **EcoRI-HF** & **BsiWI-HF** linearizes this κ light chain plasmid before κ VL insertion by SLIC.
This digestions yields linearized vector that includes CDRL3 amino acid `RTV` and followed by κ constant light (CL κ) amino acid `AAPSV`. 
On κ VL insert, include 5' upstream homology `SEQUENCE HERE` (before signal peptide) and 3' downstream homology `SEQUENCE HERE`.

<!-- Image example -->

##### Antibody F(Ab) Oligo Inserts

Something here

<!-- Footnotes -->

[^hom]: As opposed to the conventional restriction/ligation-based cloning. There are many homology-based cloning protocols, including SLIC (as outlined here), NEBuilder HiFi, Takara In-Fusion, etc. SLIC is cost-effective, requiring T4 DNA polymerase (not T4 DNA ligase) to prepare the insert(s) fragment and linearized vector before transforming into competent *E. coli*. Read this review: [Jake F. Watson & Javier García-Nafría 2019](https://doi.org/10.1074/jbc.REV119.009109) (*JBC*).

[^ddg]: Usually in double-digest restriction with a pair of restriction endonucleases (REases) in compatible reaction buffer. God forbid if you need to use 1 REase, because then you will have to screen for insert with the right orientation. 

[^rest]: *Hehe*, pun intended.

[^tiller]: "Efficient generation of monoclonal antibodies from single human B cells by single cell RT-PCR and expression vector cloning", [Thomas Tiller et al. 2008](https://doi.org/10.1016/j.jim.2007.09.017) (*Journal of Immunological Methods*).

[^gieselmann]: "Effective high-throughput isolation of fully human antibodies targeting infectious pathogens", [Lutz Gieselmann et al. 2021](https://doi.org/10.1038/s41596-021-00554-w) (*Nature Protocols*).

[^heavych1]: Human IgG1 heavy chain constant region CH1 starts with `ASTK` amino acid sequence. The heavy chain empty does not include `A` amino acid. Most likely, a full plasmid with VH inserted leads to loss of **SalI** cut site. However, **ApaI** cut site can be used to linearize full plasmid (EcoRI/ApaI combination is CutSmart compatible) to replace VH insert with a new insert to generate a new construct.
