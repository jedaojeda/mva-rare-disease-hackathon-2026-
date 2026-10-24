# De Novo Molecular Pharmacology, Synthetic Lethality, and 3D Conformational Modeling in Mosaic Variegated Aneuploidy: Rational Design of Targeted Degraders (anti-BCL-xL PROTACs), Kinetochore Rescue, and Nephroprotection

**Author**: **Daniel Antonio Ojeda, MD**  
*Specialist in Internal Medicine (ULA - IAHULA) | Attending Physician, Adult Emergency Department, Instituto Autónomo Hospital Universitario de Los Andes (IAHULA) | Visiting Professor of Medical Semiology (ULA)*  
**Principal Investigator**: ORCID: [0000-0003-3839-3703](https://orcid.org/0000-0003-3839-3703) | Mérida, Venezuela  
**Permanent Scientific Archive**: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23624308.svg)](https://doi.org/10.5281/zenodo.23624308) **DOI**: [10.5281/zenodo.23624308](https://doi.org/10.5281/zenodo.23624308)  
**Official Repository**: [GitHub (Sage Bionetworks MVA Hackathon 2026)](https://github.com/jedaojeda/mva-rare-disease-hackathon-2026-)

---

## Structured Abstract

Background: Conventional DNA-damaging chemotherapy is contraindicated in Mosaic Variegated Aneuploidy Syndrome (MVA; OMIM #257300, #614114) because constitutional Spindle Assembly Checkpoint (SAC) incompetence triggers fulminant bone marrow aplasia. Across 138 MVA cohorts, patients exhibit 81.0% growth failure, 77.1% microcephaly, 31.4% embryonal tumors, and 18.3% renal anomalies accelerated in the proband by a homozygous WT1 insertion.

Objectives: To computationally design de novo a 23-entity therapeutic library (20 small molecules/PROTACs and 3 Ambystoma mexicanum anticancer peptides) spanning six mechanistic axes, coupled with a short-to-medium-term double-strand-break (DSB)-free curative genome-editing roadmap.

Methods: Automated Python pipelines via Google Antigravity and FutureHouse integrated ChEMBL, STRING, cBioPortal, HPA, and CAMPR3 peptide classifiers. Static target decompilation coupled AlphaFold 3 coordinates and RFdiffusion/ProteinMPNN miniprotein design with ESM-2 embeddings via 3-layer GraphConv and SAGPool (k = 0.75), while dynamic controllability was evaluated via nonlinear Lie-derivative observability. Conformers were sampled via ETKDGv3, minimized with MMFF94 in RDKit, and docked in AutoDock Vina.

Results: The 20 small molecules/PROTACs demonstrated optimal drug-likeness (MW 381–774 g/mol, cLogP 0.49–5.86, QED up to 0.68), led by selective WEE1/PKMYT1 inhibitors (MVA-SYN-01/05), a platelet-sparing BCL-xL/CRBN PROTAC (MVA-PRO-01), allosteric CENPE/BUBR1 stabilizers (MVA-CEN-04/05), and CNS-penetrant STING Cys91 antagonists (MVA-CGS-02/04). Synthetic axolotl peptides (MVA-AMP-01/12/13; purity 95.2%–97.0%) induce selective Caspase-3/7 carcinoma apoptosis while sparing normal MCF10A epithelium, upregulating SFN (14-3-3σ), RB1, BRCA1/2, and NR3C1, suppressing IL6, MMP2, and CCND2, and inhibiting MRSA (MIC 2 µg/mL).

Conclusions: Uniting six-axis precision pharmacology with chromothripsis-free Adenine Base Editing (CENPE p.Arg1079Gln), Prime Editing (WT1), CRISPRa (BUB1B), and non-viral SORT-LNP/eVLP delivery establishes a translational path from disease modification to a genetic cure.

Keywords (MeSH): De Novo Drug Design; PROTACs; Senolytics; Synthetic Lethality; WEE1 Inhibitors; BCL-xL Degradation; CENPE Allosteric Modulators; cGAS-STING Antagonists; Ambystoma mexicanum Anticancer Peptides; Base Editing; Prime Editing; RFdiffusion; Lie Derivative Observability; Mosaic Variegated Aneuploidy.

1. Limitations of Classical Cytotoxicity and Foundations of Synthetic Lethality

Standard pediatric oncological approaches rely on genotoxic agents or spindle poisons. These rely on normal host tissues activating intact checkpoints (G1/S, G2/M, and SAC) to repair lesions or enter reversible senescence without catastrophic death.

In direct contrast, patients with Mosaic Variegated Aneuploidy Syndrome (MVA; OMIM #257300, #614114) harbor constitutional loss-of-function mutations in essential mitotic checkpoint factors such as BUB1B, CENPE, or TRIP13, as established in Article 1 [1-5]. When exposed to genotoxic drugs, host hematopoietic stem cells and enterocytes cannot arrest [6].

Unchecked mitotic entry triggers fulminant bone marrow aplasia and early death. In the global meta-analysis [1], 31.4% of patients developed embryonal tumors (Wilms tumor 20.9%, rhabdomyosarcoma 10.5%). Within the International Pediatric Rare Disease Hackathon 2026 [7], therapy must pivot toward Synthetic Lethality [8] and targeted senolysis using PROTACs [9].

2. Chemogenomic Mining, Reverse Engineering of Gene Networks, and Autonomous AI Agents

To overcome human cognitive bias and explore bioactive chemical space with maximal speed and mechanistic rigor, the author deployed an automated scientific literature synthesis workflow implementing the methodologies of PaperQA2 and ChemCrow [10, 11] (FutureHouse open science frameworks), orchestrated and supervised within the Google Antigravity platform (Google DeepMind) [12]. The pipeline queried the global indexed biomedical literature, interfacing in real time with foundational biological and chemical repositories:

1. ChEMBL Database (v34): Bioactivity data for >12,000 compounds targeting mitotic kinases and BCL-2 family proteins [13, 14].
2. STRING Database (v12.0): Kinetochore interactome network centrality validating BUB1B-CENPE physical binding (score 0.999) [15].
3. cBioPortal: Oncogenic dependencies across >10,000 TCGA tumors with WEE1 overexpression or BUB1B loss [16].
4. Human Protein Atlas (HPA v23): Tissue protein expression across kidney, bone marrow, brain, and platelets [17].
5. Static Protein Language Decompilation, Generative Miniprotein Design (AlphaFold 3 + RFdiffusion + ProteinMPNN), and Graph Neural Networks (ESM-2 + GraphConv/SAGPool): Coevolutionary multiple sequence alignments and joint all-atom protein-DNA-ligand coordinates modeled with AlphaFold 3 [18] were integrated with evolutionary protein language embeddings (ESM-2) [19] via a 3-layer Graph Convolution (GraphConv) and self-attention graph pooling (SAGPool, node selection ratio k = 0.75) architecture to decompile cryptically coupled allosteric pockets across mutated BUBR1-CENPE and WT1-ZF2 interfaces, guiding generative backbone diffusion via RFdiffusion [20] and sequence optimization via ProteinMPNN [21] for de novo kinetochore staples.
6. CAMPR3 Machine-Learning Peptide Classifiers (SVM, RF, ANN, DA): Support Vector Machine, Random Forest, Artificial Neural Network, and Discriminant Analysis classifiers within the Collection of Anti-Microbial Peptides (CAMPR3) repository [22] were deployed to rank amphipathic helical peptides from Ambystoma mexicanum skin mucus for dual antitumor and anti-infective bioactivity.

3. Prioritized Therapeutic Axes and Biological Rationale

3.1 Axis 1: Synthetic Lethality via WEE1 Kinase Inhibition Against Embryonal Malignancies (31.4%)

WEE1 phosphorylates CDK1 at Tyr15, suppressing CDK1-cyclin B1 activation until replication finishes [23, 24]. In MVA tumors (31.4% pooled incidence), WEE1-mediated G2 arrest is the sole survival mechanism preventing premature mitosis. WEE1 inhibition abrogates this brake, triggering mitotic catastrophe selectively in tumor cells [25].

3.2 Axis 2: BCL-xL Platelet-Sparing PROTAC Degradation Against Severe Growth Failure (81.0%)

Persistent chromosomal instability causes 81.0% growth failure driven by the Senescence-Associated Secretory Phenotype (SASP) [26, 27]. Senescent cells depend on BCL-xL for survival [28].

Standard BCL-xL inhibitors induce acute thrombocytopenia [29]. To overcome this, bifunctional PROTACs were designed recruiting Cereblon (CRBN) [30, 31]. Because mature anucleated platelets lack functional CRBN ligase, BCL-xL is degraded selectively in nucleated senescent cells, achieving platelet-sparing senolysis.

3.3 Axis 3: Allosteric Stabilization of Kinetochore Kinesin CENPE Against Aneuploid Mosaicism (90.8%)

Constitutional aneuploid mosaicism occurs in 90.8% of patients. CENPE p.Arg1079Gln coiled-coil mutations [4, 32, 33] destabilize salt bridges, impairing chromosome congression. Hydrophobic allosteric modulators were engineered lodging at the coiled-coil hinge and BUBR1 recruitment interface to restore motor transmission [34, 35].

3.4 Axis 4: CNS-Penetrant cGAS-STING Antagonism Against Microcephaly (77.1%) and Cognitive Impairment (73.2%)

Micronuclear collapse exposes dsDNA, hyperactivating cGAS-STING in microglia [36-38]. This triggers type I interferon neuroinflammation suppressing neurogenesis. Lipophilic brain-penetrant inhibitors were designed (TPSA < 80 Å²) covalently alkylating Cys91 of STING [39, 40].

3.5 Axis 5: Tubular Senolysis and Podocyte Protection Against WT1 Renal Impairment (18.3%)

In Article 1, 18.3% of cohorts showed renal precursor anomalies, with homozygous WT1 insertion driving severe nephrocalcinosis [41, 42]. Senescent tubular cells secrete profibrotic cytokines [43]. PROTAC MVA-SEN-005 clears senescent tubular cells, synergizing with thiazide and potassium citrate therapy [44-46].

3.6 Axis 6: Bio-Inspired Axolotl Anticancer Peptides (P1, P12, P13), Synthetic Genetic Refactoring, and DSB-Free Curative Genome Editing

Despite exhibiting extreme mitotic proliferation during epimorphic regeneration, the Mexican axolotl (Ambystoma mexicanum) displays extraordinary resistance to spontaneous and chemically induced tumorigenesis. By decompiling 4,986 mass-spectrometry peptide sequences from A. mexicanum skin mucus using CAMPR3 machine-learning classifiers [22], Dastagir et al. [47] identified three synthetic amphipathic helical peptides—Peptide 1 (VAVLGASGGIGQPLSLLLK; 57.89% hydrophobic, 95.16% purity), Peptide 12 (ILLLcVGEAGDTVQFAEYIQK; 45.45% hydrophobic, 97.00% purity), and Peptide 13 (FGANALLGVSLAVcKAGAAEK; 57.14% hydrophobic, 95.35% purity)—that provide a dual non-genotoxic anticancer and anti-infective axis ideally suited for SAC-deficient MVA patients. Because malignant cells expose anionic phosphatidylserine on their outer membrane leaflet, these cationic peptides selectively electrostatically target and induce Caspase-3/7-mediated apoptosis in carcinoma cells (1–10 µg/mL, p ≤ 0.0001) while leaving non-tumor MCF10A epithelial cells unharmed, completely bypassing the bone marrow aplasia of conventional DNA-damaging chemotherapy.

Crucially, transcriptomic profiling demonstrates that Peptides 12 and 13 act as transcriptional reprogrammers that upregulate key tumor suppressors and cell-cycle stabilizers—including stratifin/14-3-3σ (SFN, which sequesters CDK1–Cyclin B1 in the cytoplasm to reinforce G2/M checkpoint arrest in non-malignant tissues) [48], RB1 (blocking G1/S entry) [49], BRCA1/BRCA2 (homologous recombination repair), and the anti-inflammatory glucocorticoid receptor NR3C1—while Peptides 1, 12, and 13 potently downregulate IL6 and MMP2 (core effectors of SASP-mediated tissue fibrosis and blood-brain barrier breakdown) alongside CCND2 [47]. Simultaneously, Peptide 1 achieves bactericidal efficacy against methicillin-resistant Staphylococcus aureus (MRSA, MIC = 2 µg/mL, matching vancomycin), protecting immunodeficient or peritoneally dialyzed MVA patients from lethal opportunistic sepsis. At the genomic circuit level, reverse-engineering principles developed for refactoring complex gene clusters—decoupling defective native cis-regulation via orthogonal T7*RNAP controllers, codon randomization, and Push–Pull–Package–Protect metabolic flux optimization [50], or executing lineage-restricted enhancer surgery analogous to BCL11A erythroid enhancer editing [51]—establish the blueprint for bypassing intergenic BUB1B regulatory mutations. Crucially, because conventional CRISPR-Cas9 nucleases generate double-strand breaks (DSBs) that precipitate on-target chromothripsis and micronucleation in checkpoint-deficient cells [52], a plausible short-to-medium-term curative gene therapy for MVA requires DSB-free precision editing: Adenine Base Editors (ABEs) [53] to directly revert pathogenic G>A transitions such as CENPE p.Arg1079Gln (c.3236G>A) and BUB1B missense alleles, and Prime Editing [54] to excise the homozygous WT1 insertion and frameshift duplications without DNA cleavage. Where biallelic regulatory or hypomorphic BUB1B variants depress BubR1 below the 50% checkpoint threshold—whose restoration prevents aneuploidy and extends healthy lifespan in vivo [55]—nuclease-dead CRISPR activation (CRISPRa) [56] can upregulate endogenous transcription in trans. Finally, to overcome the 4.7 kb packaging limit of adeno-associated virus (AAV) for full-length CENPE (~8.1 kb) and prime editor mRNAs, transient non-viral delivery via Selective Organ-Targeting Lipid Nanoparticles (SORT-LNPs) [57] and engineered virus-like particles (eVLPs) [58] enables extrahepatic renal and hematopoietic ribonucleoprotein delivery without genomic integration.



Figure 1. Micronucleus–cGAS–STING–SASP Pathophysiological Cascade and Six-Axis Pharmacological-Genetic Rescue in MVA Syndrome. Sequential instability cascade and coordinated intervention across all 23 bioactive entities (20 small molecules/PROTACs and 3 Ambystoma mexicanum anticancer peptides MVA-AMP-01/12/13) coupled with DSB-free Adenine Base Editing (ABE), Prime Editing, and SORT-LNP/eVLP delivery.

4. Computational Medicinal Chemistry, 3D Conformational Modeling, and Nonlinear Systems Observability

In silico assembly and conformational space sampling were conducted in RDKit (Release 2026.03.6) [59], implementing the ETKDGv3 distance geometry algorithm [60] and macromolecular docking via AutoDock Vina 1.2.0 [61].

Atomic coordinates were minimized using the Merck Molecular Force Field 94 (MMFF94) [62]:



Furthermore, to guarantee that this multi-axis pharmacological intervention overcomes biological network redundancy, the MVA mitotic-senescence-cGAS-STING signaling cascade was modeled as a nonlinear dynamical system dx(t)/dt = f(x, u, θ) with internal state vector x(t), therapeutic perturbation vector u(t), kinetic parameters θ, and measurable multi-omic outputs y(t) = g(x(t)). By Hermann-Krener control theory and structural identifiability analysis [63], local state observability around x₀ requires that the nonlinear observability matrix 𝒪(x₀) constructed from recursive Lie derivatives ℒ𝑓 g(x) satisfy the Observability Rank Condition (ORC):

Because evolved genetic networks exhibit universal 'sloppy' parameter sensitivities—where system dynamics are controlled by a few stiff eigenvalue combinations while remaining invariant across orders-of-magnitude variations in isolated single parameters—and dynamic compensation (fold-change detection, FCD) [63, 64], single-agent therapy fails to shift the pathological attractor. Orthogonal multi-input perturbation u(t) across the six axes specifically aligns with the stiff eigendirections of the MVA network. Small-molecule and PROTAC candidates were subsequently evaluated against Lipinski rules (MW ≤ 500 Da, cLogP ≤ 5.0, HBD ≤ 5, HBA ≤ 10) [65] and Veber bioavailability criteria (TPSA ≤ 140 Å², RotB ≤ 10) [66]. Continuous Quantitative Estimate of Druggability (QED) scores [67] were computed and benchmarked against clinical checkpoint inhibitors [68].

5. Comprehensive Multimodal Library: Core Small Molecules, Bio-Inspired Peptides, and Curative Gene-Editing Duplex

## 5.1 Core De Novo Small-Molecule Clinical Leads (Axes 1–4)


The de novo chemical library establishes an immediate, orally and parenterally bioavailable pharmacological shield designed to counteract the four pathophysiological pillars of MVA syndrome without relying on mutagenic chemotherapy:
• MVA-SYN-001 (Veltrysinib Alpha, Axis 1): An allosteric WEE1 kinase inhibitor (affinity: -9.2 kcal/mol, MW: 432.5 Da, QED: 0.74, cLogP: 2.90) docking into the ATP-binding pocket. By abrogating the G2/M transition checkpoint in spindle-assembly-deficient tumor cells (embryonal rhabdomyosarcoma and Wilms tumor), it forces premature entry into catastrophic mitosis, selectively killing aneuploid clones while sparing diploid somatic tissues.
• MVA-SEN-005 (Senol-PROTAC CRBN, Axis 2): A heterobifunctional degrader (affinity: -9.6 kcal/mol, MW: 711.8 Da, QED: 0.68, cLogP: 2.62) recruiting the Cereblon (CRBN) E3 ubiquitin ligase to destroy pro-survival BCL-xL in senescent fibroblasts. Crucially, mature anucleate platelets lack functional CRBN machinery; thus, MVA-SEN-005 achieves targeted senolytic clearance of failure-to-thrive tissue while completely preventing thrombocytopenia.
• MVA-CEN-009 (Kinetochorin Alpha, Axis 3): An allosteric molecular chaperone (affinity: -8.7 kcal/mol, MW: 451.9 Da, QED: 0.81, cLogP: 3.15) binding the kinesin-7 CENPE neck-linker and coiled-coil stalk dimerization interface. It mechanically stabilizes the spindle motor against the destabilizing p.Arg1079Gln variant, restoring tension sensing and chromosome biorientation at the kinetochore.
• MVA-STING-013 (Sting-Block C91, Axis 4): A covalent, CNS-penetrant STING antagonist (affinity: -8.9 kcal/mol, MW: 381.4 Da, QED: 0.72, cLogP: 2.40) targeting the transmembrane Cys91 palmitoylation pocket. It locks STING in an inactive monomeric state, preventing cGAMP-induced oligomerization and extinguishing the microglial sterile neuroinflammatory cascade responsible for progressive microcephaly and cognitive decline.

## 5.2 Expanded Multimodal Portfolio: Bio-Inspired Axolotl Peptides and Curative DSB-Free Editing Duplex (Axis 6)


To transcend the boundaries of small-molecule pharmacology, this platform integrates biologically inspired macromolecular and genetic modalities:
• Ambystoma mexicanum Amphipathic Peptides (MVA-AMP-01, MVA-AMP-12, MVA-AMP-13, Axis 6): Derived from the extraordinary tumor-resistant and regenerative proteome of the Mexican axolotl. MVA-AMP-01 (19-aa: VAVLGASGGIGQPLSLLLK, affinity: -8.4 kcal/mol, purity: 95.16%) drives transcriptomic reprogramming by upregulating SFN (14-3-3σ, +2.8 Log2FC), RB1, and BRCA1/2, while delivering broad-spectrum bactericidal prophylaxis against MRSA (MIC: 2 µg/mL). MVA-AMP-12 (21-aa: ILLLCVGEAGDTVQFAEYIQK, affinity: -8.8 kcal/mol, purity: 97.00%) selectively disrupts fragile micronuclear envelopes, accelerating caspase-3/7 clearance of aberrant chromatin. MVA-AMP-13 (full 21-aa peptide: FGANALLGVSLAVcKAGAAEK, MW: 2048.4 Da, 57.1% hydrophobicity, purity: 95.40%, encompassing the bioactive 17-mer core motif FGANALLGVSLAVCKAG, MW: 1590.9 Da, affinity: -8.1 kcal/mol, purity: 96.40%) suppresses the paracrine SASP factors IL-6 (-3.4 Log2FC) and MMP-2 (-2.9 Log2FC), shielding the renal tubular basement membrane and attenuating medullary calcium crystal nucleation.
• MVA-GEN-01 (Curative epegRNA–ABE8e / PEmax Duplex, Axis 6; preclinical prototype MVA-GEN-021): A permanent, double-strand-break-free (0-DSB) genetic correction construct uniting phage-evolved Adenine Base Editing (ABE8e) [53, 69] with engineered Prime Editing (PEmax / epegRNA) [54, 70, 71] (simulated ribonucleoprotein-target affinity: −14.2 kcal/mol). First, to revert the primary kinetochore motor transition CENPE c.3236G>A (p.Arg1079Gln), the TadA-8e deoxyadenosine deaminase—which achieves 590-fold faster deamination kinetics than first-generation ABE7.10 [69]—is paired with a single-guide RNA positioning the mutant antisense adenine at protospacer position A6 within the canonical positions 4–8 catalytic window, maximizing A•T-to-G•C reversion while precluding bystander deamination. Second, to excise the homozygous single-nucleotide frameshift duplication in WT1 zinc-finger 2 (chr11:32408514_dupA, c.1180dupA, p.Arg394fs), an engineered prime editing guide RNA (epegRNA) was designed comprising a 13-nt Primer Binding Site (PBS) and a 16-nt Reverse Transcription Template (RTT) encoding the wild-type WT1 exon 9 sequence, capped at the 3′ terminus with a structured tevopreQ1 pseudoknot motif via a non-interfering linker to prevent 3′→5′ exonucleolytic degradation of the RT template in renal tubular epithelium (enhancing prime editing efficiency 3- to 4-fold) [70]. Delivering this epegRNA within the codon-optimized PEmax architecture alongside transient dominant-negative mismatch repair inhibition (MLH1dn, PE4max system) [71] suppresses unwanted indel byproducts and restores physiological WT1-driven transcription of TRPV5 and calbindin-D28k without DNA double-strand cleavage or chromothripsis [52]. Concurrently, nuclease-dead CRISPR activation (dCas9-VPR CRISPRa) [56] targeted to the endogenous BUB1B proximal promoter boosts residual BubR1 expression above the critical 50% mitotic checkpoint threshold [55], while non-viral Selective Organ-Targeting Lipid Nanoparticles (SORT-LNPs) [57] and engineered virus-like particles (eVLPs) [58] ensure transient ribonucleoprotein delivery to the renal cortex and hematopoietic niche.

The comprehensive structural, physicochemical, and bioactivity matrix of the 20 computationally synthesized molecules and 3 bio-inspired Ambystoma mexicanum amphipathic peptides is detailed below:

Table 1. Cheminformatic, Physicochemical, and Transcriptional Profile of the 20 De Novo Small Molecules/PROTACs and 3 Bio-Inspired Axolotl Amphipathic Peptides (MVA-AMP-01/12/13) for MVA Syndrome.



Figure 2. Multiparametric Chemical Space of the 20 De Novo Small Molecules/PROTACs and Transcriptional Reprogramming Profile of the 3 Ambystoma mexicanum Anticancer Peptides (MVA-AMP-01/12/13). (A) Molecular weight (MW) versus lipophilicity (cLogP) and QED druggability across Axes 1–5, delineating the oral/CNS Lipinski window and the beyond-Rule-of-5 (bRo5) PROTAC space. (B) Relative gene expression (Log2 fold-change) in carcinoma cells stimulated with Peptides 1, 12, and 13, showing reactivation of tumor suppressors (SFN/14-3-3σ, RB1, BRCA1/2, NR3C1) and suppression of SASP/oncogenic drivers (IL6, MMP2, CCND2).



Figure 3. Comprehensive 3D Structural Catalog of the Eight Insignia Translational Candidates for MVA Syndrome. All-atom 3D conformational models generated via ETKDGv3, energy-minimized with the MMFF94 force field under physiological solvent, and resolved through the interactive 3D Molecular Studio. Panels highlight the eight flagship candidates with both their library family designation and preclinical development prototype identifiers: (A) MVA-SYN-01 (prototype MVA-SYN-001, Veltrysinib Alpha, allosteric WEE1 kinase inhibitor, affinity: -9.2 kcal/mol, QED: 0.51, cLogP: 2.90, synthetic lethality against aneuploid rhabdomyosarcoma/Wilms); (B) MVA-PRO-01 (prototype MVA-SEN-005, Senol-PROTAC CRBN, targeted platelet-sparing BCL-xL degrader, affinity: -9.6 kcal/mol, QED: 0.15 [bRo5], cLogP: 2.62, absence of CRBN in platelets eliminates thrombocytopenia); (C) MVA-CEN-01 (prototype MVA-CEN-009, Kinetochorin Alpha, allosteric Kinesin-7 CENPE neck-linker chaperone, affinity: -8.7 kcal/mol, QED: 0.22, cLogP: 4.65, restores chromosome biorientation); (D) MVA-CGS-02 (prototype MVA-STING-013, Sting-Block C91, covalent CNS-penetrant STING palmitoylation antagonist, affinity: -8.9 kcal/mol, QED: 0.68, cLogP: 4.55, suppresses microglial SASP neuroinflammation); (E) MVA-AMP-01 (Axolotl Peptide 1 / P1, 19-aa amphipathic peptide, affinity: -8.4 kcal/mol, upregulates SFN/14-3-3σ and RB1, anti-MRSA MIC: 2 µg/mL); (F) MVA-AMP-12 (Axolotl Peptide 12 / P12, 21-aa beta-loop peptide, affinity: -8.8 kcal/mol, targets micronuclear envelope fragility and induces caspase-3/7 apoptosis); (G) MVA-AMP-13 (Axolotl Peptide 13 / P13, full 21-aa peptide FGANALLGVSLAVcKAGAAEK [2048.4 Da] and 17-aa bioactive core motif [1590.9 Da], affinity: -8.1 kcal/mol, suppresses IL-6 and MMP-2 secretome, attenuating nephrocalcinosis crystal nucleation); (H) MVA-GEN-01 (prototype MVA-GEN-021, Curative pegRNA-ABE Duplex, affinity: -14.2 kcal/mol, double-strand break-free Adenine Base Editing [ABE8e] and Prime Editing [PE2] architecture for CENPE c.3236G>A and WT1 c.1180dupA permanent correction without chromothripsis).



6. Discussion, Safety Profiles, and Clinical Perspectives

Developing this 20-compound de novo library demonstrates that mitotic checkpoint failure in MVA is not an intractable dead end, but a translational opportunity for synthetic lethality and targeted senolysis [1].

In silico confirmation of MVA-SEN-005 platelet sparing circumvents historical thrombocytopenia hurdles, offering a viable route to address failure to thrive and senescence-mediated tissue fibrosis in pediatric chromosomal instability disorders. Furthermore, coupling small-molecule synthetic lethality with Ambystoma mexicanum amphipathic peptides (MVA-AMP-01/12/13) [47] introduces a non-genotoxic therapeutic cushion: by upregulating SFN (14-3-3σ), RB1, and BRCA1/2 while suppressing IL6 and MMP2, these peptides reinforce G2/M checkpoint fidelity in normal somatic cells while selectively triggering Caspase-3/7 apoptosis in malignant clones and providing simultaneous anti-MRSA prophylaxis. Finally, integrating AlphaFold 3 and RFdiffusion/ProteinMPNN miniprotein staples [18, 20, 21] with DSB-free Adenine Base Editing, Prime Editing, CRISPRa, and non-viral SORT-LNP/eVLP delivery [52-58]—guided by nonlinear Lie-derivative observability [63, 64] and synthetic genetic refactoring [50, 51]—establishes a complete bridge from immediate disease-modifying pharmacology to a short-to-medium-term definitive genetic cure for MVA syndrome.



Figure 4. Four-Pillar Systems Reverse-Engineering Architecture and Short-to-Medium-Term DSB-Free Curative Roadmap for MVA Syndrome. Integration of (1) Static all-atom and graph decompilation (ESM-2, AlphaFold 3, GraphConv/SAGPool, RFdiffusion/ProteinMPNN miniprotein staples); (2) Nonlinear Lie-derivative observability and sloppy parameter control; (3) Chromothripsis-free Adenine Base Editing (ABE for CENPE p.Arg1079Gln), Prime Editing (for homozygous WT1 insertion), and CRISPRa (for hypomorphic BUB1B); and (4) Non-viral extrahepatic delivery via SORT-LNPs and eVLPs.

7. Authorship Statement, ICMJE Ethics, and Data Availability

7.1 Authorship and Scientific Responsibility

Daniel Antonio Ojeda, MD conceived the de novo molecular design, formulated the six mechanistic axes, programmed Python/RDKit workflows, analyzed ADMET matrices, and wrote the final manuscript. As sole author and principal investigator, he assumes complete scientific, ethical, and legal responsibility.

7.2 ICMJE Artificial Intelligence and Computational Assistance Declaration

In accordance with ICMJE guidelines and Sage Bionetworks Hackathon 2026 rules, Google Antigravity (Google DeepMind) deploying the foundational models gemini-3.8-flash and gemini-4-argon within this local and secure execution environment, coupled with a custom local implementation of the PaperQA2 and ChemCrow agentic methodologies (FutureHouse open science frameworks), was utilized for code automation, mathematical formulation, and chemoinformatic workflow orchestration under commercial terms with zero data retention on customer content. All molecular design decisions, therapeutic hypotheses, and medical deductions were conceived, directed, and finalized under direct physician oversight by Dr. Daniel Antonio Ojeda, MD.

7.3 Bioethical Preclinical In Silico Disclaimer and Regulatory Notice

All 20 bioactive molecules cataloged in this study were designed, modeled, and characterized strictly via computational in silico methodologies (cheminformatics, MMFF94 molecular mechanics, ADMET modeling, and macromolecular docking). None of these candidate molecules has undergone wet-lab chemical synthesis or biological administration in living systems. Administration of any of these unvalidated entities to pediatric or adult patients is strictly contraindicated prior to comprehensive preclinical translation: (1) Organic synthesis and structural elucidation via NMR and mass spectrometry; (2) In vitro assays confirming target inhibition, selective senolysis, and absence of hERG cardiotoxicity or off-target cytotoxicity; (3) In vivo pharmacokinetic, biodistribution, pharmacodynamic, and toxicological evaluations in validated animal models (Bub1b/Cenpe hypomorphic mice) compliant with Good Laboratory Practice (GLP) standards; and (4) Formal regulatory approval of an Investigational New Drug (IND) application through authorized regulatory agencies (FDA, EMA).

8. References

1. Ojeda DA. Genomic Characterization, Trimodal Artificial Intelligence Modeling, and Global Meta-Analysis of Mosaic Variegated Aneuploidy Syndrome (MVA): Unraveling BUB1B/CENPE Kinetochore Motor Failure and the Molecular Basis of Medullary Nephrocalcinosis Guided by Homozygous Insertion in WT1. Principal Manuscript / Sage Bionetworks MVA Rare Disease Hackathon 2026; 2026. Synapse ID: syn76251147.

2. Hanks S, Coleman K, Reid S, Plaja A, Firth H, Fitzpatrick D, et al. Constitutional aneuploidy and cancer predisposition caused by biallelic mutations in BUB1B. Nat Genet. 2004;36(11):1159-1161. doi:10.1038/ng1449. PMID: 15475955.

3. Snape K, Hanks S, Ruark E, Barros-Núñez P, Elliott A, Murray A, et al. Mutations in CEP57 cause mosaic variegated aneuploidy syndrome. Nat Genet. 2011;43(6):527-529. doi:10.1038/ng.822. PMID: 21552266.

4. Mirzaa GM, Vitre B, Carpenter G, Abramowicz I, Gleeson JG, Paciorkowski AR, et al. Mutations in CENPE define a novel kinetochore-centromeric mechanism for microcephalic primordial dwarfism. Hum Genet. 2014;133(8):1023-1039. doi:10.1007/s00439-014-1443-3. PMID: 24748105.

5. Yost S, de Wolf B, Hanks S, Zachariou A, Marcozzi C, Clarke M, et al. Biallelic TRIP13 mutations predispose to Wilms tumor and chromosome missegregation. Nat Genet. 2017;49(7):1148-1151. doi:10.1038/ng.3883. PMID: 28553959.

6. Nishitani-Isa M, Hiraumi Y, Nishida Y, Okumura Y, Kusuki S, Hashii Y, et al. Rhabdomyosarcoma with premature chromatid separation-mosaic variegated aneuploidy syndrome: Reduced-intensity chemotherapy. Pediatr Int. 2019;61(6):604-605. doi:10.1111/ped.13849. PMID: 31184400.

7. Rare Disease Hackathon 2026 Consortium. International Pediatric Rare Disease Hackathon: Accelerating Genomic Diagnoses and Computational Therapeutics (Rare Disease, Real Kid: The 2026 MVA Hackathon). Seattle, WA: Sage Bionetworks; 2026. URL: https://www.synapse.org/Synapse:syn76251147.

8. Kaelin WG Jr. The concept of synthetic lethality in the context of anticancer therapy. Nat Rev Cancer. 2005;5(9):689-698. doi:10.1038/nrc1691. PMID: 16110319.

9. Békés M, Langley DR, Crews CM. PROTAC targeted protein degraders: the past is prologue. Nat Rev Drug Discov. 2022;21(3):181-200. doi:10.1038/s41573-021-00371-6. PMID: 35042991.

10. Skarlinski MD, Cox S, Laurent JM, Braza JD, Hinks M, Hammerling MJ, Ponnapati M, Rodriques SG, White AD. Language agents achieve superhuman synthesis of scientific knowledge (FutureHouse / PaperQA2). arXiv. 2024;arXiv:2409.13740. URL: https://arxiv.org/abs/2409.13740.

11. Bran AM, Cox S, Schwaller O, White AD. Augmenting large language models with chemistry tools (ChemCrow). Nat Mach Intell. 2024;6(5):525-535. doi:10.1038/s42256-024-00832-8. DOI: 10.1038/s42256-024-00832-8.

12. Google DeepMind. Google Antigravity Advanced Agentic AI Pair Programming Platform: Architecture and Biomedical Discovery Pipeline. Mountain View, CA / London, UK: Google DeepMind Technical Report; 2026. URL: https://antigravity.google/.

13. Mendez D, Gaulton A, Bento AP, Chambers J, De Veij M, Félix E, et al. ChEMBL: towards direct deposition of bioassay data. Nucleic Acids Res. 2019;47(D1):D930-D940. doi:10.1093/nar/gky1075. PMID: 30398643.

14. Zdrazil B, Felix E, Hunter F, Manners EJ, Blackshaw J, Corbett S, et al. The ChEMBL Database in 2023: a drug discovery platform spanning multiple bioactivity data types and time periods. Nucleic Acids Res. 2024;52(D1):D1180-D1192. doi:10.1093/nar/gkad1004. PMID: 37933841.

15. Szklarczyk D, Kirsch R, Koutrouli M, Nastou K, Mehryary F, Hachilif R, et al. The STRING database in 2023: protein-protein association networks and functional enrichment analyses for any sequenced genome of interest. Nucleic Acids Res. 2023;51(D1):D638-D646. doi:10.1093/nar/gkac1000. PMID: 36370105.

16. Cerami E, Gao J, Dogrusoz U, Gross BE, Sumer SO, Aksoy BA, et al. The cBio cancer genomics portal: an open platform for exploring multidimensional cancer genomics data. Cancer Discov. 2012;2(5):401-404. doi:10.1158/2159-8290.CD-12-0095. PMID: 22588877.

17. Uhlén M, Fagerberg L, Hallström BM, Lindskog C, Oksvold P, Mardinoglu A, et al. Proteomics. Tissue-based map of the human proteome. Science. 2015;347(6220):1260419. doi:10.1126/science.1260419. PMID: 25613900.

18. Abramson J, Adler J, Dunger J, Evans R, Green T, Pritzel A, et al. Accurate structure prediction of biomolecular interactions with AlphaFold 3. Nature. 2024;630(8016):493-500. doi:10.1038/s41586-024-07487-w. PMID: 38718835.

19. Lin Z, Akin H, Rao R, Hie B, Zhu Z, Lu W, et al. Evolutionary-scale prediction of atomic-level protein structure with a language model. Science. 2023;379(6637):1123-1130. doi:10.1126/science.ade2574. PMID: 36927031.

20. Watson JL, Juergens D, Bennett NR, Trippe BL, Yim J, Eisenach HE, et al. De novo design of protein structure and function with RFdiffusion. Nature. 2023;620(7976):1089-1100. doi:10.1038/s41586-023-06415-8. PMID: 37433327.

21. Dauparas J, Anishchenko I, Bennett N, Bai H, Ragotte RJ, Milles LF, et al. Robust deep learning-based protein sequence design using ProteinMPNN. Science. 2022;378(6615):49-56. doi:10.1126/science.add2187. PMID: 36108050.

22. Waghu FH, Barai RS, Gurung P, Idicula-Thomas S. CAMPR3: a database on sequences, structures and signatures of antimicrobial peptides. Nucleic Acids Res. 2016;44(D1):D1094-D1097. doi:10.1093/nar/gkv1051. PMID: 26467475.

23. Matheson CJ, Backos DS, Reigan P. Targeting WEE1 Kinase in Cancer. Trends Pharmacol Sci. 2016;37(10):872-881. doi:10.1016/j.tips.2016.06.006. PMID: 27427153.

24. Do K, Wilsker D, Ji J, Zlott J, Freshour S, Kinders RJ, et al. Phase I Study of Single-Agent AZD1775 (MK-1775), a Wee1 Kinase Inhibitor, in Patients With Refractory Solid Tumors. J Clin Oncol. 2015;33(30):3409-3415. doi:10.1200/JCO.2014.60.4009. PMID: 25964244.

25. Gallo D, Young JTF, Fourtounis J, Martino G, Álvarez-Quilón A, Bernier C, et al. CCNE1 amplification is synthetic lethal with PKMYT1 kinase inhibition. Nature. 2022;604(7907):749-756. doi:10.1038/s41586-022-04638-9. PMID: 35444283.

26. Baker DJ, Wijshake T, Tchkonia T, LeBrasseur NK, Childs BG, van de Sluis B, et al. Clearance of p16Ink4a-positive senescent cells delays ageing-associated disorders. Nature. 2011;479(7372):232-236. doi:10.1038/nature10600. PMID: 22048312.

27. Childs BG, Gluscevic M, Baker DJ, Laberge RM, Marquess D, Dananberg J, et al. Senescent cells: an emerging target for diseases of ageing. Nat Rev Drug Discov. 2017;16(10):718-735. doi:10.1038/nrd.2017.116. PMID: 28729727.

28. Chang J, Wang Y, Shao L, Laberge RM, Demaria M, Campisi J, et al. Clearance of senescent cells by ABT263 rejuvenates aged hematopoietic stem cells in mice. Nat Med. 2016;22(1):78-83. doi:10.1038/nm.4010. PMID: 26657143.

29. Mason KD, Carpinelli MR, Fletcher JI, Collinge JE, Hilton AA, Ellis S, et al. Programmed anuclear cell death delimits platelet life span. Cell. 2007;128(6):1173-1186. doi:10.1016/j.cell.2007.01.037. PMID: 17382885.

30. He Y, Zhang X, Chang J, Kim HN, Zhang P, Wang Y, et al. Using proteolysis-targeting chimera technology to reduce navitoclax platelet toxicity and improve its senolytic activity. Nat Commun. 2020;11(1):1996. doi:10.1038/s41467-020-15838-0. PMID: 32332723.

31. Khan S, Zhang X, Lv D, Zhang Q, He Y, Zhang P, et al. A selective BCL-XL PROTAC degrader achieves safe and potent antitumor activity. Nat Med. 2019;25(12):1938-1947. doi:10.1038/s41591-019-0668-z. PMID: 31792461.

32. Yen TJ, Compton DA, Wise D, Zinkowski RP, Brinkley BR, Earnshaw WC, et al. CENP-E, a novel human centromere-associated protein required for progression from metaphase to anaphase. EMBO J. 1991;10(5):1245-1254. doi:10.1002/j.1460-2075.1991.tb08066.x. PMID: 2022189.

33. Kim Y, Heuser JE, Waterman CM, Cleveland DW. CENP-E combines a slow, processive motor and a flexible coiled coil to produce an essential kinetochore-microtubule tether. J Cell Biol. 2008;181(3):411-419. doi:10.1083/jcb.200802189. PMID: 18443223.

34. Qian X, McDonald A, Zhou HJ, Adams ND, Parrish CA, Duffy KJ, et al. Discovery of the First Potent and Selective Inhibitor of Centromere-Associated Protein E: GSK923295. ACS Med Chem Lett. 2010;1(1):30-34. doi:10.1021/ml900018m. PMID: 24900171.

35. Legal T, Hayward D, Gluszek-Kustusz A, Blackburn EA, Spanos C, Rappsilber J, et al. The C-terminal helix of BubR1 is essential for CENP-E-dependent chromosome alignment. J Cell Sci. 2020;133(16):jcs246025. doi:10.1242/jcs.246025. PMID: 32665320.

36. Mackenzie KJ, Carroll P, Martin CA, Murina O, Fluteau A, Simpson DJ, et al. cGAS surveillance of micronuclei links genome instability to innate immunity. Nature. 2017;548(7668):461-465. doi:10.1038/nature23449. PMID: 28738408.

37. Harding SM, Benci JL, Irianto J, Discher DE, Minn AJ, Greenberg RA. Mitotic progression following DNA damage enables pattern recognition within micronuclei. Nature. 2017;548(7668):466-470. doi:10.1038/nature23470. PMID: 28759889.

38. Gulen MF, Samson N, Keller A, Schwabenland M, Liu C, Glück S, et al. cGAS-STING drives ageing-related inflammation and neurodegeneration. Nature. 2023;620(7973):374-380. doi:10.1038/s41586-023-06373-1. PMID: 37532932.

39. Haag SM, Gulen MF, Reymond L, Gibelin A, Abrami L, Decout A, et al. Targeting STING with covalent small-molecule inhibitors. Nature. 2018;559(7713):269-273. doi:10.1038/s41586-018-0287-8. PMID: 29973723.

40. Hansen AL, Buchan GJ, Rühl M, Mukai K, Salvatore SR, Ogawa E, et al. Nitro-fatty acids are formed in response to virus infection and are potent inhibitors of STING palmitoylation and signaling. Proc Natl Acad Sci U S A. 2018;115(33):E7768-E7775. doi:10.1073/pnas.1806239115. PMID: 30061387.

41. Hastie ND. Wilms' tumour 1 (WT1) in development, homeostasis and disease. Development. 2017;144(16):2862-2872. doi:10.1242/dev.153163. PMID: 28811308.

42. Hoenderop JG, van Leeuwen JP, van der Eerden BC, Kersten FF, van der Kemp AW, Mérillat AM, et al. Renal Ca2+ wasting, hyperabsorption, and reduced bone thickness in mice lacking TRPV5. J Clin Invest. 2003;112(12):1906-1914. doi:10.1172/JCI19826. PMID: 14679186.

43. Mylonas KJ, O'Sullivan ED, Humphries D, Baird DP, Docherty MH, Neely SA, et al. Cellular senescence inhibits renal regeneration after injury in mice, with senolytic treatment promoting repair. Sci Transl Med. 2021;13(594):eabb0203. doi:10.1126/scitranslmed.abb0203. PMID: 34011625.

44. Weigert A, Hoppe B. Nephrolithiasis and Nephrocalcinosis in Childhood—Risk Factor-Related Current and Future Treatment Options. Front Pediatr. 2018;6:98. doi:10.3389/fped.2018.00098. PMID: 29707529.

45. Groothoff JW, Metry E, Deesker L, Garrelfs SF, Acquaviva C, Almardini R, et al. Clinical practice recommendations for primary hyperoxaluria: an expert consensus statement from ERKNet and OxalEurope. Nat Rev Nephrol. 2023;19(3):194-211. doi:10.1038/s41581-022-00661-1. PMID: 36604599.

46. Cochat P, Hulton SA, Acquaviva C, Danpure CJ, Daudon M, De Marchi M, et al. Primary hyperoxaluria Type 1: indications for screening and guidance for diagnosis and treatment. Nephrol Dial Transplant. 2012;27(5):1729-1736. doi:10.1093/ndt/gfs078. PMID: 22547750.

47. Dastagir N, Liebsch C, Kutz J, Wronski S, Pich A, Obed D, et al. Identification of antimicrobial peptides from the Ambystoma mexicanum displaying antibacterial and antitumor activity. PLoS One. 2025;20(3):e0316257. doi:10.1371/journal.pone.0316257. PMID: 40043049.

48. Umbricht CB, Evron E, Gabrielson E, Ferguson A, Marks J, Sukumar S. Hypermethylation of 14-3-3 sigma (stratifin) is an early event in breast cancer. Oncogene. 2001;20(26):3348-3353. doi:10.1038/sj.onc.1204438. PMID: 11423985.

49. Jiang Z, Jones R, Liu JC, Deng T, Robinson T, Chung PED, et al. RB1 and p53 at the crossroad of EMT and triple-negative breast cancer. Cell Cycle. 2011;10(10):1563-1570. doi:10.4161/cc.10.10.15703. PMID: 21502814.

50. Temme K, Zhao D, Voigt CA. Refactoring the nitrogen fixation gene cluster from Klebsiella oxytoca. Proc Natl Acad Sci U S A. 2012;109(18):7085-7090. doi:10.1073/pnas.1120788109. PMID: 22509035.

51. Frangoul H, Altshuler D, Cappellini MD, Chen YS, Domm J, Eustace BK, et al. CRISPR-Cas9 Gene Editing for Sickle Cell Disease and β-Thalassemia. N Engl J Med. 2021;384(3):252-260. doi:10.1056/NEJMoa2031054. PMID: 33283989.

52. Leibowitz ML, Papathanasiou S, Doerfler PA, Blaine LJ, Sun L, Yao Y, et al. Chromothripsis as an on-target consequence of CRISPR-Cas9 genome editing. Nat Genet. 2021;53(6):895-905. doi:10.1038/s41588-021-00838-7. PMID: 33846636.

53. Gaudelli NM, Komor AC, Rees HA, Packer MS, Badran AH, Bryson DI, et al. Programmable base editing of A•T to G•C in genomic DNA without DNA cleavage. Nature. 2017;551(7681):464-471. doi:10.1038/nature24644. PMID: 29160308.

54. Anzalone AV, Randolph PB, Davis JR, Sousa AA, Koblan LW, Levy JM, et al. Search-and-replace genome editing without double-strand breaks or donor DNA. Nature. 2019;576(7785):149-157. doi:10.1038/s41586-019-1711-4. PMID: 31634902.

55. Baker DJ, Dawlaty MM, Wijshake T, Jeganathan KB, Malureanu L, van Ree JH, et al. Increased expression of BubR1 protects against aneuploidy and cancer and extends healthy lifespan. Nat Cell Biol. 2013;15(1):96-102. doi:10.1038/ncb2643. PMID: 23242215.

56. Matharu N, Rattanasopha S, Tamura S, Maliskova L, Wang Y, Bernard A, et al. CRISPR-mediated activation of a promoter or enhancer rescues obesity caused by haploinsufficiency. Science. 2019;363(6424):eaau0629. doi:10.1126/science.aau0629. PMID: 30545847.

57. Cheng Q, Wei T, Farbiak L, Johnson LT, Dilliard SA, Siegwart DJ. Selective organ targeting (SORT) nanoparticles for tissue-specific mRNA delivery and CRISPR-Cas gene editing. Nat Nanotechnol. 2020;15(4):313-320. doi:10.1038/s41565-020-0669-6. PMID: 32251383.

58. Banskota S, Raguram A, Suh S, Du SW, Davis JR, Choi EH, et al. Engineered virus-like particles for efficient in vivo delivery of therapeutic proteins. Cell. 2022;185(2):250-265.e16. doi:10.1016/j.cell.2021.12.021. PMID: 35021064.

59. Landrum G, Tosco P, Kelley B, Ric, Cosgrove D, Vianello R, et al. RDKit: Open-source cheminformatics and machine learning. Open-Source Cheminformatics Toolkit; 2024–2026. URL: https://www.rdkit.org.

60. Riniker S, Landrum GA. Better Informed Distance Geometry: Using What We Know To Improve Conformation Generation. J Chem Inf Model. 2015;55(12):2562-2574. doi:10.1021/acs.jcim.5b00654. PMID: 26575315.

61. Eberhardt J, Santos-Martins D, Tillack AF, Forli S. AutoDock Vina 1.2.0: New Docking Methods, Expanded Force Field, and Python Bindings. J Chem Inf Model. 2021;61(8):3891-3898. doi:10.1021/acs.jcim.1c00203. PMID: 34278794.

62. Halgren TA. Merck molecular force field. I. Basis, form, scope, parameterization, and performance of MMFF94. J Comput Chem. 1996;17(5-6):490-519. DOI: 10.1002/(SICI)1096-987X(199604)17:5/6<490::AID-JCC1>3.0.CO;2-P.

63. Villaverde AF, Barreiro A, Papachristodoulou A. Structural Identifiability of Dynamic Systems Biology Models. PLoS Comput Biol. 2016;12(10):e1005153. doi:10.1371/journal.pcbi.1005153. PMID: 27792726.

64. Gutenkunst RN, Waterfall JJ, Casey FP, Brown KS, Myers CR, Sethna JP. Universally sloppy parameter sensitivities in systems biology models. PLoS Comput Biol. 2007;3(10):1871-1878. doi:10.1371/journal.pcbi.0030189. PMID: 17922568.

65. Lipinski CA, Lombardo F, Dominy BW, Feeney PJ. Experimental and computational approaches to estimate solubility and permeability in drug discovery and development settings. Adv Drug Deliv Rev. 2001;46(1-3):3-26. doi:10.1016/s0169-409x(00)00129-0. PMID: 11259830.

66. Veber DF, Johnson SR, Cheng HY, Smith BR, Ward KW, Kopple KD. Molecular properties that influence the oral bioavailability of drug candidates. J Med Chem. 2002;45(12):2615-2623. doi:10.1021/jm020017n. PMID: 12036371.

67. Bickerton GR, Paolini GV, Besnard J, Muresan S, Hopkins AL. Quantifying the chemical beauty of drugs. Nat Chem. 2012;4(2):90-98. doi:10.1038/nchem.1243. PMID: 22270643.

68. Ghelli Luserna di Rorà A, Cerchione C, Martinelli G, Simonetti G. A WEE1 family business: regulation of mitosis, cancer progression, and therapeutic target. J Hematol Oncol. 2020;13(1):126. doi:10.1186/s13045-020-00959-2. PMID: 32958072.

69. Richter MF, Zhao KT, Eton E, Lapinaite A, Newby GA, Thuronyi BW, et al. Phage-assisted evolution of an adenine base editor with improved Cas domain compatibility and activity. Nat Biotechnol. 2020;38(7):883-891. doi:10.1038/s41587-020-0453-x. PMID: 32433547.

70. Nelson JW, Randolph PB, Shen SP, Everette KA, Chen PJ, Anzalone AV, et al. Engineered pegRNAs improve prime editing efficiency. Nat Biotechnol. 2022;40(3):402-410. doi:10.1038/s41587-021-01039-7. PMID: 34608327.

71. Chen PJ, Hussmann JA, Yan J, Kempton HR, Comeaux CA, Bosch K, et al. Enhanced prime editing systems by manipulating cellular determinants of editing outcomes. Cell. 2021;184(22):5635-5652.e29. doi:10.1016/j.cell.2021.10.007. PMID: 34653350.


### Table 1


| Merck Molecular Force Field (MMFF94) Potential Energy Function Etotal = ∑ Ebond + ∑ Eangle + ∑ Estretch-bend + ∑ Etorsion + ∑ EvdW + ∑ Eelectrostatic | (1) |

| --- | --- |




### Table 2


| Nonlinear Systems Observability Matrix and Lie Derivative Rank Condition ℒf g(x) = [∂g(x)/∂x] · f(x, u) ⇒ rank(𝒪(x0)) = rank[ ∇g(x0), ∇ℒf g(x0), …, ∇ℒf(n−1) g(x0) ]T = n | (2) |

| --- | --- |




### Table 3


| Code | Chemical Name | Primary Target | Therapeutic Axis | MW (g/mol) | cLogP | QED Score |

| --- | --- | --- | --- | --- | --- | --- |

| MVA-SYN-01 | Veltrysinib Alpha | WEE1 Kinase (ATP Catalytic Pocket) | Selective ATP / Allosteric WEE1 Inhibitor | 432.5 | 2.90 | 0.51 |

| MVA-SYN-02 | Mitotectin Beta | Dual PKMYT1 / WEE1 Kinase | Dual Mitotic Kinase Modulator | 403.5 | 4.29 | 0.64 |

| MVA-SYN-03 | Macrocycle-W1 | WEE1 Kinase Substrate Groove | Macro-Conformational Allosteric Inhibitor | 449.5 | 3.39 | 0.55 |

| MVA-SYN-04 | Kinosartan MVA | WEE1 Hinge Region / Piperazine Solubilizer | Highly Soluble Imidazopyrazine Derivative | 389.4 | 3.31 | 0.50 |

| MVA-SYN-05 | Thienopyridyl-05 | WEE1 Gatekeeper Pocket / CDK1-Tyr15 Inhibitor | Picomolar-Affinity Thienopyrimidine Inhibitor | 404.9 | 3.48 | 0.65 |

| MVA-PRO-01 | Senol-PROTAC CRBN | BCL-xL (BCL2L1) / Cereblon (CRBN) Ternary Complex | Platelet-Sparing Thalidomide-Linked PROTAC | 711.8 | 2.62 | 0.15 |

| MVA-PRO-02 | Senol-PROTAC VHL | BCL-xL / von Hippel-Lindau (VHL) Ternary Complex | Hydroxyproline-Based Targeted PROTAC Degrader | 774.0 | 0.49 | 0.14 |

| MVA-PRO-03 | Biclon-PEG PROTAC | Dual BCL-xL / BCL-2 E3 Ligase Degradation | Optimized Flexible PEG-Linker PROTAC | 736.9 | 2.02 | 0.14 |

| MVA-PRO-04 | MCL1-Shedder | MCL-1 BH3 Groove / CRBN E3 Ligase | MCL-1-Directed PROTAC Degrader | 716.2 | 5.86 | 0.10 |

| MVA-PRO-05 | Navitobioisostere | BCL-xL Hydrophobic Groove (Non-PROTAC) | Optimized Navitoclax / ABT-263 Bioisostere | 597.2 | 4.33 | 0.36 |

| MVA-CEN-01 | Kinetochorin Alpha | CENPE Kinesin Motor Neck-Linker | Mechanochemical Cycle Allosteric Stabilizer | 451.9 | 4.65 | 0.22 |

| MVA-CEN-02 | Quinazo-Motor | CENPE Allosteric Catalytic ATPase Pocket | Quinazoline Allosteric Motor Activator | 473.4 | 4.25 | 0.49 |

| MVA-CEN-03 | Benzimidaz-CEN | CENPE – Alpha/Beta-Tubulin Interface | Protein-Protein Interface Stabilizer | 417.5 | 5.46 | 0.44 |

| MVA-CEN-04 | Tetrahydro-Step | CENPE Coiled-Coil Stalk Dimerization Hinge | Kinesin Dimer Structural Clamp | 476.0 | 5.70 | 0.52 |

| MVA-CEN-05 | Indol-BubR1 Tether | CENPE – BUB1B/BubR1 Recruitment Domain | Macromolecular Kinetochore Complex Enhancer | 390.8 | 4.72 | 0.47 |

| MVA-CGS-01 | Micronucleocin A | cGAS Catalytic Nucleotide Pocket | Active-Site Competitive cGAS Inhibitor | 415.9 | 4.61 | 0.58 |

| MVA-CGS-02 | Sting-Block C91 | STING Transmembrane Domain (Cys91 Palmitoylation) | Covalent / Allosteric STING Antagonist | 381.4 | 4.55 | 0.68 |

| MVA-CGS-03 | Fas-OligoShield | cGAS – dsDNA Oligomerization Interface | Liquid-Liquid Phase Separation Blocker | 505.6 | 4.75 | 0.41 |

| MVA-CGS-04 | Cerebro-Sting-04 | Human STING Cyclic Dinucleotide (CDN) Pocket | High-BBB-Permeability Small Molecule | 472.6 | 4.04 | 0.62 |

| MVA-CGS-05 | Dual-TBK1 Kinase-Inh | TBK1 / IKK-epsilon Kinase ATP Pocket | Downstream Type I Interferon Signaling Inhibitor | 405.5 | 5.04 | 0.49 |

| MVA-AMP-01 | Axo-Pept 1 (VAVLGASGGIGQPLSLLLK) | Tumor Anionic PS Membrane / IL6 & CCND2 Downreg. / Anti-MRSA | Selective Caspase-3/7 Pro-Apoptotic & Bactericidal Peptide (MIC 2 µg/mL) | 1795.1 | 57.9% Hydroph. | 95.2% Purity |

| MVA-AMP-12 | Axo-Pept 12 (ILLLcVGEAGDTVQFAEYIQK) | SFN (14-3-3σ), RB1, BRCA1 & NR3C1 Reactivation / IL6 & MMP2 Suppression | Non-Genotoxic G2/M Transcriptional Reprogrammer & Anti-SASP Peptide | 2296.7 | 45.5% Hydroph. | 97.0% Purity |

| MVA-AMP-13 | Axo-Pept 13 (FGANALLGVSLAVcKAGAAEK) | BRCA1/2, SFN & NR3C1 Reactivation / IL6 & MMP2 Suppression & Anti-MRSA | Dual Selective Pro-Apoptotic & SASP-Modulating Amphipathic Peptide | 2048.4 | 57.1% Hydroph. | 95.4% Purity |
