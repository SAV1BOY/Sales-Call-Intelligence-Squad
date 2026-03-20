# Engine de Tagueamento de Evidência

> Engine responsável por marcar trechos específicos da transcrição com tags de tipo, qualidade e relevância para uso em scorecards e coaching.

## Função
Identificar e taguear trechos da transcrição que servem como evidência de competência ou deficiência do closer em cada bloco avaliado.

## Inputs
- Transcrição completa segmentada por speaker e etapa
- Timestamps normalizados
- Catálogo de tipos de evidência (positiva, negativa, neutra)
- Critérios de relevância por bloco do scorecard
- Threshold mínimo de relevância para taguear

## Lógica de Processamento
1. Varrer a transcrição etapa por etapa buscando evidências:
   - Evidência positiva: aplicação correta de framework, pergunta profunda, tratamento eficaz de objeção, fechamento assertivo
   - Evidência negativa: pergunta superficial, monólogo excessivo, objeção ignorada, pressão inadequada
   - Evidência neutra: momento informativo sem impacto positivo ou negativo
2. Para cada evidência detectada, registrar:
   - Trecho exato da transcrição (máximo 200 palavras)
   - Timestamp de início e fim
   - Speaker (closer ou lead)
   - Etapa da call onde ocorreu
   - Tipo (positiva, negativa, neutra)
   - Subtipo (framework aplicado, objeção detectada, pergunta de aprofundamento, etc.)
   - Score de relevância (0-100)
3. Validar coerência das tags:
   - Não duplicar tags no mesmo trecho
   - Garantir que cada bloco do scorecard tem pelo menos 2 evidências
   - Sinalizar blocos sem evidência suficiente
4. Priorizar evidências por relevância para coaching:
   - Evidências negativas com alto impacto são priorizadas
   - Evidências positivas excepcionais são destacadas para reforço

## Outputs
- Lista de evidências tagueadas com metadados completos
- Evidências agrupadas por bloco do scorecard
- Evidências priorizadas para coaching (top 5 positivas, top 5 negativas)
- Trechos marcados para reescrita (evidências negativas de alto impacto)
- Mapa visual de evidências ao longo da timeline da call

## Integração
- Recebe dados do **timestamp-parser** (timestamps normalizados)
- Recebe dados da **stage-segmentation-engine** (contexto de etapa)
- Recebe dados do **speaker-segmentation** (identificação de speaker)
- Alimenta o **scorecard-engine** (evidências por bloco)
- Alimenta o **rewrite-engine** (trechos negativos para reescrita)
- Alimenta o **objection-taxonomy-engine** (trechos de objeção)
- Alimenta packs de coaching (evidências priorizadas)
