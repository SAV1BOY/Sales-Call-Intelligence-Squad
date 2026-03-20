# 04 — Scoring and Root Cause

> Pontuar a call em 10 blocos (total 100 pontos) e identificar a causa raiz do resultado obtido.

## Objetivo

Aplicar o modelo de scoring padronizado em 10 blocos de competência, gerar pontuação final da call (0-100) e realizar diagnóstico de causa raiz que explique por que a call teve o resultado que teve (fechou, perdeu, follow-up).

## Quando Executar

- Após conclusão dos workflows 02 e 03 (análise minuto a minuto + detecção de frameworks).
- Como parte do workflow 06 (Full Funnel Call Audit).
- Quando solicitada avaliação de performance de um closer.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| scorecard-analyst | Executa a pontuação dos 10 blocos com base nas evidências coletadas |
| deal-risk-doctor | Realiza análise de causa raiz do resultado da call |

## Frameworks Utilizados

- call-scoring-model (10 blocos x 10 pontos = 100 pontos)
- deal-risk-diagnosis (para análise de causa raiz)
- root-cause-analysis-protocol

## Checklists Obrigatórios

- scoring-consistency-checklist
- root-cause-evidence-checklist

## Etapas

### Etapa 1 — Coleta de Evidências para Scoring
**Responsável**: scorecard-analyst
**Input**: Relatório minuto a minuto (workflow 02) + relatório de frameworks (workflow 03) + transcrição segmentada
**Ação**:
1. Consolidar todas as evidências disponíveis dos workflows anteriores.
2. Organizar evidências por bloco de scoring:
   - Bloco 1: Abertura e Rapport (conexão inicial, postura, tom)
   - Bloco 2: Diagnóstico e Descoberta (qualidade das perguntas, profundidade)
   - Bloco 3: Amplificação da Dor (implicação, consequência, urgência)
   - Bloco 4: Apresentação da Solução (clareza, conexão com dor, mecanismo)
   - Bloco 5: Prova Social e Autoridade (cases, resultados, credibilidade)
   - Bloco 6: Ancoragem de Valor e Preço (stack, contraste, ROI)
   - Bloco 7: Tratamento de Objeções (isolamento, reframe, resolução)
   - Bloco 8: Controle de Frame (liderança, postura consultiva, autoridade)
   - Bloco 9: Close e Decisão (timing, técnica, assertividade)
   - Bloco 10: Próximos Passos e Follow-up (clareza, compromisso, handoff)
3. Para cada bloco, selecionar 2-3 evidências mais relevantes.
**Output**: Dossiê de evidências organizado por bloco.
**Quality Gate**: Cada bloco tem pelo menos 1 evidência; evidências são citações diretas com timestamp.

### Etapa 2 — Pontuação dos 10 Blocos
**Responsável**: scorecard-analyst
**Input**: Dossiê de evidências
**Ação**:
1. Para cada bloco (0-10 pontos), avaliar com base nas evidências:
   - 0-2: Ausente ou gravemente deficiente.
   - 3-4: Tentou mas executou mal.
   - 5-6: Execução mediana, com falhas significativas.
   - 7-8: Boa execução com oportunidades de melhoria.
   - 9-10: Execução excelente, referência de best practice.
2. Justificar cada nota com evidência textual específica.
3. Identificar o bloco com maior gap entre potencial e execução.
4. Calcular score total (soma dos 10 blocos).
5. Classificar a call: Elite (85+), Forte (70-84), Mediana (55-69), Fraca (40-54), Crítica (<40).
**Output**: Scorecard completo com 10 notas justificadas + score total + classificação.
**Quality Gate**: scoring-consistency-checklist (notas justificadas, sem viés, evidências citadas).

### Etapa 3 — Análise de Causa Raiz
**Responsável**: deal-risk-doctor
**Input**: Scorecard + transcrição segmentada + resultado da call
**Ação**:
1. Se a call foi perdida: identificar os 1-3 fatores primários que causaram a perda.
2. Se a call foi ganha: identificar os 1-3 fatores que mais contribuíram para o fechamento.
3. Aplicar análise dos 5 Porquês para chegar à causa raiz verdadeira.
4. Classificar a causa raiz em categorias:
   - Técnica do closer (skill gap)
   - Qualidade do lead (fit inadequado)
   - Mismatch de oferta (produto não atende)
   - Fatores externos (timing, orçamento, decisor ausente)
   - Processo (handoff ruim, follow-up falho)
5. Avaliar se a causa raiz era controlável pelo closer ou não.
**Output**: Diagnóstico de causa raiz com classificação e controlabilidade.
**Quality Gate**: root-cause-evidence-checklist (causa raiz apoiada por evidências, 5 Porquês documentados).

### Etapa 4 — Recomendações Priorizadas
**Responsável**: scorecard-analyst + deal-risk-doctor
**Input**: Scorecard + causa raiz
**Ação**:
1. Gerar top 3 recomendações de melhoria para o closer baseadas nos blocos mais fracos.
2. Para cada recomendação, especificar: o que treinar, framework sugerido, exemplo prático.
3. Identificar se a causa raiz demanda ação do closer, do gestor ou de outro squad.
4. Estimar impacto potencial no score se as recomendações forem implementadas.
**Output**: Lista de recomendações priorizadas com estimativa de impacto.
**Quality Gate**: Recomendações são específicas, acionáveis e ligadas a evidências do scorecard.

### Etapa 5 — Compilação e Registro
**Responsável**: scorecard-analyst
**Input**: Scorecard + causa raiz + recomendações
**Ação**:
1. Compilar relatório final de scoring e causa raiz.
2. Registrar score no registry do closer (histórico de scores).
3. Atualizar métricas agregadas do time.
4. Disponibilizar para workflow 05 (coaching e rewrite) e workflow 06 (audit completo).
**Output**: Relatório final publicado + registries atualizados.
**Quality Gate**: Score registrado, causa raiz documentada, dados disponíveis para downstream.

## Templates de Output

- call-scorecard-report (10 blocos + score total + causa raiz)

## Registries Atualizados

- closer-score-registry (score da call adicionado ao histórico)
- root-cause-registry (causa raiz categorizada e registrada)
- team-metrics-registry (métricas agregadas atualizadas)

## Critérios de Conclusão

- [ ] 10 blocos pontuados com evidência textual para cada nota
- [ ] Score total calculado e classificação atribuída
- [ ] Causa raiz identificada com análise dos 5 Porquês
- [ ] Causa raiz classificada por categoria e controlabilidade
- [ ] Top 3 recomendações priorizadas com estimativa de impacto
- [ ] Score registrado no histórico do closer

## Próximo Workflow

→ 05-coaching-rewrite-loop.md (reescrita de momentos críticos com before/after)
