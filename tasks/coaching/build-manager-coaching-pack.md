# Montar Pack de Coaching para Gestor

> Montar pack completo para o gestor comercial conduzir sessão de coaching com o closer.

## Objetivo
Entregar ao gestor um pacote pronto para uso com diagnóstico, prioridades, reescritas e roteiro de sessão — o gestor não precisa auditar a call, apenas conduzir o coaching com o material preparado.

## Trigger
- Auditoria completa da call concluída (scorecard + causa raiz + reescritas)
- Solicitação de coaching pelo gestor ou pelo Sales Chief

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Closer Trainer | Monta o pack de coaching completo |
| Coaching Rewriter | Fornece reescritas dos momentos críticos |
| Scorecard Analyst | Fornece scorecard resumido e comparação histórica |
| Sales Chief | Valida prioridades de coaching |

## Inputs
- Scorecard completo da call
- Relatório de causa raiz
- Reescritas dos momentos críticos
- Histórico de coaching do closer
- Plano de treino vigente (se existir)

## Processo
1. Compilar resumo executivo da auditoria (1 página): score, pontos fortes, pontos fracos
2. Destacar as 3 prioridades de coaching baseadas na causa raiz
3. Incluir reescritas dos momentos críticos relevantes para as prioridades
4. Preparar roteiro de sessão de coaching (30 minutos):
   - Abertura: reconhecer acertos (2min)
   - Diagnóstico: apresentar dados e evidências (8min)
   - Reescritas: praticar versões melhoradas (10min)
   - Plano: definir ações e métricas (5min)
   - Fechamento: compromisso e próxima revisão (5min)
5. Incluir perguntas de coaching para o gestor usar (não dar respostas, provocar reflexão)
6. Adicionar comparação de evolução: score atual vs. anteriores
7. Incluir métricas de acompanhamento sugeridas
8. Formatar pack para impressão ou apresentação digital

## Frameworks Aplicados
- Coaching Progression Check
- Coaching Specificity Check
- Coaching Actionability Check
- Scorecard-to-Coaching Bridge

## Checklists de Qualidade
- Resumo executivo claro e de 1 página
- 3 prioridades baseadas em causa raiz (não em opinião)
- Roteiro de sessão com timing por bloco
- Perguntas de coaching incluídas (reflexivas, não prescritivas)
- Evolução histórica comparada

## Output Esperado
- Pack de coaching em `reports/coaching/CALL-ID-coaching-pack`
- Roteiro de sessão com timing
- Perguntas de coaching para o gestor

## Registry Atualizado
- `data/registries/coaching-registry.yaml`
- `data/registries/closer-performance-registry.yaml`

## Critérios de Conclusão
- [ ] Resumo executivo de 1 página compilado
- [ ] 3 prioridades de coaching definidas
- [ ] Reescritas incluídas e vinculadas às prioridades
- [ ] Roteiro de sessão preparado com timing e perguntas de coaching
- [ ] Evolução histórica comparada e pack formatado

---

## Contexto
Gestores comerciais não têm tempo para auditar calls individualmente. Esta task existe para entregar um pacote pronto para uso que transforma dados de auditoria em material de coaching acionável, eliminando o gap entre análise técnica e sessão de desenvolvimento.

## Especificação de I/O
- **Input**: Scorecard completo da call + relatório de causa raiz + reescritas dos momentos críticos + histórico de coaching do closer
- **Output**: `templates/reports/manager-coaching-report` + `templates/scorecards/closer-performance-scorecard`

## Quality Gates Intermediários
- Após compilação do resumo executivo (step 1): checklist `manager-review-quality` — resumo de 1 página, sem jargão técnico, prioridades claras
- Antes de output final: checklist `coaching-plan-quality` — roteiro com timing, perguntas reflexivas, evolução histórica presente

## Escalation & Rework
- Se histórico de coaching insuficiente (< 2 sessões anteriores): escalar para `closer-trainer` para reconstruir baseline
- Se quality gate falha: rework loop (max 3 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `coaching_impact_score`: melhoria no score do closer após sessão conduzida com o pack
- `rewrite_adoption_rate`: % de reescritas do pack que o closer implementou nas calls seguintes

## Referências Cruzadas
- Workflow: `workflows/05-coaching-rewrite-loop.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/closer-trainer.md`, `agents/scorecard-analyst.md`, `agents/sales-chief.md`
- Templates: `templates/reports/manager-coaching-report.md`, `templates/scorecards/closer-performance-scorecard.md`
- Registries atualizados: `data/registries/lessons-learned-registry`

## Handoff
- **Output entregue a**: gestor comercial (manager) para condução da sessão de coaching com o closer
- **Formato de entrega**: pack de coaching em `reports/coaching/CALL-ID-coaching-pack` usando `templates/reports/manager-coaching-report.md`
- **Condição de entrega**: resumo executivo de 1 página, 3 prioridades baseadas em causa raiz, roteiro de sessão com timing, perguntas reflexivas incluídas, evolução histórica comparada
- **Próximo passo no pipeline**: gestor conduz sessão de coaching de 30 min com o closer usando o pack; resultados da sessão registrados em coaching-registry; impacto medido nas calls seguintes

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
