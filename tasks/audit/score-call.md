# Pontuar Call

> Atribuir pontuação estruturada à call: 10 blocos, 100 pontos, com evidência textual por bloco.

## Objetivo
Gerar score objetivo e granular da call que permita comparação entre closers, evolução temporal e priorização de coaching — eliminando avaliações subjetivas.

## Trigger
- Frameworks detectados e relatório de detecção disponível
- Execução do workflow `04-scoring-and-root-cause`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Scorecard Analyst | Executa pontuação dos 10 blocos com evidência |
| Call Auditor | Valida coerência entre score e análises de etapa |
| QA Guardian | Audita consistência de scoring com calibração vigente |

## Inputs
- Transcrição segmentada com timestamps
- Relatório de frameworks detectados
- Mapa de etapas da call
- Scorecard template vigente com pesos por tipo de call
- Calibração de scoring atualizada

## Processo
1. Carregar scorecard template com pesos ajustados ao tipo de call
2. Avaliar cada um dos 10 blocos: rapport, discovery, diagnóstico, pitch, value stack, pricing, objeções, fechamento, talk ratio, controle de frame
3. Para cada bloco: atribuir nota de 0 a 10 com justificativa baseada em trecho da transcrição
4. Aplicar pesos por bloco conforme tipo de call (first call, follow-up, closing, discovery)
5. Calcular score total ponderado (0-100)
6. Classificar performance: Excelente (85+), Boa (70-84), Regular (50-69), Fraca (<50)
7. Identificar os 3 blocos mais fortes e os 3 mais fracos
8. Comparar score com média histórica do closer e da equipe
9. Gerar scorecard visual com distribuição por bloco

## Frameworks Aplicados
- Call Scorecard Framework (10 blocos)
- Sales Call Stage Taxonomy
- Calibração de scoring vigente

## Checklists de Qualidade
- Todos os 10 blocos pontuados com nota de 0 a 10
- Cada nota tem evidência textual com timestamp
- Pesos aplicados conforme tipo de call
- Score total calculado corretamente (soma ponderada)
- Comparação histórica incluída

## Output Esperado
- Scorecard completo em `reports/scorecards/CALL-ID-scorecard`
- Score total ponderado com classificação de performance
- Top 3 forças e top 3 fraquezas com evidência

## Registry Atualizado
- `data/registries/scorecards-registry.yaml`
- `data/registries/closer-performance-registry.yaml`

## Critérios de Conclusão
- [ ] 10 blocos pontuados com evidência textual
- [ ] Pesos ajustados ao tipo de call
- [ ] Score total calculado e classificado
- [ ] Forças e fraquezas identificadas
- [ ] Comparação histórica realizada
- [ ] Registry de scorecards atualizado

---

## Contexto
O score é o artefato central do pipeline de auditoria — sem pontuação objetiva e granular, não há como comparar closers, medir evolução temporal nem priorizar coaching. Esta task existe para eliminar avaliações subjetivas, produzindo um score de 0-100 em 10 blocos com evidência textual por bloco, que serve como base para causa raiz, coaching e certificação.

## Especificação de I/O
- **Input**: Transcrição segmentada com timestamps + relatório de frameworks detectados + mapa de etapas da call + scorecard template vigente com pesos por tipo de call + calibração de scoring atualizada
- **Output**: `templates/scorecards/call-scorecard-template.md` + score total ponderado (0-100) com classificação de performance + top 3 forças e top 3 fraquezas com evidência

## Quality Gates Intermediários
- Após análise inicial: todos os 10 blocos pontuados com nota de 0-10; cada nota tem evidência textual com timestamp; pesos aplicados conforme tipo de call
- Antes de output final: qa-guardian audita consistência de scoring com calibração vigente; score total calculado corretamente (soma ponderada); comparação histórica incluída

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar) e framework-detector (complementar detecções)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre scorecard-analyst e call-auditor sobre nota de bloco: escalar para qa-guardian para arbitragem com base na calibração vigente

## Métricas de Sucesso
- Precisão do score: variância < 10% entre auditores diferentes na mesma call (calibração)
- 100% dos blocos com evidência textual (zero notas sem justificativa)

## Referências Cruzadas
- Workflow: `workflows/04-scoring-and-root-cause.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/scorecard-analyst.md`, `agents/call-auditor.md`, `agents/qa-guardian.md`
- Templates: `templates/scorecards/call-scorecard-template.md`, `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/scorecards-registry`
