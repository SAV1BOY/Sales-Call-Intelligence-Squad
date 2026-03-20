# Analisar Qualidade do Pitch

> Avaliar pitch: ponte com diagnóstico, value proposition, social proof e personalização.

## Objetivo
Verificar se o closer construiu um pitch que conecta diretamente com a dor descoberta, apresenta valor claro e usa prova social relevante — pitch genérico é sinal de discovery fraco ou falta de técnica.

## Trigger
- Transcrição segmentada com etapa de pitch delimitada
- Análises de discovery e ampliação de dor concluídas

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Avalia estrutura e eficácia do pitch |
| Alex Hormozi | Valida Grand Slam Offer e Value Equation |
| Cole Gordon | Valida ponte entre diagnóstico e prescrição |
| Jordan Belfort | Avalia controle de frame durante o pitch |

## Inputs
- Transcrição segmentada: seção de pitch com timestamps
- Análise de discovery (dor identificada, palavras do lead)
- Detalhes da oferta apresentada
- Grand Slam Offer e Value Equation como referência

## Processo
1. Verificar se o closer fez ponte explícita entre a dor do lead e a solução
2. Avaliar se usou as palavras do próprio lead para descrever o problema
3. Analisar a value proposition: resultado prometido, timeline, esforço exigido
4. Verificar aplicação da Value Equation: Dream Outcome × Perceived Likelihood / Time × Effort
5. Avaliar uso de social proof: casos, resultados, depoimentos (específicos vs. genéricos)
6. Verificar personalização do pitch: adaptado ao lead ou apresentação padrão?
7. Analisar se vendeu a transformação (vacation) ou o processo (plane flight)
8. Identificar se o lead demonstrou interesse/engajamento durante o pitch
9. Avaliar duração do pitch: prolixo (>15min) ou conciso e impactante

## Frameworks Aplicados
- Grand Slam Offer (Hormozi)
- Value Equation (Dream Outcome × Likelihood / Time × Effort)
- Sell the Vacation, Not the Plane Flight
- Doctor Frame (prescrição conectada ao diagnóstico)

## Checklists de Qualidade
- Ponte diagnóstico→solução presente com evidência
- Palavras do lead reutilizadas no pitch (sim/não, trechos)
- Value Equation aplicada (parcial/completa)
- Social proof específico e relevante ao caso
- Pitch personalizado (não genérico)

## Output Esperado
- Análise de pitch em `reports/analysis/CALL-ID-pitch`
- Avaliação de cada componente: ponte, value prop, social proof, personalização
- Nota do bloco pitch (0-10) com justificativa

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo pitch_score)

## Critérios de Conclusão
- [ ] Ponte diagnóstico→solução avaliada
- [ ] Value Equation analisada componente por componente
- [ ] Social proof avaliado (tipo, especificidade, relevância)
- [ ] Personalização do pitch verificada
- [ ] Engajamento do lead durante o pitch registrado
- [ ] Nota atribuída com evidência textual

---

## Contexto
Pitch genérico é sinal de discovery fraco ou falta de técnica — e é o momento onde o closer converte dor em desejo de compra. Esta task existe para avaliar se o pitch conectou diretamente com a dor descoberta, apresentou valor claro via Value Equation e usou prova social relevante, garantindo que o closer não está "apresentando slides" mas sim prescrevendo uma solução personalizada.

## Especificação de I/O
- **Input**: Transcrição segmentada no formato `[MM:SS] [SPEAKER]: text`, seção de pitch delimitada + análises de discovery e ampliação de dor concluídas + detalhes da oferta
- **Output**: `templates/reports/full-call-audit-report.md`, seções "Empresa/Método/Produto" e "Pitch Amarrado à Fala do Lead" + nota do bloco pitch (0-10)

## Quality Gates Intermediários
- Após análise inicial: ponte diagnóstico-solução verificada com trecho exato; palavras do lead reutilizadas no pitch documentadas; Value Equation avaliada componente por componente
- Antes de output final: qa-guardian valida coerência entre nota de pitch e nota de discovery (pitch personalizado com discovery raso é inconsistência a ser investigada)

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar seção de pitch, verificar delimitação de etapas)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts (ex: Hormozi vs. Gordon sobre abordagem de value proposition): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- Taxa de pitches classificados como "personalizado" vs. "genérico" por closer (tracking de evolução)
- Correlação entre nota de pitch e taxa de conversão > 0.5

## Referências Cruzadas
- Workflow: `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/call-auditor.md`, `agents/experts/alex-hormozi.md`, `agents/experts/cole-gordon.md`, `agents/experts/sabri-suby.md`
- Templates: `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/scorecards-registry`
