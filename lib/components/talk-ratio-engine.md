# Engine de Talk Ratio

> Engine responsável por calcular métricas de proporção de fala entre closer e lead, incluindo contagem de tempo, perguntas e monólogos.

## Função
Analisar a transcrição segmentada por speaker e calcular métricas detalhadas de proporção de fala que indicam qualidade da interação.

## Inputs
- Transcrição segmentada por speaker com timestamps
- Identificação confirmada de closer e lead
- Segmentação por etapa da call (output da stage-segmentation-engine)
- Benchmarks de talk ratio por etapa (configuráveis)

## Lógica de Processamento
1. Calcular tempo total de fala do closer e do lead:
   - Somar duração de cada turno de fala por speaker
   - Calcular percentual de cada speaker sobre o total
   - Talk ratio ideal geral: closer 40%, lead 60%
2. Calcular talk ratio por etapa:
   - Abertura: closer 60-70% (esperado, está conduzindo)
   - Discovery: closer 30-40% (ideal, deve escutar mais)
   - Pitch: closer 70-80% (esperado, está apresentando)
   - Price Reveal: closer 50-60% (equilíbrio)
   - Objeção: closer 40-50% (deve escutar a objeção completa)
   - Fechamento: closer 50-60% (direcionando mas confirmando)
3. Detectar monólogos problemáticos:
   - Monólogo = fala ininterrupta acima de 90 segundos
   - Contar quantidade de monólogos por speaker
   - Marcar monólogos acima de 3 minutos como críticos
4. Calcular métricas de perguntas:
   - Total de perguntas feitas pelo closer
   - Ratio perguntas/afirmações do closer
   - Perguntas abertas vs perguntas fechadas
   - Perguntas de aprofundamento (follow-up após resposta)
5. Calcular métricas de silêncio:
   - Pausas acima de 3 segundos (silêncio estratégico ou constrangedor)
   - Silêncio após pergunta de fechamento (positivo se intencional)
6. Comparar com benchmarks e gerar score de talk ratio (0-100)

## Outputs
- Talk ratio geral (closer% vs lead%)
- Talk ratio por etapa da call
- Quantidade e duração de monólogos por speaker
- Total de perguntas (abertas, fechadas, follow-up)
- Ratio perguntas/afirmações
- Pausas significativas detectadas
- Score de talk ratio (0-100)
- Comparativo com benchmarks e média do squad

## Integração
- Recebe dados do **speaker-segmentation** (quem fala quando)
- Recebe dados da **stage-segmentation-engine** (etapas da call)
- Alimenta o **scorecard-engine** (talk ratio como componente de cada bloco)
- Alimenta relatórios semanais (tendência de talk ratio do closer)
- Alimenta o **closer-maturity-engine** (evolução de talk ratio ao longo do tempo)
