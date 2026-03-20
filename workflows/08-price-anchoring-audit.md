# 08 — Price Anchoring Audit

> Auditoria completa da estratégia de ancoragem de valor e apresentação de preço na call.

## Objetivo

Avaliar como o closer construiu (ou não) a percepção de valor antes de revelar o preço, analisar a qualidade da ancoragem, o timing da apresentação do investimento e a eficácia do stack de valor, produzindo recomendações de melhoria baseadas em frameworks de precificação high-ticket.

## Quando Executar

- Quando o scorecard (workflow 04) indica nota baixa no Bloco 6 (Ancoragem de Valor e Preço).
- Quando a objeção principal da call foi preço/investimento (workflow 07).
- Como parte da certificação mensal de closers (workflow 12).
- Quando há queda na taxa de conversão e suspeita de problema na apresentação de preço.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| pricing-anchoring-analyst | Responsável principal pela auditoria de ancoragem e análise de valor |
| scorecard-analyst | Fornece contexto do score geral e do bloco de preço |

## Frameworks Utilizados

- price-anchoring-framework (âncora alta → stack → contraste → investimento)
- value-equation-model (valor percebido = resultado esperado + probabilidade / tempo + esforço + risco)
- hormozi-value-stack

## Checklists Obrigatórios

- price-anchoring-audit-checklist
- value-equation-completeness

## Etapas

### Etapa 1 — Mapeamento da Jornada de Valor na Call
**Responsável**: pricing-anchoring-analyst
**Input**: Transcrição segmentada + fases da call identificadas
**Ação**:
1. Identificar todos os momentos onde valor foi construído (ou deveria ter sido) ao longo da call.
2. Mapear a sequência de construção de valor:
   - Quando o closer quantificou a dor em reais/tempo/oportunidade perdida?
   - Quando apresentou resultados de clientes similares?
   - Quando construiu o stack de valor (bônus, garantias, suporte)?
   - Quando revelou o preço?
3. Registrar timestamp e trecho exato de cada momento de construção de valor.
4. Identificar gaps na jornada de valor (momentos onde a construção deveria ter ocorrido mas não ocorreu).
**Output**: Mapa da jornada de valor com gaps identificados.
**Quality Gate**: Todos os momentos de valor mapeados cronologicamente; gaps documentados.

### Etapa 2 — Avaliação da Value Equation
**Responsável**: pricing-anchoring-analyst
**Input**: Mapa da jornada de valor + transcrição
**Ação**:
1. Avaliar cada componente da value equation:
   - **Resultado Esperado**: O closer pintou um futuro desejado claro e específico? (1-10)
   - **Probabilidade Percebida**: O closer construiu confiança de que o resultado será alcançado? (1-10)
   - **Tempo para Resultado**: O closer reduziu a percepção de tempo até o resultado? (1-10)
   - **Esforço Requerido**: O closer minimizou a percepção de esforço? (1-10)
   - **Risco Percebido**: O closer reduziu o risco com garantias e social proof? (1-10)
2. Calcular score da value equation: (Resultado × Probabilidade) / (Tempo × Esforço × Risco).
3. Identificar o componente mais fraco e seu impacto na percepção de preço.
**Output**: Score detalhado da value equation com componente mais fraco identificado.
**Quality Gate**: value-equation-completeness (todos os 5 componentes avaliados com evidências).

### Etapa 3 — Análise da Ancoragem de Preço
**Responsável**: pricing-anchoring-analyst
**Input**: Transcrição (fase de preço) + mapa de valor
**Ação**:
1. Avaliar a técnica de ancoragem utilizada:
   - Âncora alta estabelecida antes do preço real? (Sim/Não — com que valor?)
   - Contraste utilizado (preço vs. custo de não agir)? (Sim/Não)
   - Stack de valor construído antes de revelar investimento? (Sim/Não)
   - Preço apresentado como investimento ou como custo? (Investimento/Custo)
2. Avaliar o timing da revelação do preço:
   - Preço revelado após construção suficiente de valor? (Sim/Não)
   - Lead pediu o preço antes do closer estar pronto? (Sim/Não — como reagiu?)
3. Avaliar a reação do lead ao preço e a resposta do closer.
4. Comparar com a sequência ideal do framework de ancoragem.
**Output**: Análise detalhada da ancoragem com gaps e oportunidades.
**Quality Gate**: Cada elemento de ancoragem avaliado; sequência comparada com framework ideal.

### Etapa 4 — Benchmarking e Recomendações
**Responsável**: pricing-anchoring-analyst
**Input**: Análise completa de valor e ancoragem
**Ação**:
1. Comparar a performance de ancoragem com benchmarks de calls ganhas.
2. Identificar os 3 maiores gaps na construção de valor e ancoragem.
3. Para cada gap, produzir recomendação específica com script sugerido.
4. Calcular estimativa de melhoria no close rate se os gaps forem corrigidos.
5. Produzir checklist personalizado de ancoragem para o closer.
**Output**: Relatório de benchmarking + recomendações + checklist personalizado.
**Quality Gate**: Recomendações são específicas e incluem scripts executáveis.

### Etapa 5 — Compilação e Registro
**Responsável**: pricing-anchoring-analyst
**Input**: Análise completa de ancoragem
**Ação**:
1. Compilar relatório final de auditoria de ancoragem.
2. Registrar findings no closer-pricing-registry.
3. Disponibilizar para workflows de coaching (05) e certificação (12).
4. Sinalizar se o problema de preço é do closer ou da oferta (para workflow 16).
**Output**: Relatório publicado + registries atualizados.
**Quality Gate**: price-anchoring-audit-checklist 100% aprovado.

## Templates de Output

- price-anchoring-audit-report (value equation + ancoragem + recomendações)

## Registries Atualizados

- closer-pricing-registry (performance de ancoragem por closer)
- offer-fit-registry (sinalização se problema é da oferta)

## Critérios de Conclusão

- [ ] Jornada de valor mapeada cronologicamente com gaps
- [ ] Value equation avaliada nos 5 componentes com evidências
- [ ] Técnica e timing de ancoragem analisados contra framework ideal
- [ ] Top 3 gaps identificados com scripts de melhoria
- [ ] Relatório compilado e registries atualizados

## Próximo Workflow

→ 05-coaching-rewrite-loop.md (para reescrita dos momentos de preço) ou 16-closer-to-offer-feedback.md (se problema for da oferta)
