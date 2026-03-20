# Engine de Scoring de Risco do Deal

> Engine responsável por calcular o nível de risco de cada deal baseado em 8 fatores ponderados, classificando a probabilidade de perda.

## Função
Avaliar múltiplos fatores de risco em um deal para gerar um score que indica a probabilidade de fechamento ou perda, orientando ações preventivas.

## Inputs
- Score da call no scorecard (output do scorecard-engine)
- Dados do lead (nicho, ticket, canal de origem, nível de consciência)
- Objeções levantadas e status de resolução
- Presença de decisor na call
- Tempo desde a call até o momento da avaliação
- Histórico de follow-ups realizados
- Sinais de compra ou rejeição detectados
- Engajamento pós-call (abriu e-mail, respondeu WhatsApp, etc.)

## Lógica de Processamento
1. Avaliar os 8 fatores de risco (0-100 cada):
   - **Fator 1 — Qualidade do Discovery** (peso 20%): Score do bloco de discovery no scorecard. Discovery raso = risco alto
   - **Fator 2 — Objeções não resolvidas** (peso 15%): Quantidade e severidade de objeções pendentes
   - **Fator 3 — Presença do decisor** (peso 15%): Decisor presente na call vs delegado vs ausente
   - **Fator 4 — Engajamento do lead** (peso 10%): Nível de participação, perguntas feitas, sinais de interesse
   - **Fator 5 — Competitividade** (peso 10%): Lead mencionou concorrentes ou alternativas
   - **Fator 6 — Timeline do lead** (peso 10%): Urgência declarada vs vaga vs inexistente
   - **Fator 7 — Score geral da call** (peso 10%): Score total no scorecard
   - **Fator 8 — Engajamento pós-call** (peso 10%): Resposta a follow-up, abertura de materiais
2. Calcular score de risco ponderado (0-100, onde 100 = máximo risco)
3. Classificar nível de risco:
   - 0-25: Risco baixo (deal saudável, manter processo)
   - 26-50: Risco médio (atenção em pontos específicos)
   - 51-75: Risco alto (intervenção necessária)
   - 76-100: Risco crítico (deal provavelmente perdido sem ação imediata)
4. Gerar recomendações de ação por nível de risco
5. Priorizar deals por urgência de intervenção

## Outputs
- Score de risco total (0-100)
- Score individual de cada fator
- Classificação de risco (baixo, médio, alto, crítico)
- Top 3 fatores de maior risco neste deal
- Recomendações de ação específicas
- Previsão de probabilidade de fechamento (%)

## Integração
- Recebe dados do **scorecard-engine** (score da call)
- Recebe dados da **objection-taxonomy-engine** (objeções pendentes)
- Recebe dados da **evidence-tagging-engine** (sinais de compra/rejeição)
- Alimenta o dashboard executivo (pipeline por nível de risco)
- Alimenta alertas automáticos para gestores (deals críticos)
- Alimenta relatórios semanais (tendência de risco do pipeline)
