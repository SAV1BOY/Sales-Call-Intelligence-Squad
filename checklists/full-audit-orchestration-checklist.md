# Full Audit Orchestration Checklist

> Valida a qualidade do relatório consolidado de auditoria full-funnel antes da entrega final.

## Objetivo

Garantir que o relatório executivo produzido pelo workflow 06 (Full Funnel Call Audit) está completo, consistente e acionável. Este checklist é o quality gate final antes da entrega ao closer e gestor.

## Quando Usar

Após a Etapa 3 (consolidação) do workflow 06, antes de aprovar a entrega na Etapa 4. O relatório só avança para entrega se 100% dos itens estiverem aprovados.

## Checklist

### Completude do Scorecard
- [ ] Todos os 10 blocos do scorecard estão pontuados com nota individual
- [ ] Cada bloco possui justificativa com evidência (trecho + timestamp)
- [ ] A fórmula de cálculo do score final está explícita com pesos declarados
- [ ] O score final é coerente com a média ponderada dos blocos
- [ ] A classificação da call está correta (Crítica / Fraca / Regular / Boa / Forte / Elite)

### Detecção de Frameworks
- [ ] Framework detection está completa — todas as fases da call foram analisadas
- [ ] Não há gaps de cobertura (nenhuma fase ficou sem análise de framework)
- [ ] O percentual de aderência a cada framework está calculado
- [ ] Frameworks esperados mas ausentes estão sinalizados como gap

### Causa Raiz
- [ ] A causa raiz principal está explicitamente identificada e priorizada
- [ ] A causa raiz diferencia erro do closer vs. problema do lead vs. oferta inadequada
- [ ] Há no máximo 3 causas raiz, priorizadas por impacto
- [ ] Cada causa raiz tem evidência associada com trecho e timestamp

### Rewrites de Coaching
- [ ] Mínimo de 3 rewrites incluídos no relatório
- [ ] Cada rewrite tem formato ANTES (trecho real) e DEPOIS (versão melhorada)
- [ ] Cada rewrite identifica o framework aplicado na versão melhorada
- [ ] Cada rewrite inclui justificativa de por que a versão melhorada é superior
- [ ] Rewrites correspondem a momentos críticos identificados na análise

### Consistência Cross-Agent
- [ ] Não há contradições entre o score e a causa raiz (score baixo em discovery + causa raiz alinhada)
- [ ] Os momentos críticos citados no relatório são consistentes entre seções
- [ ] Timestamps são padronizados e consistentes em todo o documento
- [ ] Quando houve divergência entre agentes, a resolução está documentada

### Completude do Template
- [ ] Resumo da Call preenchido (closer, lead, produto, data, resultado)
- [ ] Score Final com 10 blocos + nota total + classificação
- [ ] Causa Raiz com diagnóstico + fatores contribuintes
- [ ] Top 5 Momentos Críticos com timestamp + resumo + impacto
- [ ] Cobertura de Frameworks com % aderência + gaps
- [ ] Rewrites Prioritários (top 3 before/after)
- [ ] Recomendações de Coaching com ações prioritárias
- [ ] Parecer do Sales-Chief com visão holística

### Registries e Rastreamento
- [ ] Audit-registry será atualizado com a auditoria completa
- [ ] Closer-score-registry será atualizado com o score
- [ ] Coaching-log-registry será atualizado com os rewrites e recomendações
- [ ] Framework-detection-registry será atualizado com as detecções
- [ ] Call-log-registry terá o status final da call atualizado
- [ ] Ticket de auditoria está pronto para fechamento

### Qualidade das Recomendações
- [ ] Todas as recomendações são acionáveis (ação específica, não genérica)
- [ ] Recomendações estão priorizadas por impacto esperado
- [ ] Cada recomendação é aplicável na próxima call do closer

### Coerência do Relatório Executivo
- [ ] O resumo executivo é compreensível sem ler o relatório completo
- [ ] A linguagem é objetiva, sem julgamentos vagos
- [ ] Comparação com histórico do closer está incluída (se disponível)
- [ ] O relatório tem voz unificada (não parece colagem de outputs de múltiplos agentes)

## Critérios de Aprovação

- **Aprovado**: 100% dos itens marcados — relatório pronto para entrega
- **Revisão necessária**: 1-3 itens faltando — devolver seções específicas para correção
- **Reprovado**: 4+ itens faltando OU qualquer item de consistência cross-agent reprovado — devolver para re-consolidação

## Scoring Rubric

Cada item deve ser pontuado de 0 a 5:

| Score | Significado |
|-------|------------|
| 0 | Ausente — item não abordado |
| 1 | Mencionado sem evidência |
| 2 | Presente com evidência fraca ou genérica |
| 3 | Presente com evidência específica (trecho + timestamp) |
| 4 | Forte — evidência + análise + recomendação |
| 5 | Exemplar — material para swipe file |

### Thresholds
- **Pass mínimo**: média >= 3.0 (todos os itens)
- **GOOD**: média >= 3.5
- **GOLD**: média >= 4.5
- **Rework trigger**: qualquer item com score 0 OU média < 2.5
- **Aprovação**: QA Guardian valida; Sales Chief aprova output final

## Agente Responsável

sales-chief — Aplica este checklist como quality gate final do workflow 06.

## Frequência

Aplicar em **100% das auditorias full-funnel** (workflow 06) antes da entrega.
