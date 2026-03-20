# Construir Relatório Minuto a Minuto

> Construir relatório completo minuto a minuto: o que aconteceu, avaliação e recomendação por momento.

## Objetivo
Criar o artefato mais granular da auditoria — um mapa temporal completo que permite ao gestor e ao closer verem exatamente o que aconteceu em cada momento, com avaliação e sugestão de melhoria.

## Trigger
- Todas as análises de etapa concluídas (rapport, discovery, pitch, pricing, objeções, close)
- Execução do workflow `02-minute-by-minute-analysis`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Consolida análises em linha temporal |
| Scorecard Analyst | Vincula momentos a blocos do scorecard |
| Framework Detector | Marca frameworks aplicados por minuto |
| Coaching Rewriter | Prepara sugestões de melhoria por momento |

## Inputs
- Transcrição segmentada com timestamps
- Todas as análises de etapa concluídas
- Relatório de frameworks detectados
- Scorecard da call

## Processo
1. Dividir a call em intervalos de 1 minuto (ou por turno de fala, o que for mais granular)
2. Para cada minuto, registrar: etapa, quem fala, o que acontece, framework usado
3. Classificar cada momento: positivo (acerto), neutro, negativo (erro/oportunidade perdida)
4. Vincular momentos negativos com blocos do scorecard impactados
5. Para cada momento negativo, incluir recomendação de melhoria
6. Marcar os 5 momentos mais críticos da call (decisivos para o resultado)
7. Incluir análise de momentum: quando o closer ganhou/perdeu controle
8. Gerar timeline visual com código de cores (verde/amarelo/vermelho)
9. Adicionar notas de coaching nos momentos mais críticos

## Frameworks Aplicados
- Minute-by-Minute Analysis Framework
- Todos os frameworks detectados na call (referência cruzada)
- Sales Call Stage Taxonomy

## Checklists de Qualidade
- Todos os minutos da call cobertos sem gaps
- Cada momento classificado (positivo/neutro/negativo)
- Momentos negativos têm recomendação de melhoria
- 5 momentos mais críticos destacados
- Timeline visual gerada com código de cores

## Output Esperado
- Relatório minuto a minuto em `reports/minute-by-minute/CALL-ID-mxm`
- Timeline visual com classificação por cores
- Lista dos 5 momentos mais críticos com contexto e recomendação

## Registry Atualizado
- `data/registries/calls-registry.yaml` (status "relatório completo")

## Critérios de Conclusão
- [ ] Todos os minutos mapeados com etapa e ação
- [ ] Momentos classificados (positivo/neutro/negativo)
- [ ] Recomendações incluídas para momentos negativos
- [ ] 5 momentos mais críticos destacados
- [ ] Timeline visual gerada
- [ ] Relatório consolidado e salvo
