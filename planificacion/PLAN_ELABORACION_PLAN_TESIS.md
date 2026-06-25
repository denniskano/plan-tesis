# Plan de elaboración del Plan de Tesis — Grupo 9.2

**Tema:** Alineación entre contratos OpenAPI bancarios y modelos de referencia BIAN mediante análisis estructural y similitud semántica.

**Integrantes:** Alex Mancilla · Jack Paitan  
**Tipo de investigación:** Tecnológica (investigación basada en diseño — no encuestas ni población/muestra al estilo Sampieri)  
**Producto del curso:** Plan de tesis (Guía N°01) — **solo este documento**; construcción/experimentación queda fuera de alcance (§1.6)

**Documento maestro:** `../latex/build/Plan_Tesis_Grupo9.2.pdf` (~43 pp.)  
**Fuentes revisadas:** transcripciones PI-01 a PI-10 · bibliografía en `../../bibliografia/`  
**Índice del proyecto:** `../README.md` · checklists por fase en `../fases/`  
**Última actualización:** 2026-05-28

> **Decisión de equipo:** No se redacta contenido para Guía N°02 u otro curso. La delimitación de lo excluido aparece en §1.6; no hay sección de «experimentación futura» en Cap. 4.

---

## Estado resumido (fases)

| Fase | Alcance | Estado | Checklist |
|------|---------|--------|-----------|
| **0** | Fichas + Anexo B (14 papers) | ✅ | `fases/fase-0-bibliografia/CHECKLIST.md` |
| **A** | Esqueleto LaTeX + índices | ✅ (portada Guía 01 pendiente menor) | `fases/fase-a-indice/CHECKLIST.md` |
| **B** | Cap. 1 planteamiento + PI-10 | ✅ | `fases/fase-b-planteamiento/CHECKLIST.md` |
| **C** | §3.5–§3.6 estado del arte + Fig. 6 | ✅ | `fases/fase-c-marco-teorico/CHECKLIST.md` |
| **D** | Cap. 2 objetivos + Fig. 4 | ✅ | `fases/fase-d-objetivos/CHECKLIST.md` |
| **E** | §3.1–§3.4 marco + glosario + Fig. 5 | ✅ | `fases/fase-e-marco-teorico/CHECKLIST.md` |
| **G** | Cap. 5 + anexos LaTeX + referencias | ✅ | `fases/fase-g-administracion/CHECKLIST.md` |
| **F** | Cap. 4 metodología | ⏳ parcial | — |
| **H** | Revisión cierre docente | ⏳ | §3 abajo |

**Retroalimentación docente PI-10:** `fases/fase-b-planteamiento/FEEDBACK_DOCENTE_PI10.md`

---

## 0. Qué exige el curso (síntesis de las 8 clases)

### 0.1 Objetivo del curso (PI-01, PI-04)

- Elaborar el **plan de tesis (pretesis)** con el **problema formulado con claridad**.
- **Tesis 1 (este curso)** = proponer y delimitar el problema + diseño del procedimiento. **Tesis 2** = otro curso; **no es alcance de este repo** (PI-02).
- Se evalúan **documento + exposición**; el hilo conductor y la redacción son críticos.
- Graduación revisará que sigas la **Guía 1**; el docente exige **más** que la guía base (PI-08).

### 0.2 Cadena lógica obligatoria (PI-01, PI-04, PI-08)

```
Contexto → Problemática → Problema → Subproblemas → Objetivos (+ hipótesis y variables)
         → Marco teórico (antecedentes del estado del arte) → Metodología → Administración
```

| Elemento | Qué es según el docente | Error frecuente a evitar |
|----------|-------------------------|---------------------------|
| **Problemática** | El “dolor”; contexto **histórico/pasado** que motiva el estudio (PI-08) | Confundirla con el problema o con la técnica |
| **Problema** | Existe si alguien lo percibe; debe ser **medible** (PI-04) | Redactarlo como un objetivo (“evaluar…”, “implementar…”) |
| **Objeto de estudio** | Lo concreto que observas/mides (contratos OpenAPI) | Confundir con BIAN abstracto, con el dato, o con la técnica |
| **Ámbito** | Sector/contexto (banca, arquitecturas API) | Mezclar ámbito con técnica |
| **Técnica** | Medio (matching, similitud, embeddings) — la IA es **medio, no fin** (PI-01) | Empezar por el algoritmo sin problema de dominio |
| **Objetivos** | **Transformaciones**: data inicial → transformación → data resultado (PI-01, PI-08) | Más de 5 objetivos; verbos vacíos sin entrada/salida |
| **Estado del arte** | El **borde** del conocimiento: qué han hecho otros (PI-05) | Usar papers de aporte como si fueran estado del arte |
| **Marco teórico** | Síntesis + definiciones + clasificación de conceptos (PI-05, PI-08) | “Vaciar” resúmenes de papers sin hilo |
| **Metodología** | Investigación **basada en diseño** / tecnológica (PI-08) | Encuestas, población/muestra tipo ciencias sociales |

### 0.3 Entregables y gestión (PI-03, PI-05, PI-06, PI-08)

- **Zotero** con papers clasificados → ✅ `referencias.bib` + lista APA en PDF · verificar DOI finales.
- Cargar en **aula virtual**: **documento + referencias + paper** (PI-03) → ⏳ subir PDF + `.bib` + paper.
- **Anexos obligatorios (curso):** matriz consistencia ✅ · operación variables ✅ LaTeX Anexo D.
- **Preliminares:** índice, lista de figuras y tablas → ✅ automáticos al compilar.
- **Figura de objetivos** → ✅ Fig. 4 Cap. 2.

### 0.4 Papers: estado del arte vs. aporte (PI-02, PI-05, PI-06)

- **Estado del arte:** surveys, systematic reviews, mapping studies (PI-05, PI-06) → §3.5–§3.6 ✅.
- Los papers de **aporte** sustentan **conceptos** en §3.4 y Cap. 4; no sustituyen al estado del arte.

---

## 1. Estructura del documento (Guía 1 + extensiones del docente — PI-08)

Tabla de contenido **objetivo** vs **estado LaTeX** (`latex/chapters/`).

### Preliminares

| Sección | Estado |
|---------|--------|
| Portada | ✅ Anexo III (`portada.tex` + `datos-generales.tex`) |
| Resumen / abstract | ✅ |
| Índice, figuras, tablas | ✅ automático |

---

### CAPÍTULO 1 — PLANTEAMIENTO ✅

**LaTeX:** `latex/chapters/cap01-planteamiento/` · **Fase B**

| Sección | Estado |
|---------|--------|
| §1.1–§1.9 | ✅ |
| Fig. 1–3 | ✅ |
| Tablas 1.1–1.8 (alcances, tipologías, objeto, etc.) | ✅ |
| Feedback PI-10 aplicado | ✅ `FEEDBACK_DOCENTE_PI10.md` |

**1.6.1 Alcances (implementado en `tables/tab01-alcances.tex`)**

| Alcance | Limitación |
|---------|------------|
| Diseño del modelo S/E/C → AlignmentScore | No construcción del artefacto software ni experimentación a escala |
| Evaluar alineación estructural y semántica OpenAPI ↔ BIAN | No despliegue en producción |
| Métricas sobre artefactos documentales | No foco en testing/seguridad runtime (E5) |
| Contratos OpenAPI bancarios vs. SD BIAN | No catálogo BIAN completo; sin piloto fijo |
| Análisis documental | No encuestas |

---

### CAPÍTULO 2 — OBJETIVOS ✅

**LaTeX:** `latex/chapters/cap02-objetivos/_cap02.tex` · **Fase D**

| Sección | Estado |
|---------|--------|
| §2.1 Línea de base | ✅ |
| §2.2 Objetivo general | ✅ (≈ Anexo C) |
| §2.3 OE1–OE4 transformadores | ✅ Tabla objetivos |
| §2.4 Hipótesis H1–H4 | ✅ |
| §2.5 Variables | ✅ Tabla 5 |
| §2.6 Fig. 4 cadena objetivos | ✅ |

**OE implementados (matriz Anexo C):**

| ID | Transformación |
|----|----------------|
| OE1 | OpenAPI + BIAN → representaciones normalizadas |
| OE2 | Normalizado → StructuralScore (E) |
| OE3 | Normalizado → SemanticScore (S) |
| OE4 | E, S + normalización → C, AlignmentScore, clasificación |

---

### CAPÍTULO 3 — MARCO TEÓRICO ✅

**LaTeX:** `latex/chapters/cap03-marco/` · **Fases C + E**

| Sección | Estado | Fase |
|---------|--------|------|
| §3.1 Antecedentes | ✅ `01-antecedentes.tex` | E |
| §3.2 Bases conceptuales + Fig. 5 | ✅ `02-bases-conceptuales.tex` | E |
| §3.3 Glosario (18 términos) | ✅ Tabla 7 | E |
| §3.4 Bases teóricas | ✅ `04-bases-teoricas.tex` | E |
| §3.5 Estado del arte E1–E6 + Tabla 6 | ✅ `05-estado-arte.tex` | C |
| §3.6 Brecha V1–V5 + Fig. 6 | ✅ `06-brecha.tex` | C |

Borrador Markdown fuente §3.5–§3.6: `fases/fase-c-marco-teorico/CAPITULO_03_ESTADO_DEL_ARTE.md`

**Ejes E1–E6:** ver `fases/fase-0-bibliografia/EJES_ESTADO_DEL_ARTE.md` y Tabla 6.

---

### CAPÍTULO 4 — DISEÑO METODOLÓGICO ⏳

**LaTeX:** `latex/chapters/cap04-metodologia/` · **Fase F**

| Sección | Estado |
|---------|--------|
| §4.1 Tipo y enfoque | ⏳ placeholder |
| §4.2 Procedimiento + Fig. 7 (E) | ⏳ parcial |
| §4.3–§4.6 | ⏳ placeholder |
| §4.7–§4.8 Validez / amenazas | ⏳ placeholder |

**Papers `aporte/` prioritarios Cap. 4:** Moon 2025, Mainas 2023, Muhamad 2022, Shimangaud 2026.

**Pendiente docente (PI-10):** ejemplo ampliado de contrato (I5) → Cap. 4 o Anexo F.

---

### CAPÍTULO 5 — ADMINISTRACIÓN ✅

**LaTeX:** `latex/chapters/cap05-administracion/` · **Fase G**

| Sección | Estado |
|---------|--------|
| §5.1 Cronograma (Tabla 9) | ✅ |
| §5.2 Recursos | ✅ |
| §5.3 Roles | ✅ |
| §5.4 Riesgos | ✅ |
| §5.5 Presupuesto | ✅ |

---

### ANEXOS

| Anexo | Excel / fuente | LaTeX |
|-------|----------------|-------|
| A — String búsqueda | ✅ redactado | ✅ `anexo-a.tex` |
| B — Matriz papers | ✅ `Matriz_Papers_EstadoDelArte_Grupo9.2.xlsx` | ✅ `anexo-b.tex` |
| C — Matriz consistencia | ✅ `Matriz_Consistencia_Grupo9.2.xlsx` | ✅ `anexo-c.tex` |
| D — Operación variables | ✅ | ✅ `anexo-d.tex` |
| E — Diseño factorial | N/A | ✅ `anexo-e.tex` |
| F — Ejemplos OpenAPI/BIAN | ✅ | ✅ `anexo-f.tex` |

---

### Figuras del plan (implementadas)

| Figura | Sección | Archivo |
|--------|---------|---------|
| 1 | §1.1 | `figuras/cap01/Figura_01_Contexto.png` |
| 2 | §1.4 | `figuras/cap01/Figura_02_Objeto_Unidad_Analisis.png` |
| 3 | §1.4 | `figuras/modelo-alineacion/Figura_03_AlignmentScore.pdf` |
| 4 | §2.6 | `figuras/cap02/Figura_04_Cadena_Objetivos.png` |
| 5 | §3.2 | `figuras/cap03/Figura_05_Bases_Conceptuales.png` |
| 6 | §3.6 | `figuras/cap03/Figura_06_Brecha.png` |
| 7 | §4.2 | `figuras/modelo-alineacion/Figura_07_StructuralScore.pdf` |
| 8 | — | **No aplica** (experimentación fuera de alcance) |

Regenerar Fig. 4–6: `herramientas/scripts/build_figuras_fase_cd.py` · Fig. 1–2: `build_figuras_fase_b.py`

---

## 2. Mapa sesiones → qué aportan al plan

| Sesión | Tema central | Aplicación directa |
|--------|--------------|-------------------|
| **PI-01** | Estructura 5 capítulos; hilo conductor; mapa semántico | Arquitectura global ✅ |
| **PI-02** | Papers review vs aporte; Zotero | Fase 0 ✅ · Zotero ⏳ |
| **PI-03** | Entrega documento en aula virtual | ⏳ subir PDF |
| **PI-04** | Problema ≠ objetivo; keywords EN | Cap. 1–2 ✅ |
| **PI-05** | Estado del arte; marco con sentido | Cap. 3 ✅ |
| **PI-06/07** | Tablas sistematizadas | §3.5 ✅ |
| **PI-08** | Esquema extendido; variables; anexos | Cap. 2 ✅ · anexos LaTeX ⏳ |
| **PI-10** | Matriz 5 fases; transformadores; objeto concreto | Cap. 1–2 ✅ · acta en `FEEDBACK_DOCENTE_PI10.md` |

---

## 3. Plan de trabajo por fases (detalle)

### Fase 0 — Bibliografía ✅

**Carpeta:** `fases/fase-0-bibliografia/`

- [x] 14 fichas · Excel Anexo B · revisión cruzada · §3.5–§3.6 borrador

### Fase A — Índice y esqueleto ✅

**Carpeta:** `fases/fase-a-indice/` · **LaTeX:** `latex/`

- [x] Estructura capítulos 1–5 + anexos + preliminares
- [x] Índices automáticos
- [ ] Portada formato exacto Guía N°01

### Fase B — Capítulo 1 ✅

**Carpeta:** `fases/fase-b-planteamiento/`

- [x] §1.1–§1.9 · Fig. 1–3 · PI-10 Cap. 1 · revisión cruzada

### Fase C — §3.5–§3.6 ✅

**Carpeta:** `fases/fase-c-marco-teorico/`

- [x] LaTeX integrado · Fig. 6 · revisión cruzada
- [ ] Revisión docente

### Fase D — Capítulo 2 ✅

**Carpeta:** `fases/fase-d-objetivos/`

- [x] OG · OE1–OE4 · H1–H4 · variables · Fig. 4 · revisión cruzada
- [ ] Revisión docente

### Fase E — §3.1–§3.4 ✅

**Carpeta:** `fases/fase-e-marco-teorico/`

- [x] Antecedentes · bases conceptuales · glosario 18 términos · bases teóricas · Fig. 5
- [ ] Revisión cruzada · revisión docente · Zotero

### Fase F — Capítulo 4 ⏳

1. Completar §4.1–§4.8 (diseño reproducible, sin experimentación)
2. Representación intermedia (tabular / grafo / RDF)
3. Fórmulas explícitas S, E, C, AlignmentScore
4. Casos ilustrativos BIAN + **ejemplo ampliado** contrato (I5)
5. Apoyos Fig. S/C en §4.4–§4.5

### Fase G — Capítulo 5 + anexos ✅

- [x] Cronograma · recursos · roles · riesgos · presupuesto
- [x] Anexos A–F en LaTeX
- [x] Referencias APA + `referencias.bib`
- [ ] Verificar metadatos Zotero vs. fichas

### Fase H — Revisión de cierre ⏳

- [ ] Hilo conductor + glosario §3.3 en todos los capítulos
- [ ] Problemática ≠ problema ≠ objetivo
- [ ] Estado del arte + vacío explícito
- [ ] Metodología tecnológica sin encuestas
- [ ] Referencias uniformes · portada Guía 01

---

## 4. Asignación sugerida Grupo 9.2

| Actividad | Responsable | Estado |
|-----------|-------------|--------|
| Cap. 1 + alcances | Alex | ✅ |
| Matriz estado del arte (14 papers) | Jack | ✅ |
| Cap. 2 objetivos/hipótesis/figura | Ambos | ✅ |
| Cap. 3 §3.1–§3.6 | Alex (§3.5–§3.6) · Jack (§3.1–§3.4) | ✅ |
| Cap. 4 diseño metodológico | Jack | ⏳ |
| Cap. 5 + anexos + Zotero | Jack | ⏳ |
| Revisión hilo conductor | Ambos | ⏳ |

---

## 5. Decisiones de equipo (registro)

| # | Decisión | Resolución |
|---|----------|------------|
| 1 | Modelo S/E/C + α/β/γ + clasificación | ✅ Cap. 1 §1.4 · Anexo figuras |
| 2 | Objeto = OpenAPI bancario; BIAN = referencia | ✅ Cap. 1 |
| 3 | Matriz 5 fases; sin piloto Payment Execution | ✅ Anexo C |
| 4 | Solo plan Guía N°01; no redactar Guía 2 | ✅ §1.6 · 2026-05-28 |
| 5 | Métrica semántica (embeddings vs ontología) | ⏳ definir en Cap. 4 Fase F |
| 6 | Representación intermedia BIAN/OpenAPI | ⏳ Cap. 4 Fase F |

---

## 6. Inventario bibliográfico

| Carpeta | Cant. | Rol |
|---------|-------|-----|
| `bibliografia/estado-del-arte/` | 14 | Cap. 3 §3.5–§3.6 |
| `bibliografia/aporte/` | 22 | §3.4 + Cap. 4 |
| `bibliografia/contexto-openapi-bian/` | 7 | Cap. 1 + Cap. 4 |
| `bibliografia/otros/` | 2 | Revisar relevancia |

---

## 7. Próxima acción

1. **Fase F** — completar Cap. 4 metodología.
2. **Subir PDF** + `referencias.bib` + paper al aula virtual (PI-03).
3. **Fase H** — revisión cierre docente · portada Guía N°01.

---

## 8. Comandos

```bash
cd plan-tesis/latex && make pdf
herramientas/.venv-excel/bin/python3 herramientas/scripts/build_figuras_fase_b.py
herramientas/.venv-excel/bin/python3 herramientas/scripts/build_figuras_fase_cd.py
herramientas/.venv-excel/bin/python3 herramientas/scripts/build_matriz_papers.py
herramientas/.venv-excel/bin/python3 herramientas/scripts/build_matriz_consistencia.py
```

---

*Plan vivo — sincronizado con checklists en `fases/` y PDF en `latex/build/`.*
