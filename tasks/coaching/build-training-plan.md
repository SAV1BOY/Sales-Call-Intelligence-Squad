# Construir Plano de Treino

> Construir plano de treino individualizado: top 3 prioridades, exercícios práticos e métricas de progresso.

## Objetivo
Criar plano de desenvolvimento estruturado para o closer baseado em padrões identificados em múltiplas calls — não é sobre uma call específica, mas sobre gaps recorrentes que precisam de treino sistemático.

## Trigger
- Mínimo de 3 calls auditadas do mesmo closer
- Padrões recorrentes identificados nas causas raiz
- Solicitação de plano de desenvolvimento pelo gestor

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Closer Trainer | Constrói o plano de treino completo |
| Scorecard Analyst | Fornece análise de tendências de scores |
| Sales Chief | Aprova plano e define prazos |
| QA Guardian | Valida que o plano é específico e mensurável |

## Inputs
- Scorecards das últimas 5-10 calls do closer
- Relatórios de causa raiz (padrões recorrentes)
- Histórico de coaching anterior
- Perfil de maturidade do closer
- Frameworks mais deficientes

## Processo
1. Analisar tendências de score por bloco nas últimas 5-10 calls
2. Identificar os 3 gaps mais recorrentes e de maior impacto
3. Priorizar por impacto na taxa de conversão × facilidade de correção
4. Para cada prioridade, definir:
   - Habilidade específica a desenvolver
   - Framework de referência para estudo
   - Exercício prático (role-play, drill, análise de call modelo)
   - Métrica de progresso (score do bloco, comportamento observável)
   - Prazo para reavaliação
5. Definir cadência de acompanhamento: semanal para gaps críticos
6. Incluir calls de referência (exemplos positivos do próprio closer ou de top performers)
7. Definir critério de graduação: quando o closer superou o gap
8. Vincular plano ao scorecard para tracking automático

## Frameworks Aplicados
- Coaching Progression Check
- Coaching Priority Check
- Scorecard-to-Coaching Bridge
- Competency Development Framework

## Checklists de Qualidade
- Top 3 prioridades baseadas em dados (não em impressão)
- Cada prioridade tem exercício prático e métrica
- Prazos definidos e realistas
- Calls de referência incluídas
- Critério de graduação claro e mensurável

## Output Esperado
- Plano de treino em `reports/training/CLOSER-NAME-training-plan`
- Top 3 prioridades com exercícios, métricas e prazos
- Cadência de acompanhamento definida

## Registry Atualizado
- `data/registries/coaching-registry.yaml`
- `data/registries/closer-performance-registry.yaml`

## Critérios de Conclusão
- [ ] Tendências de score analisadas (mínimo 3 calls)
- [ ] Top 3 gaps identificados com dados
- [ ] Exercício prático e métricas definidos por prioridade
- [ ] Prazos, cadência estabelecidos e plano aprovado pelo Sales Chief

---

## Contexto
Coaching pontual por call não resolve gaps recorrentes. Esta task existe para transformar padrões identificados em múltiplas auditorias em um plano de desenvolvimento estruturado e mensurável, atacando causas sistêmicas de baixa performance.

## Especificação de I/O
- **Input**: Scorecards das últimas 5-10 calls do closer + relatórios de causa raiz + histórico de coaching + perfil de maturidade
- **Output**: `reports/training/CLOSER-NAME-training-plan` (formato definido por `templates/reports/manager-coaching-report`)

## Quality Gates Intermediários
- Após identificação dos top 3 gaps (step 2-3): checklist `coaching-plan-quality` — cada gap baseado em dados, não impressão; impacto na conversão justificado
- Antes de output final: QA Guardian valida que exercícios são específicos, mensuráveis e com prazo

## Escalation & Rework
- Se closer tem score médio < 40 (nível crítico): escalar para `sales-chief` para avaliar fit closer-oferta junto com `c_level_squad`
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `time_to_competence`: tempo para closer atingir score mínimo nos blocos treinados
- `coaching_impact_score`: delta de score antes e depois do plano de treino

## Handoff
- Output entregue a: `closer-trainer` para execução de sessões de coaching (task `run-coaching-session`)
- Formato de entrega: `reports/training/CLOSER-NAME-training-plan` (formato definido por `templates/reports/manager-coaching-report`)
- Condição de entrega: checklist `coaching-plan-quality` aprovado (cada gap baseado em dados, exercícios específicos e mensuráveis com prazo) E QA Guardian validou especificidade
- Próximo passo no pipeline: Etapa 2 do workflow `12-monthly-closer-certification` (Avaliação de Competências Técnicas pelo closer-trainer)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-8 com revalidação do checklist obrigatório
- Max ciclos: 3
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 3 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/12-monthly-closer-certification.md`
- Agents: `agents/closer-trainer.md`, `agents/scorecard-analyst.md`, `agents/sales-chief.md`, `agents/qa-guardian.md`
- Templates: `templates/reports/manager-coaching-report.md`, `templates/scorecards/closer-performance-scorecard.md`
- Registries atualizados: `data/registries/coaching-registry.yaml`, `data/registries/closer-performance-registry.yaml`
