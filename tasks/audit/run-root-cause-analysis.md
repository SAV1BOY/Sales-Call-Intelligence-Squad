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
