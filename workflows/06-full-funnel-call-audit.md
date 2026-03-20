# 06 — Full Funnel Call Audit

> Auditoria completa end-to-end de uma sales call: do intake à entrega de coaching. O workflow master.

## Objetivo

Orquestrar todos os workflows de análise (00 a 05) em sequência, garantindo que cada etapa alimente a próxima corretamente, e produzir o pacote completo de auditoria: transcrição, análise minuto a minuto, detecção de frameworks, scoring, causa raiz e coaching — tudo consolidado em um relatório executivo.

## Quando Executar

- Para qualquer call que demande auditoria completa (padrão de qualidade do squad).
- Quando um closer solicita feedback detalhado.
- Para calls com resultado inesperado (perdeu deal que deveria ter fechado, ou fechou deal improvável).
- Como parte da certificação mensal de closers (workflow 12).

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| sales-chief | Orquestrador master — coordena a sequência, valida outputs, entrega relatório final |
| transcript-analyst | Workflows 00 e 01 (transcrição e segmentação) |
| call-auditor | Workflow 02 (análise minuto a minuto) |
| framework-detector | Workflow 03 (detecção de frameworks) |
| scorecard-analyst | Workflow 04 (scoring) |
| deal-risk-doctor | Workflow 04 (causa raiz) |
| coaching-rewriter | Workflow 05 (reescrita de momentos) |
| objection-specialist | Suporte nos workflows 03 e 05 |
| pricing-anchoring-analyst | Suporte nos workflows 03 e 05 |

## Frameworks Utilizados

- full-funnel-audit-protocol
- Todos os frameworks utilizados nos workflows 00-05

## Checklists Obrigatórios

- full-audit-orchestration-checklist
- Todos os checklists dos workflows individuais (00-05)

## Etapas

### Etapa 1 — Intake e Planejamento da Auditoria
**Responsável**: sales-chief
**Input**: Gravação da call + metadados (closer, lead, produto, data, resultado)
**Ação**:
1. Receber solicitação de auditoria e validar completude dos inputs.
2. Verificar prioridade da auditoria (urgente, padrão, retroativa).
3. Confirmar disponibilidade de todos os agentes necessários.
4. Definir SLA de entrega com base na prioridade.
5. Criar ticket de auditoria com ID único e rastreamento de progresso.
**Output**: Ticket de auditoria criado com SLA definido.
**Quality Gate**: Todos os inputs validados; ticket criado com ID.

### Etapa 2 — Execução do Pipeline de Análise
**Responsável**: sales-chief (orquestrando agentes)
**Input**: Ticket de auditoria + gravação
**Ação**:
1. Disparar workflow 00 (Recording to Transcript) → transcript-analyst.
2. Após conclusão do 00, disparar workflow 01 (Cleaning and Segmentation) → transcript-analyst.
3. Após conclusão do 01, disparar em paralelo:
   - Workflow 02 (Minute-by-Minute Analysis) → call-auditor.
   - Workflow 03 (Framework Detection Loop) → framework-detector.
4. Após conclusão de 02 e 03, disparar workflow 04 (Scoring and Root Cause) → scorecard-analyst + deal-risk-doctor.
5. Após conclusão do 04, disparar workflow 05 (Coaching Rewrite Loop) → coaching-rewriter.
6. Monitorar progresso de cada etapa e intervir se houver bloqueio ou atraso.
**Output**: Todos os outputs dos workflows 00-05 completos e validados.
**Quality Gate**: Cada workflow individual passou seu quality gate antes de avançar.

### Etapa 3 — Consolidação do Relatório Executivo
**Responsável**: sales-chief
**Input**: Outputs de todos os workflows (00-05)
**Ação**:
1. Compilar relatório executivo consolidado com seções:
   - Resumo da Call (quem, quando, produto, resultado).
   - Score Final (10 blocos + nota total + classificação).
   - Causa Raiz (diagnóstico principal + fatores contribuintes).
   - Top 5 Momentos Críticos (timestamp + resumo + impacto).
   - Cobertura de Frameworks (% de aderência + gaps principais).
   - Rewrites Prioritários (top 3 before/after).
   - Recomendações de Coaching (ações prioritárias).
2. Adicionar parecer do sales-chief: visão holística da performance.
3. Comparar score com histórico do closer (tendência de melhoria ou piora).
4. Identificar se há padrões recorrentes que demandam intervenção estrutural.
**Output**: Relatório executivo completo de auditoria.
**Quality Gate**: Todas as seções preenchidas; parecer do sales-chief incluído; comparação histórica feita.

### Etapa 4 — Quality Assurance Final
**Responsável**: sales-chief
**Input**: Relatório executivo consolidado
**Ação**:
1. Revisar consistência entre seções (score alinha com causa raiz, rewrites alinham com gaps).
2. Verificar que todas as evidências são citadas corretamente com timestamps.
3. Confirmar que recomendações são acionáveis e priorizadas.
4. Validar que o relatório é compreensível para o closer e para o gestor.
5. Aprovar ou solicitar revisão de seções específicas.
**Output**: Relatório aprovado para entrega.
**Quality Gate**: full-audit-orchestration-checklist 100% aprovado.

### Etapa 5 — Entrega e Registro
**Responsável**: sales-chief
**Input**: Relatório aprovado
**Ação**:
1. Publicar relatório final no formato padrão.
2. Notificar closer e gestor que a auditoria está disponível.
3. Registrar auditoria completa no audit-registry.
4. Atualizar todos os registries dependentes (closer-score, coaching-log, framework-detection).
5. Fechar ticket de auditoria com status "entregue".
6. Rotear para workflows downstream se aplicável (09 para win, 10 para loss, 12 para certificação).
**Output**: Relatório entregue + ticket fechado + registries atualizados.
**Quality Gate**: Ticket fechado, todos os registries atualizados, stakeholders notificados.

## Templates de Output

- executive-audit-report (relatório consolidado completo)
- audit-summary-one-pager (versão condensada para gestores)

## Registries Atualizados

- audit-registry (auditoria completa registrada)
- closer-score-registry (score atualizado)
- coaching-log-registry (coaching registrado)
- framework-detection-registry (detecções registradas)
- call-log-registry (status final da call atualizado)

## Critérios de Conclusão

- [ ] Workflows 00-05 executados e quality gates aprovados
- [ ] Relatório executivo consolidado com todas as seções
- [ ] Parecer do sales-chief incluído com visão holística
- [ ] Comparação com histórico do closer realizada
- [ ] Quality assurance final aprovado
- [ ] Relatório entregue a closer e gestor
- [ ] Todos os registries atualizados e ticket fechado

## Próximo Workflow

→ Depende do resultado da call:
  - Call ganha → 09-win-pattern-extraction.md
  - Call perdida → 10-loss-pattern-extraction.md
  - Closer em certificação → 12-monthly-closer-certification.md

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | Intake e planejamento validados | Todos os inputs completos (gravação + metadados); ticket criado com ID único e SLA definido | Voltar a Etapa 1 (solicitar inputs faltantes ou redefinir prioridade) |
| Etapa 2 (WF00) → Etapa 2 (WF01) | Quality gate do workflow 00 aprovado | Transcrição normalizada, speakers identificados, segmentação por blocos concluída | Voltar ao workflow 00 (reprocessar etapa falha) |
| Etapa 2 (WF01) → Etapa 2 (WF02+03) | Quality gate do workflow 01 aprovado | Transcrição segmentada por fases, resumo executivo gerado, talk-time calculado | Voltar ao workflow 01 (corrigir segmentação ou resumo) |
| Etapa 2 (WF02+03) → Etapa 2 (WF04) | Quality gates dos workflows 02 e 03 aprovados | Análise minuto a minuto completa e detecção de frameworks validada por specialists | Voltar ao workflow 02 ou 03 (completar análise pendente) |
| Etapa 2 (WF04) → Etapa 2 (WF05) | Quality gate do workflow 04 aprovado | Scorecard com 10 blocos pontuados, causa raiz identificada, recomendações priorizadas | Voltar ao workflow 04 (revisar scoring ou aprofundar causa raiz) |
| Etapa 2 (WF05) → Etapa 3 | Quality gate do workflow 05 aprovado | Rewrites before/after validados, pacote de coaching com exercícios práticos | Voltar ao workflow 05 (refinar rewrites ou completar pacote) |
| Etapa 3 → Etapa 4 | Relatório executivo consolidado | Todas as seções preenchidas; parecer do sales-chief incluído; comparação histórica feita | Voltar a Etapa 3 (completar seções faltantes ou adicionar parecer) |
| Etapa 4 → Etapa 5 | full-audit-orchestration-checklist 100% | Consistência entre seções, evidências citadas, recomendações acionáveis, relatório compreensível | Voltar a Etapa 4 (corrigir inconsistências ou seções reprovadas) |
| Etapa 5 → Conclusão | Entrega e registro completos | Ticket fechado, todos os registries atualizados, stakeholders notificados | Voltar a Etapa 5 (atualizar registries faltantes ou notificar stakeholders) |

## Decision Points
- Após Etapa 2 (WF01 concluído): se transcrição possui fases fora de ordem ou fases ausentes → sinalizar para call-auditor e framework-detector como anomalia antes de disparar workflows 02 e 03
- Após Etapa 3: se score final < 40 (Crítica) → incluir flag de urgência no relatório e priorizar entrega; se score >= 85 (Elite) → incluir flag para extração de win patterns (workflow 09) mesmo em calls não fechadas
- Após Etapa 4: se QA identifica inconsistências entre score e causa raiz → devolver seções específicas para revisão em vez de reprovar relatório inteiro

## Escalation Triggers
- Se qualquer workflow individual (00-05) excede o SLA definido → sales-chief intervém para destravar bloqueio e realocar recursos
- Se há divergência entre agentes sobre o diagnóstico final (ex: scorecard-analyst e deal-risk-doctor discordam sobre causa raiz) → sales-chief arbitra com base em evidências consolidadas
- Se o closer em questão possui 3+ auditorias consecutivas com score < 55 → escalar para sales-chief para decisão sobre programa intensivo de recuperação ou remoção do time
