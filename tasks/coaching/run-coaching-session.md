# Executar Sessão de Coaching

> Executar sessão de coaching estruturada baseada na auditoria, com prática deliberada e compromissos.

## Objetivo
Conduzir sessão de coaching eficaz que transforme dados da auditoria em melhoria real de performance — não é palestra, é prática deliberada com feedback imediato.

## Trigger
- Pack de coaching montado e aprovado
- Agendamento de sessão pelo gestor
- Execução pós-auditoria de call com score < 60

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Closer Trainer | Conduz a sessão de coaching |
| Coaching Rewriter | Fornece reescritas para prática |
| Sales Chief | Supervisiona qualidade do coaching |

## Inputs
- Pack de coaching completo
- Reescritas dos momentos críticos
- Scorecard da call auditada
- Plano de treino vigente do closer
- Histórico de sessões anteriores

## Processo
1. Preparar ambiente: revisar pack, selecionar 2-3 pontos focais (não sobrecarregar)
2. Abertura (3min): reconhecer pontos fortes da call — começar pelo positivo
3. Diagnóstico compartilhado (7min): apresentar dados e perguntar percepção do closer
4. Escuta ativa: deixar o closer explicar suas decisões antes de corrigir
5. Prática deliberada (12min): role-play dos momentos reescritos
   - Closer pratica a versão melhorada
   - Feedback imediato após cada tentativa
   - Repetir até execução natural
6. Plano de ação (5min): definir 1-2 ações específicas para próximas calls
7. Compromisso (3min): closer verbaliza o que vai fazer diferente e quando
8. Registrar sessão: pontos abordados, prática realizada, compromissos assumidos
9. Agendar follow-up: próxima revisão vinculada às ações definidas

## Frameworks Aplicados
- Coaching Actionability Check
- Coaching Specificity Check
- Coaching Progression Check
- Deliberate Practice Framework

## Checklists de Qualidade
- Sessão focada em 2-3 pontos (não mais)
- Positivos reconhecidos antes de gaps
- Closer teve espaço para falar e refletir
- Role-play realizado com repetição
- Ações específicas e mensuráveis definidas
- Compromisso verbalizado pelo closer

## Output Esperado
- Registro de sessão em `reports/coaching/CALL-ID-session-log`
- Compromissos do closer documentados com prazos
- Próximo follow-up agendado

## Registry Atualizado
- `data/registries/coaching-registry.yaml`
- `data/registries/closer-performance-registry.yaml` (sessões realizadas)

## Critérios de Conclusão
- [ ] Sessão conduzida com estrutura (abertura → diagnóstico → prática → plano)
- [ ] Role-play realizado com momentos reescritos
- [ ] 1-2 ações específicas definidas
- [ ] Compromisso registrado
- [ ] Follow-up agendado
- [ ] Sessão documentada no registry
