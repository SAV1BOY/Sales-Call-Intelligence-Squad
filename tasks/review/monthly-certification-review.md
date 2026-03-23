# Review Mensal de Certificação

> Review mensal de certificação de closers: avaliar maturidade, progressão e decisões de certificação.

## Objetivo
Manter processo formal de certificação que garante padrão mínimo de qualidade na equipe — identifica quem está pronto para mais responsabilidade e quem precisa de suporte intensivo.

## Trigger
- Primeiro dia útil de cada mês
- Execução do workflow `12-monthly-closer-certification`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Closer Trainer | Apresenta avaliação de cada closer |
| Scorecard Analyst | Fornece análise estatística mensal |
| QA Guardian | Audita consistência das avaliações |
| Sales Chief | Toma decisões finais de certificação |

## Inputs
- Scorecards do mês por closer
- Relatórios de coaching e evolução
- Planos de treino vigentes e progresso
- Certificações anteriores
- Benchmarks da equipe

## Processo
1. Compilar performance mensal por closer: score médio, tendência, consistência
2. Comparar com mês anterior: evolução ou regressão por closer
3. Avaliar progresso dos planos de treino: metas atingidas ou não
4. Aplicar critérios de certificação para cada closer
5. Decidir por closer: manter nível, promover, rebaixar ou iniciar plano intensivo
6. Identificar closers prontos para mentoria (ajudar outros)
7. Identificar closers em risco (2 meses consecutivos abaixo do mínimo)
8. Atualizar certificações no registry
9. Comunicar decisões e próximos passos por closer

## Frameworks Aplicados
- Competency Development Framework
- Coaching Progression Check
- Certification Standards

## Checklists de Qualidade
- Todos os closers ativos avaliados
- Performance mensal baseada em mínimo 5 calls
- Evolução comparada com mês anterior
- Decisões de certificação justificadas com dados
- Closers em risco identificados e com plano

## Output Esperado
- Relatório de certificação em `reports/reviews/monthly-certification-YYYY-MM`
- Status de certificação por closer: nível, decisão, justificativa
- Lista de ações por closer

## Registry Atualizado
- `data/registries/closer-certification-registry.yaml`
- `data/registries/closer-performance-registry.yaml`
- `data/registries/review-registry.yaml`

## Critérios de Conclusão
- [ ] Todos os closers avaliados
- [ ] Decisões de certificação documentadas
- [ ] Closers em risco identificados com plano
- [ ] Certificações atualizadas no registry
- [ ] Comunicação de resultados realizada
- [ ] Próxima review agendada

---

## Contexto
Esta task existe para manter um processo formal de certificação que garante padrão mínimo de qualidade na equipe de closers. Sem certificação periódica, não há como identificar quem está pronto para mais responsabilidade e quem precisa de suporte intensivo antes que os resultados de vendas sejam impactados.

## Especificação de I/O
- **Input**: Scorecards do mês por closer, relatórios de coaching e evolução, planos de treino vigentes, certificações anteriores, benchmarks da equipe
- **Output**: Relatório de certificação em `reports/reviews/monthly-certification-YYYY-MM` usando `templates/reports/closer-certification-report.md`

## Quality Gates Intermediários
- Após compilação de performance mensal (step 1-3): todos os closers ativos avaliados, performance baseada em mínimo 5 calls
- Antes de output final: decisões de certificação justificadas com dados, closers em risco identificados com plano de ação

## Escalation & Rework
- Se closer está 2 meses consecutivos abaixo do mínimo (score < 60): escalar para sales-chief + c_level_squad para avaliar fit closer-oferta
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief

## Métricas de Sucesso
- certification_pass_rate (taxa de aprovação na certificação)
- score_improvement_rate dos closers em plano de desenvolvimento

## Referências Cruzadas
- Workflow: `workflows/12-monthly-closer-certification.md`
- Agents: `agents/closer-trainer.md`, `agents/scorecard-analyst.md`, `agents/qa-guardian.md`, `agents/sales-chief.md`
- Templates: `templates/reports/closer-certification-report.md`, `templates/scorecards/closer-performance-scorecard.md`, `templates/scorecards/certification-scorecard.md`
- Registries atualizados: `data/registries/closer-certification-registry.yaml`, `data/registries/closer-performance-registry.yaml`, `data/registries/review-registry.yaml`

## Handoff
- **Output entregue a**: sales-chief para decisões finais de certificação e comunicação aos closers e gestores
- **Formato de entrega**: relatório de certificação em `reports/reviews/monthly-certification-YYYY-MM` usando `templates/reports/closer-certification-report.md`
- **Condição de entrega**: todos os closers ativos avaliados, decisões de certificação justificadas com dados, closers em risco identificados com plano de ação
- **Próximo passo no pipeline**: sales-chief comunica decisões; closer-trainer executa planos intensivos para closers em risco; closer-certification-registry atualizado

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
