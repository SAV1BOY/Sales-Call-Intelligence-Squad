# Parser de Timestamps

> Utilitário responsável por normalizar timestamps de diferentes fontes para um formato padrão usado em todo o sistema.

## Função
Receber timestamps em diversos formatos de plataformas de gravação e convertê-los para o formato padrão do Squad.

## Formatos Aceitos
- **HH:MM:SS** (01:23:45) — formato de hora completo
- **MM:SS** (23:45) — formato minuto:segundo
- **SS** (1425) — segundos totais desde o início
- **HH:MM:SS.mmm** (01:23:45.123) — com milissegundos
- **ISO 8601** (PT1H23M45S) — formato ISO de duração
- **Texto livre** ("aos 23 minutos e 45 segundos") — detecção por regex

## Lógica de Normalização
1. Detectar formato de entrada por pattern matching
2. Converter para formato interno: segundos totais (inteiro)
3. Gerar formato de saída padrão: MM:SS (para calls < 1h) ou HH:MM:SS (para calls >= 1h)
4. Validar que o timestamp está dentro da duração da call
5. Arredondar milissegundos para segundo mais próximo
6. Tratar edge cases: timestamps negativos, maiores que duração da call, formato inválido

## Formato Padrão de Saída
- Calls com menos de 60 minutos: **MM:SS** (ex: 23:45)
- Calls com 60 minutos ou mais: **HH:MM:SS** (ex: 01:23:45)
- Referência em texto: **[MM:SS]** com colchetes

## Validações
- Timestamp não pode ser negativo
- Timestamp não pode exceder duração total da call
- Timestamp de início deve ser menor que timestamp de fim (em ranges)
- Formato deve ser consistente dentro do mesmo documento

## Integração
- Alimenta o **evidence-tagging-engine** (timestamps de evidências)
- Alimenta o **stage-segmentation-engine** (timestamps de transição)
- Alimenta relatórios e scorecards (referências temporais)
- Usado por todos os scripts de processamento como utilitário base

## Exemplos de Conversão
- "01:23:45" → 5025 segundos → [01:23:45]
- "23:45" → 1425 segundos → [23:45]
- "1425" → 1425 segundos → [23:45]
- "aos 23 minutos e 45 segundos" → 1425 segundos → [23:45]
