# Taxonomia de Risco do Deal

> Classificação dos níveis de risco de deals no pipeline: baixo, médio, alto e crítico, com indicadores e ações recomendadas.

## Função
Padronizar a classificação de risco para priorização de follow-up, intervenção de gestão e previsão de pipeline.

## Nível 1 — Risco Baixo (Score 0-25)
**Definição**: Deal saudável com alta probabilidade de fechamento. Processo de venda fluindo conforme esperado.
**Indicadores**:
- Score da call acima de 75
- Discovery profundo com dor quantificada
- Decisor presente na call
- Objeções tratadas e confirmadas como resolvidas
- Lead engajado no follow-up (responde rápido)
- Timeline definida com urgência real
**Probabilidade estimada de fechamento**: 65-85%
**Ações recomendadas**: Manter processo padrão. Follow-up conforme agendado. Não acelerar nem desacelerar.
**Frequência de revisão**: Semanal (check-in padrão)

## Nível 2 — Risco Médio (Score 26-50)
**Definição**: Deal com sinais mistos. Alguns indicadores positivos e alguns preocupantes.
**Indicadores**:
- Score da call entre 60-75
- Discovery adequado mas com lacunas de quantificação
- Decisor parcialmente envolvido (presente mas passivo)
- 1-2 objeções parcialmente resolvidas
- Lead responde ao follow-up mas com delay
- Timeline vaga ("em breve", "nas próximas semanas")
**Probabilidade estimada de fechamento**: 35-55%
**Ações recomendadas**: Intensificar follow-up com valor agregado. Enviar material complementar. Tentar incluir decisor em próxima interação. Definir deadline claro.
**Frequência de revisão**: 2x por semana

## Nível 3 — Risco Alto (Score 51-75)
**Definição**: Deal em perigo com múltiplos sinais negativos. Precisa de intervenção para salvar.
**Indicadores**:
- Score da call entre 45-60
- Discovery superficial — dor não quantificada
- Decisor ausente ou desconhecido
- Objeções não resolvidas ou evadidas
- Lead não responde ao follow-up ou responde com evasivas
- Sem timeline definida
- Lead mencionou concorrentes ativamente
**Probabilidade estimada de fechamento**: 15-30%
**Ações recomendadas**: Intervenção imediata do gestor. Reabrir discovery com nova call. Tentar acesso ao decisor por outro caminho. Considerar mudança de closer. Oferecer projeto piloto menor.
**Frequência de revisão**: Diária

## Nível 4 — Risco Crítico (Score 76-100)
**Definição**: Deal provavelmente perdido. Apenas ação extraordinária pode salvar.
**Indicadores**:
- Score da call abaixo de 45
- Discovery inexistente ou completamente superficial
- Decisor inacessível
- Múltiplas objeções não resolvidas
- Lead não responde há 7+ dias
- Lead declarou estar avaliando concorrente preferido
- Sinais claros de ghosting
**Probabilidade estimada de fechamento**: 0-15%
**Ações recomendadas**: Avaliar se vale investir mais tempo. Tentativa final com abordagem completamente diferente. Se não responder em 5 dias, classificar como perdido e fazer post-mortem.
**Frequência de revisão**: Decisão imediata (salvar ou abandonar)

## Fatores Agravantes (Aumentam o Risco)
- Lead recebeu proposta de concorrente: +15 pontos de risco
- Call terminou sem next step: +20 pontos de risco
- Lead cancelou ou reagendou call 2+ vezes: +10 pontos de risco
- Closer não é o mesmo da call original: +10 pontos de risco
- Tempo desde a call acima de 14 dias sem progresso: +20 pontos de risco

## Fatores Atenuantes (Diminuem o Risco)
- Indicação de cliente ativo: -15 pontos de risco
- Lead pediu proposta formal proativamente: -10 pontos de risco
- Decisor confirmou participação em próxima call: -15 pontos de risco
- Lead compartilhou dados internos confidenciais: -10 pontos de risco

## Integração
- Usado pelo **deal-risk-scoring-engine** como referência de classificação
- Usado no dashboard executivo para visão de pipeline por risco
- Usado por gestores para priorização diária de ações
