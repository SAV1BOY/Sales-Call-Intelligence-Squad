# Extrair Padrões de Calls Perdidas

> Extrair padrões recorrentes de calls perdidas: gaps comuns, erros repetidos, causas sistêmicas.

## Objetivo
Identificar os erros e gaps que aparecem consistentemente nas calls perdidas — permitindo ações preventivas e treinamento direcionado para eliminar causas recorrentes de perda.

## Trigger
- Mínimo 5 calls perdidas auditadas no período
- Execução do workflow `10-loss-pattern-extraction`
- Review semanal ou mensal de qualidade

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Win-Loss Miner | Executa mineração de padrões de perda |
| Deal Risk Doctor | Analisa causas raiz recorrentes |
| Revenue Intelligence Analyst | Correlaciona perdas com variáveis sistêmicas |
| Sales Chief | Prioriza ações corretivas baseadas nos padrões |

## Inputs
- Scorecards de calls perdidas (últimas 20-30)
- Relatórios de causa raiz das calls perdidas
- Transcrições segmentadas
- Dados de oferta, ticket, ICP, SDR por call

## Processo
1. Filtrar calls perdidas no período (mínimo 5 para significância)
2. Agrupar causas raiz por categoria: closer, lead, oferta, pricing, handoff
3. Identificar os 3 blocos do scorecard mais fracos nas calls perdidas
4. Mapear erros recorrentes: quais comportamentos se repetem nas perdas?
5. Identificar em qual etapa a call "morre" com mais frequência
6. Analisar se perdas estão concentradas em closer, oferta ou segmento específico
7. Correlacionar com variáveis externas: dia da semana, horário, canal de origem
8. Distinguir entre causa evitável (treino resolve) e causa estrutural (processo/oferta)
9. Documentar top 5 padrões de perda com evidência e frequência

## Frameworks Aplicados
- Loss Pattern Extraction Framework
- Root Cause Analysis (agregado)
- Pareto Analysis (80/20 das causas)

## Checklists de Qualidade
- Mínimo 5 calls analisadas para cada padrão
- Causas agrupadas por categoria e frequência
- Distinção clara entre causa evitável e estrutural
- Correlações com variáveis externas testadas
- Ações corretivas sugeridas por padrão

## Output Esperado
- Relatório de loss patterns em `reports/intelligence/loss-patterns-PERIODO`
- Top 5 padrões de perda com evidência e frequência
- Ações corretivas priorizadas por impacto

## Registry Atualizado
- `data/registries/intelligence-registry.yaml`
- `data/registries/root-cause-patterns-registry.yaml`

## Critérios de Conclusão
- [ ] Mínimo 5 calls perdidas analisadas
- [ ] Top 5 padrões identificados com evidência
- [ ] Causas agrupadas por categoria
- [ ] Distinção evitável vs. estrutural realizada
- [ ] Ações corretivas sugeridas
- [ ] Registry de padrões atualizado

---

## Contexto
Calls perdidas isoladas escondem causas sistêmicas. Esta task existe para minerar padrões recorrentes de perda, distinguir entre problemas de execução (treino resolve) e problemas estruturais (processo/oferta), e gerar ações preventivas que eliminam causas raiz em escala.

## Especificação de I/O
- **Input**: Scorecards de calls perdidas (últimas 20-30) + relatórios de causa raiz + transcrições segmentadas + dados de oferta/ticket/ICP/SDR
- **Output**: `templates/reports/win-loss-analysis-report` (relatório de loss patterns com top 5 padrões e ações corretivas)

## Quality Gates Intermediários
- Após agrupamento de causas raiz (steps 2-5): checklist `win-loss-analysis-quality` — mínimo 5 calls por padrão, causas agrupadas por categoria e frequência
- Antes de output final: checklist `promise-sanity-check-quality` + `handoff-quality` — distinção clara evitável vs. estrutural, correlações testadas

## Escalation & Rework
- Se padrão de perda aponta causa estrutural (oferta/pricing/processo): escalar para `sales-chief` para handoff ao squad relevante (`c_level_squad`, `traffic_squad`)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `close_rate_by_closer`: evolução da taxa de conversão após eliminação dos padrões de perda identificados
- `win_pattern_registry_currency`: % dos padrões catalogados com ação corretiva implementada

## Referências Cruzadas
- Workflow: `workflows/10-loss-pattern-extraction.md`
- Agents: `agents/win-loss-miner.md`, `agents/deal-risk-doctor.md`, `agents/sdr-handoff-analyst.md`, `agents/offer-fit-analyst.md`
- Templates: `templates/reports/win-loss-analysis-report.md`
- Registries atualizados: `data/registries/loss-patterns-registry`, `data/registries/deal-risk-registry`
