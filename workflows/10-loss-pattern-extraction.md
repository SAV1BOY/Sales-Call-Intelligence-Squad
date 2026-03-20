# 10 — Loss Pattern Extraction

> Extrair padrões de derrota de calls perdidas para prevenção sistemática.

## Objetivo

Analisar calls que resultaram em perda (não fechou, no-show em follow-up, desistência) para identificar padrões recorrentes de falha: erros técnicos repetidos, momentos onde a call descarrilou, objeções não resolvidas e fatores contextuais que contribuíram para a perda. Produzir mapa de riscos e alertas preventivos.

## Quando Executar

- Após auditoria completa (workflow 06) de uma call perdida.
- Quando a taxa de conversão do time ou de um closer específico cai abaixo do benchmark.
- Mensalmente, como parte da análise de padrões do time (workflow 11).
- Quando um padrão de perda suspeito é identificado (ex: todas as perdas envolvem a mesma objeção).

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| win-loss-miner | Responsável principal pela mineração e catalogação de padrões de perda |
| deal-risk-doctor | Análise de causa raiz e diagnóstico de riscos sistêmicos |
| sales-chief | Validação e decisão sobre ações corretivas estruturais |

## Frameworks Utilizados

- win-loss-pattern-mining (modo loss)
- deal-risk-diagnosis
- loss-taxonomy (classificação padronizada de tipos de perda)

## Checklists Obrigatórios

- loss-pattern-extraction-quality
- root-cause-evidence-checklist

## Etapas

### Etapa 1 — Contextualização das Calls Perdidas
**Responsável**: win-loss-miner
**Input**: Auditorias completas de calls perdidas (workflow 06)
**Ação**:
1. Selecionar calls para análise (individual ou batch de período).
2. Registrar contexto completo: closer, lead profile, produto, ticket, origem do lead, resultado específico (não fechou na call, pediu para pensar, ghostou, escolheu concorrente).
3. Classificar tipo de perda usando loss-taxonomy:
   - Perda por objeção não resolvida.
   - Perda por falta de urgência.
   - Perda por mismatch de oferta.
   - Perda por falha técnica do closer.
   - Perda por lead desqualificado (problema de upstream).
4. Identificar correlações iniciais (mesmo closer, mesmo produto, mesma origem).
**Output**: Calls classificadas por tipo de perda com contexto completo.
**Quality Gate**: Contexto completo para cada call; classificação inicial de tipo de perda.

### Etapa 2 — Mineração de Padrões de Falha
**Responsável**: win-loss-miner + deal-risk-doctor
**Input**: Calls classificadas + transcrições segmentadas + relatórios de auditoria
**Ação**:
1. Para cada call perdida, identificar e catalogar:
   - **Ponto de Ruptura**: O momento exato onde a call descarrilou.
   - **Erro Técnico Principal**: A falha mais impactante do closer.
   - **Objeção Fatal**: A objeção que não foi resolvida (se aplicável).
   - **Sinal Ignorado**: Sinais do lead que o closer não percebeu ou não reagiu.
   - **Framework Ausente**: Técnica que deveria ter sido aplicada e não foi.
   - **Fator Contextual**: Elementos fora do controle do closer que contribuíram.
2. Para cada padrão, registrar evidência textual com timestamp.
3. Classificar cada padrão como controlável ou não-controlável pelo closer.
**Output**: Catálogo de padrões de falha com evidências e classificação.
**Quality Gate**: Ponto de ruptura identificado para cada call; evidências textuais citadas.

### Etapa 3 — Análise de Recorrência e Correlação
**Responsável**: win-loss-miner
**Input**: Catálogo atual + banco histórico de padrões de perda
**Ação**:
1. Cruzar padrões com banco histórico para identificar recorrências.
2. Calcular frequência de cada padrão de perda no time e por closer.
3. Identificar correlações: padrão X aparece mais com closer Y, produto Z ou origem W.
4. Mapear tendências temporais: padrões que estão aumentando ou diminuindo.
5. Calcular custo estimado de cada padrão (deals perdidos x ticket médio).
**Output**: Análise de recorrência com correlações e custo estimado.
**Quality Gate**: Correlações apoiadas por dados; custo estimado calculado.

### Etapa 4 — Diagnóstico Sistêmico
**Responsável**: deal-risk-doctor + sales-chief
**Input**: Padrões recorrentes com correlações
**Ação**:
1. Separar problemas individuais (closer específico) de problemas sistêmicos (afeta todo o time).
2. Para problemas sistêmicos, identificar causa raiz estrutural:
   - Treinamento insuficiente em framework X.
   - Oferta com gap no componente Y.
   - Lead generation atraindo perfil inadequado.
   - Script/pitch com falha estrutural.
3. Priorizar problemas por impacto financeiro e frequência.
4. Definir se a solução é coaching (closer), processo (squad) ou estratégica (C-level).
**Output**: Diagnóstico sistêmico com priorização e nível de solução.
**Quality Gate**: Problemas sistêmicos vs. individuais separados; soluções no nível correto.

### Etapa 5 — Produção de Alertas e Recomendações
**Responsável**: win-loss-miner
**Input**: Diagnóstico completo
**Ação**:
1. Produzir mapa de riscos com top 5 padrões de perda mais custosos.
2. Para cada padrão, gerar alerta preventivo: sinais de que o padrão está se repetindo.
3. Criar recomendações acionáveis por nível (closer, squad, C-level).
4. Registrar no loss-pattern-registry com scores de frequência e impacto.
5. Disponibilizar para workflows 11 (review semanal), 17 (recuperação) e 14-16 (feedbacks cross-squad).
**Output**: Mapa de riscos + alertas preventivos + recomendações publicadas.
**Quality Gate**: loss-pattern-extraction-quality (evidências, frequências, recomendações acionáveis).

## Templates de Output

- loss-pattern-report (catálogo de padrões + mapa de riscos + recomendações)

## Registries Atualizados

- loss-pattern-registry (padrões de perda catalogados e atualizados)
- deal-risk-registry (riscos sistêmicos documentados)
- team-metrics-registry (custo de padrões de perda)

## Critérios de Conclusão

- [ ] Calls perdidas contextualizadas e classificadas por tipo de perda
- [ ] Padrões de falha minerados com ponto de ruptura e evidência textual
- [ ] Recorrência e correlações analisadas com custo estimado
- [ ] Diagnóstico sistêmico separando problemas individuais de estruturais
- [ ] Mapa de riscos e alertas preventivos publicados

## Próximo Workflow

→ 17-lost-deal-recovery.md (para tentativa de recuperação de deals perdidos)
→ 11-weekly-sales-quality-review.md (para consolidação no review semanal)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | Calls classificadas por tipo de perda | Contexto completo para cada call; classificação inicial por loss-taxonomy aplicada; correlações iniciais identificadas | Voltar a Etapa 1 (completar metadados ou revisar classificação de tipo de perda) |
| Etapa 2 → Etapa 3 | Catálogo de padrões de falha completo | Ponto de ruptura identificado para cada call; evidências textuais citadas; classificação controlável vs. não-controlável | Voltar a Etapa 2 (aprofundar mineração em calls sem ponto de ruptura claro) |
| Etapa 3 → Etapa 4 | Análise de recorrência concluída | Correlações apoiadas por dados; custo estimado calculado; tendências temporais mapeadas | Voltar a Etapa 3 (completar cruzamento com banco histórico ou recalcular custos) |
| Etapa 4 → Etapa 5 | Diagnóstico sistêmico validado | Problemas individuais separados de sistêmicos; causa raiz estrutural identificada; nível de solução definido | Voltar a Etapa 4 (revalidar separação individual vs. sistêmico com dados adicionais) |
| Etapa 5 → Conclusão | loss-pattern-extraction-quality | Mapa de riscos com top 5 padrões, alertas preventivos, recomendações acionáveis por nível (closer/squad/C-level) | Voltar a Etapa 5 (refinar alertas genéricos ou completar recomendações por nível) |

## Decision Points
- Após Etapa 1: se a maioria das perdas concentra-se em um tipo (ex: "objeção não resolvida") → aprofundar mineração nessa categoria na Etapa 2; se perdas são distribuídas entre vários tipos → analisar todas as categorias com profundidade uniforme
- Após Etapa 3: se padrão de perda correlaciona-se fortemente com um closer específico → direcionar para coaching individual (workflow 05); se correlaciona-se com um produto ou origem de lead → direcionar para feedback cross-squad (workflows 14-16)
- Após Etapa 4: se diagnóstico aponta problema sistêmico (treinamento, oferta, lead gen) → incluir recomendação de ação estrutural no relatório; se problema é exclusivamente individual → limitar recomendação a coaching

## Escalation Triggers
- Se custo estimado dos padrões de perda ultrapassa threshold definido pelo squad (ex: R$ 100k em deals perdidos no mês) → escalar para sales-chief para ação corretiva imediata
- Se padrão de perda indica lead generation atraindo perfil sistematicamente inadequado → escalar para sales-chief para feedback ao time de marketing/SDR
- Se 3+ closers apresentam o mesmo padrão de falha no mesmo período → escalar para sales-chief como problema de treinamento do time que demanda workshop emergencial
