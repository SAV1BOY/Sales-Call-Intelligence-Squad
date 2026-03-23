# Construir Dashboard Executivo

> Construir dashboard executivo com KPIs consolidados, tendências temporais e ações recomendadas.

## Objetivo
Entregar visão consolidada e acionável para liderança — não é dump de dados, é inteligência processada que mostra onde está, para onde vai e o que fazer para melhorar.

## Trigger
- Review semanal de qualidade
- Review mensal de certificação
- Solicitação da liderança comercial

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Revenue Intelligence Analyst | Constrói dashboard e análises |
| Scorecard Analyst | Fornece métricas agregadas de scoring |
| Win-Loss Miner | Fornece padrões de vitória e perda |
| Sales Chief | Valida insights e prioriza ações |

## Inputs
- Scorecards de todas as calls do período
- Taxas de conversão por closer, oferta, canal
- Padrões de vitória e perda extraídos
- Dados de coaching e evolução de closers
- Dados de certificação

## Processo
1. Consolidar KPIs primários: score médio, taxa de conversão, ticket médio
2. Calcular KPIs por closer: ranking, evolução, consistência
3. Analisar tendências: melhoria, estagnação ou piora por métrica
4. Gerar análise por bloco do scorecard: quais blocos estão mais fracos na equipe
5. Incluir win/loss ratio com causas raiz predominantes
6. Analisar performance por oferta: qual oferta converte mais e por quê
7. Incluir status de coaching: sessões realizadas, evolução pós-coaching
8. Incluir status de certificação: closers certificados, pendentes, reprovados
9. Gerar top 3 ações recomendadas baseadas nos dados
10. Formatar para apresentação executiva (visual, conciso, acionável)

## Frameworks Aplicados
- Executive Intelligence Framework
- Pareto Analysis (80/20)
- Trend Analysis

## Checklists de Qualidade
- KPIs calculados com dados completos do período
- Tendências mostram mínimo 4 semanas de dados
- Ações recomendadas são específicas e acionáveis
- Dashboard visual e de fácil leitura
- Comparação com período anterior incluída

## Output Esperado
- Dashboard em `reports/intelligence/executive-dashboard-PERIODO`
- KPIs consolidados com tendências
- Top 3 ações recomendadas com justificativa

## Registry Atualizado
- `data/registries/intelligence-registry.yaml`

## Critérios de Conclusão
- [ ] KPIs primários consolidados
- [ ] Análise por closer com ranking e evolução
- [ ] Tendências temporais incluídas
- [ ] Win/loss patterns resumidos
- [ ] Top 3 ações recomendadas definidas
- [ ] Dashboard formatado para apresentação

---

## Contexto
Liderança comercial precisa de visão consolidada e acionável, não dump de dados. Esta task existe para transformar dados dispersos de auditorias, scorecards e padrões em inteligência processada que mostra onde a operação está, para onde vai e o que fazer para melhorar.

## Especificação de I/O
- **Input**: Scorecards do período + taxas de conversão por closer/oferta/canal + padrões win/loss + dados de coaching e certificação
- **Output**: `templates/reports/executive-sales-intelligence-report` (dashboard executivo com KPIs, tendências e ações)

## Quality Gates Intermediários
- Após consolidação de KPIs (steps 1-3): dados completos do período, tendências com mínimo 4 semanas, comparação com período anterior
- Antes de output final: checklist `manager-review-quality` — top 3 ações recomendadas são específicas e acionáveis, dashboard visual e de fácil leitura

## Escalation & Rework
- Se dados insuficientes para tendência confiável (< 4 semanas ou < 10 calls): escalar para `revenue-intelligence-analyst` para ajustar escopo
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `average_call_score`: score médio consolidado no dashboard como indicador primário
- `close_rate_by_closer`: taxa de conversão por closer como driver de ações recomendadas

## Referências Cruzadas
- Workflow: `workflows/11-weekly-sales-quality-review.md`, `workflows/20-ralphloop-sales-retro.md`
- Agents: `agents/revenue-intelligence-analyst.md`, `agents/scorecard-analyst.md`, `agents/win-loss-miner.md`, `agents/sales-chief.md`
- Templates: `templates/reports/executive-sales-intelligence-report.md`
- Registries atualizados: `data/registries/intelligence-registry.yaml`

## Handoff
- **Output entregue a**: Sales Chief (`agents/sales-chief.md`) para validação e apresentação à liderança comercial
- **Formato de entrega**: `templates/reports/executive-sales-intelligence-report` (dashboard executivo com KPIs, tendências e top 3 ações recomendadas)
- **Condição de entrega**: KPIs completos do período, tendências com mínimo 4 semanas, top 3 ações específicas e acionáveis, dashboard visual e de fácil leitura
- **Próximo passo no pipeline**: review semanal/mensal de qualidade via `workflows/11-weekly-sales-quality-review.md` ou retro via `workflows/20-ralphloop-sales-retro.md`

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
