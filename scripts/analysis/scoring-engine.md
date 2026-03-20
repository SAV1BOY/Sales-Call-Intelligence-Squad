# Script: Engine de Scoring Automático

> Calcular score por bloco e total do scorecard automaticamente para cada call processada.

## Objetivo
Consolidar todas as métricas e evidências de uma call para gerar o score do scorecard de forma automatizada e consistente.

## Input
- Transcrição processada com todas as tags (etapa, speaker, evidências)
- Métricas de talk ratio por etapa (output do talk-ratio-calculator)
- Frameworks detectados por etapa (output do framework-detector-engine)
- Objeções classificadas (output do objection-classifier)
- Timestamps de momentos relevantes (output do timestamp-extractor)
- Pesos configurados por operação (lib/utilities/scoring-weighting-logic)

## Processo
1. Para cada bloco do scorecard, coletar inputs:
   - **Abertura**: duração, presença de pauta, rapport detectado, controle assumido
   - **Discovery**: profundidade de dor (camadas), quantificação, talk ratio, frameworks usados
   - **Pitch**: personalização detectada, cases mencionados, micro-commits, duração adequada
   - **Price Reveal**: ancoragem detectada, value stack presente, risk reversal, hesitação
   - **Objeção**: isolamento feito, looping detectado, resolução confirmada, resultado
   - **Fechamento**: tipo de close, next step travado, confiança, naturalidade
2. Calcular score bruto por bloco (0-100) usando rubrica de qualidade
3. Aplicar pesos por bloco conforme configuração da operação
4. Detectar penalizações aplicáveis:
   - Monólogo acima de 5 min (-5)
   - Objeção ignorada (-10)
   - Pressão emocional (-20)
   - Script robótico detectado (-5)
5. Detectar bonificações aplicáveis:
   - Discovery 4+ camadas (+5)
   - Quantificação colaborativa (+3)
   - Turnaround de objeção magistral (+10)
6. Calcular score final: ponderado + bonificações - penalizações
7. Classificar performance: crítico, abaixo, adequado, bom, excelente
8. Gerar scorecard completo com evidências por bloco

## Output
- Score total (0-100) com classificação
- Score por bloco (0-100) com evidências
- Lista de penalizações aplicadas com justificativa
- Lista de bonificações aplicadas com justificativa
- Comparativo com média do squad e histórico do closer
- Top 3 pontos fortes e top 3 pontos de melhoria
- Scorecard formatado para coaching pack

## Dependências
- Todos os scripts de processamento (transcrição limpa, segmentada, tagueada)
- Todos os scripts de análise (talk ratio, frameworks, objeções)
- Scorecard engine (lib/components/scorecard-engine)
- Scoring weighting logic (lib/utilities/scoring-weighting-logic)
- Call quality rubric (lib/utilities/call-quality-rubric)

## Frequência de Execução
- Executado automaticamente ao final do pipeline de processamento de cada call
- Tempo médio de processamento: menos de 10 segundos
- Resultados disponíveis imediatamente após processamento completo
