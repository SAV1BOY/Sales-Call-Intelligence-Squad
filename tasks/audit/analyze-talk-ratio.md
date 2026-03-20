# Analisar Talk Ratio

> Analisar proporção de fala closer vs. lead, quantidade de perguntas, interrupções e silêncios.

## Objetivo
Medir quantitativamente o equilíbrio de fala na call — closer que fala demais não descobre dor, closer que fala de menos perde controle. Talk ratio é indicador direto de qualidade de discovery.

## Trigger
- Transcrição normalizada com speaker tags disponível
- Execução do workflow `06-full-funnel-call-audit`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Talk Ratio Analyst | Calcula métricas quantitativas de talk ratio |
| Call Auditor | Interpreta métricas no contexto da call |
| Jeremy Miner | Valida se perguntas dominaram a fala do closer |

## Inputs
- Transcrição normalizada com speaker tags `[CLOSER]` e `[LEAD]`
- Timestamps de cada turno de fala
- Mapa de etapas da call (para talk ratio por fase)

## Processo
1. Calcular tempo total de fala do closer vs. lead (em minutos e percentual)
2. Calcular talk ratio global (ideal: closer 40%, lead 60%)
3. Calcular talk ratio por etapa: rapport, discovery, pitch, pricing, objeções, closing
4. Contar número total de perguntas feitas pelo closer
5. Classificar perguntas: abertas vs. fechadas, investigativas vs. retóricas
6. Contar interrupções: closer interrompendo lead e vice-versa
7. Identificar monólogos longos do closer (>2 minutos sem pausa)
8. Identificar silêncios significativos (>5 segundos) e contexto
9. Avaliar se talk ratio por fase está adequado (discovery: lead 70%+, pitch: closer 70%+)
10. Comparar com benchmarks da equipe e histórico do closer

## Frameworks Aplicados
- Talk Ratio Analysis Framework
- NEPQ: perguntas dominam a fala (Miner)
- Doctor Frame: diagnóstico exige ouvir

## Checklists de Qualidade
- Talk ratio global calculado com precisão
- Talk ratio por etapa calculado e comparado com benchmarks
- Perguntas contadas e classificadas (abertas/fechadas)
- Interrupções contadas e contextualizadas
- Monólogos longos identificados com timestamp

## Output Esperado
- Análise de talk ratio em `reports/analysis/CALL-ID-talk-ratio`
- Métricas: ratio global, ratio por etapa, perguntas, interrupções
- Nota do bloco talk ratio (0-10) com justificativa

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo talk_ratio_score)

## Critérios de Conclusão
- [ ] Talk ratio global calculado (% closer vs. % lead)
- [ ] Talk ratio por etapa calculado
- [ ] Perguntas contadas e classificadas
- [ ] Interrupções identificadas
- [ ] Monólogos e silêncios mapeados
- [ ] Nota atribuída com comparação a benchmarks
