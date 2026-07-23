# Guía de exposición — Julio 2026 (PI-13 / PI-14)

**Grupo 9.2:** Alex Mancilla · Jack Paitan  
**Tema:** Alineación contratos OpenAPI bancarios ↔ Service Domains BIAN · modelo S/E/C  
**PDF:** `../latex/build/Plan_Tesis_Grupo9.2.pdf`

---

## 1. Calendario y reglas

| Sesión | Fecha | Formato | Evaluación |
|--------|-------|---------|------------|
| Exposición documento | **23 jul** o **30 jul** (confirmar ficha) | Pantalla = **PDF del plan** (sin PPT obligatorio) | **Con nota** · rúbrica enviada |
| Exposición final | **30 jul** | **PPT** permitido | **Con nota** · sin comentarios de mejora |

**Reglas del docente (PI-14):**
- No reprogramar de forma arbitraria; solo intercambio de ficha con otro grupo.
- En la sesión con nota el docente **evalúa**, no corrige en detalle.
- Partir la revisión por **Cap. 4 metodología** y retroceder (problemática, objeto, intro).

---

## 2. Checklist previo (5 min antes)

Ver también [`CHECKLIST_PRE_EXPOSICION.md`](CHECKLIST_PRE_EXPOSICION.md).

- [ ] PDF compilado al día (`make pdf` en `../latex/`)
- [ ] Zotero abierto con **Casas (2021)** y **Shvaiko & Euzenat (2005)** (PDF descargado)
- [ ] Índice visible (panel navegación Word/PDF o `\tableofcontents`)
- [ ] Micrófono probado; **compartir pantalla completa** (no solo ventana del PDF)
- [ ] Acuerdo Alex/Jack: quién navega, quién marca conceptos al hablar

---

## 3. Estructura de la exposición documento (~12–15 min)

Orden sugerido (cangrejo: metodología → atrás):

| Min | Sección PDF | Quién | Qué decir / mostrar |
|-----|-------------|-------|---------------------|
| 0–1 | Cap. 4 §4.2 + §4.2.1 | Alex | «Estos son los pasos con verbos y cómo cada OE se amarra a una fase.» **Marcar** tabla OE↔fase. |
| 1–3 | Cap. 4 §4.3 | Jack | Tabla adquisición: objeto, UA, señal, instrumento, muestra (Clase 04). |
| 3–5 | Cap. 2 §2.2–§2.5 | Alex | Objetivo superior vs OG; OE1–OE4 como transformadores; factores/ratios. |
| 5–7 | Cap. 1 §1.4 + Fig. ontología | Jack | Objeto, UA, producto; **Fig. ontología** — señalar cajas al hablar. |
| 7–9 | Cap. 1 §1.2 | Jack | Problemática real: TSB, open banking, síntomas (viñetas). **No** confundir con problema técnico. |
| 9–10 | Cap. 1 §1.3 | Alex | Tres niveles; problema tecnológico = método **insuficiente**, no «no existe». |
| 10–12 | **Referencia 1** | Alex | §1.2 cita Casas → abrir paper → marcar párrafo 40 % dominio concreto. |
| 12–14 | **Referencia 2** | Jack | Cap. 4 / §3.4 cita Shvaiko → marcar definición schema matching. |
| 14–15 | Cap. 3 §3.6 | Ambos | Brecha V1–V5 ≠ problema matriz (una frase cada uno). |

**Cierre (15 s):** «El plan entrega diseño del procedimiento S/E/C; validación empírica queda en Tesis 2 (§1.6).»

---

## 4. Dos casitos concretos (PI-10 + PI-13)

Usar **Anexo F** o Tabla 1.4. Marcar en pantalla al nombrar cada columna.

### Caso A — Fragmentación semántica (S)

| OpenAPI | BIAN (Payment Initiation) |
|---------|-------------------------|
| `POST /payments` · schema `PaymentRequest` | Behavior `InitiatePayment` · BO `PaymentOrder` |

**Mensaje:** mismos roles de negocio, nombres distintos → afecta **SemanticScore (S)**.

### Caso B — Cobertura parcial (C)

| OpenAPI expone | BIAN define además |
|----------------|------------------|
| `GET /payments/{id}` | `InitiatePayment`, `ConfirmPayment`, `CancelPayment` |

**Mensaje:** operaciones incompletas → baja **CoverageScore (C)** aunque E sea alto.

**Frase de cierre:** «El artefacto agrega S, E, C en AlignmentScore por instancia contrato × Service Domain.»

---

## 5. Modelo S/E/C (2 min — obligatorio PI-10)

Mostrar **Fig. 3** (§1.4) o `../figuras/modelo-alineacion/Figura_03_AlignmentScore.pdf`:

1. **E (StructuralScore):** paths/operations/schemas ↔ behaviors/BO  
2. **S (SemanticScore):** similitud de significado (embeddings / matching)  
3. **C (CoverageScore):** proporción del SD cubierta por el contrato  
4. **AlignmentScore** = αS + βE + γC → clasificación Alta/Media/Baja/Nula  

Decir explícito: «S/E/C se calculan por **unidad de análisis**; el score global es por **contrato × SD**.»

---

## 6. Preguntas frecuentes del docente (respuestas preparadas)

| Pregunta | Respuesta corta |
|----------|-----------------|
| ¿Cuál es la UA? | Par endpoint/schema ↔ behavior/business object dentro de un contrato evaluado contra un SD. |
| ¿Objeto de estudio? | Contrato OpenAPI bancario completo (archivo YAML/JSON). |
| ¿Problema real vs subyacente vs técnico? | Real = síntomas sector (§1.2); subyacente = dos jerarquías comparables (§1.4); técnico = falta de método reproducible de medición (§1.3). |
| ¿Objetivo superior? | Si existiera el artefacto, equipos cuantificarían coherencia antes del despliegue (Cap. 2 §2.2). |
| ¿Brecha vs matriz? | Brecha = estado del arte (Cap. 3); matriz = problema tecnológico del diseño (Anexo C). |
| ¿Por qué no experimentan ahora? | Guía 1 = solo diseño (§1.6); protocolo bosquejado en §4.2 para Tesis 2. |
| ¿Leíste la referencia que citas? | Sí → mostrar pasaje en Casas / Shvaiko (tener PDF abierto). |

---

## 7. Exposición final con PPT (30 jul)

**Archivo generado:** [`ppt/Exposicion_Plan_Tesis_Grupo9.2.pptx`](ppt/Exposicion_Plan_Tesis_Grupo9.2.pptx) (21 diapositivas · ppt-rules completo)  
**Revisión Alex/Jack:** [`ppt/REVISION_PPT_ALEX_JACK.md`](ppt/REVISION_PPT_ALEX_JACK.md)  
**Guion oral:** [`ppt/NOTAS_ORAL_RUBRICA.md`](ppt/NOTAS_ORAL_RUBRICA.md)

### Diapositivas (12 — ~12 min)

1. Título + IEEE/ACM + integrantes  
2. Introducción — conceptos y estrategia  
3. Ontología (Fig. objeto/UA)  
4. Problemática real (TSB, Casas)  
5. Objeto de estudio  
6. Problema tecnológico + OE1–OE4  
7. Modelo S/E/C (Fig. 3)  
8. Caso A + Caso B  
9. Cadena objetivos (Fig. 4)  
10. Metodología §4.2.1 (verbos)  
11. Brecha V1–V5 (Fig. 6)  
12. Alcance Guía 1 + referencias + cierre  

**Evitar:** párrafos largos en slides; bullets de una línea; animaciones innecesarias.

---

## 8. Errores que penalizan (PI-12/13/14)

- Hablar sin **señalar** el PDF («como mudo sin gestos»).  
- Citar un paper sin poder mostrar **dónde** está la idea.  
- Confundir problemática con problema tecnológico o con objetivo.  
- Decir «no existe método» sin matiz de insuficiencia.  
- Párrafos enormes al proyectar el documento.  
- Figuras de LLM sin fuente o sin rehacer a mano.  
- Llegar tarde o pedir cambio de fecha sin intercambio de ficha.

---

## 9. División de roles sugerida

| Bloque | Alex | Jack |
|--------|------|------|
| Metodología + OE | ✓ navega Cap. 4 | apoyo |
| Problemática + objeto | apoyo | ✓ navega Cap. 1 |
| Referencia Casas | ✓ | — |
| Referencia Shvaiko | — | ✓ |
| Brecha + cierre | mitad | mitad |

Ensayar **una vez completa** grabando pantalla (5 min) y revisar si las ideas «viajan» sin audio.

---

*Guía operativa Grupo 9.2 — sesiones 23/30 jul 2026. Complementa `../planificacion/REVISION_ORAL_ALEX_JACK.md` y `../fases/FEEDBACK_DOCENTE_PI12-14.md`.*
