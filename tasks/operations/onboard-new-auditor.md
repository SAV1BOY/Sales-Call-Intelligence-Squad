# Onboarding de Novo Auditor

> Onboarding de novo auditor: calibração inicial, treinamento em frameworks e validação por QA.

## Objetivo
Garantir que novos auditores produzam auditorias com a mesma qualidade e consistência dos existentes — auditor descalibrado gera scores incomparáveis e coaching equivocado.

## Trigger
- Novo auditor adicionado ao squad
- Expansão da capacidade de auditoria

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| QA Guardian | Conduz calibração e validação |
| Call Auditor | Serve como referência de auditoria calibrada |
| Sales Chief | Aprova auditor para operação independente |

## Inputs
- Documentação completa do sistema de auditoria
- Scorecard template com critérios detalhados
- Biblioteca de frameworks
- 5 calls já auditadas (para exercício de calibração)
- Checklists de qualidade vigentes

## Processo
1. Apresentar arquitetura do squad: agentes, workflows, tasks, registries
2. Treinar em cada framework de auditoria: SPIN, NEPQ, Value Equation, etc.
3. Treinar nos checklists de qualidade: o que valida uma boa auditoria
4. Exercício de calibração: auditar 5 calls que já foram auditadas
5. Comparar scores do novo auditor com auditoria de referência
6. Identificar discrepâncias e corrigir vieses
7. Repetir calibração até variação < 5 pontos no score total
8. Auditar 3 calls novas com supervisão do QA Guardian
9. Validar qualidade: completude, precisão, consistência
10. Aprovar para operação independente ou solicitar calibração adicional

## Frameworks Aplicados
- QA Methodology Consistency Check
- Inter-Rater Reliability Framework
- Calibration Standards
- Todos os frameworks de auditoria (para treinamento)

## Checklists de Qualidade
- Auditor treinou em todos os frameworks obrigatórios
- Exercício de calibração concluído (5 calls)
- Variação < 5 pontos vs. auditoria de referência
- 3 calls auditadas com supervisão e aprovadas
- QA Guardian validou qualidade final

## Output Esperado
- Perfil do auditor em `data/registries/qa-registry.yaml`
- Resultado da calibração: variação por bloco
- Aprovação ou pendência para operação independente

## Registry Atualizado
- `data/registries/qa-registry.yaml`

## Critérios de Conclusão
- [ ] Treinamento em frameworks concluído
- [ ] Calibração realizada (5 calls de referência)
- [ ] Variação < 5 pontos no score total
- [ ] 3 calls auditadas com supervisão e aprovadas
- [ ] QA Guardian aprovou para operação independente
- [ ] Registro criado no qa-registry

---

## Contexto
Esta task existe para garantir que novos auditores produzam auditorias com qualidade e consistência equivalentes às dos auditores existentes. Auditor descalibrado gera scores incomparáveis, coaching equivocado e erosão de confiança no sistema de auditoria.

## Especificação de I/O
- **Input**: Documentação do sistema de auditoria, scorecard template, biblioteca de frameworks, 5 calls já auditadas (referência), checklists de qualidade vigentes
- **Output**: Perfil do auditor em `data/registries/qa-registry.yaml`, resultado da calibração (variação por bloco), aprovação ou pendência para operação independente

## Quality Gates Intermediários
- Após exercício de calibração (step 4-5): variação < 5 pontos no score total vs. auditoria de referência
- Antes de output final: 3 calls auditadas com supervisão aprovadas pelo QA Guardian, todos os frameworks obrigatórios treinados

## Escalation & Rework
- Se variação persiste > 5 pontos após 2 rodadas de calibração: escalar para sales-chief para decidir calibração adicional ou reatribuição
- Se quality gate falha: rework loop (max 2 ciclos de re-calibração), depois escalar para sales-chief

## Métricas de Sucesso
- time_to_competence do novo auditor (dias até operação independente)
- Variância do novo auditor vs. auditores calibrados nas primeiras 10 auditorias

## Referências Cruzadas
- Workflow: `workflows/04-scoring-and-root-cause.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/qa-guardian.md`, `agents/call-auditor.md`, `agents/sales-chief.md`
- Templates: `templates/scorecards/call-scorecard-template.md`, `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/qa-registry.yaml`
