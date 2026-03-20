# 11 — Weekly Sales Quality Review

> Review semanal consolidado de qualidade de vendas do time com métricas, padrões e ações.

## Objetivo

Produzir relatório semanal que consolida todas as auditorias, scores, padrões de vitória e derrota, e indicadores de qualidade do time de vendas, fornecendo ao gestor uma visão clara do estado atual e das ações prioritárias para a próxima semana.

## Quando Executar

- Toda sexta-feira (ou último dia útil da semana).
- Pode ser antecipado se houver situação crítica identificada durante a semana.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| sales-chief | Responsável principal pela consolidação, análise e produção do relatório |
| scorecard-analyst | Fornece dados agregados de scoring da semana |
| win-loss-miner | Fornece padrões de vitória e derrota da semana |

## Frameworks Utilizados

- weekly-review-protocol
- performance-trend-analysis

## Checklists Obrigatórios

- weekly-review-completeness
- data-accuracy-verification

## Etapas

### Etapa 1 — Coleta de Dados da Semana
**Responsável**: sales-chief
**Input**: Registries atualizados ao longo da semana (auditorias, scores, padrões)
**Ação**:
1. Coletar do closer-score-registry todos os scores da semana.
2. Coletar do audit-registry todas as auditorias realizadas.
3. Coletar do win-pattern-registry e loss-pattern-registry novos padrões da semana.
4. Coletar do coaching-log-registry sessões de coaching realizadas.
5. Levantar métricas brutas: calls realizadas, calls auditadas, taxa de conversão, ticket médio.
6. Verificar se algum closer ficou sem auditoria na semana.
**Output**: Dataset consolidado da semana.
**Quality Gate**: data-accuracy-verification (dados cruzados entre registries, sem inconsistências).

### Etapa 2 — Análise de Performance Individual
**Responsável**: scorecard-analyst
**Input**: Scores da semana + histórico de cada closer
**Ação**:
1. Calcular score médio de cada closer na semana.
2. Comparar com média das últimas 4 semanas (tendência).
3. Identificar closers em ascensão (melhoria consistente) e em declínio (piora consistente).
4. Identificar blocos de scoring com maior variação (positiva e negativa) por closer.
5. Produzir ranking semanal do time por score médio.
**Output**: Dashboard de performance individual com tendências.
**Quality Gate**: Tendências calculadas com base em pelo menos 2 calls por closer.

### Etapa 3 — Análise de Padrões do Time
**Responsável**: win-loss-miner
**Input**: Padrões extraídos na semana + banco histórico
**Ação**:
1. Consolidar padrões de vitória mais frequentes da semana.
2. Consolidar padrões de perda mais frequentes da semana.
3. Identificar padrões novos que surgiram pela primeira vez.
4. Calcular distribuição de causas raiz das perdas da semana.
5. Destacar o padrão mais relevante da semana (maior impacto ou maior frequência).
**Output**: Resumo de padrões da semana com destaques.
**Quality Gate**: Padrões consolidados com frequência; destaque semanal justificado.

### Etapa 4 — Compilação do Relatório Semanal
**Responsável**: sales-chief
**Input**: Dashboard individual + padrões do time + métricas brutas
**Ação**:
1. Compilar relatório no formato executive-sales-intelligence-report:
   - **Resumo Executivo**: 3-5 bullet points com os destaques da semana.
   - **Métricas da Semana**: Calls, auditorias, conversão, ticket médio, score médio do time.
   - **Ranking de Closers**: Performance individual com tendência.
   - **Padrão da Semana**: O insight mais importante extraído das análises.
   - **Top 3 Wins**: Melhores momentos da semana (com closer e citação).
   - **Top 3 Alertas**: Problemas mais urgentes que demandam ação.
   - **Ações da Próxima Semana**: Coaching planejado, treinamentos, ajustes de processo.
2. Incluir comparativo com semana anterior (deltas).
3. Adicionar parecer qualitativo do sales-chief sobre a saúde do time.
**Output**: Relatório semanal completo.
**Quality Gate**: weekly-review-completeness (todas as seções preenchidas, dados verificados).

### Etapa 5 — Distribuição e Planejamento
**Responsável**: sales-chief
**Input**: Relatório semanal finalizado
**Ação**:
1. Publicar relatório para gestores e C-level.
2. Preparar versão condensada para compartilhar com o time de closers.
3. Definir plano de ação da próxima semana com base nos alertas e recomendações.
4. Agendar sessões de coaching prioritárias.
5. Registrar no weekly-review-registry para histórico e comparação futura.
**Output**: Relatório distribuído + plano de ação definido.
**Quality Gate**: Plano de ação com responsáveis e prazos definidos.

## Templates de Output

- executive-sales-intelligence-report (relatório semanal completo)
- weekly-team-summary (versão condensada para closers)

## Registries Atualizados

- weekly-review-registry (relatório da semana registrado)
- action-plan-registry (ações da próxima semana registradas)

## Critérios de Conclusão

- [ ] Dados da semana coletados e verificados de todos os registries
- [ ] Performance individual analisada com tendências de 4 semanas
- [ ] Padrões de vitória e derrota da semana consolidados
- [ ] Relatório semanal compilado com todas as seções
- [ ] Plano de ação da próxima semana definido com responsáveis e prazos
- [ ] Relatório distribuído para gestores e time

## Próximo Workflow

→ 12-monthly-closer-certification.md (alimenta dados para certificação mensal)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | data-accuracy-verification | Dados cruzados entre registries sem inconsistências; nenhum closer sem auditoria | Voltar a Etapa 1 para recoleta |
| Etapa 2 → Etapa 3 | Tendências calculadas | Pelo menos 2 calls por closer para base de tendência | Voltar a Etapa 1 para incluir calls faltantes |
| Etapa 3 → Etapa 4 | Padrões consolidados | Frequência calculada e destaque semanal justificado | Voltar a Etapa 3 para revalidar padrões |
| Etapa 4 → Etapa 5 | weekly-review-completeness | Todas as seções do relatório preenchidas e dados verificados | Voltar a Etapa 4 para completar seções |
| Etapa 5 → Conclusão | Plano de ação completo | Responsáveis e prazos definidos para cada ação | Voltar a Etapa 5 para detalhar plano |

## Decision Points
- Após Etapa 1: se todos os registries estão completos → prosseguir; se há closer sem auditoria na semana → sinalizar gap e decidir se inclui dados parciais ou solicita auditoria emergencial
- Após Etapa 2: se closer apresenta declínio consistente por 3+ semanas → acionar coaching prioritário imediato; se performance estável → seguir fluxo normal
- Após Etapa 4: se relatório revela situação crítica (queda abrupta de conversão ou score) → antecipar publicação e convocar reunião emergencial

## Escalation Triggers
- Se taxa de conversão do time cai mais de 20% vs. semana anterior → pausar, escalar para sales-chief para análise de causa raiz imediata
- Se mais de 50% dos closers ficaram sem auditoria na semana → pausar, escalar para sales-chief para revisão de capacidade do squad
- Se dados entre registries apresentam inconsistências graves → pausar, escalar para scorecard-analyst para reconciliação antes de prosseguir
