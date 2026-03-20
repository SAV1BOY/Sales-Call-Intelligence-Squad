# 15 — Closer to Traffic Feedback

> Insights das calls para o Traffic Squad sobre qualidade do lead por origem e canal.

## Objetivo

Analisar a qualidade dos leads que chegam às calls segmentando por origem de tráfego (canal, campanha, criativo), correlacionar qualidade do lead com taxa de conversão e ticket, e produzir feedback acionável para o Traffic Squad otimizar alocação de budget e segmentação.

## Quando Executar

- Quinzenalmente ou mensalmente, consolidando dados de múltiplas calls.
- Quando uma fonte de leads apresenta taxa de conversão significativamente abaixo da média.
- Quando novo canal de aquisição é testado e precisa de feedback de qualidade.
- Quando há mudança significativa no perfil de leads chegando às calls.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| revenue-intelligence-analyst | Responsável pela análise de qualidade por origem e produção do feedback |
| sales-chief | Valida conclusões e prioriza recomendações |

## Frameworks Utilizados

- lead-source-quality-analysis
- traffic-to-close-funnel-mapping
- lead-scoring-by-origin

## Checklists Obrigatórios

- cross-squad-feedback-quality
- data-sample-size-validation

## Etapas

### Etapa 1 — Segmentação de Calls por Origem
**Responsável**: revenue-intelligence-analyst
**Input**: Call-log-registry com metadados de origem + auditorias do período
**Ação**:
1. Agrupar calls por origem de tráfego: Google Ads, Meta Ads, orgânico, indicação, SDR outbound, webinar, etc.
2. Para cada grupo, calcular: número de calls, taxa de conversão, ticket médio, score médio.
3. Identificar origens com amostra suficiente para análise (mínimo 5 calls).
4. Registrar origens com amostra insuficiente para acumulação futura.
**Output**: Calls segmentadas por origem com métricas básicas por grupo.
**Quality Gate**: data-sample-size-validation (amostra mínima por origem respeitada).

### Etapa 2 — Análise de Qualidade do Lead por Origem
**Responsável**: revenue-intelligence-analyst
**Input**: Calls segmentadas + transcrições + relatórios de auditoria
**Ação**:
1. Para cada origem com amostra suficiente, avaliar qualidade do lead:
   - **Fit de perfil**: O lead tem o perfil ideal para o produto? (1-5)
   - **Nível de consciência**: O lead já entende o problema e a solução? (1-5)
   - **Urgência**: O lead tem urgência real para resolver? (1-5)
   - **Capacidade de investimento**: O lead tem budget compatível? (1-5)
   - **Autoridade de decisão**: O lead pode decidir sozinho? (1-5)
2. Calcular score de qualidade médio por origem.
3. Identificar padrões qualitativos por origem (ex: leads de Meta têm urgência baixa, leads de Google têm fit alto).
4. Extrair citações representativas de leads de cada origem.
**Output**: Score de qualidade por origem + padrões qualitativos.
**Quality Gate**: Score baseado em múltiplos critérios; padrões apoiados por evidência.

### Etapa 3 — Análise de ROI por Origem
**Responsável**: revenue-intelligence-analyst
**Input**: Métricas por origem + dados de conversão e ticket
**Ação**:
1. Calcular para cada origem:
   - Taxa de conversão (calls → vendas).
   - Ticket médio dos fechamentos.
   - Revenue total por origem no período.
   - Score médio das calls por origem.
2. Ranquear origens por eficiência (conversão × ticket).
3. Identificar origens com alto volume mas baixa conversão (oportunidade de otimização).
4. Identificar origens com alta conversão mas baixo volume (oportunidade de escala).
5. Calcular "custo do lead ruim": tempo do closer gasto em calls improdutivas por origem.
**Output**: Análise de ROI por origem com ranking de eficiência.
**Quality Gate**: ROI calculado com dados verificados; ranking consistente com métricas.

### Etapa 4 — Produção do Feedback para Traffic Squad
**Responsável**: revenue-intelligence-analyst
**Input**: Qualidade por origem + ROI + padrões qualitativos
**Ação**:
1. Compilar relatório para Traffic Squad:
   - **Ranking de Origens**: Da mais eficiente à menos eficiente.
   - **Perfil Ideal por Origem**: Quais leads de cada origem convertem melhor.
   - **Alertas**: Origens com qualidade em declínio ou perfil incompatível.
   - **Oportunidades**: Origens subexploradas com bom potencial.
   - **Recomendações de Segmentação**: Ajustes sugeridos em targeting.
   - **Custo de Ineficiência**: Tempo/recurso desperdiçado com leads ruins por origem.
2. Incluir citações de leads para ilustrar perfil típico de cada origem.
3. Manter foco em dados acionáveis para otimização de tráfego.
**Output**: Relatório de feedback para Traffic Squad.
**Quality Gate**: cross-squad-feedback-quality (dados verificados, recomendações acionáveis).

### Etapa 5 — Validação, Entrega e Registro
**Responsável**: sales-chief
**Input**: Relatório de feedback
**Ação**:
1. Validar que as conclusões são robustas (amostra suficiente, correlações significativas).
2. Aprovar recomendações de realocação de budget (se aplicável).
3. Entregar feedback ao líder de Traffic Squad.
4. Registrar no cross-squad-feedback-registry.
5. Definir métricas de acompanhamento para o próximo período.
**Output**: Feedback entregue + registry atualizado.
**Quality Gate**: Sales-chief aprovou; métricas de follow-up definidas.

## Templates de Output

- traffic-intelligence-report (qualidade por origem + ROI + recomendações)

## Registries Atualizados

- cross-squad-feedback-registry (feedback para Traffic registrado)
- lead-quality-registry (scores por origem atualizados)

## Critérios de Conclusão

- [ ] Calls segmentadas por origem com amostra validada
- [ ] Qualidade do lead avaliada por origem nos 5 critérios
- [ ] ROI por origem calculado com ranking de eficiência
- [ ] Relatório para Traffic Squad compilado com recomendações
- [ ] Feedback validado e entregue com métricas de acompanhamento

## Próximo Workflow

→ 16-closer-to-offer-feedback.md (insights sobre fit da oferta)
