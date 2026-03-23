# Onboarding de Novo Closer

> Onboarding estruturado de novo closer: baseline de performance, assessment inicial e plano de desenvolvimento.

## Objetivo
Estabelecer baseline confiável de performance do novo closer desde o primeiro dia — sem baseline, não há como medir evolução. Garantir que o closer conheça os padrões e comece com plano claro.

## Trigger
- Novo closer contratado ou transferido para a equipe
- Primeiro dia de operação do closer

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Closer Trainer | Conduz onboarding e assessment |
| Call Auditor | Audita primeiras calls para baseline |
| Scorecard Analyst | Gera baseline de performance |
| Sales Chief | Aprova plano de desenvolvimento e define metas |

## Inputs
- Informações do novo closer (experiência, background)
- Scorecard template e critérios de certificação
- Frameworks obrigatórios do squad
- Calls de referência (exemplos de alta performance)
- Plano de onboarding padrão

## Processo
1. Apresentar o sistema de auditoria: como funciona, o que é avaliado, como o score funciona
2. Compartilhar frameworks obrigatórios: Doctor Frame, First Pact, Value Equation
3. Apresentar calls de referência: exemplos de alta performance comentados
4. Auditar as 3 primeiras calls do closer com critérios completos
5. Gerar baseline de performance: score médio, forças e fraquezas iniciais
6. Comparar baseline com média da equipe e critérios de certificação
7. Construir plano de desenvolvimento inicial: top 3 prioridades do closer
8. Definir cadência de acompanhamento: semanal nas primeiras 4 semanas
9. Atribuir mentor (closer senior) se disponível
10. Agendar primeira sessão de coaching para após a 5a call auditada

## Frameworks Aplicados
- Competency Development Framework
- Onboarding Checklist
- Certification Standards (para definir gap inicial)

## Checklists de Qualidade
- Sistema de auditoria apresentado e compreendido
- Frameworks obrigatórios compartilhados
- 3 primeiras calls auditadas para baseline
- Baseline documentado com scores por bloco
- Plano de desenvolvimento com prioridades e prazos

## Output Esperado
- Perfil do closer em `data/registries/closer-performance-registry.yaml`
- Baseline de performance com scores das 3 primeiras calls
- Plano de desenvolvimento inicial

## Registry Atualizado
- `data/registries/closer-performance-registry.yaml`
- `data/registries/closer-certification-registry.yaml`
- `data/registries/coaching-registry.yaml`

## Critérios de Conclusão
- [ ] Closer recebeu apresentação do sistema
- [ ] Frameworks obrigatórios compartilhados
- [ ] 3 primeiras calls auditadas
- [ ] Baseline de performance gerado
- [ ] Plano de desenvolvimento criado
- [ ] Cadência de acompanhamento definida
- [ ] Registro criado em todos os registries

---

## Contexto
Esta task existe para estabelecer um baseline confiável de performance desde o primeiro dia do closer. Sem baseline, não há como medir evolução real — e sem plano estruturado, o closer demora mais para atingir o padrão mínimo do time.

## Especificação de I/O
- **Input**: Informações do novo closer (experiência, background), scorecard template, frameworks obrigatórios, calls de referência (alta performance)
- **Output**: Perfil do closer em `data/registries/closer-performance-registry.yaml`, baseline de performance (scores das 3 primeiras calls), plano de desenvolvimento inicial

## Quality Gates Intermediários
- Após auditoria das 3 primeiras calls (step 4): baseline documentado com scores por bloco e comparação com média da equipe
- Antes de output final: plano de desenvolvimento com top 3 prioridades, cadência de acompanhamento definida, mentor atribuído

## Escalation & Rework
- Se baseline muito abaixo da média (score < 40): escalar para sales-chief para avaliar fit closer-oferta antes de prosseguir
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief

## Métricas de Sucesso
- time_to_competence (tempo para closer atingir score mínimo de certificação: 70)
- coaching_impact_score nas primeiras 4 semanas

## Referências Cruzadas
- Workflow: `workflows/12-monthly-closer-certification.md`, `workflows/05-coaching-rewrite-loop.md`
- Agents: `agents/closer-trainer.md`, `agents/call-auditor.md`, `agents/scorecard-analyst.md`, `agents/sales-chief.md`
- Templates: `templates/scorecards/closer-performance-scorecard.md`, `templates/reports/manager-coaching-report.md`
- Registries atualizados: `data/registries/closer-performance-registry.yaml`, `data/registries/closer-certification-registry.yaml`, `data/registries/coaching-registry.yaml`

## Handoff
- **Output entregue a**: closer-trainer para execução do plano de desenvolvimento e sales-chief para aprovação de metas iniciais
- **Formato de entrega**: perfil do closer em `data/registries/closer-performance-registry.yaml` + baseline de performance (scores das 3 primeiras calls) + plano de desenvolvimento inicial
- **Condição de entrega**: 3 primeiras calls auditadas, baseline documentado com scores por bloco, plano de desenvolvimento com top 3 prioridades, cadência de acompanhamento semanal definida
- **Próximo passo no pipeline**: closer-trainer inicia acompanhamento semanal nas primeiras 4 semanas; primeira sessão de coaching agendada após 5a call auditada; closer entra no ciclo de certificação mensal

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
