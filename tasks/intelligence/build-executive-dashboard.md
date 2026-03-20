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
