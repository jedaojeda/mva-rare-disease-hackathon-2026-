# 3D Chemical Structures & Molecular Library: Mosaic Variegated Aneuploidy (MVA)

**Principal Investigator**: Dr. Daniel Antonio Ojeda, MD (Internal Medicine Specialist, ULA - IAHULA)  
**Hackathon**: Sage Bionetworks Rare Disease Global Hackathon 2026 (Track 2: Drug Repurposing & De Novo Discovery)

This directory contains the complete structural coordinates, forcefield-minimized conformations, and benchmark matrices for the **20 de novo small molecules/PROTACs** and **3 bio-inspired Axolotl (*Ambystoma mexicanum*) peptides** engineered by Dr. Daniel Antonio Ojeda.

---

## 📂 Subdirectory Organization

```
chemical_library_and_3d/
├── structures_3d_pdb/           # 24 Protein Data Bank (.pdb) coordinate files
│   ├── MVA-AMP-01 Axolotl Peptide.pdb
│   ├── MVA-AMP-12 Axolotl Peptide.pdb
│   ├── MVA-AMP-13 Axolotl Peptide.pdb
│   ├── MVA-SYN-01 Veltrysinib Alpha.pdb
│   ├── MVA-PRO-01 Senol-PROTAC CRBN.pdb
│   ├── MVA-CEN-01 Kinetochorin Alpha.pdb
│   ├── MVA-CGS-02 Sting-Block C91.pdb
│   └── ... (All 24 therapeutic leads: 20 small molecules/PROTACs + 3 peptides + 1 gene editor duplex)
│
├── structures_3d_sdf/           # Structure-Data Files (.sdf) with 3D charges & bonds
│   ├── Master Library 20 De Novo Molecules MVA.sdf   # Master combined SDF library
│   ├── MVA-SYN-01 Veltrysinib Alpha.sdf
│   ├── MVA-PRO-01 Senol-PROTAC CRBN.sdf
│   ├── MVA-CEN-01 Kinetochorin Alpha.sdf
│   └── ... (All 20 individual ligand SDF files)
│
├── catalogs_and_benchmarks/     # Tabular matrices with binding affinities & ADMET
│   ├── Master Library 24 Therapies MVA 2026.csv
│   ├── Elite 8 Precision Therapeutic Candidates MVA.csv
│   └── Elite 8 Precision Therapeutic Candidates MVA.md
│
└── README.md                    # This directory catalog
```

---

## 🔬 How to Inspect & Render 3D Coordinates

1. **In-Browser Interactive Studio (No Software Needed)**:
   - Open: `track2_drug_repurposing/interactive_3d_studio/3D Studio Elite Lead Candidates and Axolotl MVA.html`
   - Real-time 3D rotation, Ball & Stick, Spacefill, Cartoon, and PNG snapshot exporter.

2. **Academic Molecular Viewers (PyMOL, UCSF ChimeraX, VMD)**:
   ```bash
   # In PyMOL:
   pymol structures_3d_pdb/"MVA-SYN-01 Veltrysinib Alpha.pdb"
   pymol structures_3d_pdb/"MVA-PRO-01 Senol-PROTAC CRBN.pdb"
   ```

3. **Chemoinformatics Packages (RDKit / OpenBabel)**:
   ```python
   from rdkit import Chem
   suppl = Chem.SDMolSupplier('structures_3d_sdf/Master Library 20 De Novo Molecules MVA.sdf')
   for mol in suppl:
       print(mol.GetProp('_Name'), Chem.MolToSmiles(mol))
   ```

---
*Mérida, Venezuela | Dr. Daniel Antonio Ojeda, MD*
