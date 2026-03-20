# Script: Extrator de Timestamps Relevantes

> Extrair e catalogar timestamps de momentos relevantes da call para referência rápida em análises e coaching.

## Objetivo
Identificar automaticamente momentos-chave da call e registrar seus timestamps para referência em scorecards, coaching e swipe files.

## Input
- Transcrição tagueada com etapas (output do stage-tagger)
- Segmentação por speaker com métricas (output do speaker-segmenter)
- Catálogo de momentos relevantes para extrair

## Processo
1. Extrair timestamps de transição de etapa:
   - Início de cada etapa (abertura, discovery, pitch, etc.)
   - Fim de cada etapa
   - Momento de transição (fala que marca a mudança)
2. Extrair timestamps de momentos positivos:
   - Pergunta de aprofundamento que revelou dor importante
   - Aplicação de framework bem executada
   - Momento de virada emocional do lead
   - Tratamento eficaz de objeção
   - Sinal de compra do lead
   - Fechamento bem sucedido
3. Extrair timestamps de momentos negativos:
   - Monólogo acima de 90 segundos
   - Objeção ignorada ou mal tratada
   - Perda de controle da call
   - Hesitação no preço
   - Pressão inadequada
   - Momento onde o lead se fechou emocionalmente
4. Extrair timestamps de silêncio:
   - Pausas acima de 3 segundos (com classificação: estratégico ou constrangedor)
   - Silêncio pós-pergunta de fechamento
5. Para cada timestamp extraído, registrar:
   - Momento: [MM:SS]
   - Tipo: positivo, negativo, neutro, transição
   - Categoria: qual aspecto da call representa
   - Trecho associado: texto do momento (máximo 50 palavras)
   - Prioridade: alta, média, baixa (para coaching)
6. Ordenar por prioridade para coaching e por cronologia para análise

## Output
- Lista de timestamps relevantes com metadados
- Timestamps agrupados por tipo (positivo, negativo, transição)
- Timestamps priorizados para coaching (top 5)
- Timeline visual da call com momentos marcados
- Formato exportável para scorecards e packs de coaching

## Dependências
- Transcrição tagueada (output do stage-tagger)
- Parser de timestamps (lib/utilities/timestamp-parser)
- Evidence tagging engine (lib/components/evidence-tagging-engine)

## Frequência de Execução
- Executado automaticamente após tagueamento de etapas
- Tempo médio de processamento: menos de 10 segundos
- Resultados alimentam diretamente o scorecard e o coaching pack
