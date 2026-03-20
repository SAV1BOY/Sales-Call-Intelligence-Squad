# 13 — SDR to Closer Feedback Loop

> Feedback estruturado do desempenho do handoff SDR→Closer baseado na análise das calls.

## Objetivo

Analisar a qualidade do handoff entre SDR e closer a partir das evidências encontradas nas calls auditadas, identificando gaps no agendamento, qualificação e preparação do lead, e produzindo feedback acionável para o time de SDRs melhorar a qualidade dos leads entregues.

## Quando Executar

- Semanalmente, como parte do review semanal (workflow 11).
- Quando múltiplas calls na semana apresentam problema de qualificação ou expectativa do lead.
- Quando um SDR específico tem alta taxa de no-show ou baixa conversão de seus leads agendados.
- Ao final de cada mês, como consolidação para o relatório mensal.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| sdr-handoff-analyst | Responsável principal pela análise de handoff e produção do feedback |
| sales-chief | Valida findings e prioriza recomendações |

## Frameworks Utilizados

- sdr-handoff-quality-model
- lead-qualification-criteria (BANT, SPIN adaptado para qualificação)
- expectation-alignment-protocol

## Checklists Obrigatórios

- handoff-audit-completeness
- feedback-objectivity-checklist

## Etapas

### Etapa 1 — Coleta de Evidências de Handoff nas Calls
**Responsável**: sdr-handoff-analyst
**Input**: Transcrições segmentadas do período + relatórios de auditoria
**Ação**:
1. Extrair de cada call auditada os primeiros 3-5 minutos (fase de rapport e abertura).
2. Identificar sinais de qualidade do handoff:
   - O lead sabia por que estava na call? (Expectativa alinhada/desalinhada)
   - O lead estava qualificado? (Budget, autoridade, necessidade, timing)
   - O lead tinha as informações corretas sobre o produto/oferta?
   - Houve "resumo" ou "recapitulação" do que foi discutido com o SDR?
3. Registrar citações do lead que revelam a qualidade do handoff (ex: "Não sei bem o que é isso", "A pessoa me disse que era gratuito").
4. Classificar qualidade do handoff: excelente, adequado, deficiente, prejudicial.
**Output**: Inventário de evidências de handoff por call com classificação.
**Quality Gate**: Primeiros minutos de cada call analisados; classificação justificada com citação.

### Etapa 2 — Análise de Padrões de Handoff
**Responsável**: sdr-handoff-analyst
**Input**: Inventário de evidências do período
**Ação**:
1. Consolidar classificações de handoff do período.
2. Calcular distribuição: % excelente, % adequado, % deficiente, % prejudicial.
3. Identificar padrões recorrentes de problema:
   - Expectativa inflada (SDR prometeu algo que não existe).
   - Qualificação insuficiente (lead sem budget/autoridade/necessidade).
   - Contexto não passado (closer não sabe nada sobre o lead).
   - Agendamento forçado (lead não tinha real interesse).
4. Correlacionar qualidade do handoff com resultado da call (conversão).
5. Se possível, mapear problemas por SDR específico.
**Output**: Análise de padrões com correlação handoff×conversão.
**Quality Gate**: Padrões documentados com frequência e correlação calculada.

### Etapa 3 — Produção do Feedback Estruturado
**Responsável**: sdr-handoff-analyst
**Input**: Análise de padrões
**Ação**:
1. Produzir feedback no formato sdr-handoff-audit-report:
   - **Score de Handoff do Período**: Nota geral (1-10) com justificativa.
   - **O que Está Funcionando**: Aspectos positivos do handoff com exemplos.
   - **O que Precisa Melhorar**: Gaps identificados com evidências das calls.
   - **Citações do Lead**: Frases exatas do lead que revelam o problema (anonimizadas se necessário).
   - **Recomendações**: Ações específicas para o time de SDRs.
   - **Impacto Estimado**: Como a melhoria do handoff impactaria a conversão.
2. Manter tom construtivo e baseado em dados (não acusatório).
3. Incluir exemplos de handoff excelente como referência positiva.
**Output**: Relatório de feedback estruturado para SDRs.
**Quality Gate**: feedback-objectivity-checklist (dados, não opiniões; construtivo; acionável).

### Etapa 4 — Validação e Entrega
**Responsável**: sales-chief
**Input**: Relatório de feedback
**Ação**:
1. Revisar feedback para garantir alinhamento com estratégia do time.
2. Priorizar recomendações (o que implementar primeiro).
3. Validar que o tom é apropriado para comunicação cross-squad.
4. Aprovar entrega do feedback ao líder de SDRs.
5. Definir follow-up: como medir se as recomendações foram implementadas.
**Output**: Feedback aprovado e entregue + métricas de follow-up definidas.
**Quality Gate**: Sales-chief aprovou; follow-up planejado.

### Etapa 5 — Registro e Acompanhamento
**Responsável**: sdr-handoff-analyst
**Input**: Feedback entregue
**Ação**:
1. Registrar feedback no handoff-feedback-registry.
2. Criar baseline de métricas para medir impacto das recomendações.
3. Agendar reavaliação para o próximo período.
4. Atualizar critérios de qualificação se necessário.
**Output**: Registry atualizado + baseline de métricas.
**Quality Gate**: Registro completo; reavaliação agendada.

## Templates de Output

- sdr-handoff-audit-report (relatório completo de handoff)

## Registries Atualizados

- handoff-feedback-registry (feedback registrado com data e status)
- lead-quality-registry (métricas de qualidade por origem/SDR)

## Critérios de Conclusão

- [ ] Evidências de handoff extraídas de todas as calls do período
- [ ] Padrões de problema identificados com frequência e correlação
- [ ] Feedback estruturado produzido com citações e recomendações
- [ ] Feedback validado pelo sales-chief e entregue ao líder de SDRs
- [ ] Baseline de métricas criado para acompanhamento

## Próximo Workflow

→ 14-closer-to-copy-feedback.md (insights cross-squad para Copy)
