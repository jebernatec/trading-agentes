# trading-agentes

Sistema de trading autónomo 24/7 que corre en el portátil-servidor de Juan. El LLM solo analiza (noticias, hipótesis); riesgo, sizing y ejecución son código determinista. Producto propio, para Juan.

## Objetivo y criterio de terminado
Paper trading estable 4-8 semanas con métricas aceptables (definidas en PLAN.md) antes de tocar capital real. Capital real solo con orden explícita de Juan.

## Fuentes de verdad
- `docs/diseno-original.md`: diseño inicial (sobredimensionado: K8s/Kafka/nube no aplican).
- `docs/comite-inversion-amigo.md` + `docs/integracion-comite.md`: marco de comité multi-agente y qué adoptamos.
- Referencias investigadas: NautilusTrader, Freqtrade, vectorbt, TradingAgents (TauricResearch).
- Estudios: los LLM decidiendo compra/venta rinden peor que un momentum simple; usarlos como analistas.

## Reglas específicas
- Prohibido operar con dinero real sin orden explícita de Juan en la sesión.
- Límites duros (pérdida diaria, tamaño máximo, kill switch) viven en el ejecutor, nunca en un agente.
- El LLM nunca llama al broker directamente.
- Backtests: walk-forward, con costos y slippage. Cifras siempre reproducibles con script.
- Agentes no calculan métricas: motor determinista; si falta, `NO CALCULADO`. Sin look-ahead (datos point-in-time). Cada decisión deja audit trail.
- API keys solo en `.env` (ignorado por git).

## Mapa
- `src\` código · `datos\` datos de mercado (no versionados) · `docs\` diseño y notas · `entregables\` reportes.
