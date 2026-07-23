# Libreto completo — Exposición Plan de Tesis Grupo 9.2

**PPT:** `ppt/Exposicion_Plan_Tesis_Grupo9.2-ampliado.pptx`  
**Duración:** 15:00 (22 slides orales; **omitir slide 2**)  
**Integrantes:** Alex Mancilla · Jack Paitan  
**Regla:** señalar la diapositiva al hablar (como «mudo que señala» — PI-13).

---

## Antes de empezar

- [ ] PDF Casas (2021) y Shvaiko (2005) abiertos en pestañas
- [ ] PDF plan §1.4 / Anexo C listo por si preguntan matriz
- [ ] Navegación: slide **1 → 3** (saltar slide 2 Fuentes)

---

## SLIDE 1 · 0:00–0:45 · **Jack**

**Diapositiva:** Título + IEEE/ACM

> Buenas [tardes/noches]. Somos el Grupo 9.2 — Alex Mancilla y Jack Paitan.  
>  
> Nuestro plan de tesis aborda la **alineación entre contratos OpenAPI bancarios y Service Domains BIAN**, mediante un modelo de puntuación **S, E, C** y un **AlignmentScore** integrado.  
>  
> Es una **investigación tecnológica** en la línea de **design science**: diseñamos un procedimiento reproducible, no implementamos aún el software en producción.  
>  
> Clasificamos el tema en **IEEE: Knowledge Representation** y **ACM: Semantic networks / alineación de esquemas**, porque comparamos representaciones formales de negocio y de API.

**Acción:** señalar título y líneas IEEE/ACM.

---

## SLIDE 2 · ⛔ NO EXPONER

**Avanzar directo a slide 3.** (Fuentes = entrega Drive, ppt-rules §3.)

---

## SLIDE 3 · 0:45–1:35 · **Alex**

**Diapositiva:** Introducción §1.1

> En banca, las APIs se documentan con **OpenAPI**: un contrato YAML o JSON legible por máquina. Casas et al. confirman que es el estándar de facto — lo citamos en la problemática.  
>  
> En paralelo, **BIAN** organiza capacidades de negocio en **Service Domains**; actúa como **referencia**, no sustituye el contrato técnico — Farzi, 2021.  
>  
> Llamamos **alineación** al grado en que un contrato OpenAPI y un Service Domain emparejado coinciden en **estructura y significado**.  
>  
> El producto del estudio es el modelo **SemanticScore (S)**, **StructuralScore (E)**, **CoverageScore (C)** y el **AlignmentScore** agregado.  
>  
> En esta **Guía 1** documentamos el **diseño** del procedimiento. La validación empírica a escala queda para **Tesis 2**, según §1.6.

**Acción:** marcar cada bullet al nombrarlo; no leer el slide entero de corrido.

---

## SLIDE 4 · 1:35–2:20 · **Jack**

**Diapositiva:** Ontología (figura)

> Esta figura resume nuestra **ontología interna** — no es una contribución publicada; nos orienta al redactar y al exponer.  
>  
> Señalo cuatro piezas: el **objeto de estudio real** es el **contrato OpenAPI bancario** completo. La **unidad de análisis** es la **instancia** de medición: un par comparable dentro del contrato evaluado contra un Service Domain, identificado como `{fuente}_{service-domain}_{versión}`.  
>  
> El **producto** son los scores **S, E, C** y el **AlignmentScore**. **BIAN** es **referencia de contraste**, no el objeto.  
>  
> Esta distinción evita la pregunta típica: «¿evalúan BIAN o el contrato?» — evaluamos el **contrato** frente a BIAN.

**Acción:** señalar cajas objeto · UA · producto · referencia BIAN.

---

## SLIDE 5 · 2:20–3:10 · **Jack**

**Diapositiva:** Problemática — situación real (figura)

> Pasamos a la **problemática**, §1.2 — la **situación real**. Esto **no** es el problema de la matriz ni el problema tecnológico.  
>  
> **¿Dónde ocurre?** En el ecosistema bancario digital: APIs propias, fintechs, **open banking** — por ejemplo la investigación de la CMA en Reino Unido, 2016.  
>  
> **¿Quiénes actúan?** Arquitectura, integración, gobernanza de APIs y socios externos.  
>  
> Los **síntomas** los vemos en la siguiente diapositiva; aquí la idea es: hay **dolor observable** en el sector — fragmentación, costos de integración — y eso **motiva** medir coherencia **antes** de integrar, pero **no se resuelve** solo con nuestro artefacto de diseño.

**Acción:** señalar figura de contexto / actores en la imagen.

---

## SLIDE 6 · 3:10–4:05 · **Jack**

**Diapositiva:** Síntomas, dolor, estadísticas (2 figuras)

> Los **síntomas** concretos: **fragmentación semántica** entre equipos, **retrabajo** en adaptadores, **deriva** entre negocio y capa REST en cada release.  
>  
> Caso **TSB, 2018**: fallas masivas tras migración IT — muestra el riesgo cuando la capa API pierde trazabilidad con el negocio. *(Señalar figura TSB si aplica.)*  
>  
> **Casas et al., 2021** — mapeo de 47 artículos: el **68 %** propone herramientas y el **43 %** mejora documentación, pero **ninguno** enlaza OpenAPI con modelos BIAN de forma sistemática. *(Señalar figura Casas / cifra.)*  
>  
> Si el docente pide el paper: «Sí, lo leímos» — abrir PDF Casas y señalar el apartado del mapeo.

**Acción:** señalar **ambas** figuras; mencionar cifra **68 %** de memoria.

---

## SLIDE 7 · 4:05–4:50 · **Jack**

**Diapositiva:** Objeto de estudio — situación subyacente (figura)

> Subimos un nivel: la **situación subyacente**, §1.4. La **causa** abstracta de los síntomas es la **desalineación** entre dos jerarquías comparables: el **contrato OpenAPI** — paths, operations, schemas — y el **Service Domain BIAN** — behaviors, business objects, relaciones.  
>  
> El **objeto de estudio** es el **contrato OpenAPI bancario** — el archivo YAML o JSON publicado. **No** evaluamos código en producción ni tráfico runtime.  
>  
> BIAN funciona como **modelo de referencia** para contrastar si la interfaz expuesta cuenta la misma historia de negocio.

**Acción:** señalar capa técnica vs capa negocio en la figura.

---

## SLIDE 8 · 4:50–5:30 · **Jack**

**Diapositiva:** Objeto real — taxonomía y ciclo de vida

> El **objeto de estudio real** existe independiente del observador: es el contrato que el banco **publica**.  
>  
> Su **taxonomía** en el plan: OpenAPI **3.x**, dominios como pagos, cuentas o préstamos, versiones versionadas en repositorio de APIs.  
>  
> El **ciclo de vida** del **contrato** — diseño, revisión, publicación, consumo — **no** confundirlo con el ciclo de vida del proceso bancario completo.  
>  
> Ejemplos concretos están en el **Anexo F** del informe.

**Acción:** señalar figura taxonomía / ciclo si está en la imagen.

---

## SLIDE 9 · 5:30–6:15 · **Alex**

**Diapositiva:** Instrumento y objeto modelado (figura procedimiento)

> Para **capturar** propiedades del contrato usamos un **instrumento** documental, no encuestas ni IoT:  
>  
> — **Parser OpenAPI 3.x** + extracto del Service Domain BIAN.  
> — **Procedimiento de normalización** (OE1).  
> — **Schema matching** y **similitud semántica** para calcular E y S.  
>  
> El **objeto modelado** son representaciones normalizadas, matrices de correspondencia y scores en **[0, 1]**.  
>  
> En la siguiente slide mostramos **ejemplos** y **estados** de clasificación del artefacto.

**Acción:** señalar flujo instrumento → representación → scores en la figura.

---

## SLIDE 10 · 6:15–7:00 · **Alex**

**Diapositiva:** Casos A/B + estados (figura)

> **Caso A — SemanticScore (S):** en OpenAPI tenemos `POST /payments` con schema `PaymentRequest`; en BIAN, `InitiatePayment` y `PaymentOrder`. Mismos roles de negocio, **nombres distintos** → baja **S**. *(Señalar columna OpenAPI / BIAN.)*  
>  
> **Caso B — CoverageScore (C):** el contrato solo expone `GET /payments/{id}`, pero BIAN define además `Initiate`, `Confirm` y `Cancel Payment`. Cobertura **incompleta** → baja **C** aunque el matching estructural E sea alto.  
>  
> El artefacto clasifica el contrato en **Alta, Media, Baja o Nula** según umbrales provisionales: **0,80 / 0,60 / 0,40** — convención del diseño, calibración futura en Tesis 2.  
>  
> Los scores se calculan por **unidad de análisis** y se interpretan por **contrato × Service Domain**.

**Acción:** señalar casos y escala Alta–Nula.

---

## SLIDE 11 · 7:00–7:50 · **Alex**

**Diapositiva:** Problema tecnológico + P1–P4

> Este es el **problema tecnológico** — §1.3 — el de la **matriz de consistencia**. Es **distinto** de la problemática del sector.  
>  
> Decimos que los métodos actuales son **insuficientes o no adaptados** a OpenAPI↔BIAN — **no** «no existe ningún método». Hay revisión manual y schema matching genérico, pero falta un procedimiento **reproducible** para este par artefactual.  
>  
> El **artefacto** a diseñar: procedimiento + modelo **S/E/C → AlignmentScore** — software **documentado** en el plan.  
>  
> Las preguntas **P1–P4** operacionalizan: **P1** matching estructural → **E**; **P2** similitud semántica → **S**; **P3** cobertura → **C**; **P4** score integrado y clasificación.

**Acción:** enfatizar «**insuficiente**»; señalar P1–P4.

---

## SLIDE 12 · 7:50–8:25 · **Alex**

**Diapositiva:** Objetivo general + VD

> **Insumo inicial:** contrato OpenAPI bancario + Service Domain BIAN emparejado.  
>  
> **Objetivo general técnico:** diseñar el modelo S/E/C y el procedimiento reproducible de alineación.  
>  
> **Variable dependiente del artefacto:** el **AlignmentScore** en **[0, 1]** más la **clasificación** por niveles.  
>  
> El **objetivo superior** — consecuencia en el mundo real si el artefacto operara — es que equipos de arquitectura **cuantifiquen coherencia antes del despliegue**. En Guía 1 **no implementamos** ese cambio en producción; entregamos el **diseño**.

**Acción:** distinguir OG técnico vs objetivo superior.

---

## SLIDE 13 · 8:25–9:15 · **Alex**

**Diapositiva:** OE1–OE4 — cadena (figura)

> Cada **objetivo específico** es un **hito con producto medible** — no confundir con «programar en Python» o «hacer experimentos», que el docente descarta como OE.  
>  
> **OE1:** normalizar → representaciones comparables.  
> **OE2:** emparejar estructuras → **StructuralScore (E)**.  
> **OE3:** similitud semántica → **SemanticScore (S)**.  
> **OE4:** integrar → **CoverageScore (C)**, **AlignmentScore** y tipologías de desalineación.  
>  
> La **Fase 1** del modelo es el **diseño** del procedimiento; **OE1–OE4** son transformadores sucesivos sobre los artefactos — como muestra la figura.

**Acción:** recorrer la cadena con el cursor en la figura.

---

## SLIDE 14 · 9:15–9:55 · **Alex**

**Diapositiva:** Variables independientes (Tabla 5)

> Las **variables independientes** son **factores de diseño** que controla el investigador — **no** hiperparámetros de entrenamiento como epochs o learning rate.  
>  
> **OE1:** esquema de **representación intermedia**.  
> **OE2:** estrategia de **schema matching** — Shvaiko & Euzenat, 2005.  
> **OE3:** técnica de **similitud semántica** — embeddings, ontología o híbrido.  
> **OE4:** pesos **α, β, γ** de agregación, con **α + β + γ = 1**.  
>  
> Cada factor tiene **estados o alternativas** definidas en el plan para una validación futura.

**Acción:** señalar filas OE1–OE4 en la tabla del slide.

---

## SLIDE 15 · 9:55–10:35 · **Alex**

**Diapositiva:** Variables dependientes (Tabla 5 · Anexo D)

> Las **variables dependientes** son los **ratios** medidos:  
>  
> **OE1:** completitud de la normalización.  
> **OE2:** **E** ∈ [0, 1].  
> **OE3:** **S** ∈ [0, 1].  
> **OE4:** **C**, **AlignmentScore** y nivel de clasificación.  
>  
> Fórmula central: **AlignmentScore = α·S + β·E + γ·C**.  
>  
> El detalle operativo de medición está en el **Anexo D**; la trazabilidad con hipótesis, en el **Anexo C**.

**Acción:** decir la fórmula mirando slide 17 si hace falta reforzar.

---

## SLIDE 16 · 10:35–11:15 · **Alex**

**Diapositiva:** Metodología — 5 fases con verbos

> Si el docente pide «empiecen por metodología», esta es la slide — PI-14.  
>  
> **Fase 1 · Diseñar** entradas, scores y umbrales → modelo documentado.  
> **Fase 2 · Normalizar** (OE1).  
> **Fase 3 · Emparejar** estructuralmente → E (OE2).  
> **Fase 4 · Calcular** similitud → S (OE3).  
> **Fase 5 · Integrar** S, E, C → C + AlignmentScore + tipologías (OE4).  
>  
> Cada verbo corresponde a una fila de la tabla §4.2.1 del informe.

**Acción:** señalar cada fase; tener PDF §4.2.1 por si profundizan.

---

## SLIDE 17 · 11:15–12:00 · **Alex**

**Diapositiva:** Artefacto S / E / C (figura)

> El **artefacto** descompone la evaluación en tres componentes:  
>  
> **E (StructuralScore):** correspondencia entre organización REST y modelo BIAN — base teórica en **Shvaiko & Euzenat, 2005**.  
> **S (SemanticScore):** similitud de significado entre conceptos.  
> **C (CoverageScore):** proporción del Service Domain cubierta por el contrato.  
>  
> **AlignmentScore = α·S + β·E + γ·C** → clasificación **Alta / Media / Baja / Nula**.  
>  
> **S, E y C se calculan por unidad de análisis**; el score global se interpreta por **contrato × Service Domain**.

**Acción:** señalar S, E, C y la fórmula en la figura. Tener PDF Shvaiko listo.

---

## SLIDE 18 · 12:00–12:40 · **Alex**

**Diapositiva:** Matriz de consistencia (I)

> La **matriz de consistencia**, Anexo C, alinea **problema tecnológico**, **objetivo**, **producto verificable** por fase. **No** es la brecha del estado del arte.  
>  
> **Fase 1:** problema — método insuficiente para cuantificar alineación OpenAPI↔BIAN; objetivo — diseñar modelo S/E/C; producto — modelo metodológico documentado.  
>  
> **Fase 2 / OE1:** representaciones no comparables → normalizar → representaciones versionadas.  
>  
> **Fase 3 / OE2:** sin E sistemático → emparejar → matriz + **E** ∈ [0, 1].  
>  
> Señalo las columnas **Problema → Objetivo → Producto**; el detalle completo está en el PDF Anexo C.

**Acción:** señalar columnas de la tabla; no leer celda por celda.

---

## SLIDE 19 · 12:40–13:20 · **Alex**

**Diapositiva:** Matriz de consistencia (II)

> Segunda parte: **variables independientes**, **dependientes** e **hipótesis** por fase.  
>  
> **H1 (OE1):** normalización intermedia habilita cálculo sistemático de S, E, C.  
> **H2 (OE2):** schema matching produce **E** coherente con la organización REST vs BIAN.  
> **H3 (OE3):** similitud semántica produce **S** que discrimina desalineaciones.  
> **H4 (OE4):** agregación ponderada produce **AlignmentScore** interpretable.  
>  
> Los factores **α, β, γ** y los ratios **S, E, C** quedan explícitos en la matriz y en la Tabla 5 del Capítulo 2.

**Acción:** mencionar H1–H4; abrir Anexo C si el docente pide fila completa.

---

## SLIDE 20 · 13:20–14:00 · **Jack + Alex**

**Diapositiva:** Brecha V1–V5 (figura)

**Jack (V1–V2):**

> La **brecha** viene del **estado del arte**, §3.6 — **distinta** de la matriz.  
> **V1:** no hay marco sistemático OpenAPI↔BIAN. **V2:** falta cuantificación reproducible de desalineación.

**Alex (V3–V5):**

> **V3:** integración S+E+C en un score interpretable. **V4:** procedimiento aplicable pre-despliegue. **V5:** separación clara entre calidad runtime y coherencia documental.  
>  
> La figura muestra la transición E1–E6 → vacíos V1–V5 → oportunidad de nuestro plan.

**Acción:** señalar vacíos en la figura; cerrar: «**Brecha ≠ matriz**».

---

## SLIDE 21 · 14:00–14:30 · **Jack**

**Diapositiva:** Conclusiones

> Concluimos con **relaciones entre conceptos**, no con opinión personal:  
>  
> OpenAPI es **maduro** como artefacto técnico; falta un procedimiento **OpenAPI↔BIAN** reproducible.  
> Objeto (**contrato**) + referencia (**BIAN**) + **UA** (instancia) producen scores **S, E, C** integrados.  
> **OE1–OE4** encadenan transformaciones con productos verificables.  
> La **matriz Anexo C** cierra trazabilidad problema → objetivos → VI/VD → hipótesis.  
> **Guía 1** entrega el **diseño**; **Tesis 2** prevé software y validación empírica.

---

## SLIDE 22 · 14:30–14:45 · **Alex**

**Diapositiva:** Recomendaciones (breve)

> Como **recomendaciones** para continuidad: implementar el artefacto según §4.2; calibrar umbrales con muestra bancaria; validar **H1–H4** con contratos públicos del Anexo F; integrar el score en gobernanza de APIs **antes** del despliegue.

---

## SLIDE 23 · 14:45–15:00 · **Jack**

**Diapositiva:** Referencias + cierre

> Citamos en esta exposición a **Casas et al., 2021**; **Shvaiko & Euzenat, 2005**; **Farzi, 2021**; **CMA, 2016**; y el caso **TSB, 2018**.  
>  
> Tenemos los PDFs de **Casas** y **Shvaiko** disponibles para mostrar el pasaje citado.  
>  
> **¿Preguntas?**  
>  
> *(Cierre fijo, 15 s:)* «El plan entrega el **diseño** del procedimiento S/E/C; la **validación empírica** queda en **Tesis 2**, §1.6.»

---

## Anexo — Respuestas rápidas (preguntas del docente)

| Pregunta | Respuesta (quien responde) |
|----------|----------------------------|
| ¿Cuál es la UA? | Instancia `{fuente}_{SD}_{versión}`: par endpoint/schema ↔ behavior/BO dentro del contrato vs un SD. (**Jack**) |
| ¿Objeto de estudio? | Contrato OpenAPI bancario completo (YAML/JSON). BIAN = referencia. (**Jack**) |
| ¿Tres niveles de problema? | Real §1.2 → subyacente §1.4 → tecnológico §1.3 / matriz. (**Alex**) |
| ¿Brecha vs matriz? | Brecha = Cap. 3 estado del arte; matriz = problema tecnológico Anexo C. (**Alex**) |
| ¿Por qué no experimentan? | Guía 1 = diseño §1.6; protocolo bosquejado para Tesis 2. (**Alex**) |
| ¿Leíste Casas/Shvaiko? | Sí → abrir PDF y señalar párrafo (68 % Casas; taxonomía matching Shvaiko). (**quien citó**) |
| ¿Instancia o contrato? | UA = instancia; score global agregado por contrato × SD. (**Alex**) |

---

## Errores a evitar (PI-12/13/14)

- Hablar sin señalar la diapositiva  
- Decir «no existe método» (usar **insuficiente / no adaptado**)  
- Confundir problemática ↔ problema tecnológico ↔ brecha ↔ matriz  
- Exponer slide 2 Fuentes  
- Leer párrafos enteros del slide  

---

*Libreto Grupo 9.2 — sincronizado con `Exposicion_Plan_Tesis_Grupo9.2-ampliado.pptx` y `GUION_15MIN_AMPLIADO.md`.*
