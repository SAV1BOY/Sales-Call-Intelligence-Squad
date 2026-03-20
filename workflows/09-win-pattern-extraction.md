# 09 — Win Pattern Extraction

> Extrair padrões de vitória de calls ganhas para replicação sistemática pelo time.

## Objetivo

Analisar calls que resultaram em fechamento para identificar padrões replicáveis: técnicas que funcionaram, sequências eficazes, frases de impacto, momentos de virada e condições contextuais que favoreceram o close. Produzir um banco de padrões de vitória consultável.

## Quando Executar

- Após auditoria completa (workflow 06) de uma call ganha.
- Quando um closer apresenta taxa de conversão acima da média e precisa ser estudado.
- Mensalmente, como parte da análise de padrões do time (workflow 11).
- Quando um novo produto/oferta está em fase inicial e precisa-se identificar o que funciona.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| win-loss-miner | Responsável principal pela mineração e catalogação de padrões de vitória |
| sales-chief | Valida relevância e replicabilidade dos padrões extraídos |

## Frameworks Utilizados

- win-loss-pattern-mining
- replicability-assessment-model (contexto-dependente vs. universalmente replicável)

## Checklists Obrigatórios

- win-pattern-extraction-quality
- evidence-citation-standards

## Etapas

### Etapa 1 — Seleção e Contextualização de Calls Ganhas
**Responsável**: win-loss-miner
**Input**: Auditorias completas de calls ganhas (workflow 06)
**Ação**:
1. Selecionar calls para análise (individual ou batch).
2. Registrar contexto de cada call: tipo de lead, produto, ticket, closer, ciclo de venda.
3. Identificar calls "normais" vs. calls "outlier" (fechamento inesperado, ticket acima da média).
4. Priorizar calls outlier para análise mais profunda (há algo excepcional a aprender).
**Output**: Lista de calls selecionadas com contexto e priorização.
**Quality Gate**: Contexto completo registrado para cada call; outliers identificados.

### Etapa 2 — Mineração de Padrões de Vitória
**Responsável**: win-loss-miner
**Input**: Transcrições segmentadas + relatórios de auditoria das calls selecionadas
**Ação**:
1. Para cada call ganha, identificar e catalogar:
   - **Frases de Impacto**: Falas do closer que geraram reação positiva visível no lead.
   - **Sequências Eficazes**: Ordem de ações que levou a progressão (ex: diagnóstico profundo → amplificação → solução just-in-time).
   - **Momentos de Virada**: O instante onde o lead passou de indeciso para decidido.
   - **Técnicas Bem Executadas**: Frameworks aplicados com excelência e seu resultado.
   - **Perguntas Poderosas**: Perguntas que abriram o lead ou geraram insight.
   - **Tratamento de Objeção Eficaz**: Objeções que foram resolvidas e como.
2. Para cada padrão, registrar evidência textual com timestamp.
3. Marcar se o padrão parece contexto-dependente ou universalmente replicável.
**Output**: Catálogo de padrões de vitória com evidências.
**Quality Gate**: Cada padrão tem evidência textual; replicabilidade avaliada.

### Etapa 3 — Cross-Reference e Validação de Recorrência
**Responsável**: win-loss-miner
**Input**: Catálogo da call atual + banco de padrões históricos
**Ação**:
1. Cruzar padrões encontrados com o banco histórico de padrões de vitória.
2. Identificar padrões recorrentes (aparecem em múltiplas calls ganhas).
3. Calcular frequência e correlação com fechamento para cada padrão.
4. Separar padrões novos (primeira ocorrência) de padrões validados (recorrentes).
5. Atualizar score de confiança dos padrões existentes.
**Output**: Padrões validados com score de recorrência + novos padrões candidatos.
**Quality Gate**: Cross-reference feito com banco histórico; scores de confiança atualizados.

### Etapa 4 — Produção de Playbook de Replicação
**Responsável**: win-loss-miner + sales-chief
**Input**: Padrões validados
**Ação**:
1. Selecionar top 5 padrões mais replicáveis e de maior impacto.
2. Para cada padrão, produzir ficha de replicação:
   - Nome do padrão e descrição em 1 linha.
   - Quando usar (contexto e condições ideais).
   - Como executar (passo a passo com script de referência).
   - Exemplo real (citação da call onde funcionou).
   - Armadilhas comuns (como não executar).
3. Validar com sales-chief que os padrões são recomendáveis para o time.
**Output**: Playbook de replicação com fichas dos top 5 padrões.
**Quality Gate**: Padrões validados pelo sales-chief; fichas completas e acionáveis.

### Etapa 5 — Registro e Distribuição
**Responsável**: win-loss-miner
**Input**: Playbook de replicação
**Ação**:
1. Adicionar novos padrões ao win-pattern-registry.
2. Atualizar scores de confiança dos padrões existentes.
3. Publicar playbook para consulta do time.
4. Sinalizar padrões que devem ser incorporados ao treinamento (workflow 12).
**Output**: Registry atualizado + playbook publicado.
**Quality Gate**: Padrões registrados com evidências e scores; playbook disponível.

## Templates de Output

- win-pattern-report (catálogo de padrões + fichas de replicação)

## Registries Atualizados

- win-pattern-registry (novos padrões adicionados, scores atualizados)
- best-practices-registry (padrões validados promovidos a best practice)

## Critérios de Conclusão

- [ ] Calls ganhas selecionadas e contextualizadas
- [ ] Padrões de vitória minerados com evidência textual
- [ ] Cross-reference com banco histórico realizado
- [ ] Top 5 padrões com fichas de replicação produzidas
- [ ] Registry atualizado e playbook publicado

## Próximo Workflow

→ 11-weekly-sales-quality-review.md (padrões alimentam review semanal)
