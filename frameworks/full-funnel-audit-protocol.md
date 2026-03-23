# Full Funnel Audit Protocol

> Framework de orquestração para consolidar outputs dos workflows 00-05 em um relatório executivo único de auditoria completa.

## Origem

Protocolo interno do Sales Intelligence Squad para garantir que auditorias full-funnel sejam consistentes, completas e acionáveis. Baseado em práticas de quality assurance de processos multi-etapa, adaptado para o contexto de análise de sales calls.

## Conceito Central

O Full Funnel Audit Protocol define como o sales-chief orquestra a execução sequencial dos workflows 00 a 05, consolida seus outputs em um relatório executivo coeso e garante que não haja contradições, gaps ou redundâncias entre as análises individuais. O protocolo trata cada workflow como um módulo independente cujo output alimenta o próximo, com quality gates entre cada transição.

## Quando Aplicar

- Em toda auditoria completa de call (workflow 06).
- Quando múltiplos agentes produzem análises que precisam ser consolidadas.
- Como referência para o sales-chief ao arbitrar divergências entre agentes.

## Etapa 1 — Planejamento e Validação de Inputs

**Objetivo**: Garantir que todos os pré-requisitos estão satisfeitos antes de iniciar o pipeline.

**Regras**:
1. Confirmar que a gravação está completa e audível (sem cortes, sem falhas de áudio).
2. Validar metadados obrigatórios: closer, lead, produto, data, resultado da call.
3. Definir prioridade (urgente, padrão, retroativa) e SLA correspondente.
4. Criar ticket de auditoria com ID único para rastreamento.
5. Verificar disponibilidade dos agentes necessários no pipeline.

**Output esperado**: Ticket de auditoria criado, inputs validados, SLA definido.

## Etapa 2 — Execução Sequencial do Pipeline

**Objetivo**: Executar workflows 00-05 na ordem correta, respeitando dependências.

**Sequência obrigatória**:
1. **WF00** (Recording to Transcript) → transcript-analyst
2. **WF01** (Cleaning and Segmentation) → transcript-analyst
3. **WF02** (Minute-by-Minute Analysis) + **WF03** (Framework Detection) → em paralelo (call-auditor + framework-detector)
4. **WF04** (Scoring and Root Cause) → scorecard-analyst + deal-risk-doctor
5. **WF05** (Coaching Rewrite Loop) → coaching-rewriter

**Regras de transição**:
- Cada workflow só inicia após o quality gate do anterior ser aprovado.
- WF02 e WF03 podem rodar em paralelo porque não dependem um do outro.
- WF04 depende de WF02 e WF03 — ambos devem estar concluídos.
- WF05 depende de WF04 — precisa do scorecard e causa raiz para priorizar rewrites.

**Monitoramento**:
- sales-chief monitora progresso de cada etapa.
- Se qualquer workflow excede o SLA, sales-chief intervém para destravar.

## Etapa 3 — Consolidação do Relatório Executivo

**Objetivo**: Unificar outputs de 6+ agentes em um relatório coeso e sem contradições.

**Regras de consolidação**:

### 3.1 — Mapeamento de Outputs para Seções
| Seção do Relatório | Fonte (Workflow) | Agente Responsável |
|---------------------|-----------------|-------------------|
| Resumo da Call | WF00 + WF01 | transcript-analyst |
| Score Final (10 blocos) | WF04 | scorecard-analyst |
| Causa Raiz | WF04 | deal-risk-doctor |
| Top 5 Momentos Críticos | WF02 | call-auditor |
| Cobertura de Frameworks | WF03 | framework-detector |
| Rewrites Prioritários | WF05 | coaching-rewriter |
| Recomendações de Coaching | WF04 + WF05 | deal-risk-doctor + coaching-rewriter |
| Parecer do Sales-Chief | Consolidação | sales-chief |

### 3.2 — Regras de Merge
1. **Dados quantitativos** (scores, percentuais, contagens) devem vir de uma única fonte autoritativa — o workflow designado.
2. **Timestamps** devem ser consistentes entre seções. Se WF02 cita um momento em [12:30] e WF03 cita o mesmo em [12:28], padronizar para o timestamp do WF02 (análise mais granular).
3. **Trechos da transcrição** citados em múltiplas seções devem usar a versão limpa do WF01.
4. **Duplicatas**: se dois agentes identificam o mesmo momento crítico, manter a análise mais profunda e referenciar ambos agentes.
5. **Gaps**: se uma seção do template não foi coberta por nenhum workflow, o sales-chief deve preencher ou sinalizar como "dados insuficientes".

### 3.3 — Resolução de Conflitos entre Agentes

Quando agentes divergem sobre o mesmo ponto:

| Tipo de Conflito | Regra de Resolução |
|-----------------|-------------------|
| Score divergente (ex: scorecard-analyst dá 6, call-auditor sugere 4) | Prevalece o scorecard-analyst (owner do scoring); registrar divergência como nota |
| Causa raiz divergente (ex: deal-risk-doctor vs. framework-detector) | sales-chief arbitra com base em evidências consolidadas; incluir ambas perspectivas se complementares |
| Framework detection ambígua (ex: SPIN vs. NEPQ detectados no mesmo trecho) | framework-detector é autoritativo; se ambiguidade persiste, registrar como "técnica mista" |
| Recomendações contraditórias (ex: "falar mais" vs. "ouvir mais") | Contextualizar por fase da call — pode ser que ambas estejam corretas para momentos diferentes |
| Timestamp conflitante para o mesmo evento | Usar timestamp do WF02 (análise minuto a minuto é a referência temporal) |

**Princípio geral**: Na dúvida, incluir ambas perspectivas com contexto em vez de eliminar uma. O sales-chief adiciona parecer unificador.

## Etapa 4 — Quality Assurance do Relatório Consolidado

**Objetivo**: Garantir consistência interna, completude e clareza antes da entrega.

**Verificações obrigatórias**:
1. **Consistência score-causa raiz**: O score final deve ser coerente com o diagnóstico. Score baixo em discovery + causa raiz "objeção de preço" → verificar se a causa real não é discovery fraco.
2. **Consistência momentos-rewrites**: Os rewrites devem corresponder aos momentos críticos identificados. Não pode haver rewrite de momento não citado.
3. **Consistência frameworks-gaps**: Os gaps de framework devem alinhar com os scores baixos nos blocos correspondentes.
4. **Evidências verificáveis**: Todo trecho citado deve ter timestamp e ser rastreável à transcrição original.
5. **Recomendações acionáveis**: Cada recomendação deve ter ação específica, não genérica.
6. **Comparação histórica**: Se o closer tem auditorias anteriores, incluir tendência.

**Quality gate**: Aplicar `full-audit-orchestration-checklist` — 100% dos itens devem passar.

## Etapa 5 — Entrega e Registro

**Objetivo**: Publicar, notificar e registrar a auditoria completa.

**Ações obrigatórias**:
1. Publicar relatório no formato `templates/reports/full-call-audit-report.md`.
2. Notificar closer e gestor.
3. Registrar no audit-registry com status "entregue".
4. Atualizar registries dependentes: closer-score, coaching-log, framework-detection, call-log.
5. Fechar ticket de auditoria.
6. Rotear para workflows downstream conforme resultado (WF09 para win, WF10 para loss, WF12 para certificação).

## Padrões de Evidência

Cada seção do relatório consolidado deve incluir evidência no seguinte padrão:

| Tipo de Evidência | Formato Obrigatório | Fonte |
|-------------------|-------------------|-------|
| Trecho de transcrição | `[MM:SS] Speaker: "fala literal"` | WF01 (transcrição limpa) |
| Score de bloco | `Bloco X — Score: N/10 — Justificativa: [texto]` | WF04 |
| Framework detectado | `Framework: [nome] — Aderência: XX% — Gaps: [lista]` | WF03 |
| Momento crítico | `[MM:SS] — Tipo: [categoria] — Impacto: [descrição]` | WF02 |
| Rewrite | `ANTES: "[trecho]" → DEPOIS: "[rewrite]" — Framework: [nome] — Justificativa: [texto]` | WF05 |
| Causa raiz | `Causa: [descrição] — Evidências: [lista de trechos] — Impacto: [quantificação]` | WF04 |

## Formato de Output

O relatório consolidado deve seguir o template `templates/reports/full-call-audit-report.md` com todas as seções obrigatórias:

1. Resumo da Call (quem, quando, produto, resultado)
2. Score Final (10 blocos + nota total + classificação)
3. Causa Raiz (diagnóstico principal + fatores contribuintes)
4. Top 5 Momentos Críticos (timestamp + resumo + impacto)
5. Cobertura de Frameworks (% de aderência + gaps principais)
6. Rewrites Prioritários (top 3 before/after)
7. Recomendações de Coaching (ações prioritárias)
8. Parecer do Sales-Chief (visão holística + comparação histórica)

## Critérios de Qualidade do Relatório Consolidado

| Critério | Peso | Descrição |
|----------|------|-----------|
| Completude | 3 | Todas as seções preenchidas, sem campos vazios |
| Consistência interna | 4 | Score, causa raiz, momentos e rewrites alinhados entre si |
| Evidência verificável | 3 | Todo trecho com timestamp, todo score com justificativa |
| Acionabilidade | 3 | Recomendações específicas com prioridade e próximo passo |
| Clareza | 2 | Compreensível para closer e gestor sem contexto adicional |
| Parecer holístico | 2 | Sales-chief agrega visão que nenhum agente individual tem |
| Comparação histórica | 1 | Tendência do closer ao longo do tempo |

**Threshold de aprovação**: Score médio >= 3.0 em todos os critérios; nenhum critério com score 0.

## Frameworks Complementares

- **Minute-by-Minute Analysis Framework** — Base para a análise temporal (WF02)
- **Call Scoring Model** — Base para o scoring de 10 blocos (WF04)
- **Rewrite the Moment** — Base para os rewrites de coaching (WF05)
- **Win-Loss Pattern Mining** — Alimentado pelo output consolidado

## Erros Comuns

1. **Relatório Frankenstein** — Colar outputs dos workflows sem unificar narrativa. O relatório deve ter voz única.
2. **Contradições não resolvidas** — Agentes divergem e ambas versões ficam no relatório sem arbitragem.
3. **Excesso de detalhes** — Incluir toda a análise minuto a minuto no relatório executivo. O executivo deve ter os highlights; detalhes ficam em anexo.
4. **Rewrites desconectados** — Rewrites que não correspondem aos momentos críticos identificados.
5. **Recomendações genéricas** — "Melhorar discovery" em vez de "No minuto 5, usar 2 perguntas de implicação após identificar a dor".
