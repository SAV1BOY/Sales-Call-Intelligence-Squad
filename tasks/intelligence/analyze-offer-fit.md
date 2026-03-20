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
