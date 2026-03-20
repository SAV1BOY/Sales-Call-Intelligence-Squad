# Meta-Auditoria: QA das Auditorias

> Auditar qualidade das próprias auditorias: consistência, precisão, completude e calibração.

## Objetivo
Garantir que as auditorias produzidas pelo squad são precisas, consistentes e calibradas — sem meta-auditoria, vieses se acumulam e scores perdem confiabilidade ao longo do tempo.

## Trigger
- A cada 10 auditorias concluídas
- Discrepância significativa entre auditorias de mesmo tipo
- Onboarding de novo auditor (calibração inicial)

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| QA Guardian | Executa meta-auditoria completa |
| Sales Chief | Valida resultados e define ações corretivas |
| Scorecard Analyst | Fornece análise estatística de consistência |

## Inputs
- Últimas 10-20 auditorias completas
- Scorecards gerados no período
- Checklists de qualidade aplicados
- Histórico de calibração de scoring
- Feedback dos gestores sobre utilidade das auditorias

## Processo
1. Selecionar amostra representativa de auditorias (10-20)
2. Re-auditar 2-3 calls da amostra de forma independente
3. Comparar scores: variação entre auditoria original e re-auditoria
4. Verificar completude: todos os campos e seções preenchidos?
5. Verificar precisão: evidências textuais corretas e no contexto certo?
6. Verificar consistência: calls similares receberam scores similares?
7. Avaliar qualidade das reescritas: específicas, naturais, framework correto?
8. Verificar se checklists de qualidade foram efetivamente aplicados
9. Calcular taxa de concordância inter-auditor (se múltiplos auditores)
10. Gerar relatório de QA com discrepâncias e ações corretivas

## Frameworks Aplicados
- QA Methodology Consistency Check
- Inter-Rater Reliability Framework
- Calibration Standards

## Checklists de Qualidade
- Amostra representativa selecionada (variação de closers, resultados, tipos)
- Re-auditoria feita de forma independente (sem ver original)
- Discrepâncias quantificadas (variação de score por bloco)
- Completude verificada em 100% da amostra
- Ações corretivas específicas por discrepância

## Output Esperado
- Relatório de QA em `reports/reviews/qa-audit-PERIODO`
- Taxa de concordância e discrepâncias por bloco
- Ações corretivas para calibração

## Registry Atualizado
- `data/registries/qa-registry.yaml`
- `data/registries/review-registry.yaml`

## Critérios de Conclusão
- [ ] Amostra de 10-20 auditorias revisada
- [ ] Re-auditoria independente realizada (2-3 calls)
- [ ] Discrepâncias quantificadas
- [ ] Completude e precisão verificadas
- [ ] Ações corretivas definidas
- [ ] Calibração atualizada se necessário
