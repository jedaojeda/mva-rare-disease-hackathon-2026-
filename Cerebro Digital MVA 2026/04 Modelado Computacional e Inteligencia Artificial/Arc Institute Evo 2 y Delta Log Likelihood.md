---
aliases: [Evo 2, Arc Institute Evo 2, Delta Log Likelihood]
tags: [evo2, arc-institute, lenguaje-genomico, indels]
autor: Dr. Daniel Antonio Ojeda, MD
fecha: 2026-10-23
---

# 🔬 Arc Institute Evo 2 y Delta Log-Likelihood ($\Delta LLR$)

Desarrollado por el Arc Institute y Stanford University, **Evo 2** es una arquitectura basada en StripedHyena de 7 mil millones de parámetros entrenada sobre genomas procariotas y eucariotas para evaluar el costo evolutivo de variantes estructurales complejas.

---

## 📐 Fórmula de Delta Log-Likelihood Ratio

$$\Delta LLR(v) = \ln P_\theta(x_{\text{mut}}) - \ln P_\theta(x_{\text{wt}}) = \sum_{i=1}^L \left[ \ln P(x_{i,\text{mut}} \mid x_{<i}) - \ln P(x_{i,\text{wt}} \mid x_{<i}) \right]$$

Un valor marcadamente negativo indica que la secuencia mutada es sumamente improbable bajo la presión de selección evolutiva natural.

---

## 🔗 Notas Relacionadas
* [[Indice de Patogenicidad Integrado IPI Formula]]
* [[Google DeepMind AlphaGenome en No Codificante]]
