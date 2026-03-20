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
