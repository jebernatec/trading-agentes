# PLAN — trading-agentes

## Objetivo
Sistema de trading autónomo, paper trading primero, con LLM como analista y ejecución/riesgo deterministas.

## Fases
1. **Decisiones base** — elegir mercado (cripto/forex), broker/exchange y motor (Freqtrade vs NautilusTrader). Terminada cuando: decisiones registradas en STATUS.md.
2. **Datos y backtest honesto** — ingesta histórica, una estrategia base simple (momentum), walk-forward con costos. Terminada cuando: script reproduce métricas y supera buy&hold ajustado por riesgo.
3. **Ejecutor + riesgo duro** — módulo determinista con límites, kill switch (Telegram) y modo paper. Terminada cuando: tests cubren cada límite y el kill switch cierra todo.
4. **Capa LLM (comité)** — analistas + defensor/detractor + 3 neutrales con voto 2/3 y veto de riesgo (ver `docs/integracion-comite.md`) sobre el motor determinista; solo emite señales al riesgo, con audit trail. Terminada cuando: A/B muestra si añade valor sobre la estrategia base, con costo de LLM medido.
5. **Paper trading continuo** — servicio siempre activo en el servidor, logs y reporte diario. Terminada cuando: 4-8 semanas sin fallos y métricas aceptables.
6. **Capital real mínimo** — solo con aprobación explícita de Juan.

## Fuera de alcance
Kubernetes, Kafka, nube, dashboards Vercel, HFT.
