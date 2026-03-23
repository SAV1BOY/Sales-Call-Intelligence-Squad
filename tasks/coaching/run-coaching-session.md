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

---

## Contexto
Dados sem prática deliberada não geram mudança de comportamento. Esta task existe para garantir que a sessão de coaching siga estrutura comprovada (abertura positiva, diagnóstico, role-play, compromisso), transformando insights da auditoria em melhoria real de performance.

## Especificação de I/O
- **Input**: Pack de coaching completo + reescritas dos momentos críticos + scorecard da call + plano de treino vigente
- **Output**: Registro de sessão em `reports/coaching/CALL-ID-session-log` + compromissos documentados

## Quality Gates Intermediários
- Após prática deliberada (step 5): checklist `coaching-plan-quality` — role-play realizado, repetição até execução natural, feedback imediato dado
- Antes de output final: verificar que ações definidas são específicas, mensuráveis e com prazo

## Escalation & Rework
- Se closer não demonstra evolução após 3 sessões consecutivas: escalar para `sales-chief` para reavaliação de fit
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `coaching_impact_score`: delta de score entre call auditada e calls pós-sessão
- `rewrite_adoption_rate`: % de técnicas praticadas na sessão que aparecem nas calls seguintes

## Handoff
- Output entregue a: `closer-trainer` e `sales-chief` para revisão de certificação (workflow `12-monthly-closer-certification`, Etapa 2 e Etapa 4)
- Formato de entrega: Registro de sessão em `reports/coaching/CALL-ID-session-log` + compromissos documentados com prazos
- Condição de entrega: checklist `coaching-plan-quality` aprovado (role-play realizado, ações específicas e mensuráveis definidas, compromisso verbalizado pelo closer)
- Próximo passo no pipeline: Etapa 2 do workflow `12-monthly-closer-certification` (Avaliação de Competências Técnicas — closer-trainer avalia evolução e aderência ao coaching)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-9 com revalidação do checklist obrigatório
- Max ciclos: 3
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 3 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/05-coaching-rewrite-loop.md`
- Agents: `agents/closer-trainer.md`, `agents/coaching-rewriter.md`, `agents/sales-chief.md`
- Templates: `templates/reports/manager-coaching-report.md`
- Registries atualizados: `data/registries/coaching-registry.yaml`, `data/registries/closer-performance-registry.yaml`
