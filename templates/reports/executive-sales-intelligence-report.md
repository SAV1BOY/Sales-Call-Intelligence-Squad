# Dashboard Executivo de Sales Intelligence

> Relatório executivo com KPIs consolidados, tendências e ações recomendadas para liderança.

## Quando Usar
Relatório mensal (ou quinzenal) para C-Level e diretoria de vendas, consolidando a inteligência extraída de todas as calls do período.

## Estrutura

### Seção 1 — KPIs do Período
Números-chave em formato de dashboard.
**Formato**:
```
PERÍODO: [DD/MM a DD/MM/AAAA]

📊 VOLUME E RESULTADO
| KPI                    | Atual   | Anterior | Delta    | Meta     | Status |
|------------------------|---------|----------|----------|----------|--------|
| Calls Realizadas       | [N]     | [N]      | [+/-N]   | [N]      | [🟢/🔴]|
| Calls Auditadas        | [N]     | [N]      | [+/-N]   | [N]      | [🟢/🔴]|
| Taxa de Conversão      | [XX%]   | [XX%]    | [+/-Xpp] | [XX%]    | [🟢/🔴]|
| Revenue                | [R$ X]  | [R$ X]   | [+/-XX%] | [R$ X]   | [🟢/🔴]|
| Ticket Médio           | [R$ X]  | [R$ X]   | [+/-XX%] | [R$ X]   | [🟢/🔴]|
| Ciclo de Venda (dias)  | [N]     | [N]      | [+/-N]   | [N]      | [🟢/🔴]|

📈 QUALIDADE
| KPI                       | Atual | Anterior | Delta   | Meta  | Status |
|----------------------------|-------|----------|---------|-------|--------|
| Score Médio de Qualidade   | [XX]  | [XX]     | [+/-X]  | [XX]  | [🟢/🔴]|
| % Calls Excelentes (85+)  | [XX%] | [XX%]    | [+/-Xpp]| [XX%] | [🟢/🔴]|
| % Calls Críticas (<55)    | [XX%] | [XX%]    | [+/-Xpp]| [<X%] | [🟢/🔴]|
| Taxa de Objeção Tratada   | [XX%] | [XX%]    | [+/-Xpp]| [XX%] | [🟢/🔴]|
```

### Seção 2 — Tendências
Movimentos relevantes ao longo do tempo.
**Formato**:
```
TENDÊNCIA #1: [título — ex: "Quality Score em alta pelo 3o mês consecutivo"]
Dados: [série temporal resumida]
Causa Provável: [hipótese baseada em evidência]
Projeção: [se mantiver, resultado estimado]

TENDÊNCIA #2: [mesmo formato]
TENDÊNCIA #3: [mesmo formato]
```

### Seção 3 — Ranking do Time
Performance comparativa dos closers.
**Formato**:
```
| Rank | Closer    | Score | Conversão | Revenue    | Tendência | Ação          |
|------|-----------|-------|-----------|------------|-----------|---------------|
| 1    | [Nome]    | [XX]  | [XX%]     | [R$ X.XXX] | [↑/→/↓]  | [manter/focar]|
| 2    | [Nome]    | [XX]  | [XX%]     | [R$ X.XXX] | [↑/→/↓]  | [manter/focar]|
...
```

### Seção 4 — Insights de Mercado
Inteligência extraída das calls sobre mercado, concorrência e produto.
**Formato**:
```
INSIGHT DE MERCADO #1: [achado — ex: "40% dos leads mencionam concorrente X"]
Implicação: [o que isso significa para o negócio]
Ação Sugerida: [para qual squad/área]

INSIGHT DE MERCADO #2: [mesmo formato]
```

### Seção 5 — Alertas e Riscos
Sinais que exigem atenção da liderança.
**Formato**:
```
🔴 ALERTA CRÍTICO: [descrição — ação imediata necessária]
🟡 ATENÇÃO: [descrição — monitorar]
🟢 OPORTUNIDADE: [descrição — potencial de ganho]
```

### Seção 6 — Ações Recomendadas
Top 5 ações de maior impacto para o próximo período.
**Formato**:
```
| # | Ação                          | Impacto Estimado | Responsável | Prazo  |
|---|-------------------------------|------------------|-------------|--------|
| 1 | [ação]                        | [R$ ou %]        | [nome/squad]| [DD/MM]|
| 2 | [ação]                        | [R$ ou %]        | [nome/squad]| [DD/MM]|
| 3 | [ação]                        | [R$ ou %]        | [nome/squad]| [DD/MM]|
| 4 | [ação]                        | [R$ ou %]        | [nome/squad]| [DD/MM]|
| 5 | [ação]                        | [R$ ou %]        | [nome/squad]| [DD/MM]|
```

## Exemplo
```
PERÍODO: Mar/2026

Calls: 128 (+8%) | Conversão: 31% (+2pp) | Revenue: R$ 892k (+15%)
Score Médio: 74 (+3) | Excelentes: 18% (+5pp) | Críticas: 8% (-3pp)

TENDÊNCIA: Score subindo 3 pontos/mês desde Jan — coaching de discovery está funcionando
ALERTA: Ticket médio caiu 7% — closers dando desconto sem necessidade em 34% das calls
OPORTUNIDADE: Leads de Google Ads convertem 2x mais que Meta — realocar budget

AÇÃO #1: Treinamento de firmeza de preço → impacto estimado +R$ 45k/mês
```

## Agente Responsável
`orchestrator-agent` — Consolida dados de todos os agentes para o relatório executivo.

## Checklists de Qualidade
- `qa-score-calibration-check.md` — KPIs baseados em scores calibrados.
- `qa-bias-detection-check.md` — Tendências sem viés de interpretação.

## Preenchido Por

- **Task(s)**: analyze-offer-fit, weekly-sales-quality-review
- **Agente(s) responsável(is)**: offer-fit-analyst, revenue-intelligence-analyst, sales-chief, scorecard-analyst, closer-trainer
- **Workflow(s)**: Intelligence — Análise de Fit de Oferta (quarterly), Review Semanal de Qualidade (weekly)
- **Frequência**: weekly / quarterly
- **Registro**: data/registries/deal-risk-registry, data/registries/lessons-learned-registry
