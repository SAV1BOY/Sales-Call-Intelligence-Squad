# Relatório de Análise de Pricing

> Relatório que avalia a execução da apresentação de preço — ancoragem, value stack, concessões e impacto no resultado.

## Quando Usar
Como componente da auditoria completa, ou isoladamente quando o foco é avaliar a estratégia de pricing do closer.

## Estrutura

### Seção 1 — Resumo de Pricing
Visão geral da execução de pricing na call.
**Formato**:
```
Call ID: [ID] | Closer: [nome] | Resultado: [vendeu/não vendeu]
Ticket Apresentado: [R$ XX.XXX]
Ticket Fechado: [R$ XX.XXX ou N/A]
Desconto Concedido: [XX% ou "nenhum"]
Momento da Revelação de Preço: [MM:SS] ([XX%] da call)
Score do Bloco de Pricing: [X/10]
```

### Seção 2 — Pré-Pricing: Construção de Valor
O que aconteceu antes de revelar o preço.
**Formato**:
```
DISCOVERY DE VALOR:
- O closer identificou o custo do problema? [Sim/Não]
  - Trecho: "[fala do lead quantificando a dor]" ([MM:SS])
- O lead verbalizou o valor da solução? [Sim/Não]
  - Trecho: "[fala do lead expressando desejo de resolver]" ([MM:SS])
- Houve âncora de valor antes do preço? [Sim/Não]
  - Tipo: [ROI projetado / custo da inação / comparação externa / valor do pacote]
  - Trecho: "[fala do closer ancorando]" ([MM:SS])

AVALIAÇÃO PRÉ-PRICING:
- Valor construído suficiente antes de revelar preço: [Sim / Não / Parcialmente]
- Timing da revelação: [Precoce / Adequado / Tardio]
- Justificativa: [por que este timing foi bom ou ruim]
```

### Seção 3 — Momento da Revelação de Preço
Análise do momento exato.
**Formato**:
```
TIMESTAMP: [MM:SS]
TÉCNICA DE REVELAÇÃO:
- Tipo: [Sanduíche (benefício-preço-benefício) / Direto / Comparativo / Contraste]
- Execução: [Alta / Média / Baixa]

FALA DO CLOSER:
"[transcrição exata do momento de revelação de preço]"

REAÇÃO DO LEAD:
"[transcrição exata da reação]"
Tipo de Reação: [Aceitação / Hesitação / Choque / Objeção direta / Silêncio]
Linguagem Corporal/Tom: [se observável — tom mudou, pausa longa, etc.]

AVALIAÇÃO:
- Ancoragem eficaz: [Sim / Não] — [justificativa]
- Value stack apresentado: [Sim / Não] — [componentes listados vs. não listados]
- Preço contextualizado: [Sim / Não] — [ex: "por dia", "comparado a X"]
```

### Seção 4 — Value Stack
Análise do empilhamento de valor.
**Formato**:
```
| Componente do Value Stack  | Apresentado | Valor Atribuído | Reação do Lead |
|----------------------------|-------------|-----------------|----------------|
| [Componente 1]             | [Sim/Não]   | [R$ X.XXX]      | [reação]       |
| [Componente 2]             | [Sim/Não]   | [R$ X.XXX]      | [reação]       |
| [Bônus 1]                  | [Sim/Não]   | [R$ X.XXX]      | [reação]       |
| [Garantia]                 | [Sim/Não]   | [descrição]      | [reação]       |

Valor Total Empilhado: [R$ XX.XXX]
Preço Apresentado: [R$ XX.XXX]
Ratio Value/Price: [X:1]
Ratio Ideal: [3:1 a 10:1]
```

### Seção 5 — Concessões e Negociação
O que foi cedido e como.
**Formato**:
```
CONCESSÕES REALIZADAS:
| Concessão              | Valor    | Motivo              | Contrapartida Exigida | Avaliação      |
|------------------------|----------|---------------------|-----------------------|----------------|
| [desconto / bônus]     | [R$ X]   | [por que concedeu]  | [o que pediu em troca] | [Boa/Ruim]    |

ANÁLISE:
- Concessões justificadas: [Sim / Não]
- Manteve firmeza de preço: [Sim / Não / Parcialmente]
- Usou concessão como alavanca: [Sim / Não] — [como]
- Descontou sem necessidade: [Sim / Não] — [evidência]
```

### Seção 6 — Recomendações
Melhorias específicas para pricing.
**Formato**:
```
1. [Recomendação com rewrite específico]
2. [Recomendação com rewrite específico]
3. [Recomendação com rewrite específico]
```

## Exemplo
```
CALL-2026-0342 | Rafael | Não Vendeu | R$ 12.000
Revelação: 32:15 (68% da call) | Score: 4/10

PRÉ-PRICING: Custo do problema não quantificado. Lead não verbalizou valor.
Âncora: Nenhuma — preço revelado "solto" sem contexto.

REVELAÇÃO: "Então, o investimento é de 12 mil, que pode ser em 12x de mil..."
Reação: Silêncio de 4 segundos seguido de "hmm, preciso pensar"

Value Stack: 2 de 5 componentes apresentados. Ratio 1.5:1 (ideal 3:1+)
Concessão: Ofereceu desconto de 10% sem o lead pedir — sinal de insegurança

Recomendação 1: Quantificar o custo da inação antes de revelar preço
Recomendação 2: Apresentar value stack completo antes do número
Recomendação 3: Nunca oferecer desconto proativamente
```

## Agente Responsável
`audit-agent` — Analisa pricing como parte da auditoria.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Todos os momentos de pricing documentados.
- `coaching-actionability-check.md` — Recomendações acionáveis.

## Preenchido Por

- **Task(s)**: analyze-pricing
- **Agente(s) responsável(is)**: pricing-anchoring-analyst, alex-hormozi, sabri-suby
- **Workflow(s)**: Análise por Fase da Call — Pricing (pipeline per-call)
- **Frequência**: per-call
- **Registro**: data/registries/pricing-concessions-registry
