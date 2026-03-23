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

---

## Contexto
Talk ratio e um indicador quantitativo direto de qualidade de vendas consultivas. Closer que fala demais nao descobre dor; closer que fala de menos perde controle do frame. Esta task existe para fornecer dados objetivos (nao opinativos) sobre o equilibrio de fala, alimentando o scoring e o coaching com metricas concretas.

## Especificacao de I/O
- **Input**: Transcricao normalizada com speaker tags `[CLOSER]` e `[LEAD]` + timestamps de cada turno de fala + mapa de etapas da call
- **Output**: `templates/reports/full-call-audit-report.md`, secao "Talk Ratio" + metricas: ratio global, ratio por etapa, contagem de perguntas, interrupcoes, monologos

## Quality Gates Intermediarios
- Apos analise inicial: talk ratio global calculado com precisao (% closer vs. % lead); talk ratio por etapa calculado e comparado com benchmarks (discovery: lead 70%+, pitch: closer 70%+)
- Antes de output final: qa-guardian valida que metricas de talk ratio sao coerentes com as notas de discovery e rapport (talk ratio invertido no discovery deve refletir em nota baixa de discovery)

## Escalation & Rework
- Se dados insuficientes para analise: escalar para transcript-analyst (reprocessar speaker tags e timestamps)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre metricas quantitativas e avaliacao qualitativa do call-auditor: escalar para qa-guardian para arbitragem

## Metricas de Sucesso
- Precisao do calculo de talk ratio: margem de erro < 5% vs. contagem manual
- Talk ratio medio do time rastreado semanalmente com tendencia de melhoria

## Handoff
- Output entregue a: call-auditor / sales-chief (consolidação no full-call-audit, workflow 06 Etapa 3 — relatório executivo)
- Formato de entrega: `templates/reports/full-call-audit-report.md`, seção "Talk Ratio" + métricas quantitativas (ratio global, ratio por etapa, contagem de perguntas, interrupções, monólogos)
- Condição de entrega: checklist obrigatório de Critérios de Conclusão 100% aprovado + qa-guardian valida coerência entre métricas de talk ratio e notas de discovery/rapport
- Próximo passo no pipeline: workflow 06 Etapa 2 (pipeline de análise completa) → Etapa 3 (consolidação do relatório executivo)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-10 com revalidação do checklist obrigatório
- Max ciclos: 2
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 2 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referencias Cruzadas
- Workflow: `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/talk-ratio-analyst.md`, `agents/call-auditor.md`
- Templates: `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/scorecards-registry`
