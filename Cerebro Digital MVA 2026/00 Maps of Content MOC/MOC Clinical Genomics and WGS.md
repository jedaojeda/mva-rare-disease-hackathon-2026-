---
aliases: [MOC Genomics, WGS MOC, Track 1 MOC]
tags: [moc, genomics, track1, wgs, bub1b]
author: Daniel Antonio Ojeda, MD
date: 2026-10-23
---

# 🧬 MOC: Clinical Genomics and Whole Genome Sequencing (Track 1)

This Map of Content articulates the end-to-end genomic workflow performed across the 85.0 GB raw Illumina NovaSeq 6000 sequencing reads (FASTQ) and high-confidence variant calls (VCF) of the index proband (`PROBAND01` / `WGS_EX2312012`).

---

## 🎯 Causal Genomic Architecture

* [[BUB1B Compound Heterozygous Causal Architecture]]: The biological foundation of MVA1 syndrome.
* [[Maternal Variant chr15 40209701 T G]]: Nonsense/truncating stop-gain mutation in BUBR1 kinase domain (p.Arg407Ter).
* [[Paternal Variant chr15 40220612 T G]]: Missense modifier in BUB3/Cdc20 MCC-binding interface.
* [[Official 100 out of 100 SageBio Benchmark]]: Groundtruth validation against the clinically confirmed answer key.

---

## 🔍 Modifier and Co-Segregating Loci

* [[Kinetochore Modifier CENPE p.Arg1079Gln]]: Coiled-coil motor stalk mechanical disruption and tension loss.
* [[Oncogenic Driver WT1 ZF2 Insertion p.Arg394fs]]: Zinc-finger insertion driving medullary nephrocalcinosis and Wilms predisposition.
* [[Master Catalog 10 Prioritized Variants]]: Comprehensive 10-candidate matrix with EPCR scores and phenotypic rationales.

---

## 🔬 Multi-Lane Sequencing Quality Audit

* Cumulative sequencing depth $>140\times$ across critical mitotic checkpoint loci.
* Base-by-base quality audit with `fastp` multithreading ($>94.0\%$ Q30 across all 8 NovaSeq lanes).
* Sambamba mark-duplicates and Sentieon/GATK4 variant filtration referenced to GRCh38 (no-alt analysis set).
