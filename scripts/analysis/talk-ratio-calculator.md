# Script: Calculadora de Talk Ratio

> Calcular proporção de fala entre closer e lead por etapa e geral, com métricas de monólogo e perguntas.

## Objetivo
Processar a transcrição segmentada e gerar métricas detalhadas de talk ratio que alimentam o scorecard e relatórios de coaching.

## Input
- Transcrição segmentada por speaker com durações (output do speaker-segmenter)
- Transcrição tagueada por etapa (output do stage-tagger)
- Benchmarks de talk ratio por etapa (configuráveis)

## Processo
1. Calcular tempo total de fala por speaker:
   - Somar duração de todos os turnos do closer
   - Somar duração de todos os turnos do lead
   - Calcular percentual de cada um sobre o total falado
2. Calcular talk ratio por etapa:
   - Para cada etapa, repetir o cálculo acima
   - Comparar com benchmark da etapa (ex: discovery ideal = closer 35%)
   - Calcular desvio do benchmark (positivo = fala demais, negativo = fala de menos)
3. Detectar e classificar monólogos:
   - Identificar falas contínuas acima de 90 segundos
   - Classificar por etapa e speaker
   - Avaliar se o monólogo é adequado (pitch) ou problemático (discovery)
4. Analisar perguntas do closer:
   - Contar total de perguntas (detectar por interrogação ou padrão)
   - Classificar: abertas vs fechadas
   - Calcular ratio perguntas/afirmações
   - Identificar perguntas de follow-up (segunda pergunta sobre mesmo tema)
5. Analisar interrupções:
   - Detectar momentos onde um speaker cortou o outro
   - Contar interrupções por speaker
   - Classificar: interrupção de controle vs interrupção de ansiedade
6. Gerar score de talk ratio (0-100) baseado em benchmarks
7. Comparar com média do squad e histórico do closer

## Output
- Talk ratio geral: closer X% vs lead Y%
- Talk ratio por etapa com comparativo ao benchmark
- Lista de monólogos com duração, etapa e classificação
- Métricas de perguntas: total, abertas/fechadas, ratio, follow-ups
- Contagem de interrupções por speaker
- Score de talk ratio (0-100)
- Recomendações específicas baseadas nos desvios

## Dependências
- Transcrição segmentada por speaker (output do speaker-segmenter)
- Transcrição tagueada por etapa (output do stage-tagger)
- Talk ratio engine (lib/components/talk-ratio-engine)
- Benchmarks configurados por operação

## Frequência de Execução
- Executado automaticamente para cada call processada
- Tempo médio de processamento: menos de 5 segundos
- Resultados alimentam scorecard, coaching pack e dashboard
