# Atualizar Registries

> Atualizar todos os registries relevantes após cada auditoria concluída.

## Objetivo
Manter registries como fonte única de verdade para todo o squad — dados desatualizados geram análises incorretas, dashboards defasados e decisões erradas.

## Trigger
- Auditoria de call concluída (todas as etapas finalizadas)
- Sessão de coaching concluída
- Review semanal/mensal concluída

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Atualiza registries de call e scoring |
| Scorecard Analyst | Atualiza registries de performance |
| QA Guardian | Valida integridade dos dados atualizados |

## Inputs
- Scorecard da call concluída
- Relatório de causa raiz
- Relatório de frameworks detectados
- Sessão de coaching (se realizada)
- Output de qualquer task que gera dados

## Processo
1. Atualizar `calls-registry.yaml`: status final, scores, causa raiz, tipo
2. Atualizar `scorecards-registry.yaml`: score por bloco, total, classificação
3. Atualizar `closer-performance-registry.yaml`: novo score, média atualizada
4. Atualizar `framework-detection-registry.yaml`: frameworks detectados
5. Atualizar `root-cause-patterns-registry.yaml`: causa raiz classificada
6. Atualizar `coaching-registry.yaml`: sessão realizada, compromissos
7. Atualizar `sdr-performance-registry.yaml`: handoff score (se aplicável)
8. Verificar integridade: sem campos vazios, IDs corretos, datas válidas
9. Verificar consistência: dados do registry batem com relatórios gerados
10. Fazer backup do estado anterior antes de atualizar

## Frameworks Aplicados
- Data Integrity Framework
- Single Source of Truth Principle

## Checklists de Qualidade
- Todos os registries relevantes atualizados
- Sem campos obrigatórios vazios
- IDs de call consistentes em todos os registries
- Datas e timestamps corretos
- Backup realizado antes da atualização

## Output Esperado
- Registries atualizados em `data/registries/`
- Log de atualizações realizadas
- Confirmação de integridade

## Registry Atualizado
- `data/registries/calls-registry.yaml`
- `data/registries/scorecards-registry.yaml`
- `data/registries/closer-performance-registry.yaml`
- `data/registries/framework-detection-registry.yaml`
- `data/registries/root-cause-patterns-registry.yaml`
- `data/registries/coaching-registry.yaml`

## Critérios de Conclusão
- [ ] Todos os registries relevantes atualizados
- [ ] Integridade verificada (sem campos vazios)
- [ ] Consistência verificada (dados batem com relatórios)
- [ ] Backup realizado
- [ ] Log de atualizações documentado
