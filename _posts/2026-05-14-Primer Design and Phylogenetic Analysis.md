# Primer Design and Phylogenetic Analysis of *Nemalion elminthoides*

## Introduction

This GitHub post documents a bioinformatics workflow for algal species identification and phylogenetic analysis using the red alga *Nemalion elminthoides* as the target organism. The workflow included sequence retrieval from NCBI, multiple sequence alignment, primer design using Primer3, primer verification using Primer-BLAST, and phylogenetic tree construction using MEGA.

The selected barcode gene was rbcL, which is commonly used for algal species identification and phylogenetic reconstruction.

---

## Objectives

The objectives of this workflow were:

1. To retrieve rbcL sequences of *Nemalion elminthoides* and related red algal species from NCBI.
2. To align the sequences using ClustalW in MEGA.
3. To design primers for amplification of a region of the rbcL gene.
4. To verify the primer pair using Primer-BLAST.
5. To construct a phylogenetic tree using MEGA.
6. To interpret the relationship between *Nemalion elminthoides* and related red algal taxa.

---

## Target Organism and Gene

Target organism: *Nemalion elminthoides*  
Gene: rbcL  
Database: NCBI Nucleotide  
Analysis tools: NCBI, Primer3, Primer-BLAST, MEGA  

---

## Sequence Retrieval from NCBI

The NCBI Nucleotide database was used to retrieve rbcL sequences. The target sequence was *Nemalion elminthoides* KP238497.1. Additional rbcL sequences from related red algal taxa were downloaded for comparison and phylogenetic analysis.

| Species | Gene | Accession number | Sequence type | Database |
|---|---|---|---|---|
| *Nemalion elminthoides* | rbcL | KP238497.1 | partial cds; chloroplast | NCBI Nucleotide |
| *Actinotrichia robusta* | rbcL | KC609400.1 | partial cds; plastid | NCBI Nucleotide |
| *Actinotrichia fragilis* | rbcL | KC609399.1 | partial cds; plastid | NCBI Nucleotide |
| *Actinotrichia robusta* | rbcL | KC609393.1 | partial cds; plastid | NCBI Nucleotide |
| *Liagora ceranoides* | rbcL | JX878367.1 | partial cds; chloroplast | NCBI Nucleotide |

Screenshot to add:
<img width="1077" height="377" alt="Screenshot 2026-05-14 124343" src="https://github.com/user-attachments/assets/a31e681e-5d9d-4694-b073-c9bd4373cc95" />

---

## Multiple Sequence Alignment

The five rbcL sequences were imported into MEGA and aligned using ClustalW. The alignment was used for phylogenetic tree construction and to evaluate sequence similarity among the selected taxa.

Alignment settings:

| Parameter | Setting |
|---|---|
| Software | MEGA |
| Alignment method | ClustalW |
| Sequence type | DNA |
| Number of taxa | 5 |
| Gene | rbcL |

Screenshot to add:
<img width="1296" height="363" alt="Screenshot 2026-05-14 124521" src="https://github.com/user-attachments/assets/1afd8859-8971-4706-a9c3-41c06cccac70" />

---

## Primer Design

Primer design was performed using the clean rbcL sequence of *Nemalion elminthoides* KP238497.1. Because the shared alignment region among all five taxa was limited, primer design was performed using the target organism sequence directly. The selected primers were then checked using Primer-BLAST.

Primer3 selected the following primer pair:

| Primer | Sequence 5′→3′ | Strand | Length | Start | Stop | Tm | GC% | Product length |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Forward primer | GACATGCGCTTACCTGTAGC | Plus | 20 | 337 | 356 | 59.07°C | 55.00% | 230 bp |
| Reverse primer | CGCATGAACGGTTGAGAGTT | Minus | 20 | 566 | 547 | 58.85°C | 50.00% | 230 bp |

The selected primer pair amplifies a predicted 230 bp region of the rbcL gene. Both primers were 20 bp long, had similar melting temperatures, and had suitable GC contents.

Screenshot to add:
<img width="1106" height="561" alt="Screenshot 2026-05-14 124704" src="https://github.com/user-attachments/assets/01524e62-d126-4205-86a8-6d49257839d1" />

---

## Primer-BLAST Verification

The primer pair was checked using NCBI Primer-BLAST. The expected PCR product length was 230 bp. Primer-BLAST confirmed the primer pair positions on the target rbcL sequence.

Primer-BLAST summary:

| Parameter | Result |
|---|---|
| Forward primer | GACATGCGCTTACCTGTAGC |
| Reverse primer | CGCATGAACGGTTGAGAGTT |
| Forward primer position | 337–356 |
| Reverse primer position | 566–547 |
| Product length | 230 bp |
| Target gene | rbcL |
| Target organism | *Nemalion elminthoides* |

Screenshot to add:
<img width="1697" height="190" alt="Screenshot 2026-05-14 124943" src="https://github.com/user-attachments/assets/efeba762-220c-470a-9203-a253cb5d5caa" />

---

## Phylogenetic Tree Construction

The aligned rbcL sequences were used to construct a phylogenetic tree in MEGA. The tree was generated using the Neighbor-Joining method. Bootstrap analysis was performed with 1000 replications.

The original course protocol recommended the Kimura 2-parameter model. However, in this dataset, MEGA could not compute the Kimura 2-parameter distance matrix for all sequence pairs. Therefore, the final tree was reconstructed using the p-distance model.

Tree construction parameters:

| Parameter | Setting |
|---|---|
| Software | MEGA |
| Tree method | Neighbor-Joining |
| Test of phylogeny | Bootstrap method |
| Bootstrap replications | 1000 |
| Substitution model | p-distance |
| Rates among sites | Uniform rates |
| Gaps/missing data treatment | Pairwise deletion |

---

## Phylogenetic Tree Result

<img width="944" height="356" alt="Nemalion_rbcL_phylogenetic_tree_bootstrap" src="https://github.com/user-attachments/assets/545a30d7-f0ca-4bc8-b5fc-ffda74bfea14" />

The phylogenetic tree separated the selected red algal taxa into two main supported groups. *Nemalion elminthoides* clustered with *Liagora ceranoides* with a bootstrap value of 100, indicating strong support for this relationship. *Actinotrichia fragilis* clustered with one *Actinotrichia robusta* sequence, also with a bootstrap value of 100. The second *Actinotrichia robusta* sequence appeared as a separate branch.

These results suggest that *Nemalion elminthoides* is more closely related to *Liagora ceranoides* than to the selected *Actinotrichia* sequences in this rbcL-based analysis.

---

## Conclusion

This workflow demonstrated a complete bioinformatics approach for algal species identification and phylogenetic analysis. The rbcL gene sequence of *Nemalion elminthoides* was used to design primers with Primer3, and the resulting primer pair was verified using Primer-BLAST. The primer pair produced a predicted 230 bp amplicon with suitable melting temperature and GC content.

A phylogenetic tree was constructed using MEGA based on five rbcL sequences. The tree showed that *Nemalion elminthoides* clustered strongly with *Liagora ceranoides*, while the *Actinotrichia* sequences formed a separate group. Overall, this analysis supports the usefulness of the rbcL gene for primer design and phylogenetic reconstruction in red algae.
