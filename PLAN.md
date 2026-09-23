# PLAN — trading-agentes

## Objetivo
Sistema de trading autónomo, paper trading primero, con LLM como analista y ejecución/riesgo deterministas.

## Fases
1. **Decisiones base** — elegir mercado (cripto/forex), broker/exchange y motor (Freqtrade vs NautilusTrader). Terminada cuando: decisiones registradas en STATUS.md.
2. **Datos y backtest honesto** — ingesta histórica, una estrategia base simple (momentum), walk-forward con costos. Terminada cuando: script reproduce métricas y supera buy&hold ajustado por riesgo.
3. **Ejecutor + riesgo duro** — módulo determinista con límites, kill switch (Telegram) y modo paper. Terminada cuando: tests cubren cada límite y el kill switch cierra todo.
4. **Capa LLM** — agente analista de noticias/hipótesis que solo emite señales al riesgo. Terminada cuando: A/B mostrando si añade valor sobre la estrategia base.
5. **Paper trading continuo** — servicio siempre activo en el servidor, logs y reporte diario. Terminada cuando: 4-8 semanas sin fallos y métricas aceptables.
6. **Capital real mínimo** — solo con aprobación explícita de Juan.

## Fuera de alcance
Kubernetes, Kafka, nube, dashboards Vercel, HFT.
