# Relatório Completo de Auditoria de Call

> Relatório abrangente que cobre score, detecção de framework, análise minuto a minuto, causa raiz, rewrites e recomendações de coaching.

## Quando Usar
Para toda auditoria padrão de call de vendas. Este é o relatório principal e mais completo do squad.

## Estrutura

### Seção 1 — Resumo Executivo
Visão geral em 30 segundos para o gestor.
**Formato**:
```
Call ID: [ID] | Closer: [nome] | Data: [DD/MM/AAAA]
Lead: [nome — empresa] | Oferta: [produto] | Ticket: [R$ XX.XXX]
Resultado: [Vendeu / Não Vendeu] | Duração: [MM:SS]

SCORE TOTAL: [XX/100]
Classificação: [Excelente (85+) / Bom (70-84) / Mediano (55-69) / Crítico (<55)]

Pontos Fortes: [2-3 destaques positivos em 1 linha cada]
Pontos Críticos: [2-3 problemas principais em 1 linha cada]
Veredicto: [frase-resumo — ex: "Discovery forte mas pricing mal executado custou o deal"]
```

### Seção 2 — Scorecard Detalhado
Pontuação por bloco com evidência.
**Formato**:
```
| #  | Bloco                    | Peso | Score | Evidência Resumida                     |
|----|--------------------------|------|-------|----------------------------------------|
| 1  | Abertura e Rapport       | 10   | [X]   | [1 frase com timestamp]                |
| 2  | Qualificação Inicial     | 10   | [X]   | [1 frase com timestamp]                |
| 3  | Discovery Profunda       | 15   | [X]   | [1 frase com timestamp]                |
| 4  | Apresentação de Valor    | 10   | [X]   | [1 frase com timestamp]                |
| 5  | Prova Social/Autoridade  | 10   | [X]   | [1 frase com timestamp]                |
| 6  | Ancoragem de Preço       | 10   | [X]   | [1 frase com timestamp]                |
| 7  | Tratamento de Objeções   | 15   | [X]   | [1 frase com timestamp]                |
| 8  | Fechamento               | 10   | [X]   | [1 frase com timestamp]                |
| 9  | Next Step Lock           | 5    | [X]   | [1 frase com timestamp]                |
| 10 | Controle de Frame        | 5    | [X]   | [1 frase com timestamp]                |
|    | TOTAL                    | 100  | [XX]  |                                        |
```

### Seção 3 — Frameworks Detectados
Quais metodologias o closer utilizou (consciente ou inconscientemente).
**Formato**:
```
Frameworks Detectados:
- [Framework] — [momento da call] — [qualidade de execução: Alta/Média/Baixa]

Frameworks Esperados mas Ausentes:
- [Framework] — [momento onde deveria ter sido aplicado] — [impacto da ausência]
```

### Seção 4 — Análise Minuto a Minuto
Momentos-chave da call em ordem cronológica.
**Formato**:
```
[MM:SS] - [FASE DA CALL]
O que aconteceu: [descrição factual]
Fala do Closer: "[trecho]"
Fala do Lead: "[trecho]"
Avaliação: [Positivo ✓ / Negativo ✗ / Neutro —]
Framework: [qual técnica foi ou deveria ter sido usada]
Nota: [comentário analítico breve]
```

### Seção 5 — Análise de Causa Raiz
Por que o resultado aconteceu (ganhou ou perdeu).
**Formato**:
```
Resultado: [ganhou/perdeu]
Causa Raiz Principal: [descrição — ex: "Discovery superficial gerou apresentação genérica"]
Cadeia Causal: [A levou a B, que levou a C, que resultou em D]
Momento Decisivo: [MM:SS — o que aconteceu neste momento que definiu o resultado]
Evidência: [trechos que comprovam a cadeia causal]
```

### Seção 6 — Rewrites
Sugestões de falas alternativas para os momentos críticos.
**Formato**:
```
REWRITE #1 — [Momento MM:SS]
ANTES (o que foi dito):
"[fala original do closer]"

DEPOIS (o que deveria ter sido dito):
"[fala reescrita]"

Framework: [técnica de referência]
Justificativa: [por que a nova versão é melhor]
```

### Seção 7 — Recomendações de Coaching
Ações para desenvolvimento do closer.
**Formato**:
```
PRIORIDADE 1: [competência]
- Gap: [o que falta]
- Ação: [o que fazer]
- Exercício: [como praticar]
- Meta: [critério de sucesso]

PRIORIDADE 2: [mesmo formato]
PRIORIDADE 3: [mesmo formato]
```

## Exemplo
```
CALL-2026-0342 | Rafael Mendes | 18/03/2026
Lead: Carla Souza — TechFlow | Mentoria Premium | R$ 12.000
Resultado: Não Vendeu | 47:22

SCORE: 64/100 — Mediano
Pontos Fortes: Rapport natural (9/10), prova social convincente (8/10)
Pontos Críticos: Discovery rasa (5/15), pricing sem ancoragem (4/10)
Veredicto: "Rapport excelente desperdiçado por discovery que não revelou dor real"

Causa Raiz: Pulou para apresentação aos 11min sem explorar consequência da dor
Momento Decisivo: 32:15 — Lead disse "tá caro" sem ter sentido urgência
```

## Agente Responsável
`audit-agent` — Executa a auditoria completa. `qa-agent` — Valida a qualidade do relatório.

## Checklists de Qualidade
- `qa-methodology-consistency-check.md`
- `qa-evidence-completeness-check.md`
- `qa-score-calibration-check.md`
- `qa-bias-detection-check.md`

## Preenchido Por

- **Task(s)**: full-call-audit, analyze-rapport-and-frame, analyze-discovery, analyze-pitch, analyze-closing, analyze-talk-ratio
- **Agente(s) responsável(is)**: call-auditor, framework-detector, scorecard-analyst, objection-specialist, pricing-anchoring-analyst, talk-ratio-analyst, cole-gordon, dan-lok, neil-rackham, jeremy-miner, alex-hormozi, sabri-suby, jordan-belfort
- **Workflow(s)**: Auditoria Completa + Análise por Fase da Call (pipeline per-call)
- **Frequência**: per-call
- **Registro**: data/registries/scorecards-registry, data/registries/framework-detection-registry, data/registries/deal-risk-registry
