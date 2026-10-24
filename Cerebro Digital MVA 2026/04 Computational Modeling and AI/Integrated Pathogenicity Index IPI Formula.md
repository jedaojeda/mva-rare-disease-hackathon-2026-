---
aliases: [IPI Formula, IPI Index, Multi-Omic Ensemble]
tags: [ipi, formula, algorithm, ensemble]
author: Daniel Antonio Ojeda, MD
date: 2026-10-23
---

# 📐 Integrated Pathogenicity Index (IPI) Formulation

To consolidate predictions across biological foundation AI models into a single calibrated scalar, Dr. Daniel Antonio Ojeda formulated the **IPI Index**:

$$\text{IPI}(v) = 0.40 \cdot S_{\text{AlphaMissense}}(v) + 0.35 \cdot S_{\text{AlphaGenome}}(v) + 0.25 \cdot \min\left[ 1.0, \; \max\left( 0.0, \; \frac{-\Delta LLR_{\text{Evo2}}(v)}{10.0} \right) \right]$$

---

## 📊 Weighting Justification

* **$0.40$ (AlphaMissense)**: Direct impact on protein structural fold and catalytic active site geometry.
* **$0.35$ (AlphaGenome)**: Regulatory chromatin accessibility and cryptic splice modulation.
* **$0.25$ (Evo 2)**: Multi-species evolutionary purifying selection penalty.

---

## 🔗 Related Notes
* [[Master Catalog 10 Prioritized Variants]]
* [[Google DeepMind AlphaMissense in Missense Mutations]]
