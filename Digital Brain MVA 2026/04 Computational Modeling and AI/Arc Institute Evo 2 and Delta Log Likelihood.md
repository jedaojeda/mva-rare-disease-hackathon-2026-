---
aliases: [Evo 2, Arc Institute Evo 2, Delta Log Likelihood]
tags: [evo2, arc-institute, genomic-language-model, indels]
author: Daniel Antonio Ojeda, MD
date: 2026-10-23
---

# 🔬 Arc Institute Evo 2 and Evolutionary Delta Log-Likelihood ($\Delta LLR$)

Developed by the Arc Institute and Stanford University, **Evo 2** is a 7-billion-parameter StripedHyena architecture trained on whole genomes across the tree of life to assess evolutionary fitness penalties.

---

## 📐 Delta Log-Likelihood Ratio Formulation

$$\Delta LLR(v) = \ln P_\theta(x_{\text{mut}}) - \ln P_\theta(x_{\text{wt}}) = \sum_{i=1}^L \left[ \ln P(x_{i,\text{mut}} \mid x_{<i}) - \ln P(x_{i,\text{wt}} \mid x_{<i}) \right]$$

Substantially negative values reflect severe evolutionary purifying selection penalties, indicating disrupted biological fitness.

---

## 🔗 Related Notes
* [[Integrated Pathogenicity Index IPI Formula]]
* [[Google DeepMind AlphaGenome in Non-Coding Regions]]
