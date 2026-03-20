# Analisar Ampliação de Dor

> Avaliar se o closer amplificou a dor: consequências exploradas, custo da inação e urgência criada.

## Objetivo
Verificar se o closer transformou a dor identificada no discovery em urgência real — sem amplificação, o lead não sente pressão para decidir e posterga a compra.

## Trigger
- Análise de discovery concluída
- Execução do workflow `06-full-funnel-call-audit`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Avalia qualidade da ampliação de dor |
| Jeremy Miner | Valida perguntas de consequência e técnicas NEPQ |
| Alex Hormozi | Avalia construção do custo da inação |
| Dan Lok | Avalia pressão emocional e urgência criada |

## Inputs
- Transcrição segmentada: transição discovery → pitch
- Análise de discovery (dor identificada)
- Framework de Consequence Questioning
- Value Equation (Hormozi)

## Processo
1. Identificar o momento em que o closer transiciona de discovery para ampliação
2. Verificar se explorou consequências futuras: "O que acontece se continuar assim?"
3. Avaliar se quantificou o custo da inação (financeiro, temporal, emocional)
4. Verificar se o lead verbalizou a urgência (vs. closer impondo urgência)
5. Analisar se conectou a dor atual com impacto em outras áreas da vida/negócio
6. Avaliar se criou contraste claro entre cenário atual e cenário desejado
7. Verificar se a ampliação foi genuína ou manipulativa (pressão ética vs. antiética)
8. Medir se a urgência criada sobreviveu até o momento de pricing/fechamento

## Frameworks Aplicados
- NEPQ Consequence Questioning
- Value Equation (custo da inação vs. investimento)
- Price-to-Value Gap (Hormozi)
- Cialdini: Princípio da Escassez (quando aplicável)

## Checklists de Qualidade
- Consequências exploradas com evidência textual
- Custo da inação quantificado ou verbalizado pelo lead
- Urgência criada de forma ética (sem manipulação)
- Contraste presente-futuro construído
- Lead verbalizou urgência com suas próprias palavras

## Output Esperado
- Análise de ampliação em `reports/analysis/CALL-ID-gap-amplification`
- Mapa de consequências exploradas com trechos
- Nota de ampliação (0-10) com justificativa

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo gap_amplification_score)

## Critérios de Conclusão
- [ ] Momento de transição discovery → ampliação identificado
- [ ] Consequências exploradas documentadas
- [ ] Custo da inação avaliado (presente/ausente/parcial)
- [ ] Ética da ampliação validada
- [ ] Nota atribuída com evidência textual
- [ ] Urgência do lead verificada no momento de pricing

---

## Contexto
Sem amplificação de dor, o lead não sente urgência para decidir e posterga a compra. Esta task avalia se o closer transformou a dor identificada no discovery em pressão real e ética para agir — é o elo entre um discovery bem feito e um pricing que não gera objeção de preço.

## Especificação de I/O
- **Input**: Transcrição segmentada no formato `[MM:SS] [SPEAKER]: text`, transição discovery-pitch + análise de discovery concluída (dor identificada)
- **Output**: `templates/reports/full-call-audit-report.md`, seção "Ampliação de Dor e Implicação" + nota do bloco amplificação (0-10)

## Quality Gates Intermediários
- Após análise inicial: consequências exploradas listadas com trechos exatos e timestamps; custo da inação documentado (quantificado ou verbalizado pelo lead)
- Antes de output final: qa-guardian valida que a amplificação foi classificada como ética; nota coerente com a urgência demonstrada pelo lead no momento de pricing

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar transição discovery-pitch)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts (ex: Hormozi vs. Miner sobre intensidade da amplificação): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- 100% das análises com avaliação ética explícita (pressão genuína vs. manipulação)
- Correlação entre nota de amplificação e ausência de objeção de preço > 0.5

## Referências Cruzadas
- Workflow: `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/call-auditor.md`, `agents/experts/jeremy-miner.md`, `agents/experts/alex-hormozi.md`, `agents/experts/dan-lok.md`
- Templates: `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/scorecards-registry`
