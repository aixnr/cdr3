---
title: "Monoclonal Antibody Cloning with SLIC"
last: "2022-09-24T09:30:00-04:00"
---

*Sequence and ligation independent cloning* (SLIC) is one of homology-based cloning methods[^hom].
The conventional restriction/ligation-based cloning requires insert and vector digested with matching restriction enzymes[^ddg] and then ligated *in vitro* with T4 DNA ligase before transforming ligated plasmid into competent *E. coli*.
Homology-based cloning allows construction of plasmid without being restricted[^rest] by compatible cut sites between vector and insert.
Tiller et al. 2008[^tiller] described an important advance in the field of human B cell immunology by outlining the protocol for antibody cloning.
Recently, Gieselmann et al. 2021[^gieselmann] described an improved antibody cloning method utilizing SLIC approach for cloning antibody into expression vectors.

This page outlines steps to construct monoclonal antibody expression vectors (heavy and light chains) by using published antibody sequences, adapted from Gieselmann et al. 2021.

##### Publicly Available Antibody Sequence

Sequences for monoclonal antibodies can be obtained from the following sources: (**I**) GenBank, (**II**) PDB, and (**III**) publications themselves.
PDB would be the best place to start.
PDB is primarily for crystal structure of monoclonal antibody bound to cognate antigen, but submissions include FASTA file with amino acid sequences for all of the polypeptide chains shown.
Moreover, availability of crystal structure means that the epitope is well-resolved[^wellresolved].
Importantly, monoclonal antibodies that are resolved often have high affinity binding to antigen, often in single or double-digit nanomolar range.

When accessing sequences, there are a few things to consider:

1. The host of which the monoclonal antibody was isolated from. Often time, sequences deposited came from human and rarely from other animal hosts.
2. The B cell subset which the BCR was cloned from. Monoclonal antibodies are often isolated from antibody-secreting cells (ASCs; CD27<sup>+</sup>CD38<sup>hi</sup>CD20<sup>--</sup>) and from memory B cells (CD27<sup>+</sup>IgD<sup>--</sup>).
3. Immunizing antigen(s) and immune history. For example, viral infection typically generates a broad response, whereas some vaccination generate a limited response.
4. IGHV mutational load, indicating the extent of somatic hypermutation and could be used to infer affinity against cognate antigen.

Once the sequences are identified, the next step would be to synthesize VH and VL fragments to clone into expression vectors.

##### AbVec Features

For cloning monoclonal antibody into mammalian expression vector, AbVec plasmids are one of the options.
AbVec empty plasmids are available on Addgene.

| AbVec       | Addgene #                  | REases               | Size (bp)
| :----       | ---------                  | ----                 | :-------
| Heavy, IgG1 | AbVec2.0-IGHG1; 80795      | EcoRI-HF / SalI-HF   | --
| Light, κ    | AbVec1.1-IGKC; 80796       | EcoRI-HF / BsiWI-HF  | --
| Light, λ    | AbVec1.1-IGLC2-XhoI; 99575 | EcoRI-HF / XhoI      | --

Note that AbVec plasmids listed here are for expressing human IgG1 antibody isotype.
For other isotypes and hosts, consider using [InvivoGen pFUSE plasmid system](https://www.invivogen.com/pfuse).

**AbVec2.0-IGHG1** includes heavy chain constant heavy (CH) region starting from amino acid sequence `STKGPSVFPLAP`[^heavych1].
It does not include signal peptide, thus VH insert has to include suitable signal peptide sequence[^signalpeptide].
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

[^wellresolved]: At 2 -- 3 Å resolution, the precise molecular interaction between antibody and antigen is resolved.

[^signalpeptide]: I have used signal peptides from *Gaussia* (G) luciferase. Others have used IL-2 signal peptide; some pFUSE plasmids include IL-2 as the signal peptide. Essentially, any *strong* signal peptide and verified with SignalP server would be fine for use.
