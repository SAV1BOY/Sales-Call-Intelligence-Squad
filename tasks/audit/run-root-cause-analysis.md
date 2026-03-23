# Identificar Causa Raiz

> Executar root cause analysis: determinar se a causa do resultado está no closer, lead, oferta, pricing ou handoff.

## Objetivo
Ir além dos sintomas (score baixo) e identificar a causa raiz real que determinou o resultado da call — sem esse diagnóstico, coaching e ações corretivas são genéricos e ineficazes.

## Trigger
- Scorecard e todas as análises de etapa concluídas
- Execução do workflow `04-scoring-and-root-cause`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Deal Risk Doctor | Executa análise de causa raiz |
| Call Auditor | Fornece consolidação de todas as análises |
| Offer Fit Analyst | Avalia se o problema está na oferta vs. execução |
| SDR Handoff Analyst | Avalia contribuição do handoff para o resultado |
| Sales Chief | Valida diagnóstico final e prioriza ações |

## Inputs
- Scorecard completo da call
- Todas as análises de etapa (rapport a close)
- Relatório de frameworks detectados
- Relatório minuto a minuto
- Informações de oferta e ICP

## Processo
1. Revisar scorecard identificando os blocos com nota mais baixa
2. Cruzar blocos fracos com análises de etapa para confirmar evidências
3. Classificar causa raiz primária: closer (técnica), lead (qualificação), oferta (fit), pricing (estratégia), handoff (SDR)
4. Identificar causas raiz secundárias (geralmente há mais de uma)
5. Construir árvore de causalidade: causa raiz → consequência → impacto no resultado
6. Avaliar se a causa raiz é recorrente (verificar calls anteriores do closer)
7. Determinar se a causa raiz é treinável (skill gap) ou sistêmica (oferta, processo)
8. Recomendar ação corretiva específica para cada causa raiz
9. Priorizar ações: impacto × facilidade de correção

## Frameworks Aplicados
- Root Cause Analysis Framework
- 5 Whys (para cada bloco fraco)
- Scorecard-to-Coaching Bridge

## Checklists de Qualidade
- Causa raiz primária identificada com evidência
- Causas secundárias documentadas
- Árvore de causalidade construída
- Recorrência verificada no histórico
- Ações corretivas específicas e acionáveis
- Distinção clara entre skill gap e problema sistêmico

## Output Esperado
- Relatório de causa raiz em `reports/root-cause/CALL-ID-rca`
- Árvore de causalidade: causa → consequência → impacto
- Ações corretivas priorizadas (impacto × facilidade)

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo root_cause)
- `data/registries/root-cause-patterns-registry.yaml`

## Critérios de Conclusão
- [ ] Causa raiz primária identificada com evidência
- [ ] Causas secundárias documentadas
- [ ] Árvore de causalidade construída
- [ ] Recorrência verificada no histórico do closer
- [ ] Tipo classificado: skill gap vs. problema sistêmico
- [ ] Ações corretivas priorizadas e documentadas

---

## Contexto
Sem diagnóstico de causa raiz, coaching e ações corretivas são genéricos e ineficazes. Esta task existe para ir além dos sintomas (score baixo) e identificar se o problema está no closer (técnica), no lead (qualificação), na oferta (fit), no pricing (estratégia) ou no handoff (SDR) — habilitando intervenções cirúrgicas em vez de treinamento genérico.

## Especificação de I/O
- **Input**: Scorecard completo da call + todas as análises de etapa (rapport a close) + relatório de frameworks detectados + relatório minuto a minuto + informações de oferta e ICP
- **Output**: `templates/reports/full-call-audit-report.md`, seção "Causa Raiz" + árvore de causalidade (causa → consequência → impacto) + ações corretivas priorizadas (impacto x facilidade)

## Quality Gates Intermediários
- Após análise inicial: causa raiz primária identificada com evidência textual; causas secundárias documentadas; classificação entre skill gap vs. problema sistêmico realizada
- Antes de output final: qa-guardian valida coerência entre causa raiz e blocos mais fracos do scorecard; ações corretivas são específicas, acionáveis e priorizadas (não genéricas)

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar) e call-auditor (complementar análises de etapa)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts sobre causa raiz (ex: deal-risk-doctor vs. offer-fit-analyst): escalar para qa-guardian para arbitragem; sales-chief valida diagnóstico final

## Métricas de Sucesso
- Taxa de causas raiz classificadas corretamente (validação pelo sales-chief) > 90%
- Recorrência de causa raiz: mesma causa raiz não deve aparecer 3+ vezes para o mesmo closer sem intervenção

## Handoff
- Output entregue a: coaching-rewriter (workflow 05-coaching-rewrite-loop — seleção de momentos críticos para rewrite baseado no diagnóstico de causa raiz)
- Formato de entrega: `templates/reports/full-call-audit-report.md`, seção "Causa Raiz" + árvore de causalidade (causa → consequência → impacto) + ações corretivas priorizadas
- Condição de entrega: checklist obrigatório de Critérios de Conclusão 100% aprovado + qa-guardian valida coerência entre causa raiz e blocos mais fracos do scorecard
- Próximo passo no pipeline: workflow 05-coaching-rewrite-loop (reescrita de momentos críticos com before/after)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-9 com revalidação do checklist obrigatório
- Max ciclos: 2
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 2 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/04-scoring-and-root-cause.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/deal-risk-doctor.md`, `agents/call-auditor.md`, `agents/offer-fit-analyst.md`, `agents/sdr-handoff-analyst.md`, `agents/sales-chief.md`
- Templates: `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/calls-registry`, `data/registries/deal-risk-registry`
