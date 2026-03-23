# Guia de Integração Cross-Squad

> Como o Sales Call Intelligence Squad se conecta com outros squads: Copy, Traffic, Brand, Storytelling, C-Level, Data, Movement e Advisory.

## Princípio de Integração

O Sales Call Intelligence Squad não opera isolado. Cada insight gerado pela auditoria de calls pode alimentar decisões em outros squads, e cada squad pode fornecer contexto que enriquece a análise das calls.

## Integração com Copy Squad

### O que Compartilhamos
- Objeções mais frequentes → Copy cria conteúdo que resolve objeções antes da call
- Linguagem do prospect → Copy adapta headlines e copies para espelhar vocabulário real
- Dores verbalizadas → Copy usa dores exatas em anúncios e páginas

### O que Recebemos
- Promessas feitas no copy → Auditamos se o closer entrega na call o que o copy prometeu
- Ângulos de campanha → Contextualizamos a auditoria com base na campanha que gerou o lead

### Contrato de Handoff
| Campo | Detalhe |
|-------|---------|
| Trigger | Nova análise de objeções frequentes ou dores verbalizadas consolidada após ciclo de auditorias |
| Owner | sales-chief |
| Template | `templates/operational/cross-squad-handoff-template.md` |
| SLA | 72h acknowledgment (standard) |
| Quality Gate de Saída | Objeções categorizadas com frequência, linguagem exata do prospect documentada, dores verbalizadas com contexto de call |
| Quality Gate de Retorno | Promessas de copy mapeadas para blocos de auditoria, ângulos de campanha com período de veiculação definido |
| Registro | `data/handoffs/handoffs-registry.yaml` |
| Escalation | Se SLA ultrapassado → sales-chief escala para chief do squad receptor |

## Integração com Traffic Squad

### O que Compartilhamos
- Qualidade dos leads por canal → Quais fontes geram leads mais qualificados nas calls
- Taxa de no-show por origem → Quais campanhas geram leads que comparecem
- Tempo médio de call por fonte → Quanto tempo cada tipo de lead precisa

### O que Recebemos
- Volume e origem dos leads → Planejamento de capacidade de auditoria
- Mudanças em campanhas → Antecipação de mudanças no perfil de leads

### Contrato de Handoff
| Campo | Detalhe |
|-------|---------|
| Trigger | Consolidação de métricas de qualidade de leads por canal ou detecção de variação significativa em taxa de no-show por origem |
| Owner | sales-chief |
| Template | `templates/operational/cross-squad-handoff-template.md` |
| SLA | 72h acknowledgment (standard) |
| Quality Gate de Saída | Qualidade de leads por canal com amostra mínima, taxa de no-show por origem com período de referência, tempo médio de call por fonte com desvio padrão |
| Quality Gate de Retorno | Volume e origem dos leads com projeção atualizada, mudanças em campanhas com data de início e impacto esperado |
| Registro | `data/handoffs/handoffs-registry.yaml` |
| Escalation | Se SLA ultrapassado → sales-chief escala para chief do squad receptor |

## Integração com Brand Squad

### O que Compartilhamos
- Percepção de marca na call → Como prospects descrevem a marca antes do pitch
- Nível de awareness → Quanto o prospect já sabe antes da call
- Objeções de credibilidade → Quando o prospect questiona a legitimidade

### O que Recebemos
- Guidelines de posicionamento → Auditamos se o closer comunica on-brand
- Diferenciadores-chave → Verificamos se são mencionados na call

### Contrato de Handoff
| Campo | Detalhe |
|-------|---------|
| Trigger | Detecção de objeções de credibilidade recorrentes ou divergência entre percepção de marca relatada pelos prospects e posicionamento oficial |
| Owner | sales-chief |
| Template | `templates/operational/cross-squad-handoff-template.md` |
| SLA | 72h acknowledgment (standard) |
| Quality Gate de Saída | Percepção de marca categorizada com citações reais, nível de awareness quantificado por segmento, objeções de credibilidade com frequência e contexto |
| Quality Gate de Retorno | Guidelines de posicionamento atualizados com checklist auditável, diferenciadores-chave com phraseology aprovada para uso em calls |
| Registro | `data/handoffs/handoffs-registry.yaml` |
| Escalation | Se SLA ultrapassado → sales-chief escala para chief do squad receptor |

## Integração com Storytelling Squad

### O que Compartilhamos
- Momentos de conexão emocional → Quais histórias ressoaram com prospects
- Cases que funcionam → Quais provas sociais geram mais impacto na call
- Narrativas de transformação → Quais jornadas de cliente mais convencem

### O que Recebemos
- Banco de histórias aprovadas → Closer pode usar histórias validadas pelo Storytelling Squad
- Estruturas narrativas → Frameworks de storytelling para usar durante o pitch

### Contrato de Handoff
| Campo | Detalhe |
|-------|---------|
| Trigger | Identificação de momentos de conexão emocional de alto impacto ou novos cases de sucesso detectados nas calls |
| Owner | sales-chief |
| Template | `templates/operational/cross-squad-handoff-template.md` |
| SLA | 72h acknowledgment (standard) |
| Quality Gate de Saída | Momentos de conexão emocional com timestamp e transcrição, cases que funcionam com taxa de conversão associada, narrativas de transformação com estrutura e resultado |
| Quality Gate de Retorno | Banco de histórias aprovadas com tags de uso e contexto recomendado, estruturas narrativas com exemplos aplicados a cenários de call |
| Registro | `data/handoffs/handoffs-registry.yaml` |
| Escalation | Se SLA ultrapassado → sales-chief escala para chief do squad receptor |

## Integração com C-Level Squad

### O que Compartilhamos
- Tendências de mercado detectadas nas calls → O que prospects estão dizendo sobre o mercado
- Análise de competidores mencionados → Quais alternativas os prospects consideram
- Métricas consolidadas de performance → Dashboard executivo de vendas

### O que Recebemos
- Direcionamento estratégico → Prioridades que afetam critérios de auditoria
- Decisões de pricing → Ajustes no bloco de ancoragem

### Contrato de Handoff
| Campo | Detalhe |
|-------|---------|
| Trigger | Consolidação de tendências de mercado ou análise de competidores com impacto estratégico, ou entrega de métricas consolidadas de performance |
| Owner | sales-chief |
| Template | `templates/operational/cross-squad-handoff-template.md` |
| SLA | 24h acknowledgment (critical) |
| Quality Gate de Saída | Tendências de mercado com evidências de múltiplas calls, análise de competidores com frequência de menção e posicionamento, métricas consolidadas com período e metodologia |
| Quality Gate de Retorno | Direcionamento estratégico com critérios de auditoria atualizados, decisões de pricing com parâmetros de ancoragem revisados |
| Registro | `data/handoffs/handoffs-registry.yaml` |
| Escalation | Se SLA ultrapassado → sales-chief escala para chief do squad receptor |

## Integração com Data Squad

### O que Compartilhamos
- Dados estruturados de auditoria → Scores, frameworks detectados, resultados
- Correlações encontradas → Quais comportamentos correlacionam com close

### O que Recebemos
- Análises estatísticas → Validação quantitativa dos achados qualitativos
- Dashboards automatizados → Visualização de tendências

### Contrato de Handoff
| Campo | Detalhe |
|-------|---------|
| Trigger | Entrega de dados estruturados de auditoria para análise estatística ou novas correlações comportamento-close identificadas |
| Owner | sales-chief |
| Template | `templates/operational/cross-squad-handoff-template.md` |
| SLA | 72h acknowledgment (standard) |
| Quality Gate de Saída | Dados estruturados de auditoria com schema documentado e período de coleta, correlações encontradas com tamanho de amostra e significância preliminar |
| Quality Gate de Retorno | Análises estatísticas com metodologia, intervalo de confiança e conclusões acionáveis, dashboards automatizados com fontes de dados e frequência de atualização |
| Registro | `data/handoffs/handoffs-registry.yaml` |
| Escalation | Se SLA ultrapassado → sales-chief escala para chief do squad receptor |

## Integração com Movement e Advisory Squads

### Movement Squad
- Compartilhamos insights sobre cultura e energia da equipe de vendas
- Recebemos diretrizes sobre comunicação interna de mudanças

#### Contrato de Handoff
| Campo | Detalhe |
|-------|---------|
| Trigger | Identificação de padrões culturais ou de energia da equipe de vendas que impactam performance nas calls |
| Owner | sales-chief |
| Template | `templates/operational/cross-squad-handoff-template.md` |
| SLA | 72h acknowledgment (standard) |
| Quality Gate de Saída | Insights sobre cultura e energia da equipe com evidências de calls e impacto observado na performance |
| Quality Gate de Retorno | Diretrizes de comunicação interna de mudanças com cronograma e plano de implementação |
| Registro | `data/handoffs/handoffs-registry.yaml` |
| Escalation | Se SLA ultrapassado → sales-chief escala para chief do squad receptor |

### Advisory Squad
- Compartilhamos relatórios consolidados para consultores externos
- Recebemos benchmarks de mercado e best practices de outros clientes

#### Contrato de Handoff
| Campo | Detalhe |
|-------|---------|
| Trigger | Consolidação de relatórios de auditoria para revisão por consultores externos ou necessidade de benchmarks atualizados |
| Owner | sales-chief |
| Template | `templates/operational/cross-squad-handoff-template.md` |
| SLA | 72h acknowledgment (standard) |
| Quality Gate de Saída | Relatórios consolidados com métricas-chave, período de análise e metodologia de auditoria documentada |
| Quality Gate de Retorno | Benchmarks de mercado com fonte e data de referência, best practices com contexto de aplicabilidade e exemplos |
| Registro | `data/handoffs/handoffs-registry.yaml` |
| Escalation | Se SLA ultrapassado → sales-chief escala para chief do squad receptor |

## Protocolo de Compartilhamento

1. Insights semanais: relatório resumido enviado toda sexta-feira
2. Insights urgentes: notificação imediata via canal dedicado
3. Revisão mensal: reunião cross-squad para alinhar prioridades
4. Documentação: todos os insights compartilhados ficam registrados no registry
