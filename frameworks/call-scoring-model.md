# Call Scoring Model — Modelo de Pontuação de Call

> Sistema de 100 pontos divididos em 10 blocos com pesos definidos. Score objetivo antes de conselho subjetivo.

## Origem

Framework de avaliação padronizado inspirado em modelos de quality assurance (QA) de call centers e adaptado para vendas consultivas de high-ticket. Combina métricas quantitativas (talk ratio, tempo) com qualitativas (qualidade de perguntas, pitch amarrado). O modelo garante avaliação consistente entre diferentes analistas e calls.

## Conceito Central

Toda call recebe um score de 0 a 100 pontos, distribuídos em 10 blocos. Cada bloco tem peso definido baseado no impacto que tem no resultado da venda. O score é calculado ANTES de qualquer feedback — isso garante objetividade.

A filosofia é: primeiro medir, depois aconselhar. Um closer com score 85 precisa de fine-tuning. Um closer com score 45 precisa de reconstrução fundamental. O conselho muda radicalmente baseado no score.

## Fase da Call Onde se Aplica

**Análise pós-call**. O scoring é feito após a call usando transcrição e/ou áudio. Serve como base para feedback, coaching e tracking de evolução.

## Como Funciona

### Os 10 Blocos de Avaliação

**Bloco 1 — Abertura e Frame (10 pontos)**
- First Pact executado (0-4)
- Tom de liderança (0-3)
- Concordância do lead (0-3)

**Bloco 2 — Rapport e Conexão (8 pontos)**
- Conexão genuína estabelecida (0-4)
- Lead engajado e confortável (0-4)

**Bloco 3 — Discovery / Diagnóstico (15 pontos)**
- Perguntas de situação (limitadas) (0-3)
- Perguntas de problema (profundas) (0-4)
- Perguntas de implicação/consequência (0-4)
- Need-Payoff / Visualização (0-4)

**Bloco 4 — Escuta Ativa e Talk Ratio (10 pontos)**
- Talk ratio adequado por fase (0-4)
- Perguntas abertas predominantes (0-3)
- Silêncios estratégicos (0-3)

**Bloco 5 — Transição e Pitch Bridge (12 pontos)**
- Resumo diagnóstico antes do pitch (0-4)
- Palavras exatas do lead utilizadas (0-4)
- Product Pact obtido (0-4)

**Bloco 6 — Apresentação da Oferta (12 pontos)**
- Value stacking executado (0-4)
- Cada componente amarrado a uma dor (0-4)
- Micro-confirmações obtidas (0-4)

**Bloco 7 — Preço e Ancoragem (10 pontos)**
- Ancoragem feita antes do preço (0-4)
- Preço apresentado com confiança (0-3)
- Contraste valor vs. preço criado (0-3)

**Bloco 8 — Tratamento de Objeções (10 pontos)**
- Objeção isolada antes de contornar (0-4)
- Looping com argumentos novos (0-3)
- Tom mantido empático (0-3)

**Bloco 9 — Fechamento (8 pontos)**
- Second Pact referenciado (0-3)
- Tentativa de fechamento clara (0-3)
- Urgência genuína criada (0-2)

**Bloco 10 — Profissionalismo Geral (5 pontos)**
- Tom de voz adequado por fase (0-2)
- Sem interrupções desnecessárias (0-2)
- Encerramento profissional (0-1)

### Escala de Classificação

| Faixa | Classificação | Ação |
|-------|--------------|------|
| 90-100 | Excelente | Replicar como exemplo |
| 80-89 | Muito Bom | Fine-tuning específico |
| 70-79 | Bom | Coaching focado em 2-3 blocos |
| 60-69 | Regular | Treinamento intensivo necessário |
| 50-59 | Fraco | Reconstrução de fundamentos |
| <50 | Crítico | Revisão completa do processo |

## Aplicação Prática na Call

O analista (IA ou humano) avalia a call bloco por bloco, atribuindo pontos com justificativa. O resultado é um scorecard com:

1. Score total e classificação
2. Score por bloco com justificativa
3. Top 3 pontos fortes
4. Top 3 áreas de melhoria
5. Comparação com média do closer
6. Comparação com média da equipe

## Sinais de Boa Execução

- Scores consistentes entre diferentes analistas para a mesma call — modelo é objetivo
- Closer melhora score ao longo do tempo — coaching está funcionando
- Correlação entre score alto e conversão — modelo mede o que importa
- Feedback baseado em score é aceito sem defensividade — números são objetivos

## Sinais de Falha

- Scores variam muito entre analistas — critérios não são claros
- Score alto mas conversão baixa — modelo não mede o que importa
- Closer não melhora apesar do coaching — feedback não é acionável
- Score tratado como punição, não ferramenta — cultura errada

## Critérios de Avaliação no Scorecard

| Critério | Peso | Evidência esperada |
|----------|------|-------------------|
| Todos os 10 blocos avaliados | 3 | Cobertura completa |
| Justificativa por bloco | 3 | Evidência específica da transcrição |
| Score consistente e defensável | 3 | Outro analista chegaria ao mesmo resultado |
| Recomendações priorizadas | 2 | Top 3 ações ordenadas por impacto |
| Comparação histórica | 1 | Evolução do closer ao longo do tempo |

## Frameworks Complementares

- **Minute-by-Minute Analysis** — Alimenta o scoring com análise temporal detalhada
- **Talk Ratio Analysis** — Dados para Bloco 4
- **Win-Loss Pattern Mining** — Correlaciona scores com resultados
- **Sales Call Stage Taxonomy** — Define o que cada fase deveria conter

## Exemplo de Evidência na Transcrição

```
SCORECARD — Call #247 — Closer: Ricardo — Lead: João
Data: 2024-03-15 — Resultado: FECHADO

Bloco 1 — Abertura/Frame:      8/10  ✓ First Pact forte, tom de liderança
Bloco 2 — Rapport:             7/8   ✓ Conexão natural, lead confortável
Bloco 3 — Discovery:           12/15 ~ Bom SPIN, faltou implicação na dor 2
Bloco 4 — Escuta/Talk Ratio:   8/10  ✓ 32% closer, silêncios bem usados
Bloco 5 — Transição/Bridge:    10/12 ✓ Palavras do lead usadas, Product Pact ok
Bloco 6 — Oferta:              9/12  ~ Value stacking bom, faltou micro-confirmação
Bloco 7 — Preço/Ancoragem:     8/10  ✓ Âncora de custo + valor
Bloco 8 — Objeções:            7/10  ~ Isolou, mas loop 2 repetiu argumento
Bloco 9 — Fechamento:          7/8   ✓ Referenciou pacto, fechou no loop 2
Bloco 10 — Profissionalismo:   5/5   ✓ Tom excelente, sem interrupções

TOTAL: 81/100 — MUITO BOM
→ Recomendação principal: Aprofundar implicações no discovery e variar argumentos nos loops de objeção.
```

## Erros Comuns

1. **Score subjetivo sem critério** — "Eu acho que foi uma call 7/10" sem base definida. Cada ponto precisa ter evidência.
2. **Todos os blocos com mesmo peso** — Frame e Discovery impactam mais que Profissionalismo. Os pesos refletem importância real.
3. **Não calibrar entre analistas** — Se dois analistas dão scores muito diferentes para a mesma call, os critérios precisam ser calibrados.
4. **Score sem ação** — Dar nota sem recomendação acionável. O score sozinho não gera melhoria.
5. **Foco só no score total** — O detalhamento por bloco é mais útil que o número final. Um closer pode ter 75 total mas com score 4/15 no discovery — isso é o que precisa ser trabalhado.
