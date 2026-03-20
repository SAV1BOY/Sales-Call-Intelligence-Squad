# Calibrar Scoring

> Calibrar scoring entre auditores: alinhar critérios, resolver discrepâncias e atualizar padrões.

## Objetivo
Garantir que o score de 75 de um auditor signifique exatamente o mesmo que o score de 75 de outro — sem calibração periódica, scores derivam e perdem comparabilidade.

## Trigger
- Meta-auditoria identificou discrepâncias > 5 pontos
- Novo auditor integrado ao squad
- Trimestralmente (calibração preventiva)
- Mudança significativa em critérios ou frameworks

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| QA Guardian | Conduz sessão de calibração |
| Scorecard Analyst | Fornece análise estatística de discrepâncias |
| Call Auditor | Participa como auditor em calibração |
| Sales Chief | Aprova novos padrões se necessário |

## Inputs
- Resultado da meta-auditoria (discrepâncias identificadas)
- Scorecards de mesmas calls auditadas por diferentes auditores
- Critérios de scoring vigentes
- Histórico de calibrações anteriores
- 3-5 calls selecionadas para exercício de calibração

## Processo
1. Selecionar 3-5 calls representativas (diferentes tipos, scores, resultados)
2. Cada auditor pontua as calls de forma independente (sem ver outros)
3. Comparar scores bloco a bloco: identificar onde divergem
4. Discutir cada divergência: qual interpretação está correta?
5. Documentar consenso: definição exata de cada nota por bloco
6. Atualizar critérios de scoring com definições mais precisas
7. Criar exemplos âncora: "isto é um 3, isto é um 7, isto é um 9" por bloco
8. Re-pontuar as calls com critérios atualizados para validar alinhamento
9. Verificar que variação final é < 3 pontos por bloco
10. Documentar e distribuir padrões atualizados

## Frameworks Aplicados
- Calibration Standards
- Inter-Rater Reliability Framework
- QA Methodology Consistency Check
- Scoring Anchor Examples

## Checklists de Qualidade
- 3-5 calls representativas selecionadas
- Pontuação independente (sem contaminação)
- Divergências discutidas e resolvidas com consenso
- Critérios atualizados com definições precisas
- Exemplos âncora criados por bloco
- Variação final < 3 pontos por bloco

## Output Esperado
- Relatório de calibração em `reports/operations/calibration-PERIODO`
- Critérios de scoring atualizados
- Exemplos âncora por bloco e nota

## Registry Atualizado
- `data/registries/qa-registry.yaml`
- `data/registries/calibration-registry.yaml`

## Critérios de Conclusão
- [ ] Exercício de calibração concluído (3-5 calls)
- [ ] Divergências resolvidas com consenso
- [ ] Critérios atualizados e documentados
- [ ] Exemplos âncora criados
- [ ] Variação < 3 pontos validada
- [ ] Padrões distribuídos para todos os auditores
