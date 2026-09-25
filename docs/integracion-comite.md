# Qué tomamos del Comité de Inversión (documento del amigo)

Fuente: `comite-inversion-amigo.md`. Está pensado para decisiones de cartera (Fama-French, renta variable, cadencia lenta). Complementa el diseño original; no lo reemplaza.

## Adoptado (aplica a todo el sistema)
1. **Motor determinista primero, agentes después.** Datos → motor cuantitativo → agentes → voto → decisión. Los agentes interpretan; nunca calculan ni alteran métricas. Si no la calculó el motor: `NO CALCULADO`.
2. **Sin look-ahead.** Todo dato con timestamp point-in-time; si no se puede verificar, se declara.
3. **Jerarquía de evidencia** (cálculo determinista > datos verificados > estados financieros > literatura > macro > investigación > noticias > inferencia del agente). La noticia nunca anula un cálculo.
4. **Etiquetas anti-alucinación:** `DATOS NO DISPONIBLES`, `NO VERIFICADO`, `EVIDENCIA CONTRADICTORIA`.
5. **Defensor vs. Detractor** (adversarios que no votan) y **3 neutrales que votan** (riesgo, fundamental, macro); 2 de 3 decide, se preserva la disidencia.
6. **Veto de riesgo** solo con métrica, umbral, valor observado y mitigación.
7. **Confianza = calidad de la evidencia**, no persuasión.
8. **Audit trail:** cada decisión guarda snapshot de datos, versión del modelo, salidas de agentes, votos y disidencia.
9. **Separar señal / interpretación / gobernanza / acción.**

## Ajustes míos (criterio)
- **Costo y latencia:** 6 agentes × 5 fases son muchas llamadas al LLM. Sirve para decisiones lentas (diarias/semanales, rebalanceo), no para ticks. La ejecución sigue determinista.
- **Votos correlacionados:** 3 neutrales del mismo modelo no son independientes. Mitigar con prompts/datos distintos por agente y, si se puede, modelos distintos. No tratarlo como 3 opiniones reales.
- **Fama-French es de acciones.** En cripto no aplica tal cual; el equivalente es validar el modelo de la estrategia (estabilidad, out-of-sample, régimen). La regla "si no pasa validación, no es evidencia" se mantiene.
- **Riesgo duro en código** sigue mandando sobre cualquier voto: el veto del comité es una capa más, no la única.
