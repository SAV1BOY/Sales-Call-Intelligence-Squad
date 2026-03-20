# Brief de Ciclo de Coaching

> Documento de entrada para iniciar um novo ciclo de coaching com um closer, consolidando scores, prioridades e exercícios planejados.

## Quando Usar
No início de cada ciclo de coaching (semanal ou quinzenal), ao planejar o desenvolvimento de um closer com base nas auditorias recentes.

## Estrutura

### Seção 1 — Dados do Ciclo
Informações administrativas do ciclo.
**Formato**:
```
Closer: [nome completo]
Ciclo #: [número sequencial]
Período: [DD/MM a DD/MM/AAAA]
Cadência: [semanal / quinzenal]
Coach/Gestor: [nome]
Calls Base para Análise: [Call IDs usadas para definir prioridades]
```

### Seção 2 — Snapshot de Performance
Fotografia atual do closer.
**Formato**:
```
Score Médio Atual: [XX/100]
Score do Ciclo Anterior: [XX/100]
Delta: [+/-XX pontos]
Taxa de Conversão: [XX%]
Ticket Médio: [R$ XX.XXX]

Blocos Fortes: [top 3 blocos com score]
Blocos Fracos: [bottom 3 blocos com score]
```

### Seção 3 — Resultado do Ciclo Anterior
Avaliação do que foi trabalhado no ciclo passado.
**Formato**:
```
Prioridade 1 do Ciclo Anterior: [descrição]
→ Resultado: [Melhorou (+X pts) / Manteve / Piorou (-X pts)]
→ Evidência: [Call ID — Minuto — O que mudou]

Prioridade 2 do Ciclo Anterior: [descrição]
→ Resultado: [Melhorou / Manteve / Piorou]
→ Evidência: [Call ID — Minuto — O que mudou]

Exercícios Completados: [X de Y]
Observação: [notas sobre aderência e engajamento do closer]
```

### Seção 4 — Prioridades do Novo Ciclo
As top 3 prioridades para este ciclo.
**Formato**:
```
PRIORIDADE 1 (Maior Impacto):
- Competência: [nome do bloco/habilidade]
- Gap Identificado: [descrição específica com evidência]
- Meta: [de X para Y em [métrica]]
- Impacto Estimado: [como isso afeta conversão/ticket]

PRIORIDADE 2:
- [mesmo formato]

PRIORIDADE 3:
- [mesmo formato]

Tema Central do Ciclo: [frase-resumo — ex: "Discovery que gera urgência"]
```

### Seção 5 — Exercícios Planejados
Atividades práticas para o ciclo.
**Formato**:
```
Exercício 1: [nome — ex: "Role-play de discovery com objeção de timing"]
- Objetivo: [o que o closer vai praticar]
- Formato: [ao vivo com gestor / gravado / escrito]
- Critério de Sucesso: [como saber se acertou]
- Prazo: [DD/MM/AAAA]

Exercício 2: [mesmo formato]
Exercício 3: [mesmo formato]
```

### Seção 6 — Métricas de Acompanhamento
Como medir progresso durante o ciclo.
**Formato**:
```
| Métrica              | Baseline | Meta    | Como Medir              |
|----------------------|----------|---------|-------------------------|
| [Score do bloco X]   | [X.X]    | [Y.Y]   | [auditoria de call]     |
| [Taxa de conversão]  | [XX%]    | [YY%]   | [CRM]                   |
| [Objeções tratadas]  | [XX%]    | [YY%]   | [auditoria de call]     |

Checkpoint: [data de revisão intermediária]
Review Final: [data de encerramento do ciclo]
```

## Exemplo
```
Closer: Rafael Mendes | Ciclo #4 | 17/03 a 28/03/2026
Score Atual: 72 | Anterior: 69 | Delta: +3

Ciclo Anterior: Foco em rapport → Melhorou +4 pts (de 6 para 8 no bloco)
Exercícios: 2 de 3 completados

PRIORIDADE 1: Discovery — parar de fazer perguntas fechadas
Meta: Score de discovery de 5 para 7
Exercício: Role-play com 10 perguntas abertas de consequência — prazo 21/03

Tema Central: "Perguntas que fazem o lead sentir a dor"
```

## Agente Responsável
`coaching-agent` — Elabora o brief com base nos dados de auditoria e histórico.

## Checklists de Qualidade
- `coaching-priority-check.md` — Valida que as prioridades estão corretas.
- `coaching-actionability-check.md` — Valida que os exercícios são acionáveis.
- `coaching-progression-check.md` — Valida que os dados de evolução são confiáveis.
