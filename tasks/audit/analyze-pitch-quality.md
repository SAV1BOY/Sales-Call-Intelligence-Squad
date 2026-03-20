# Analisar Qualidade do Pitch

> Avaliar pitch: ponte com diagnóstico, value proposition, social proof e personalização.

## Objetivo
Verificar se o closer construiu um pitch que conecta diretamente com a dor descoberta, apresenta valor claro e usa prova social relevante — pitch genérico é sinal de discovery fraco ou falta de técnica.

## Trigger
- Transcrição segmentada com etapa de pitch delimitada
- Análises de discovery e ampliação de dor concluídas

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Avalia estrutura e eficácia do pitch |
| Alex Hormozi | Valida Grand Slam Offer e Value Equation |
| Cole Gordon | Valida ponte entre diagnóstico e prescrição |
| Jordan Belfort | Avalia controle de frame durante o pitch |

## Inputs
- Transcrição segmentada: seção de pitch com timestamps
- Análise de discovery (dor identificada, palavras do lead)
- Detalhes da oferta apresentada
- Grand Slam Offer e Value Equation como referência

## Processo
1. Verificar se o closer fez ponte explícita entre a dor do lead e a solução
2. Avaliar se usou as palavras do próprio lead para descrever o problema
3. Analisar a value proposition: resultado prometido, timeline, esforço exigido
4. Verificar aplicação da Value Equation: Dream Outcome × Perceived Likelihood / Time × Effort
5. Avaliar uso de social proof: casos, resultados, depoimentos (específicos vs. genéricos)
6. Verificar personalização do pitch: adaptado ao lead ou apresentação padrão?
7. Analisar se vendeu a transformação (vacation) ou o processo (plane flight)
8. Identificar se o lead demonstrou interesse/engajamento durante o pitch
9. Avaliar duração do pitch: prolixo (>15min) ou conciso e impactante

## Frameworks Aplicados
- Grand Slam Offer (Hormozi)
- Value Equation (Dream Outcome × Likelihood / Time × Effort)
- Sell the Vacation, Not the Plane Flight
- Doctor Frame (prescrição conectada ao diagnóstico)

## Checklists de Qualidade
- Ponte diagnóstico→solução presente com evidência
- Palavras do lead reutilizadas no pitch (sim/não, trechos)
- Value Equation aplicada (parcial/completa)
- Social proof específico e relevante ao caso
- Pitch personalizado (não genérico)

## Output Esperado
- Análise de pitch em `reports/analysis/CALL-ID-pitch`
- Avaliação de cada componente: ponte, value prop, social proof, personalização
- Nota do bloco pitch (0-10) com justificativa

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo pitch_score)

## Critérios de Conclusão
- [ ] Ponte diagnóstico→solução avaliada
- [ ] Value Equation analisada componente por componente
- [ ] Social proof avaliado (tipo, especificidade, relevância)
- [ ] Personalização do pitch verificada
- [ ] Engajamento do lead durante o pitch registrado
- [ ] Nota atribuída com evidência textual
