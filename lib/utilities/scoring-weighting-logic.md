# Lógica de Pesos do Scoring

> Utilitário que define como os pesos de cada bloco do scorecard são calculados e como ajustá-los por operação.

## Função
Documentar a lógica matemática de ponderação do scorecard e os critérios para ajustar pesos conforme a operação.

## Pesos Padrão (Configuração Base)
| Bloco | Peso Padrão | Justificativa |
|-------|-------------|---------------|
| Abertura | 10% | Importante mas raramente é fator decisivo de conversão |
| Discovery | 25% | Bloco mais impactante na taxa de conversão. Discovery ruim compromete tudo |
| Pitch | 15% | Relevante mas depende da qualidade do discovery |
| Price Reveal | 15% | Momento crítico que pode perder o deal se mal executado |
| Objeção | 20% | Segundo bloco mais impactante. Objeção mal tratada = deal perdido |
| Fechamento | 15% | Importante mas se discovery e objeção foram bons, fechamento é consequência |

## Cálculo do Score Ponderado
1. Score bruto por bloco: avaliação de 0 a 100
2. Score ponderado por bloco: score_bruto * peso_bloco
3. Score total: soma de todos os scores ponderados
4. Aplicar penalizações: subtrair pontos por práticas proibidas
5. Aplicar bonificações: somar pontos por práticas exemplares
6. Normalizar para 0-100 se necessário (cap em 100)

## Exemplo de Cálculo
- Abertura: 80 * 0.10 = 8.0
- Discovery: 90 * 0.25 = 22.5
- Pitch: 75 * 0.15 = 11.25
- Price Reveal: 85 * 0.15 = 12.75
- Objeção: 70 * 0.20 = 14.0
- Fechamento: 88 * 0.15 = 13.2
- **Score total: 81.7**
- Penalização (monólogo de 5 min no pitch): -5
- **Score final: 76.7**

## Ajuste de Pesos por Operação
- Operações com alto ticket (acima de R$20k): aumentar peso de Objeção para 25%, reduzir Abertura para 5%
- Operações com lead frio: aumentar peso de Abertura para 15%, reduzir Pitch para 10%
- Operações com decisor múltiplo: criar bloco extra "Engajamento do Decisor" com peso 10%

## Regras de Penalização
- Prática proibida nível 1 (menor): -5 pontos (ex: monólogo acima de 3 min)
- Prática proibida nível 2 (médio): -10 pontos (ex: ignorar objeção)
- Prática proibida nível 3 (grave): -20 pontos (ex: manipulação emocional)

## Regras de Bonificação
- Prática exemplar nível 1: +3 pontos (ex: quantificação de dor)
- Prática exemplar nível 2: +5 pontos (ex: discovery com 4+ camadas)
- Prática exemplar nível 3: +10 pontos (ex: turnaround de objeção magistral)

## Integração
- Usado pelo **scorecard-engine** como configuração de pesos
- Configurável por gestores de squad via painel de administração
- Histórico de alterações de peso mantido para rastreabilidade
