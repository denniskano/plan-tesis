# Presentación — exposición final (30 jul)

## Archivos

| Archivo | Descripción |
|---------|-------------|
| **`Exposicion_Plan_Tesis_Grupo9.2.pptx`** | Presentación (21 diapositivas, ppt-rules completo) |
| `REVISION_PPT_ALEX_JACK.md` | Revisión cruzada Alex/Jack vs ppt-rules |
| `NOTAS_ORAL_RUBRICA.md` | Guion minuto a minuto |
| `build_exposicion.py` | Script regeneración |
| `assets/` | Figuras PNG del plan |

## Cobertura ppt-rules.pptx

| Sección rules | En PPT |
|---------------|--------|
| Título + ACM/IEEE | Slide 1 |
| Introducción | Slide 2 |
| Ontología | Slide 3 |
| Problemática (2 slides) | Slides 4–5 |
| Objeto + instrumento + ejemplos | Slides 6–8 |
| Problema tecnológico + OG + OE | Slides 9–11 |
| Variables VI / VD | Slides 12–13 |
| Metodología | Slide 14 |
| Artefacto S/E/C | Slide 15 |
| **Matriz consistencia** | **Slides 16–17** |
| Brecha (≠ matriz) | Slide 18 |
| Conclusiones + Recomendaciones + Referencias | Slides 19–21 |

Formato/fuentes/Drive (rules slides 2–3): **no se exponen** (según indicación del docente).

## Imágenes

Insertadas con **ancho fijo 12,1"** (posición 0,6" × 1,35") — proporción original, sin recorte automático. Ajuste fino de posición/tamaño **manual en PowerPoint** si alguna figura alta se superpone al caption.

## Regenerar

```bash
cd plan-tesis/exposicion/ppt
.venv/bin/python3 build_exposicion.py
```
