# Scorecard de Qualidade do Time

> Scorecard consolidado do time de vendas com média, distribuição, outliers e comparação entre closers.

## Quando Usar
Em reuniões de review de time, planejamento mensal e apresentações para liderança sobre saúde do time comercial.

## Estrutura

### Seção 1 — Resumo do Time
Dados gerais consolidados.
**Formato**:
```
Time: [nome do time]
Período: [DD/MM a DD/MM/AAAA]
Total de Closers: [N]
Total de Calls Auditadas: [N]
Gestor: [nome]
```

### Seção 2 — Score Consolidado do Time
Média e distribuição por bloco.
**Formato**:
```
| Bloco                    | Média Time | Desvio | Melhor Closer  | Pior Closer   | Benchmark |
|--------------------------|------------|--------|----------------|---------------|-----------|
| Abertura e Rapport       | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Qualificação Inicial     | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Discovery Profunda       | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Apresentação de Valor    | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Prova Social/Autoridade  | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Ancoragem de Preço       | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Tratamento de Objeções   | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Fechamento               | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Next Step Lock           | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| Controle de Frame        | [X.X]      | [X.X]  | [Nome] ([X.X]) | [Nome] ([X.X])| [X.X]    |
| TOTAL                    | [XX.X]     | [X.X]  | [Nome] ([XX])  | [Nome] ([XX]) | [XX.X]   |
```

### Seção 3 — Distribuição de Scores
Como o time está distribuído.
**Formato**:
```
Excelente (85-100): [N closers] — [XX%] — Nomes: [lista]
Bom (70-84):        [N closers] — [XX%] — Nomes: [lista]
Mediano (55-69):    [N closers] — [XX%] — Nomes: [lista]
Crítico (<55):      [N closers] — [XX%] — Nomes: [lista]

Média: [XX.X]
Mediana: [XX]
Desvio Padrão: [X.X]
Amplitude: [mín]-[máx] = [range]
```

### Seção 4 — Ranking Individual
Performance comparativa completa.
**Formato**:
```
| Rank | Closer    | Score | Conversão | Revenue    | Calls | Tendência | Nível    |
|------|-----------|-------|-----------|------------|-------|-----------|----------|
| 1    | [Nome]    | [XX]  | [XX%]     | [R$ X.XXX] | [N]   | [↑/→/↓]  | [Sênior] |
| 2    | [Nome]    | [XX]  | [XX%]     | [R$ X.XXX] | [N]   | [↑/→/↓]  | [Pleno]  |
| ...  |           |       |           |            |       |           |          |
```

### Seção 5 — Outliers e Alertas
Situações que exigem atenção do gestor.
**Formato**:
```
OUTLIERS POSITIVOS (acima de 1.5 desvio padrão):
- [Nome]: [score] — [o que diferencia — competência excepcional em X]
  Recomendação: [mentor, case study, promoção]

OUTLIERS NEGATIVOS (abaixo de 1.5 desvio padrão):
- [Nome]: [score] — [gap principal — risco identificado]
  Recomendação: [coaching intensivo, acompanhamento, realocação]

ALERTAS DE TENDÊNCIA:
- [Nome]: [tendência descendente por X semanas consecutivas]
- [Nome]: [estagnação em score X por Y semanas]
```

### Seção 6 — Gaps Sistêmicos
Problemas que afetam o time todo (não individuais).
**Formato**:
```
GAP SISTÊMICO #1: [bloco com média abaixo do benchmark para TODOS os closers]
- Média do Time: [X.X] vs Benchmark: [X.X]
- Nenhum closer acima do benchmark neste bloco
- Causa Provável: [treinamento insuficiente / oferta mudou / processo falho]
- Ação: [treinamento coletivo / revisão de processo / intervenção específica]

GAP SISTÊMICO #2: [mesmo formato]
```

### Seção 7 — Plano de Ação do Time
Ações prioritárias para elevar a régua.
**Formato**:
```
| # | Ação                    | Tipo       | Impacto    | Responsável | Prazo  |
|---|-------------------------|------------|------------|-------------|--------|
| 1 | [ação coletiva]         | [Treino]   | [Alto]     | [nome]      | [DD/MM]|
| 2 | [ação individual]       | [Coaching] | [Médio]    | [nome]      | [DD/MM]|
| 3 | [ação de processo]      | [Processo] | [Alto]     | [nome]      | [DD/MM]|
```

## Exemplo
```
Time Sales HT | Mar/2026 | 7 closers | 48 calls auditadas
Média: 73.2 | Mediana: 74 | Desvio: 8.1

Distribuição: Excelente 1 (14%) | Bom 4 (57%) | Mediano 2 (29%) | Crítico 0

GAP SISTÊMICO: Ancoragem de Preço — média 5.8/10, nenhum closer acima de 7
Ação: Workshop coletivo de pricing com role-play — Marcos — 25/03

Outlier Positivo: Juliana (86) — discovery excepcional, mentor para o time
Outlier Negativo: Pedro (58) — 3a semana em queda, coaching intensivo ativado
```

## Agente Responsável
`orchestrator-agent` — Consolida dados de todos os closers.

## Checklists de Qualidade
- `qa-score-calibration-check.md` — Scores calibrados entre auditores/agentes.
- `qa-bias-detection-check.md` — Sem favorecimento individual.
