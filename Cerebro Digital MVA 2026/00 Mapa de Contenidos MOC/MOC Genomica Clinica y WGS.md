---
aliases: [MOC Genomica, WGS MOC, Track 1 MOC]
tags: [moc, genomica, track1, wgs, bub1b]
autor: Dr. Daniel Antonio Ojeda, MD
fecha: 2026-10-23
---

# 🧬 MOC: Genómica Clínica y Secuenciación WGS (Track 1)

Este mapa de contenidos articula todo el procesamiento genómico exhaustivo realizado sobre los 85.0 GB de lecturas sin procesar (FASTQ) y el archivo VCF del paciente índice (`PROBAND01` / `WGS_EX2312012`).

---

## 🎯 Arquitectura Causal del Paciente

* [[Arquitectura Causal BUB1B Heterocigoto Compuesto]]: La base fisiopatológica del síndrome MVA1.
* [[Variante Materna chr15 40209701 T G]]: Stop-gain en exón truncante de BUB1B (p.Arg407Ter).
* [[Variante Paterna chr15 40220612 T G]]: Variante missense en dominio de ensamblaje MCC/BUB3.
* [[Benchmark Oficial 100 de 100 SageBio]]: Validación contra el Answer Key clínico del hackathon.

---

## 🔍 Variantes Modificadoras y Co-Segregantes

* [[Modulador Cinetocorico CENPE p.Arg1079Gln]]: Ruptura del tallo mecánico de Kinesina-7 y colapso de tensión.
* [[Driver Oncogenico WT1 Insercion ZF2 p.Arg394fs]]: Inserción en dedo de zinc causante directa de nefrocalcinosis y riesgo de tumor de Wilms.
* [[Catalogo Maestro 10 Variantes Priorizadas]]: Matriz completa de las 10 variantes con su puntaje EPCR y justificación clínica.

---

## 🔬 Calidad de Secuenciación y Auditoría C++

* Cobertura acumulada >140x en loci críticos del huso mitótico.
* Control de calidad base por base con `fastp` multithreading (>94% Q30 en los 8 carriles NovaSeq).
* Deduplicación con `sambamba` y alineamiento referenciado a GRCh38 (no-alt analysis set).
