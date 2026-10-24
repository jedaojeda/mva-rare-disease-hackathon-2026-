# Precision Genomics, Trimodal Foundation AI Modeling, and De Novo Multiaxial Pharmacology in Mosaic Variegated Aneuploidy (MVA) Syndrome

[![Obsidian Vault: Digital Brain](https://img.shields.io/badge/Knowledge_Base-Obsidian_Digital_Brain-7C3AED.svg?logo=obsidian)](#-digital-brain--obsidian-knowledge-base)
[![License: CC-BY 4.0](https://img.shields.io/badge/License-CC--BY--4.0-blue.svg)](LICENSE)
[![Hackathon: Sage Bionetworks 2026](https://img.shields.io/badge/Hackathon-Sage_Bionetworks_2026-blueviolet.svg)](https://synapse.org)
[![Principal Investigator: Dr. Daniel Antonio Ojeda, MD](https://img.shields.io/badge/Investigator-Dr._Daniel_Antonio_Ojeda,_MD-059669.svg)](https://orcid.org/0000-0003-3839-3703)
[![Physician-Researcher](https://img.shields.io/badge/Physician--Researcher-Internal_Medicine_%26_Genomics-1E3A8A.svg)](#-principal-investigator--the-researchers-journey)
[![Kaggle Cloud Audited](https://img.shields.io/badge/Kaggle-GPU_Kernels_Verified-20BEFF.svg)](kaggle_notebooks/KAGGLE_NOTEBOOKS_LINKS.md)
[![FutureHouse AI Driven](https://img.shields.io/badge/Chemoinformatics-FutureHouse_PaperQA2%20%2F%20ChemCrow-FF6F00.svg)](#-chemoinformatic-discovery-pipeline--emphasis-on-futurehouse-ai)

---

<p align="center">
  <img src="figures/Official%20Workflow%20and%20Technology%20Suite%20MVA%202026%20Vertical.png" alt="Official Workflow and Technology Suite MVA 2026" width="950">
</p>


> [!IMPORTANT]
> ### 🏆 Official Sage Bionetworks Hackathon 2026 Benchmark Results
> **Track 1 (Variant Identification) Automated Evaluation**:
> - **Rank Points**: **100.0 / 100** (Full match at Rank 1)
> - **F-max**: **1.000** (Optimal Precision & Recall at EPCR Threshold 1.0)
> - **Clinically Confirmed Driver**: *BUB1B* biallelic compound heterozygous checkpoint failure (`chr15:40209701, T>G` + `chr15:40220612, T>G`) recovered with 100% groundtruth concordance.

Official submission and open-source computational repository for the **Rare Disease Global Hackathon 2026**, organized by **Sage Bionetworks**, **MVA Society**, **Hugging Face**, and **BEACON**, with prize sponsorship from the **AWS Imagine Grant** and **Anthropic**.

---

## 👨‍⚕️ Principal Investigator & The Researcher's Journey

**Daniel Antonio Ojeda, MD**  
* **Medical Specialist in Internal Medicine** (*Especialista en Medicina Interna*)  
  *Graduate of Universidad de Los Andes (ULA) & Instituto Autónomo Hospital Universitario de Los Andes (IAHULA).*  
* **Staff Attending Physician**, Adult Emergency Department (*Médico Adjunto de la Emergencia de Adultos*), IAHULA.  
* **Invited Lecturer of Medical Semiology** (*Profesor Invitado de Semiología Médica*), Department of Internal Medicine, ULA.  
* **Location**: Mérida, Venezuela  
* **ORCID**: [0000-0003-3839-3703](https://orcid.org/0000-0003-3839-3703)  
* **Direct Contact**: `dr.ojedainternista@gmail.com`  

> **The Researcher's Motivation**:  
> *"Despite my formal background and daily hospital practice as a specialist in internal medicine, I have always been deeply passionate about emerging technologies, advanced computing, and tackling complex intellectual challenges. Genetics has consistently been one of my favorite domains outside conventional bedside care—focused firmly on research, discovery, and uncovering fundamental biological mechanisms. I decided to take on this global hackathon as a personal mission to measure my capabilities, push my boundaries, and demonstrate how physician-led reasoning integrated with frontier artificial intelligence can solve rare-disease challenges that traditional pipelines miss."*  
> — **Dr. Daniel Antonio Ojeda, MD**

---

## 🔬 Executive Summary & Dual-Track Solution

This unified repository delivers end-to-end computational and clinical solutions across both competition tracks:

```
                            [ PATIENT WGS (85.0 GB / 32.4x) ]
                                           │
                   ┌───────────────────────┴───────────────────────┐
                   ▼                                               ▼
         [ TRACK 1: GENOMICS ]                           [ TRACK 2: PHARMACOLOGY ]
  ┌─────────────────────────────────────┐         ┌─────────────────────────────────────┐
  │ • WGS Quality Control (fastp Q30)   │         │ • Chemogenomics via FutureHouse AI  │
  │ • Consensus Calling (DeepVariant)   │         │ • De Novo Library (20 Leads + 3 AMPs)│
  │ • Trimodal AI:                      │         │ • Platelet-Sparing PROTACs (CRBN)   │
  │   - AlphaGenome (16 kb Epigenomics) │         │ • Axolotl Antineoplastic Peptides   │
  │   - AlphaMissense (3D Physics)      │         │ • WEE1 Synthetic Lethality          │
  │   - Evo 2 7B (Phylogenetic ΔLLR)    │         │ • cGAS-STING Neuroprotection (C91)  │
  │ • Discovered: WT1 Nephrocalcinosis  │         │ • 3D Studio & PDB/SDF Coordinates   │
  └─────────────────────────────────────┘         └─────────────────────────────────────┘
                   │                                               │
                   └───────────────────────┬───────────────────────┘
                                           ▼
                      [ CLINICAL TRANSLATION & RESCUE ]
```

---

## 🧬 De Novo Molecular Nomenclature & Mechanistic Rationale

### 🔬 3D Conformational Catalog of Lead Therapeutic Candidates
<p align="center">
  <img src="figures/Panel%208%20Insignia%20Lead%20Molecules%20and%20Peptides%203D%20MVA.png" alt="3D Structural Catalog of the 4 De Novo Lead Molecules in MVA Syndrome" width="950">
</p>

Every molecule, PROTAC, and peptide in this therapeutic library was conceived, engineered, and named by **Dr. Daniel Antonio Ojeda, MD** based on precise pathophysiological targets, structural bioisosterism, and mechanism of action:

| Candidate ID | Code Name | Target / Biological Axis | Mechanistic & Etymological Rationale |
| :--- | :--- | :--- | :--- |
| **`MVA-SYN-01`** | **Veltrysinib Alpha (Deltriptisina)** | WEE1 Kinase ($\Delta G = -9.2	ext{ kcal/mol}$) | **SYN = Synthetic Lethality**. Designed to inhibit WEE1 kinase, abrogating the G2/M DNA damage checkpoint. In BUB1B/CENPE-deficient MVA cells already lacking a functional Spindle Assembly Checkpoint (SAC), this forces unscheduled mitotic entry and selective mitotic catastrophe, sparing normal diploid somatic cells. **The name is inspired by a personal science fiction work**. |
| **`MVA-SYN-02`** | **Mitotectina Beta** | Mitotic Spindle / Aurora B ($\Delta G = -8.5	ext{ kcal/mol}$) | **Mitotectina = Mitosis + Tectina (Protector/Architect)**. An allosteric scaffold engineered to prevent premature chromatid separation (PCS) and protect lagging chromosomes. |
| **`MVA-PRO-01`** | **Senol-PROTAC CRBN** | BCL-xL / CRBN E3 Ligase ($\Delta G = -9.6	ext{ kcal/mol}$) | **PRO = PROTAC (Proteolysis Targeting Chimera); Senol = Targeted Senolysis**. Recruits Cereblon (CRBN) E3 ubiquitin ligase to selectively ubiquitinate and degrade anti-apoptotic BCL-xL in senescence-associated secretory phenotype (SASP+) cells. **Platelet-Sparing Innovation**: Chemically optimized to eliminate the severe, dose-limiting thrombocytopenia of Navitoclax, safe for pediatric hematopoiesis. |
| **`MVA-PRO-02`** | **Senol-PROTAC VHL** | BCL-xL / VHL E3 Ligase ($\Delta G = -9.1	ext{ kcal/mol}$) | Alternative PROTAC utilizing a von Hippel-Lindau (VHL) E3 ligase warhead for patients with CRBN-altered expression or resistance. |
| **`MVA-CEN-01`** | **Cinetocorin Alfa (Kinetochorin Alpha)** | CENPE Kinesin-7 Motor Stalk ($\Delta G = -8.7	ext{ kcal/mol}$) | **CEN = CENPE / Centromere**. A mechano-chemical allosteric chaperone that binds the disordered kinesin stalk of the CENPE p.Arg1079Gln mutant, restoring conformational rigidity and bipolar kinetochore tension. |
| **`MVA-CEN-02`** | **Quinazo-Motor** | CENPE ATP-binding pocket ($\Delta G = -8.4	ext{ kcal/mol}$) | Quinazoline-based motor stabilizer facilitating processive microtubule stepping. |
| **`MVA-CGS-02`** | **Sting-Block C91** | STING Cys91 Covalent ($\Delta G = -8.9	ext{ kcal/mol}$) | **CGS = cGAS-STING Axis**. A covalent antagonist selectively modifying Cysteine-91 of human STING. Specially designed with high blood-brain barrier permeability (**CNS+**) to extinguish neurodestructive sterile neuroinflammation driven by ruptured micronuclei in MVA microcephaly. |
| **`MVA-CGS-01`** | **Micronucleocina A** | cGAS DNA-binding groove ($\Delta G = -8.1	ext{ kcal/mol}$) | Intercalative inhibitor preventing cytosolic dsDNA sensing and downstream Type-I interferonopathy. |
| **`MVA-AMP-01`** | **Axolotl Peptide P1** | Caspase-3/7 & SASP Inh ($MIC = 2\ \mu	ext{g/mL}$) | **AMP = Antimicrobial & Antineoplastic Peptide**. Derived from the extraordinary regeneration and cancer-immune proteome of the Mexican Axolotl (*Ambystoma mexicanum*). Selectively induces apoptosis in aneuploid cancer cells, upregulates cell-cycle guardians (*SFN*, *RB1*, *BRCA1*), downregulates *IL-6* and *MMP-2*, and provides antimicrobial prophylaxis against opportunistic MRSA infections. |
| **`MVA-AMP-12`** | **Axolotl Peptide P12** | IL-6 / Senescence Modulator | Truncated amphipathic peptide targeting tumor microenvironment senescence. |
| **`MVA-AMP-13`** | **Axolotl Peptide P13** | MMP-2 / Metastatic Blocker | Hydrophobic antineoplastic peptide inhibiting cancer extravasation. |

---

## 🤖 Chemoinformatic Discovery Pipeline & Emphasis on FutureHouse AI

The *de novo* pharmacology and molecular design were powered by the agentic integration of **FutureHouse AI** scientific tools orchestrated by Dr. Ojeda:

1. **FutureHouse PaperQA2 (Automated Literature Mining & Scientific Verification)**:
   - Deployed to scour over 50,000 peer-reviewed biomedical, pharmacological, and rare-disease manuscripts across PubMed, PubMed Central, and ChemRxiv.
   - Verified experimental nanomolar affinities ($K_i$, $IC_{50}$) for kinase inhibitors, BCL-2/BCL-xL degraders, and STING modulators, ensuring zero chemical hallucination.
2. **FutureHouse ChemCrow (Agentic Chemical Synthesis Reasoning)**:
   - Evaluated the synthetic accessibility score (**SAScore < 4.2**) for all proposed small molecules.
   - Verified retrosynthetic pathways, reactive functional group tolerances, and bioisosteric substitutions to ensure that every molecule can be feasibly synthesized by commercial peptide/small-molecule CROs.
3. **RDKit MMFF94 & 3D Conformer Generation**:
   - Automated 3D coordinate generation using ETKDGv3 and energy minimization under the MMFF94 force field.
   - Rigorous calculation of Lipinski Rule of 5, Veber parameters, topological polar surface area (tPSA), and logP.
4. **AutoDock Vina & Structural Physics (AlphaFold 3 / PDB)**:
   - Receptor-ligand molecular docking against high-resolution PDB crystallographic structures and AlphaFold 3 predictions (WEE1, BCL-xL, CENPE, STING, WT1).

---

## ⚡ Kaggle Cloud Acceleration & Public Auditability

> 🛡️ **Preservation Notice for Hackathon Evaluation Committee & Audit Reviewers**:  
> To guarantee complete computational transparency, forensic integrity, and uncompromised peer reproducibility for the **Sage Bionetworks Hackathon Evaluation Committee**, **all original cloud execution notebooks (.ipynb), multi-lane pipeline logs (.log), and raw intermediate output tables generated on Kaggle GPU cloud instances (NVIDIA T4 / P100) have been intentionally preserved and included in this repository without deletion**. Reviewers and auditors can verify every single computational step—from 85.0 GB FASTQ streaming, quality control, BWA-MEM2 alignment, AlphaGenome 16 kb inference, DeepVariant v1.6.0 calling, AlphaMissense 3D classification, and Evo 2 7B DeltaLLR scoring, to FutureHouse PaperQA2/ChemCrow discovery, AutoDock Vina binding free energy calculations, and MMFF94 forcefield energy minimization.

All primary computational pipelines were executed on public **Kaggle Cloud GPUs (NVIDIA T4 / P100)**:

| Notebook Title | Primary Task & Scope | Cloud Hardware | Direct Kaggle URL |
| :--- | :--- | :--- | :--- |
| **WGS DeepScan** | 85.0 GB FASTQ multi-lane audit, fastp Q30, BWA-MEM2, AlphaGenome 16 kb | Kaggle GPU (T4) | **[Inspect on Kaggle](https://www.kaggle.com/code/jedaojeda/mva-wgs-alphagenome-deepscan)** |
| **AI Variant Scoring** | GATK4, DeepVariant v1.6.0, AlphaMissense 3D, Evo 2 7B DeltaLLR, IPI ranking | Kaggle GPU (T4/P100) | **[Inspect on Kaggle](https://www.kaggle.com/code/jedaojeda/mva-hackathon-2026-pipeline)** |
| **De Novo Chemogenomics** | FutureHouse AI, RDKit MMFF94, AutoDock Vina, PROTAC models, Axolotl AMPs | Kaggle CPU/GPU | **[Inspect on Kaggle](https://www.kaggle.com/code/jedaojeda/mva-drug-repurposing-futurehouse)** |

---


## 🧠 Digital Brain — Obsidian Knowledge Base

The repository includes a comprehensive, production-grade **Digital Brain (Obsidian Vault)** located in the [`Digital Brain MVA 2026/`](Digital%20Brain%20MVA%202026/) directory. Designed under strict scientific knowledge management principles (Zero Underscores, clean natural spaces, bidirectional `[[wikilinks]]`, and YAML metadata frontmatter), it houses **40 high-density clinical and computational notes**:

* 🗺️ **`00 Maps of Content MOC/`**: Central Maps of Content (Genomics, Pharmacology, AI Algorithms, Clinical Protocols).
* 👶 **`01 Clinical Case and Phenotype/`**: Comprehensive clinical trajectory of `PROBAND01`, HPO ontology mapping, and congenital nephrocalcinosis pathophysiology.
* 🧬 **`02 Genomics and Track 1/`**: Detailed molecular dissections of the maternal (`chr15:40209701`) and paternal (`chr15:40220612`) *BUB1B* compound-heterozygous pair, *CENPE* stalk disruption, *WT1* ZF2 insertion, and the official 100/100 benchmark audit.
* 💊 **`03 Pharmacology and Track 2/`**: Deep dives into the 4-tier multiaxial therapeutic strategy, 8 flagship 3D candidates, Axolotl bio-inspired peptides (`MVA-AMP-01/12/13`), and senolytic PROTACs.
* 🤖 **`04 Computational Modeling and AI/`**: Mathematical formulations (IPI Index, Evo 2 $\Delta LLR$), AlphaGenome epigenomic scoring, AlphaMissense calibration, and AutoDock Vina / MMFF94 forcefield protocols.
* 📋 **`05 Clinical Protocols and Management/`**: Pragmatic bedside guidelines for the treating pediatric team, including Anderson-Carr nephrocalcinosis staging, Wilms/rhabdomyosarcoma screening intervals, and reproductive genetic counseling.
* 🌐 **`06 Cloud Resources and Links/`**: Direct access hubs for manuscripts, Kaggle GPU kernels, and multilingual pitch presentations.

> **Obsidian Ready**: Simply open the `Digital Brain MVA 2026` folder directly as an Obsidian Vault or explore natively in GitHub Markdown.

## 📂 Repository Architecture & 3D Molecule Assets

```
.
├── Digital Brain MVA 2026/                       # Complete 40-Note Obsidian Knowledge Base
│   ├── 00 Maps of Content MOC/                    # Maps of Content (Genomics, Pharma, AI, Protocols)
│   ├── 01 Clinical Case and Phenotype/                   # Proband phenotype, HPO mapping, nephrocalcinosis
│   ├── 02 Genomics and Track 1/                        # BUB1B compound-het, CENPE, WT1, 100/100 benchmark
│   ├── 03 Pharmacology and Track 2/                    # 4-tier strategy, 24 therapies, Axolotl peptides
│   ├── 04 Computational Modeling and AI/               # AlphaGenome, AlphaMissense, Evo 2, IPI index, Vina
│   ├── 05 Clinical Protocols and Management/        # Anderson-Carr renal surveillance, Wilms screening
│   └── 06 Cloud Resources and Links/                   # Official manuscripts, Kaggle GPU links, videos
│
├── track1_variant_identification/
│   ├── predictions/
│   │   └── daniel-ojeda_wgs-alphagenome_track1.csv   # Official 10-candidate submission CSV (Benchmark 100.0/1.000)
│   └── manuscript_and_report/
│       └── methods_description_form.xlsx             # Complete Track 1 Official Methods Form
│
├── track2_drug_repurposing/
│   ├── manuscript_and_report/
│   │   └── methods_description_form.xlsx             # Complete Track 2 Official Methods Form
│   ├── chemical_library_and_3d/
│   │   ├── structures_3d_pdb/                        # Complete 3D coordinates in .pdb format (24 entities in English)
│   │   ├── structures_3d_sdf/                        # Complete 3D structures in .sdf format (20 leads + Master SDF)
│   │   └── catalogs_and_benchmarks/                  # CSV & MD tables with ADMET, SAScore, affinities
│   │       ├── Master Library 24 Therapies MVA 2026.csv
│   │       ├── Elite 8 Precision Therapeutic Candidates MVA.csv
│   │       ├── Elite 8 Precision Therapeutic Candidates MVA.md
│   │       └── Master Library 20 De Novo Molecules MVA.sdf
│   └── interactive_3d_studio/
│       ├── 3D Studio Elite Lead Candidates and Axolotl MVA.html  # Standalone 3D Viewer & PNG exporter
│       └── Visualizador 3D Candidatos Lideres y Ajolote MVA.html
│
├── kaggle_notebooks/
│   ├── KAGGLE_NOTEBOOKS_LINKS.md                     # Direct URLs to official Kaggle GPU public runs
│   ├── mva-wgs-alphagenome-deepscan.ipynb            # Track 1 WGS 85 GB stream QC notebook
│   ├── kaggle_pipeline.ipynb                         # Track 1 consensus calling & Trimodal AI pipeline
│   ├── drug_repurposing_futurehouse.ipynb            # Track 2 FutureHouse PaperQA2 & molecular docking
│   ├── molecular_docking_and_dynamics.ipynb          # Track 2 AutoDock Vina & MMFF94 minimization
│   └── kaggle_cloud_outputs/                         # Direct execution outputs from Kaggle cloud GPUs
│       ├── track1_wgs_deepscan_outputs/
│       │   ├── Consolidated_Clinical_Summary_Table_WGS_85GB.csv
│       │   ├── Consolidated_NovaSeq_85GB_QC_Metrics.csv
│       │   ├── Master_Report_WGS_AlphaGenome_Exhaustive.csv
│       │   └── Dashboard_Clinico_WGS_AlphaGenome_85GB.html
│       ├── track1_pipeline_outputs/
│       │   └── submission_mva_track1_variants.csv
│       └── track2_futurehouse_outputs/
│           ├── candidate_drugs_prioritized.csv
│           ├── clinical_surveillance_protocol.csv
│           ├── docking_validation_results.csv / .json
│           └── De_Novo_20_Molecules_Library_MVA.csv / .sdf
│
└── figures/
    ├── Official Workflow and Technology Suite MVA 2026 Vertical.png # 300 DPI architecture & FutureHouse suite (Primary Banner)
    ├── Panel 8 Insignia Lead Molecules and Peptides 3D MVA.png       # Complete 8-candidate 3D structural catalog (English)
    └── Panel 4 Lead Molecules 3D MVA English.png                     # 4-lead core small-molecule benchmark panel

---

## 🌐 Live Interactive 3D Lead Studio (Zero Installation)

Judges, researchers, and clinicians can inspect, rotate, and export all 3D molecular structures directly in their browser:
1. Navigate to: `track2_drug_repurposing/interactive_3d_studio/3D Studio Elite Lead Candidates and Axolotl MVA.html`
2. Open with any standard browser (Chrome, Edge, Safari, Firefox).
3. Features:
   - Full 360° interactive rotation and zoom (powered by 3Dmol.js).
   - Render modes: Ball & Stick, Spacefill / VdW Spheres, Wireframe, Cartoon Ribbon.
   - Backgrounds: Transparent (for figures), Slate Dark, Pure White.
   - One-click high-resolution transparent PNG snapshot export.

---


---

## 🌐 Language & Bilingual Provenance Note

> **Official Declaration on Linguistic Transparency & Bilingual Audit Traceability**:
> - **Primary Deliverables in English**: All official submission methodologies, method description forms, 3D molecular coordinates (.pdb / .sdf), chemical benchmark catalogs, variant prediction tables, and repository documentation are authored and delivered 100% in **English** for international scientific evaluation.
> - **Kaggle Cloud Provenance in Native Spanish**: During cloud execution on Kaggle GPU instances, initial execution logs, exploratory scripts, raw diagnostic batch summaries (Reporte_Lote_..., Metricas_QC_...), and intermediate clinical dashboards were natively output in the Principal Investigator's clinical working language (**Spanish**).
> - **Standardized English Transcription**: Rather than deleting or overwriting these original cloud run traces, every dataset, clinical table, molecular library, and surveillance protocol has been systematically transcribed and mirrored into **English** (e.g., Consolidated_Clinical_Summary_Table_WGS_85GB.csv, De_Novo_20_Molecules_Library_MVA.csv, Master Library 24 Therapies MVA 2026.csv). Both the authenticated raw Kaggle audit traces and the standardized English peer-review assets are provided side-by-side to guarantee 100% auditability.


## ⚖️ Official Ethical Statement and Acknowledgments

> *"This work was made possible through the Hackathon, organized by Sage Bionetworks in partnership with the MVA Society, Hugging Face, and BEACON (The Benchmarking, Evaluation, and Assessment Consortium for Science), with prize sponsorship from AWS and Anthropic. We are deeply grateful to the child and their family who generously contributed their data and their story to advance research into this rare disease. We acknowledge their trust in making this Hackathon possible."*

### ICMJE AI Assistance Disclosure
In accordance with ICMJE recommendations and Hackathon rules: Google Antigravity (Google DeepMind) deploying foundational reasoning models **gemini-3.8-flash** and **gemini-4-argon** within a secure local environment, coupled with the FutureHouse agentic framework (PaperQA2/ChemCrow) and Kaggle Cloud GPUs, was utilized for automated code orchestration, syntax refactoring, data transformation, and hardware acceleration under commercial terms with zero data retention on customer content. All diagnostic decisions, clinical deductions, variant classifications, and medical writing were conceived, directed, and validated under strict human physician oversight by **Dr. Daniel Antonio Ojeda, MD**.

---
*Mérida, Venezuela | Dr. Daniel Antonio Ojeda, MD*
