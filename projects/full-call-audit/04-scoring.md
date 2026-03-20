# Fase 4 — Scoring

> Aplicar o modelo de pontuação de 100 pontos em 10 blocos calibrados com base nos segmentos e frameworks detectados.

## Objetivo
Produzir um score objetivo e detalhado que quantifique a performance da call em cada dimensão avaliada.

## Inputs
- Call segmentada em 6 etapas (output da Fase 2)
- Mapa de frameworks detectados com classificação (output da Fase 3)
- Transcrição limpa (output da Fase 1)
- Critérios de scoring do `scoring-methodology.md`

## Atividades
1. Avaliar cada um dos 10 blocos seguindo os critérios padronizados
2. Para cada sub-item de cada bloco, atribuir pontuação: total, parcial (50%) ou zero
3. Citar a evidência textual da transcrição que justifica cada pontuação
4. Calcular score por bloco e score total
5. Comparar com benchmark do closer (se houver histórico no registry)
6. Comparar com benchmark do time (média geral)
7. Aplicar ajustes contextuais se necessário (tipo de call, ticket, nicho)
8. Classificar a call na faixa de performance: excelente, bom, regular, fraco ou crítico
9. Identificar os 3 blocos mais fortes e os 3 mais fracos

## Agentes Responsáveis
- Scoring Agent (responsável principal)
- Benchmark Comparator (suporte para comparações históricas)
- Calibration Agent (suporte para consistência com auditorias anteriores)

## Output
- Scorecard completo com pontuação por bloco e total
- Evidências textuais para cada pontuação
- Comparação com benchmarks (closer e time)
- Classificação de performance (faixa)
- Top 3 forças e top 3 fraquezas

## Critérios de Conclusão
- [ ] Todos os 10 blocos pontuados com evidências
- [ ] Score total calculado corretamente
- [ ] Benchmarks comparados
- [ ] Classificação de faixa definida
- [ ] Top 3 forças e fraquezas identificados

## Próxima Fase
→ Fase 5 — Análise de Causa Raiz
