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
