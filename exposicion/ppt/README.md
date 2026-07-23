# Presentación — exposición final (30 jul)

## Archivo principal (con figuras Alex)

| Archivo | Uso |
|---------|-----|
| **`Exposicion_Plan_Tesis_Grupo9.2-ampliado.pptx`** | **Usar en exposición** — 23 slides · 15 min |
| `Exposicion_Plan_Tesis_Grupo9.2-ampliado.backup.pptx` | Respaldo antes de optimizar |
| `Exposicion_Plan_Tesis_Grupo9.2.pptx` | Versión generada por script (sin figuras Alex) |

**Guion:** [`GUION_15MIN_AMPLIADO.md`](GUION_15MIN_AMPLIADO.md)

## Scripts

```bash
cd plan-tesis/exposicion/ppt
.venv/bin/python3 build_exposicion.py      # PPT base desde cero
.venv/bin/python3 optimize_ampliado.py     # optimizar ampliado (15 min + ppt-rules)
```

## ppt-rules — regla clave

- **Slide 2 Fuentes:** ⛔ **NO EXPONER** en clase (solo entrega Drive). Presentar slide 1 → 3.
- **Matriz consistencia:** slides 18–19 (obligatorio).
- **Formato:** una fuente, texto ≥20 pt; figuras de Alex con caption ≥20 pt añadido.

## Imágenes

Las figuras de Alex se mantienen **como las colocó** (posición manual). El script solo añade captions inferiores donde faltaba texto.
