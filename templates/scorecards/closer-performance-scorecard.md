# Scorecard de Performance do Closer

> Scorecard consolidado que mostra a performance média do closer ao longo do tempo, com evolução, benchmarks e comparação com o time.

## Quando Usar
Em reviews de performance, planejamento de coaching e avaliações periódicas do closer.

## Estrutura

### Seção 1 — Identificação
Dados do closer e período.
**Formato**:
```
Closer: [nome completo]
Período de Avaliação: [DD/MM a DD/MM/AAAA]
Calls Auditadas no Período: [N]
Gestor: [nome]
```

### Seção 2 — Score Consolidado
Médias por bloco com evolução.
**Formato**:
```
| Bloco                    | Média  | Mín  | Máx  | Período Ant. | Delta  | Benchmark Time |
|--------------------------|--------|------|------|--------------|--------|----------------|
| Abertura e Rapport       | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Qualificação Inicial     | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Discovery Profunda       | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Apresentação de Valor    | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Prova Social/Autoridade  | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Ancoragem de Preço       | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Tratamento de Objeções   | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Fechamento               | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Next Step Lock           | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| Controle de Frame        | [X.X]  | [X]  | [X]  | [X.X]        | [+/-X] | [X.X]          |
| TOTAL                    | [XX.X] |      |      | [XX.X]       | [+/-X] | [XX.X]         |
```

### Seção 3 — Métricas de Resultado
Correlação entre qualidade e resultado comercial.
**Formato**:
```
| Métrica                 | Atual   | Anterior | Delta    | Meta     | Benchmark |
|-------------------------|---------|----------|----------|----------|-----------|
| Taxa de Conversão       | [XX%]   | [XX%]    | [+/-Xpp] | [XX%]    | [XX%]     |
| Ticket Médio            | [R$ X]  | [R$ X]   | [+/-X%]  | [R$ X]   | [R$ X]    |
| Revenue Total           | [R$ X]  | [R$ X]   | [+/-X%]  | [R$ X]   | [R$ X]    |
| Calls por Semana        | [N]     | [N]      | [+/-N]   | [N]      | [N]       |
| No-show Rate            | [XX%]   | [XX%]    | [+/-Xpp] | [<XX%]   | [XX%]     |
| Ciclo Médio (dias)      | [N]     | [N]      | [+/-N]   | [N]      | [N]       |
```

### Seção 4 — Evolução Temporal
Série histórica dos últimos períodos.
**Formato**:
```
| Período    | Score | Conversão | Ticket Médio | Calls | Tendência |
|------------|-------|-----------|--------------|-------|-----------|
| [Sem/Mês]  | [XX]  | [XX%]     | [R$ X.XXX]   | [N]   | —         |
| [Sem/Mês]  | [XX]  | [XX%]     | [R$ X.XXX]   | [N]   | [↑/→/↓]  |
| [Sem/Mês]  | [XX]  | [XX%]     | [R$ X.XXX]   | [N]   | [↑/→/↓]  |
| [Sem/Mês]  | [XX]  | [XX%]     | [R$ X.XXX]   | [N]   | [↑/→/↓]  |

Tendência Geral: [Ascendente / Estável / Descendente]
Consistência (Desvio Padrão): [X.X] — [Alta (<5) / Média (5-10) / Baixa (>10)]
```

### Seção 5 — Posição no Time
Ranking e comparação.
**Formato**:
```
Posição no Ranking: [X de Y closers]
Percentil: [top XX%]
Distância para o #1: [+/-X pontos]
Distância para a média: [+/-X pontos]

Destaque vs. Time: [em que bloco está acima da média — e quanto]
Gap vs. Time: [em que bloco está abaixo da média — e quanto]
```

### Seção 6 — Diagnóstico e Recomendação
Síntese analítica.
**Formato**:
```
Perfil do Closer: [descrição em 2-3 linhas — estilo, forças, padrão de comportamento]
Principal Alavanca de Crescimento: [o bloco/competência que mais impactaria se melhorasse]
Risco: [se houver — ex: "burnout por volume alto", "estagnação de score"]
Recomendação: [ação principal para o próximo período]
```

## Exemplo
```
Closer: Rafael Mendes | Mar/2026 | 16 calls auditadas
Score Médio: 72/100 (anterior: 68, +4) | Conversão: 28% | Ranking: 3/7

Fortes: Rapport (8.8/10), Prova Social (8.2/10)
Fracos: Discovery (6.1/15), Pricing (4.9/10)
Tendência: Ascendente — 3o mês consecutivo de melhora
Alavanca: Discovery — se subir de 6 para 10, estimativa de +15pp em conversão
```

## Agente Responsável
`coaching-agent` — Compila o scorecard consolidado a partir das auditorias individuais.

## Checklists de Qualidade
- `coaching-progression-check.md` — Evolução medida com rigor.
- `qa-score-calibration-check.md` — Scores base são confiáveis.

## Preenchido Por

- **Task(s)**: build-coaching-pack, monthly-closer-certification
- **Agente(s) responsável(is)**: closer-trainer, scorecard-analyst, sales-chief, qa-guardian
- **Workflow(s)**: Coaching (per-call), Certificação Mensal de Closers (monthly)
- **Frequência**: per-call / monthly
- **Registro**: data/registries/lessons-learned-registry, data/registries/closers-registry
