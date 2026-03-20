# Analisar Pricing

> Avaliar apresentação de pricing: ancoragem, value stack, concessões, risk reversal e timing.

## Objetivo
Verificar se o closer apresentou o preço de forma estratégica — ancorando valor antes de preço, usando value stack, oferecendo garantias e fazendo concessões inteligentes quando necessário.

## Trigger
- Transcrição segmentada com etapa de pricing delimitada
- Execução do workflow `08-price-anchoring-audit`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Pricing Anchoring Analyst | Executa análise técnica de pricing |
| Alex Hormozi | Valida Price-to-Value Gap e Grand Slam Offer |
| Dan Lok | Avalia técnicas de high-ticket pricing |
| Call Auditor | Consolida análise e vincula com objeções de preço |

## Inputs
- Transcrição segmentada: seção de pricing com timestamps
- Detalhes da oferta e preço apresentado
- Análise de pitch (value proposition construída)
- Framework Price-to-Value Gap (Hormozi)

## Processo
1. Identificar o momento exato em que o preço foi revelado (timestamp)
2. Verificar se houve ancoragem de valor antes de revelar preço
3. Avaliar se construiu value stack: listou componentes com valor individual
4. Verificar se usou Price-to-Value Gap: valor percebido >>> preço pedido
5. Analisar presença de risk reversal: garantias, trial, reembolso
6. Avaliar reação do lead ao preço (silêncio, objeção, aceitação)
7. Verificar se closer fez concessões e se foram estratégicas ou desesperadas
8. Analisar se apresentou opções de pagamento de forma adequada
9. Verificar se manteve frame de autoridade durante pricing (não se desculpou pelo preço)
10. Avaliar se a transição de pitch para pricing foi natural

## Frameworks Aplicados
- Price-to-Value Gap (Hormozi)
- Grand Slam Offer: Value Stack
- Guarantee Stack (Hormozi)
- Straight Line: manter certeza durante pricing
- Scarcity/Urgency (quando aplicável)

## Checklists de Qualidade
- Ancoragem de valor verificada (presente/ausente)
- Value stack documentado com componentes listados
- Risk reversal avaliado (tipo, clareza, impacto)
- Concessões classificadas (estratégicas vs. desesperadas)
- Frame mantido durante pricing (sem desculpas pelo preço)

## Output Esperado
- Análise de pricing em `reports/analysis/CALL-ID-pricing`
- Avaliação: ancoragem, value stack, risk reversal, concessões
- Nota do bloco pricing (0-10) com justificativa

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo pricing_score)

## Critérios de Conclusão
- [ ] Momento de revelação de preço identificado
- [ ] Ancoragem de valor avaliada
- [ ] Value stack analisado
- [ ] Risk reversal documentado
- [ ] Concessões classificadas
- [ ] Frame durante pricing avaliado
- [ ] Nota atribuída com evidência textual

---

## Contexto
A forma como o preço é apresentado determina se o lead percebe investimento ou custo. Esta task existe para auditar a estratégia de ancoragem, value stack, risk reversal e concessões — diferenciando closer que vende valor de closer que vende preço. Sem essa análise, objeções de preço são tratadas como problema de fechamento quando na verdade são problema de ancoragem.

## Especificação de I/O
- **Input**: Transcrição segmentada no formato `[MM:SS] [SPEAKER]: text`, seção de pricing delimitada + detalhes da oferta e preço apresentado + análise de pitch (value proposition construída)
- **Output**: `templates/reports/pricing-analysis-report.md` + nota do bloco ancoragem (0-10) com justificativa

## Quality Gates Intermediários
- Após análise inicial: momento exato de revelação de preço identificado com timestamp; ancoragem de valor verificada (presente/ausente); value stack documentado com componentes listados; concessões classificadas (estratégicas vs. desesperadas)
- Antes de output final: qa-guardian valida coerência entre nota de pricing e objeções de preço registradas; se houve objeção de preço forte, nota de ancoragem deve refletir isso

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar seção de pricing, verificar se preço foi mencionado)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts (ex: Hormozi vs. Suby sobre risk reversal): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- Taxa de concessão de preço por closer rastreada e comparada com benchmark do time
- Correlação entre nota de ancoragem e ausência de objeção de preço > 0.5

## Referências Cruzadas
- Workflow: `workflows/08-price-anchoring-audit.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/pricing-anchoring-analyst.md`, `agents/experts/alex-hormozi.md`, `agents/experts/sabri-suby.md`
- Templates: `templates/reports/pricing-analysis-report.md`
- Registries atualizados: `data/registries/pricing-concessions-registry`
