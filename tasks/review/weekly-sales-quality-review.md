# Review Semanal de Qualidade

> Review semanal consolidada: scores agregados, padrões emergentes, destaques e ações corretivas.

## Objetivo
Criar ritual semanal de análise que identifica tendências cedo, celebra acertos e direciona correções antes que problemas se consolidem — cadência mínima para melhoria contínua.

## Trigger
- Todo final de semana (sexta ou segunda)
- Execução do workflow `11-weekly-sales-quality-review`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Revenue Intelligence Analyst | Consolida métricas e identifica tendências |
| Scorecard Analyst | Agrega scores da semana |
| Win-Loss Miner | Resume padrões de vitória e perda |
| Sales Chief | Conduz review e define ações |

## Inputs
- Scorecards de todas as calls auditadas na semana
- Relatórios de causa raiz da semana
- Status de coaching e sessões realizadas
- Win/loss patterns atualizados
- Dashboard executivo anterior (para comparação)

## Processo
1. Consolidar métricas da semana: calls auditadas, score médio, taxa de conversão
2. Comparar com semana anterior: melhoria, estagnação ou piora
3. Ranking de closers da semana por score médio
4. Identificar destaques positivos: melhor call, maior evolução, melhor momento
5. Identificar alertas: closers em queda, padrões de perda novos
6. Resumir causas raiz predominantes da semana
7. Verificar status de ações definidas na review anterior (executadas?)
8. Definir top 3 ações para a próxima semana com responsável e prazo
9. Atualizar biblioteca de objeções e melhores momentos se necessário
10. Gerar ata da review com decisões e ações

## Frameworks Aplicados
- Weekly Review Framework
- Trend Analysis (comparação semanal)
- Pareto Analysis (80/20 das causas)

## Checklists de Qualidade
- Todas as calls da semana incluídas na consolidação
- Comparação com semana anterior presente
- Destaques positivos e alertas documentados
- Ações da review anterior verificadas (concluídas/pendentes)
- Novas ações têm responsável e prazo

## Output Esperado
- Ata da review em `reports/reviews/weekly-review-YYYY-WNN`
- Métricas consolidadas da semana
- Top 3 ações com responsável e prazo

## Registry Atualizado
- `data/registries/intelligence-registry.yaml`
- `data/registries/review-registry.yaml`

## Critérios de Conclusão
- [ ] Métricas da semana consolidadas
- [ ] Comparação semanal realizada
- [ ] Destaques e alertas identificados
- [ ] Ações anteriores verificadas
- [ ] Novas ações definidas com responsável
- [ ] Ata gerada e distribuída

---

## Contexto
Esta task existe para criar um ritual semanal de análise que identifica tendências cedo, celebra acertos e direciona correções antes que problemas se consolidem. É a cadência mínima para melhoria contínua — sem ela, problemas só aparecem quando já impactaram resultados de vendas.

## Especificação de I/O
- **Input**: Scorecards de todas as calls da semana, relatórios de causa raiz, status de coaching, win/loss patterns, dashboard executivo anterior
- **Output**: Ata da review em `reports/reviews/weekly-review-YYYY-WNN` usando `templates/reports/executive-sales-intelligence-report.md`

## Quality Gates Intermediários
- Após consolidação de métricas (step 1-3): todas as calls da semana incluídas, comparação com semana anterior presente
- Antes de output final: ações da review anterior verificadas (concluídas/pendentes), novas ações têm responsável e prazo definidos

## Escalation & Rework
- Se closer em queda por 2+ semanas consecutivas: escalar para closer-trainer para plano de intervenção
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief

## Métricas de Sucesso
- average_call_score semanal (tendência de melhoria)
- Taxa de execução das ações definidas na review anterior

## Referências Cruzadas
- Workflow: `workflows/11-weekly-sales-quality-review.md`
- Agents: `agents/sales-chief.md`, `agents/revenue-intelligence-analyst.md`, `agents/scorecard-analyst.md`, `agents/win-loss-miner.md`
- Templates: `templates/reports/executive-sales-intelligence-report.md`, `templates/briefs/weekly-sales-review-brief.md`
- Registries atualizados: `data/registries/intelligence-registry.yaml`, `data/registries/review-registry.yaml`
