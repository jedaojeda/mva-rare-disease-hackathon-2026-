---
aliases: [Formula IPI, Indice IPI, Integracion Multi-Omica]
tags: [ipi, formula, algoritmo, ensamble]
autor: Dr. Daniel Antonio Ojeda, MD
fecha: 2026-10-23
---

# 📐 Fórmula del Índice de Patogenicidad Integrado (IPI)

Para consolidar las salidas de los tres modelos de inteligencia artificial en una métrica escalar única y calibrada, el Dr. Daniel Antonio Ojeda diseñó la **Fórmula IPI**:

$$\text{IPI}(v) = 0.40 \cdot S_{\text{AlphaMissense}}(v) + 0.35 \cdot S_{\text{AlphaGenome}}(v) + 0.25 \cdot \min\left[ 1.0, \; \max\left( 0.0, \; \frac{-\Delta LLR_{\text{Evo2}}(v)}{10.0} \right) \right]$$

---

## 📊 Calibración de Ponderaciones

* **$0.40$ (AlphaMissense)**: Evalúa el impacto directo en la estabilidad y plegamiento de la proteína.
* **$0.35$ (AlphaGenome)**: Evalúa el impacto en accesibilidad cromatínica y regulación transcripcional.
* **$0.25$ (Evo 2)**: Penaliza la pérdida de conservación evolutiva multiespecie.

---

## 🔗 Notas Relacionadas
* [[Catalogo Maestro 10 Variantes Priorizadas]]
* [[Google DeepMind AlphaMissense en Mutaciones Missense]]
