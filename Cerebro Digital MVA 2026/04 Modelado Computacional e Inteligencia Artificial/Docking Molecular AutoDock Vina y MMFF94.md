---
aliases: [Docking Molecular, AutoDock Vina, MMFF94]
tags: [docking, vina, mmff94, conformaciones-3d]
autor: Dr. Daniel Antonio Ojeda, MD
fecha: 2026-10-23
---

# 💻 Docking Molecular con AutoDock Vina y Campo de Fuerza MMFF94

Todas las interacciones ligando-proteína del Track 2 fueron modeladas mediante un protocolo biofísico reproducible:

1. **Generación Conformacional**:
   - Muestreo conformacional tridimensional mediante el algoritmo ETKDGv3 (RDKit).
2. **Minimización Energética**:
   - Relajación de gradiente conjugado con el campo de fuerza **MMFF94** bajo condiciones de solvente implícito fisiológico.
3. **Acoplamiento Macromolecular (AutoDock Vina)**:
   - Cuadrícula de búsqueda centrada en los bolsillos catalíticos de cinasa BUBR1, Kinesina-7 y canal TRPV5.
   - Energías de afinidad obtenidas en el rango de $-8.6$ a $-10.5\text{ kcal/mol}$.

---

## 🔗 Notas Relacionadas
* [[Catalogo Selecto 8 Candidatos Insignia 3D]]
* [[Biblioteca Maestra 24 Terapias MVA 2026]]
