# Script: Tagger Automático de Etapa

> Identificar e taguear automaticamente cada etapa da call na transcrição segmentada.

## Objetivo
Receber transcrição segmentada por speaker e detectar as transições entre etapas (abertura, discovery, pitch, price reveal, objeção, fechamento) para delimitar blocos de avaliação.

## Input
- Transcrição segmentada por speaker (output do speaker-segmenter)
- Modelo de etapas configurado (6 etapas padrão)
- Catálogo de patterns de transição por etapa
- Duração total da call

## Processo
1. Carregar catálogo de patterns de transição:
   - Abertura → Discovery: padrões de primeira pergunta exploratória
   - Discovery → Pitch: padrões de resumo de dor e apresentação de solução
   - Pitch → Price Reveal: padrões de menção a investimento/preço
   - Price Reveal → Objeção: padrões de hesitação/resistência do lead
   - Objeção → Fechamento: padrões de resolução e avanço para compromisso
2. Varrer transcrição sequencialmente buscando patterns de transição
3. Para cada transição detectada, registrar:
   - Timestamp exato da transição
   - Pattern que ativou a detecção
   - Nível de confiança (0-100%)
4. Validar sequência de etapas:
   - Verificar se a ordem é lógica (abertura antes de discovery, etc.)
   - Tratar etapas fora de ordem (objeção durante discovery = marcar como sub-etapa)
   - Identificar etapas ausentes (sem price reveal explícito, por exemplo)
5. Calcular duração e percentual de cada etapa
6. Gerar mapa visual de etapas com timestamps
7. Sinalizar anomalias (discovery < 3 min, pitch > 20 min, etc.)

## Output
- Transcrição tagueada com marcadores de etapa: [ABERTURA], [DISCOVERY], [PITCH], etc.
- Mapa de etapas com timestamps de início e fim
- Duração e percentual de cada etapa
- Lista de anomalias detectadas
- Etapas ausentes ou fora de ordem sinalizadas
- Nível de confiança por transição detectada

## Dependências
- Transcrição segmentada por speaker (output do speaker-segmenter)
- Catálogo de patterns (lib/taxonomies/call-stage-taxonomy)
- Stage segmentation engine (lib/components/stage-segmentation-engine)

## Frequência de Execução
- Executado automaticamente após segmentação por speaker
- Tempo médio de processamento: menos de 15 segundos
- Calls com confiança de detecção abaixo de 70% são sinalizadas para revisão
