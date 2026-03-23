# Analisar Fit Oferta-Dor-ICP

> Analisar alinhamento entre oferta apresentada, dor do lead e perfil de cliente ideal (ICP).

## Objetivo
Determinar se o problema está na execução do closer ou no fit da oferta — se a oferta não resolve a dor real do ICP, nenhuma técnica de vendas vai compensar. Separar problema de oferta de problema de execução.

## Trigger
- Padrão de perda identificado com causa raiz "oferta" em múltiplas calls
- Execução do workflow `16-closer-to-offer-feedback`
- Review trimestral de inteligência

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Offer Fit Analyst | Executa análise de fit oferta-dor-ICP |
| Alex Hormozi | Avalia Grand Slam Offer e Value Equation |
| Revenue Intelligence Analyst | Fornece dados de conversão por segmento |
| Sales Chief | Direciona feedback para time de produto/oferta |

## Inputs
- Transcrições de calls com objeções recorrentes de fit
- Dados de conversão por oferta e segmento de ICP
- Descrição da oferta atual e seus componentes
- Dores mais frequentes verbalizadas pelos leads
- Relatórios de causa raiz com tag "oferta"

## Processo
1. Mapear as dores mais frequentes verbalizadas pelos leads nas calls
2. Comparar com as promessas e componentes da oferta
3. Identificar gaps: dores que a oferta não endereça diretamente
4. Avaliar Value Equation por segmento: Dream Outcome, Likelihood, Time, Effort
5. Analisar objeções de fit recorrentes: "não é para mim", "não preciso de tudo isso"
6. Verificar se pricing está adequado para o valor percebido pelo ICP
7. Comparar conversão por segmento de ICP: qual segmento converte mais?
8. Identificar se há ICP que não deveria estar sendo atendido
9. Gerar recomendações de ajuste: oferta, pricing, segmentação, messaging

## Frameworks Aplicados
- Grand Slam Offer (Hormozi)
- Value Equation (Dream Outcome × Likelihood / Time × Effort)
- ICP Qualification Framework
- Price-to-Value Gap Analysis

## Checklists de Qualidade
- Dores mapeadas com evidência de múltiplas calls
- Gaps oferta-dor documentados com frequência
- Value Equation avaliada por segmento
- Dados de conversão por segmento incluídos
- Recomendações específicas e implementáveis

## Output Esperado
- Relatório de fit em `reports/intelligence/offer-fit-analysis-PERIODO`
- Mapa dor × oferta com gaps identificados
- Recomendações de ajuste priorizadas

## Registry Atualizado
- `data/registries/intelligence-registry.yaml`
- `data/registries/offer-feedback-registry.yaml`

## Critérios de Conclusão
- [ ] Dores mais frequentes mapeadas com evidência
- [ ] Gaps oferta-dor identificados
- [ ] Value Equation avaliada por segmento
- [ ] Conversão por segmento analisada
- [ ] Recomendações de ajuste documentadas
- [ ] Feedback encaminhado para time de oferta

---

## Contexto
Quando a oferta não resolve a dor real do ICP, nenhuma melhoria de execução do closer vai compensar. Esta task existe para separar problema de oferta de problema de execução, gerando feedback acionável para o time de produto/oferta via cross-squad.

## Especificação de I/O
- **Input**: Transcrições de calls com objeções de fit + dados de conversão por oferta/segmento + descrição da oferta + relatórios de causa raiz com tag "oferta"
- **Output**: `templates/reports/executive-sales-intelligence-report` (relatório de fit oferta-dor-ICP)

## Quality Gates Intermediários
- Após mapeamento de dores e gaps (steps 1-3): checklist `qualification-analysis-quality` — dores mapeadas com evidência de 3+ calls, gaps documentados com frequência
- Antes de output final: checklist `promise-sanity-check-quality` — recomendações específicas e implementáveis, Value Equation avaliada por segmento

## Escalation & Rework
- Se análise revela mismatch estrutural oferta-mercado: escalar para `sales-chief` para handoff ao `c_level_squad` via `templates/operational/cross-squad-handoff-template`
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `close_rate_by_offer`: evolução da taxa de conversão por oferta após ajustes recomendados
- `price_concession_rate`: redução de concessões de preço após alinhamento oferta-dor

## Referências Cruzadas
- Workflow: `workflows/16-closer-to-offer-feedback.md`
- Agents: `agents/offer-fit-analyst.md`, `agents/revenue-intelligence-analyst.md`, `agents/alex-hormozi.md`
- Templates: `templates/reports/executive-sales-intelligence-report.md`
- Registries atualizados: `data/registries/deal-risk-registry`

## Handoff
- **Output entregue a**: Sales Chief (`agents/sales-chief.md`) para review e handoff cross-squad ao time de produto/oferta
- **Formato de entrega**: `templates/reports/executive-sales-intelligence-report` (relatório de fit oferta-dor-ICP) + mapa dor × oferta com gaps
- **Condição de entrega**: dores mapeadas com evidência de 3+ calls, gaps documentados, Value Equation avaliada por segmento, recomendações específicas e implementáveis
- **Próximo passo no pipeline**: feedback para time de oferta via `workflows/16-closer-to-offer-feedback.md` e handoff cross-squad via `templates/operational/cross-squad-handoff-template`

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
