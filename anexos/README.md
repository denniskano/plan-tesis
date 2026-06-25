# Anexos del plan de tesis — Grupo 9.2

| Anexo | Archivo | Estado |
|-------|---------|--------|
| **B — Matriz de papers (estado del arte)** | `Matriz_Papers_EstadoDelArte_Grupo9.2.xlsx` | ✅ 14 fichas sincronizadas (Fase 0) |
| **C — Matriz de consistencia** | `Matriz_Consistencia_Grupo9.2.xlsx` | ✅ Generada (5 fases, modelo S/E/C) |
| **Figuras — Modelo de alineación** | `figuras_alineacion_openapi_bian.pdf` | ✅ Fuente · páginas en `../figuras/modelo-alineacion/` |
| Guía exposición matriz | `GUIA_EXPOSICION_MATRIZ_CONSISTENCIA.md` | ✅ Guion oral |
| D — Matriz de operación de variables | ✅ LaTeX Anexo D | ✅ |
| A — String de búsqueda | ✅ Anexo A LaTeX | ✅ |
| F — Ejemplos OpenAPI y BIAN | ✅ Anexo F LaTeX | ✅ |

```bash
# Anexo B — fichas papers (Fase 0)
herramientas/.venv-excel/bin/python3 herramientas/scripts/build_matriz_papers.py

# Anexo C — consistencia
herramientas/.venv-excel/bin/python3 herramientas/scripts/build_matriz_consistencia.py
```

---

## Modelo de alineación (producto central)

| Score | Significado |
|-------|-------------|
| **S** — SemanticScore | Similitud de significado OpenAPI ↔ BIAN |
| **E** — StructuralScore | Correspondencia de jerarquía y organización |
| **C** — CoverageScore | Conceptos BIAN cubiertos por el contrato |

**AlignmentScore = α·S + β·E + γ·C** (α + β + γ = 1)

**Clasificación:** Alta (≥ 0,80) · Media (0,60–0,79) · Baja (0,40–0,59) · Nula (< 0,40)

### Decisión de equipo — SchemaConformanceScore (δ)

La **página 4** del PDF incluye un cuarto término **SchemaConformanceScore (δ)** y la fórmula
`AlignmentScore = α·S + β·E + γ·C + δ·SchemaConformance`. Eso **no forma parte** del modelo
oficial del plan (Guía 1): Cap. 1, matriz de consistencia y matriz OG-OE usan **solo S, E y C**.

- **Uso de pág. 4:** desglose ilustrativo de **CoverageScore** (SD, CR, BQ, OP, SC).
- **δ:** descartado en el plan de tesis; reservado como línea futura (tesis 2), no citar como
  componente del AlignmentScore en redacción formal.

---

## Mapa — PDF fuente y carpeta canónica

**Fuente multipágina:** `figuras_alineacion_openapi_bian.pdf` (este directorio).  
**Archivos para LaTeX:** `../figuras/modelo-alineacion/` (extraídos con `pdfseparate`).  
**Índice maestro:** `../figuras/README.md`.

| Pág. fuente | Archivo en `figuras/modelo-alineacion/` | Sección | Figura plan |
|-------------|----------------------------------------|---------|-------------|
| **1** | `Figura_03_AlignmentScore.pdf` | Cap. 1 §1.4.1 | **Figura 3** |
| **2** | `Figura_07_StructuralScore.pdf` | Cap. 4 §4.2 | **Figura 7** |
| **3** | `Apoyo_SemanticScore.pdf` | Cap. 4 §4.4 | Apoyo S |
| **4** | `Apoyo_CoverageScore.pdf` | Cap. 4 §4.5 | Apoyo C (sin δ) |

### Coherencia con PI-10

- **Pág. 2 y 3** usan ejemplo **SavingsAccount / apertura cuenta** (caso concreto).
- Ese material corresponde a **Cap. 4 (metodología / casos)**, no al Cap. 1 (ejemplo genérico).
- Al redactar Fase F, generalizar o mover el caso al §4.6 / Anexo F.

### Referencias cruzadas

| Documento | Uso |
|-----------|-----|
| `../figuras/README.md` | Índice maestro de todas las figuras |
| `../figuras/modelo-alineacion/` | Archivos incluidos en LaTeX |
| `../latex/chapters/cap01-planteamiento/` | Fig. 3 |
| `../latex/chapters/cap04-metodologia/` | Fig. 7 + apoyos S/C |
| `GUIA_EXPOSICION_MATRIZ_CONSISTENCIA.md` | Pág. 1 en exposición Fase 5 |

## LaTeX

Ver macros en `../latex/config/commands.tex`: `\figCapThree`, `\figCapSeven`, `\figApoyoS`, `\figApoyoC`.
