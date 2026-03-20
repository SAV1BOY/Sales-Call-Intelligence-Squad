# Engine de Segmentação por Etapa

> Engine responsável por detectar as transições entre etapas de uma call de vendas e segmentar a transcrição em blocos avaliáveis.

## Função
Analisar a transcrição completa de uma call e identificar onde cada etapa começa e termina, permitindo avaliação individual por bloco no scorecard.

## Inputs
- Transcrição completa da call com timestamps
- Identificação de speakers (closer vs lead)
- Duração total da call
- Modelo de etapas configurado (padrão: 6 etapas)

## Lógica de Processamento
1. Receber transcrição limpa e segmentada por speaker
2. Identificar marcadores de transição de etapa por patterns:
   - Abertura → Discovery: primeira pergunta exploratória do closer
   - Discovery → Pitch: closer resume dor e começa a apresentar solução
   - Pitch → Price Reveal: closer transiciona para investimento/preço
   - Price Reveal → Objeção: lead levanta resistência ou hesitação
   - Objeção → Fechamento: closer resolve objeção e avança para compromisso
3. Validar transições detectadas:
   - Transição coerente com duração esperada de cada etapa
   - Sem sobreposição de etapas
   - Todas as etapas presentes (ou marcar como ausente)
4. Tratar casos especiais:
   - Etapas fora de ordem (objeção durante discovery)
   - Etapas repetidas (volta ao discovery após objeção)
   - Etapas ausentes (sem price reveal explícito)
5. Calcular métricas por etapa:
   - Duração em minutos e percentual da call total
   - Talk ratio por etapa
   - Número de turnos de fala por etapa
6. Gerar segmentação final com timestamps de início e fim de cada etapa

## Outputs
- Mapa de etapas com timestamps (início, fim, duração)
- Percentual da call dedicado a cada etapa
- Etapas ausentes ou fora de ordem sinalizadas
- Métricas de fala por etapa (talk ratio, turnos, monólogos)
- Trechos de transição marcados para revisão

## Integração
- Recebe dados do **speaker-segmentation** (quem fala quando)
- Recebe dados do **timestamp-parser** (timestamps normalizados)
- Alimenta o **scorecard-engine** (delimita blocos para avaliação)
- Alimenta o **talk-ratio-engine** (métricas por etapa)
- Alimenta o **evidence-tagging-engine** (contexto de etapa para cada evidência)
