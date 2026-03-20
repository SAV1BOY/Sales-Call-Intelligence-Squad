# Review Trimestral de Inteligência

> Review trimestral consolidada: tendências de longo prazo, padrões estruturais e recomendações estratégicas.

## Objetivo
Identificar tendências e padrões que só aparecem com volume de dados maior — decisões de oferta, pricing, ICP e processo que impactam toda a operação comercial.

## Trigger
- Primeiro dia útil de cada trimestre
- Acúmulo de 50+ calls auditadas no trimestre

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Revenue Intelligence Analyst | Conduz análise trimestral completa |
| Offer Fit Analyst | Avalia fit oferta-dor-ICP em escala |
| Win-Loss Miner | Apresenta padrões consolidados |
| Sales Chief | Toma decisões estratégicas baseadas na inteligência |

## Inputs
- Todas as métricas semanais e mensais do trimestre
- Padrões de vitória e perda consolidados
- Análises de fit oferta-dor-ICP
- Evolução de closers e certificações
- Dados de mercado e concorrência (se disponíveis)

## Processo
1. Consolidar métricas trimestrais: score médio, conversão, ticket, volume
2. Analisar tendência de 12+ semanas: melhoria sustentada ou oscilação
3. Identificar padrões estruturais: causas que persistem apesar de coaching
4. Avaliar fit oferta-dor-ICP com volume significativo de dados
5. Analisar evolução da equipe: maturidade média, gap entre top e bottom
6. Identificar mudanças no perfil de leads ou objeções (sinais de mercado)
7. Avaliar ROI do programa de coaching: investimento vs. melhoria de conversão
8. Comparar trimestre com anterior: progresso real ou ilusório
9. Gerar recomendações estratégicas: oferta, pricing, processo, equipe
10. Definir OKRs de qualidade para o próximo trimestre

## Frameworks Aplicados
- Quarterly Intelligence Framework
- Trend Analysis (12+ semanas)
- Strategic Recommendations Framework

## Checklists de Qualidade
- Mínimo 50 calls no trimestre para significância
- Tendências de longo prazo analisadas (não apenas snapshot)
- Recomendações estratégicas diferenciadas de táticas
- ROI de coaching calculado
- OKRs definidos e mensuráveis

## Output Esperado
- Relatório trimestral em `reports/reviews/quarterly-intelligence-YYYY-QN`
- Tendências de longo prazo com visualizações
- Recomendações estratégicas priorizadas e OKRs

## Registry Atualizado
- `data/registries/intelligence-registry.yaml`
- `data/registries/review-registry.yaml`

## Critérios de Conclusão
- [ ] Métricas trimestrais consolidadas
- [ ] Tendências de 12+ semanas analisadas
- [ ] Padrões estruturais identificados
- [ ] Fit oferta-dor-ICP avaliado
- [ ] ROI de coaching calculado
- [ ] OKRs do próximo trimestre definidos

---

## Contexto
Esta task existe para identificar tendências e padrões estruturais que só aparecem com volume significativo de dados (50+ calls). Decisões de oferta, pricing, ICP e processo que impactam toda a operação comercial precisam dessa visão de longo prazo — análises semanais não capturam sinais estruturais.

## Especificação de I/O
- **Input**: Métricas semanais e mensais do trimestre, padrões de vitória/perda consolidados, análises de fit oferta-dor-ICP, evolução de closers e certificações
- **Output**: Relatório trimestral em `reports/reviews/quarterly-intelligence-YYYY-QN` usando `templates/reports/executive-sales-intelligence-report.md`

## Quality Gates Intermediários
- Após consolidação de métricas (step 1-2): mínimo 50 calls no trimestre para significância estatística
- Antes de output final: recomendações estratégicas diferenciadas de táticas, ROI de coaching calculado, OKRs mensuráveis definidos

## Escalation & Rework
- Se padrões estruturais indicam problema fora do domínio de vendas (ex: oferta, pricing, ICP): escalar para sales-chief para handoff ao c_level_squad
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief

## Métricas de Sucesso
- win_pattern_registry_currency (registro de padrões atualizado com dados do trimestre)
- ROI do programa de coaching (investimento vs. melhoria de conversão)

## Referências Cruzadas
- Workflow: `workflows/09-win-pattern-extraction.md`, `workflows/10-loss-pattern-extraction.md`, `workflows/11-weekly-sales-quality-review.md`
- Agents: `agents/revenue-intelligence-analyst.md`, `agents/offer-fit-analyst.md`, `agents/win-loss-miner.md`, `agents/sales-chief.md`
- Templates: `templates/reports/executive-sales-intelligence-report.md`, `templates/reports/win-loss-analysis-report.md`
- Registries atualizados: `data/registries/intelligence-registry.yaml`, `data/registries/review-registry.yaml`
