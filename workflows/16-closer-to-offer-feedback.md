# 16 — Closer to Offer Feedback

> Insights das calls para o time de Oferta/C-Level sobre mismatch entre oferta e mercado.

## Objetivo

Identificar e documentar evidências de desalinhamento entre a oferta atual e as necessidades reais do mercado, baseado no que os leads dizem nas calls. Produzir feedback estratégico para o time de produto/oferta e C-Level com recomendações de ajuste de posicionamento, pricing, componentes da oferta e garantias.

## Quando Executar

- Mensalmente, como consolidação de insights estratégicos.
- Quando múltiplas calls apresentam a mesma objeção relacionada à oferta (não ao closer).
- Quando taxa de conversão cai e a causa raiz é identificada como mismatch de oferta.
- Quando novo produto/oferta está em fase de validação de mercado.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| offer-fit-analyst | Responsável principal pela análise de fit oferta×mercado |
| sales-chief | Valida conclusões e endossa recomendações para C-Level |
| revenue-intelligence-analyst | Suporte na consolidação de dados cross-squad |

## Frameworks Utilizados

- offer-market-fit-analysis
- value-proposition-gap-model
- pricing-sensitivity-mapping

## Checklists Obrigatórios

- strategic-feedback-quality
- c-level-communication-standards

## Etapas

### Etapa 1 — Identificação de Sinais de Mismatch na Call
**Responsável**: offer-fit-analyst
**Input**: Transcrições segmentadas + relatórios de objeção (workflow 07) + root cause analysis (workflow 04)
**Ação**:
1. Filtrar calls onde a causa raiz da perda foi classificada como "mismatch de oferta".
2. Identificar sinais recorrentes de mismatch nas calls:
   - Lead demonstra interesse na transformação mas resiste à oferta específica.
   - Objeção de preço que persiste mesmo após ancoragem bem executada.
   - Lead menciona funcionalidade/componente que a oferta não tem.
   - Lead compara com concorrente e percebe desvantagem na oferta.
   - Lead quer resultado X mas a oferta promete resultado Y.
3. Extrair citações verbatim que evidenciam cada tipo de mismatch.
4. Separar problemas de oferta dos problemas de execução do closer.
**Output**: Inventário de sinais de mismatch com citações e classificação.
**Quality Gate**: Sinais baseados em múltiplas calls (não incidente isolado); separação clara de oferta vs. execução.

### Etapa 2 — Análise de Componentes da Oferta
**Responsável**: offer-fit-analyst
**Input**: Inventário de sinais + detalhes da oferta atual
**Ação**:
1. Avaliar cada componente da oferta contra o feedback das calls:
   - **Produto Core**: Resolve o problema que o lead tem? (fit alto/médio/baixo)
   - **Pricing**: Alinhado com a percepção de valor do mercado? (adequado/alto/baixo)
   - **Modelo de Entrega**: Formato preferido pelo lead? (alinhado/desalinhado)
   - **Garantias**: Suficientes para reduzir risco percebido? (adequadas/insuficientes)
   - **Bônus/Stack**: Percebidos como valiosos pelo lead? (valorizado/indiferente)
   - **Timeline de Resultado**: Compatível com urgência do lead? (alinhada/longa)
2. Mapear gaps entre o que o mercado quer e o que a oferta entrega.
3. Quantificar impacto de cada gap na conversão.
**Output**: Análise de componentes com gaps mapeados e impacto estimado.
**Quality Gate**: Cada componente avaliado com evidência de calls; impacto quantificado.

### Etapa 3 — Análise de Sensibilidade de Preço
**Responsável**: offer-fit-analyst
**Input**: Dados de calls com objeção de preço + resultados de ancoragem (workflow 08)
**Ação**:
1. Analisar em que faixa de preço os leads resistem mais.
2. Identificar se a resistência é de preço absoluto ou de valor percebido.
3. Avaliar se opções de parcelamento/condição alteram a dinâmica.
4. Comparar preço com referências que os leads mencionam (concorrentes, alternativas).
5. Produzir mapa de sensibilidade com zonas de conforto e resistência.
**Output**: Mapa de sensibilidade de preço com insights qualitativos.
**Quality Gate**: Análise baseada em amostra representativa; distinção entre preço e valor.

### Etapa 4 — Produção de Recomendações Estratégicas
**Responsável**: offer-fit-analyst + sales-chief
**Input**: Análise de componentes + sensibilidade de preço + inventário de mismatch
**Ação**:
1. Produzir recomendações estratégicas priorizadas:
   - Ajustes de posicionamento (como comunicar a oferta diferente).
   - Ajustes de componentes (o que adicionar, remover ou modificar).
   - Ajustes de pricing (repricing, tiers, condições especiais).
   - Ajustes de garantia (redução de risco percebido).
   - Novos segmentos (leads que convertem bem e não estão sendo targetados).
2. Para cada recomendação: evidência, impacto estimado, esforço de implementação.
3. Formatar para audiência C-Level (conciso, estratégico, orientado a resultado).
**Output**: Relatório estratégico com recomendações priorizadas.
**Quality Gate**: strategic-feedback-quality + c-level-communication-standards.

### Etapa 5 — Entrega e Registro
**Responsável**: sales-chief
**Input**: Relatório estratégico
**Ação**:
1. Revisar e endossar as recomendações.
2. Apresentar ao C-Level / time de oferta.
3. Registrar no strategic-feedback-registry.
4. Definir follow-up para avaliar implementação e impacto.
**Output**: Feedback estratégico entregue + registry atualizado.
**Quality Gate**: Apresentação feita; follow-up agendado.

## Templates de Output

- offer-fit-intelligence-report (mismatch + componentes + pricing + recomendações)

## Registries Atualizados

- strategic-feedback-registry (feedback para C-Level registrado)
- offer-fit-registry (análise de fit atualizada)

## Critérios de Conclusão

- [ ] Sinais de mismatch inventariados com citações de múltiplas calls
- [ ] Componentes da oferta avaliados contra feedback real do mercado
- [ ] Sensibilidade de preço mapeada com distinção preço vs. valor
- [ ] Recomendações estratégicas priorizadas para C-Level
- [ ] Feedback entregue com follow-up de implementação agendado

## Próximo Workflow

→ 20-ralphloop-sales-retro.md (insights alimentam retrospectiva e aprendizado contínuo)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | Sinais baseados em múltiplas calls | Mismatch evidenciado em 3+ calls; separação clara entre problema de oferta e problema de execução do closer | Voltar a Etapa 1 para ampliar amostra ou reclassificar sinais |
| Etapa 2 → Etapa 3 | Componentes avaliados com evidência | Cada componente da oferta avaliado contra feedback de calls; impacto quantificado | Voltar a Etapa 2 para preencher componentes não avaliados |
| Etapa 3 → Etapa 4 | Análise de preço representativa | Amostra representativa; distinção clara entre resistência de preço absoluto e valor percebido | Voltar a Etapa 3 para refinar análise com mais dados |
| Etapa 4 → Etapa 5 | strategic-feedback-quality + c-level-communication-standards | Recomendações priorizadas com evidência, impacto estimado e esforço de implementação | Voltar a Etapa 4 para reformatar para padrão C-Level |
| Etapa 5 → Conclusão | Apresentação feita e follow-up agendado | C-Level recebeu feedback; follow-up de implementação agendado | Voltar a Etapa 5 para completar entrega |

## Decision Points
- Após Etapa 1: se sinais indicam problema de execução do closer (não da oferta) → redirecionar para coaching (workflow 05) em vez de feedback de oferta; se confirmado como mismatch de oferta → prosseguir
- Após Etapa 3: se resistência é predominantemente de valor percebido (não preço absoluto) → focar recomendações em comunicação e posicionamento; se é preço absoluto → recomendar revisão de pricing ou criação de tiers
- Após Etapa 4: se recomendações envolvem mudança estrutural na oferta → preparar business case completo para C-Level; se são ajustes de posicionamento → seguir com relatório padrão

## Escalation Triggers
- Se mais de 50% das perdas no período têm causa raiz de mismatch de oferta → pausar, escalar para sales-chief para reunião emergencial com C-Level
- Se leads consistentemente mencionam concorrente como superior em aspecto crítico → pausar, escalar para sales-chief para análise competitiva urgente
- Se nova oferta em validação tem taxa de conversão abaixo de 5% após 2+ semanas → pausar, escalar para sales-chief para recomendar pivô ou pausa na oferta
