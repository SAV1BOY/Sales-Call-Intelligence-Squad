# Relatório de Análise Win/Loss

> Relatório que identifica padrões sistemáticos em calls ganhas vs. perdidas para descobrir o que diferencia vitórias de derrotas.

## Quando Usar
Análise periódica (mensal ou quinzenal) para identificar padrões replicáveis de vitória e armadilhas recorrentes de derrota.

## Estrutura

### Seção 1 — Resumo do Período
Dados gerais do período analisado.
**Formato**:
```
Período: [DD/MM a DD/MM/AAAA]
Total de Calls Analisadas: [N]
Calls Ganhas: [N] ([XX%])
Calls Perdidas: [N] ([XX%])
Revenue Gerado: [R$ XXX.XXX]
Revenue Perdido Estimado: [R$ XXX.XXX]
Ticket Médio — Ganhas: [R$ XX.XXX]
Ticket Médio — Oportunidades Perdidas: [R$ XX.XXX]
```

### Seção 2 — Padrões de Vitória
O que as calls ganhas têm em comum.
**Formato**:
```
PADRÃO DE VITÓRIA #[N]:
- Descrição: [o que acontece — ex: "Discovery com mínimo 3 perguntas de consequência"]
- Frequência em Calls Ganhas: [XX%]
- Frequência em Calls Perdidas: [XX%]
- Delta: [diferença percentual]
- Evidências:
  - Call [ID] — [MM:SS]: "[trecho]"
  - Call [ID] — [MM:SS]: "[trecho]"
- Impacto Estimado: [correlação com resultado]
- Recomendação: [como replicar este padrão]
```

### Seção 3 — Padrões de Derrota
O que as calls perdidas têm em comum.
**Formato**:
```
PADRÃO DE DERROTA #[N]:
- Descrição: [o que acontece — ex: "Preço revelado antes de value stack"]
- Frequência em Calls Perdidas: [XX%]
- Frequência em Calls Ganhas: [XX%]
- Delta: [diferença percentual]
- Evidências:
  - Call [ID] — [MM:SS]: "[trecho]"
- Impacto Estimado: [correlação com resultado]
- Recomendação: [como evitar este padrão]
```

### Seção 4 — Análise Comparativa
Métricas lado a lado.
**Formato**:
```
| Métrica                           | Calls Ganhas | Calls Perdidas | Diferença |
|-----------------------------------|-------------|----------------|-----------|
| Score médio                       | [XX]        | [XX]           | [+/-XX]   |
| Duração média                     | [MM:SS]     | [MM:SS]        | [+/-MM]   |
| Tempo em discovery (%)            | [XX%]       | [XX%]          | [+/-XX%]  |
| Perguntas abertas (média)         | [N]         | [N]            | [+/-N]    |
| Objeções tratadas com sucesso (%) | [XX%]       | [XX%]          | [+/-XX%]  |
| Value stack completo (%)          | [XX%]       | [XX%]          | [+/-XX%]  |
| Next step lock (%)                | [XX%]       | [XX%]          | [+/-XX%]  |
| Tempo falando closer vs. lead     | [XX/XX%]    | [XX/XX%]       | [delta]   |
```

### Seção 5 — Motivos de Perda
Categorização dos motivos declarados e reais.
**Formato**:
```
| Motivo Declarado        | Frequência | Motivo Real (Root Cause)              | Frequência |
|-------------------------|------------|---------------------------------------|------------|
| "Preciso pensar"        | [XX%]      | [Discovery insuficiente / Sem urgência]| [XX%]     |
| "Tá caro"              | [XX%]      | [Valor não construído / Ancoragem fraca]| [XX%]    |
| "Vou ver com meu sócio" | [XX%]      | [Decisor não identificado / Sem BANT]  | [XX%]    |
```

### Seção 6 — Insights Acionáveis
Top 3 ações de maior impacto.
**Formato**:
```
INSIGHT #1: [descoberta principal]
Ação: [o que fazer]
Impacto Projetado: [estimativa de ganho]
Responsável: [quem executa]

INSIGHT #2: [mesmo formato]
INSIGHT #3: [mesmo formato]
```

## Exemplo
```
Período: Mar/2026 | 48 calls | 14 ganhas (29%) | 34 perdidas (71%)
Revenue: R$ 198.000 | Perdido: R$ 476.000

PADRÃO DE VITÓRIA #1: Discovery com pergunta de consequência
- Ganhas: 86% | Perdidas: 24% | Delta: 62pp
- Closers que perguntam "e o que acontece se não resolver?" convertem 3x mais

PADRÃO DE DERROTA #1: Preço antes de value stack
- Perdidas: 71% | Ganhas: 7% | Delta: 64pp
- Revelação prematura de preço é o preditor #1 de perda

INSIGHT: Se eliminarmos revelação prematura de preço, estimamos +8 deals/mês = +R$ 112.000
```

## Agente Responsável
`audit-agent` — Executa mineração de padrões. `coaching-agent` — Transforma em treinamento.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Padrões com evidência.
- `qa-bias-detection-check.md` — Sem viés de resultado.
- `qa-score-calibration-check.md` — Scores confiáveis para comparação.

## Preenchido Por

- **Task(s)**: extract-win-patterns, extract-loss-patterns
- **Agente(s) responsável(is)**: win-loss-miner, revenue-intelligence-analyst, framework-detector, deal-risk-doctor, sdr-handoff-analyst, offer-fit-analyst
- **Workflow(s)**: Intelligence — Mineração de Padrões de Vitória e Derrota (monthly)
- **Frequência**: monthly
- **Registro**: data/registries/win-patterns-registry, data/registries/loss-patterns-registry, data/registries/deal-risk-registry
