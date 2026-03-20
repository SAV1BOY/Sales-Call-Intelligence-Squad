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

---

## Contexto
Esta task existe para garantir que as próprias auditorias do squad são precisas, consistentes e calibradas. Sem meta-auditoria, vieses se acumulam silenciosamente, scores perdem confiabilidade e todo o sistema de coaching e certificação fica comprometido.

## Especificação de I/O
- **Input**: Últimas 10-20 auditorias completas, scorecards do período, checklists aplicados, histórico de calibração, feedback dos gestores
- **Output**: Relatório de QA em `reports/reviews/qa-audit-PERIODO`, taxa de concordância inter-auditor, ações corretivas para calibração

## Quality Gates Intermediários
- Após re-auditoria independente (step 2-3): variação de score quantificada por bloco, re-auditoria feita sem acesso ao original
- Antes de output final: completude verificada em 100% da amostra, ações corretivas específicas por discrepância identificada

## Escalation & Rework
- Se variância > 15% entre auditores no mesmo call: escalar para qa-guardian para sessão de calibração imediata
- Se quality gate falha: rework loop (max 1 ciclo), depois escalar para sales-chief para convocar calibration session

## Métricas de Sucesso
- Taxa de concordância inter-auditor (target: variação < 5 pontos no score total)
- Completude das auditorias (% de campos e seções preenchidos corretamente)

## Referências Cruzadas
- Workflow: `workflows/06-full-funnel-call-audit.md`, `workflows/04-scoring-and-root-cause.md`
- Agents: `agents/qa-guardian.md`, `agents/sales-chief.md`, `agents/scorecard-analyst.md`
- Templates: `templates/scorecards/call-scorecard-template.md`, `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/qa-registry.yaml`, `data/registries/review-registry.yaml`
