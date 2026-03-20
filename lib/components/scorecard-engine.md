# Engine de Scorecard

> Engine responsável por calcular o score de cada call analisada, aplicando pesos por bloco, normalização e classificação final.

## Função
Receber avaliações por bloco de uma call de vendas e calcular o score total ponderado, classificando a performance do closer.

## Inputs
- Avaliação individual de cada bloco (0-100): Abertura, Discovery, Pitch, Price Reveal, Objeção, Fechamento
- Peso de cada bloco (configurável por operação)
- Flags de penalização (práticas proibidas detectadas)
- Flags de bonificação (práticas exemplares detectadas)

## Lógica de Processamento
1. Receber scores brutos de cada bloco (6 blocos padrão)
2. Aplicar peso de cada bloco conforme configuração:
   - Abertura: peso 10% (padrão)
   - Discovery: peso 25% (padrão)
   - Pitch: peso 15% (padrão)
   - Price Reveal: peso 15% (padrão)
   - Objeção: peso 20% (padrão)
   - Fechamento: peso 15% (padrão)
3. Calcular score ponderado: soma de (score_bloco * peso_bloco)
4. Aplicar penalizações (-5 a -20 pontos por prática proibida detectada)
5. Aplicar bonificações (+3 a +10 pontos por prática exemplar detectada)
6. Normalizar resultado final para escala 0-100
7. Classificar: 0-40 (crítico), 41-60 (abaixo do esperado), 61-75 (adequado), 76-85 (bom), 86-100 (excelente)

## Outputs
- Score total ponderado (0-100)
- Score individual por bloco
- Classificação textual (crítico → excelente)
- Lista de penalizações aplicadas com justificativa
- Lista de bonificações aplicadas com justificativa
- Comparativo com média do squad e média histórica do closer

## Integração
- Recebe dados da **stage-segmentation-engine** (blocos identificados)
- Recebe dados da **framework-detection-engine** (frameworks encontrados)
- Recebe dados da **talk-ratio-engine** (métricas de fala)
- Alimenta o **closer-maturity-engine** com histórico de scores
- Alimenta relatórios semanais e dashboards executivos
- Alimenta o **deal-risk-scoring-engine** com score da call
