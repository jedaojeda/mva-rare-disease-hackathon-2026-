---
aliases: [Molecular Docking, AutoDock Vina, MMFF94 Forcefield]
tags: [docking, vina, mmff94, 3d-conformations]
author: Daniel Antonio Ojeda, MD
date: 2026-10-23
---

# 💻 Molecular Docking with AutoDock Vina and MMFF94 Forcefield

All ligand-receptor complexes in Track 2 were modeled through a reproducible biophysical pipeline:

1. **3D Conformational Generation**:
   - Distance geometry sampling via RDKit's ETKDGv3 algorithm.
2. **Forcefield Energy Minimization**:
   - Conjugate gradient minimization with the **MMFF94** forcefield under implicit solvent conditions.
3. **Macromolecular Docking (AutoDock Vina)**:
   - Grid boxes centered on catalytic domains of BUBR1, Kinesin-7, and TRPV5.
   - Binding free energies ranged from $-8.6$ to $-10.5\text{ kcal/mol}$.

---

## 🔗 Related Notes
* [[Select Catalog 8 Flagship 3D Candidates]]
* [[Master Library 24 Therapies MVA 2026]]
