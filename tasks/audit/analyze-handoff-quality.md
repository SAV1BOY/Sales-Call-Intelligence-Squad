# Analisar Qualidade do Handoff SDR→Closer

> Avaliar qualidade do handoff SDR→closer: informações transmitidas, qualificação e preparação.

## Objetivo
Determinar se o SDR entregou o lead qualificado e contextualizado para o closer — handoff fraco obriga o closer a refazer discovery e reduz taxa de conversão.

## Trigger
- Intake de call concluído com informações de SDR disponíveis
- Execução do workflow `13-sdr-to-closer-feedback-loop`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| SDR Handoff Analyst | Executa análise técnica do handoff |
| Call Auditor | Correlaciona handoff com performance da call |
| Transcript Analyst | Extrai evidências de handoff na transcrição |

## Inputs
- Transcrição normalizada (primeiros 5 minutos especialmente)
- Informações de qualificação do SDR (se disponíveis)
- Metadata da call: origem, SDR responsável
- Critérios de qualificação do ICP

## Processo
1. Verificar se closer demonstrou ter informações prévias sobre o lead
2. Analisar se closer precisou refazer perguntas básicas (nome, cargo, empresa, problema)
3. Avaliar se lead tinha expectativa correta sobre a call (sabia do que se tratava)
4. Verificar se lead estava qualificado conforme ICP: decisor, budget, timing, fit
5. Identificar gaps de informação: o que faltou no handoff
6. Avaliar se o agendamento foi feito com urgência adequada
7. Verificar se houve no-show ou atraso e possíveis causas no handoff
8. Documentar impacto do handoff na performance geral da call
9. Gerar feedback estruturado para o SDR

## Frameworks Aplicados
- ICP Qualification Framework
- SDR Handoff Checklist
- Sales Call Stage Taxonomy (impacto no rapport/discovery)

## Checklists de Qualidade
- Informações transmitidas pelo SDR listadas (presentes/ausentes)
- Qualificação do lead avaliada contra ICP
- Impacto do handoff na call documentado
- Feedback para SDR estruturado e acionável
- Evidências textuais da transcrição incluídas

## Output Esperado
- Análise de handoff em `reports/analysis/CALL-ID-handoff`
- Checklist de informações transmitidas vs. ausentes
- Nota de qualidade do handoff e feedback para SDR

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo handoff_score)
- `data/registries/sdr-performance-registry.yaml`

## Critérios de Conclusão
- [ ] Informações transmitidas pelo SDR mapeadas
- [ ] Qualificação do lead avaliada contra ICP
- [ ] Gaps de informação identificados
- [ ] Impacto na call documentado
- [ ] Feedback para SDR gerado
- [ ] Registry de SDR atualizado

---

## Contexto
Handoff fraco do SDR obriga o closer a refazer discovery básico, desperdiça os primeiros minutos da call e reduz conversão. Esta task existe para isolar o impacto do handoff no resultado da call, gerar feedback estruturado para o SDR e alimentar o loop de melhoria contínua entre pré-venda e venda.

## Especificação de I/O
- **Input**: Transcrição normalizada (primeiros 5 minutos com foco em rapport/abertura) no formato `[MM:SS] [SPEAKER]: text` + metadata da call (SDR responsável, origem, qualificação prévia)
- **Output**: `templates/reports/sdr-handoff-audit-report.md` + checklist de informações transmitidas vs. ausentes + feedback estruturado para SDR

## Quality Gates Intermediários
- Após análise inicial: informações transmitidas pelo SDR listadas com evidência textual dos primeiros minutos; qualificação do lead avaliada contra critérios de ICP
- Antes de output final: qa-guardian valida que o feedback para SDR é construtivo, baseado em dados e acionável (não acusatório)

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar primeiros minutos; verificar se há dados de qualificação do SDR)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre análise de handoff e análise de rapport: escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- Correlação entre nota de handoff e conversão da call documentada por período
- Taxa de implementação do feedback pelo time de SDRs > 60% no ciclo seguinte

## Referências Cruzadas
- Workflow: `workflows/13-sdr-to-closer-feedback-loop.md`
- Agents: `agents/sdr-handoff-analyst.md`, `agents/call-auditor.md`, `agents/transcript-analyst.md`
- Templates: `templates/reports/sdr-handoff-audit-report.md`
- Registries atualizados: `data/registries/handoff-registry`
