# Atualizar Scorecards

> Atualizar scorecards consolidados com novos resultados e recalcular médias e rankings.

## Objetivo
Manter scorecards individuais e de equipe sempre atualizados — base para coaching, certificação e dashboard executivo. Scorecards desatualizados invalidam todas as análises que dependem deles.

## Trigger
- Nova call auditada e pontuada
- Recalibragem de scoring aplicada (notas podem mudar retroativamente)
- Review semanal (consolidação)

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Scorecard Analyst | Executa atualização e recálculos |
| QA Guardian | Valida precisão dos cálculos |
| Revenue Intelligence Analyst | Recalcula métricas agregadas |

## Inputs
- Scorecard da call recém-auditada
- Scorecards históricos do closer
- Calibração de scoring vigente
- Benchmarks da equipe

## Processo
1. Inserir novo scorecard no histórico do closer
2. Recalcular média móvel (últimas 10 calls)
3. Recalcular desvio padrão (consistência)
4. Atualizar ranking da equipe por score médio
5. Verificar se houve mudança de tendência (melhoria/piora)
6. Recalcular médias por bloco do scorecard
7. Atualizar benchmarks da equipe com novo dado
8. Sinalizar se closer cruzou limiar de certificação (para cima ou para baixo)
9. Gerar snapshot comparativo: antes vs. depois da atualização
10. Notificar se houver mudança significativa em ranking ou tendência

## Frameworks Aplicados
- Scorecard Analytics Framework
- Moving Average Calculation
- Trend Detection

## Checklists de Qualidade
- Novo scorecard inserido sem duplicata
- Média móvel recalculada corretamente
- Ranking atualizado e sem empates não resolvidos
- Tendência recalculada e coerente
- Benchmarks da equipe atualizados

## Output Esperado
- Scorecards atualizados em `data/registries/scorecards-registry.yaml`
- Ranking atualizado da equipe
- Alertas de mudança significativa (se houver)

## Registry Atualizado
- `data/registries/scorecards-registry.yaml`
- `data/registries/closer-performance-registry.yaml`

## Critérios de Conclusão
- [ ] Novo scorecard inserido no histórico
- [ ] Média móvel e desvio padrão recalculados
- [ ] Ranking da equipe atualizado
- [ ] Tendência verificada
- [ ] Benchmarks atualizados
- [ ] Alertas gerados se mudança significativa
