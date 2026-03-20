# Brief de Review Semanal de Vendas

> Documento que consolida as calls da semana, scores, padrões identificados e destaques para a reunião semanal do squad.

## Quando Usar
Toda sexta-feira ou início de segunda-feira, antes da reunião semanal de review do time de vendas.

## Estrutura

### Seção 1 — Resumo da Semana
Números gerais do período.
**Formato**:
```
Período: [DD/MM a DD/MM/AAAA]
Total de Calls Realizadas: [N]
Total de Calls Auditadas: [N] ([XX%] do total)
Taxa de Conversão Geral: [XX%]
Ticket Médio: [R$ XX.XXX]
Revenue Total: [R$ XXX.XXX]
Comparação com Semana Anterior: [+XX% / -XX% / estável]
```

### Seção 2 — Score do Time
Performance qualitativa consolidada.
**Formato**:
```
Score Médio do Time: [XX/100]
Desvio Padrão: [X.X]
Maior Score: [XX — Closer: Nome — Call ID: XXXX]
Menor Score: [XX — Closer: Nome — Call ID: XXXX]

Distribuição:
- 85-100 (Excelente): [N calls] ([XX%])
- 70-84 (Bom): [N calls] ([XX%])
- 55-69 (Mediano): [N calls] ([XX%])
- Abaixo de 55 (Crítico): [N calls] ([XX%])
```

### Seção 3 — Performance por Closer
Ranking individual da semana.
**Formato**:
```
| Closer    | Calls | Score Médio | Conversão | Ticket Médio | Tendência |
|-----------|-------|-------------|-----------|--------------|-----------|
| [Nome]    | [N]   | [XX]        | [XX%]     | [R$ X.XXX]   | [↑/→/↓]  |
```

### Seção 4 — Padrões da Semana
Temas recorrentes identificados nas auditorias.
**Formato**:
```
Padrão Positivo #1: [descrição — frequência — impacto]
Padrão Positivo #2: [descrição — frequência — impacto]
Padrão Negativo #1: [descrição — frequência — impacto — ação sugerida]
Padrão Negativo #2: [descrição — frequência — impacto — ação sugerida]
Objeção Mais Frequente: [objeção — frequência — taxa de tratamento com sucesso]
```

### Seção 5 — Destaques
Momentos notáveis para reconhecimento ou aprendizado coletivo.
**Formato**:
```
Melhor Momento da Semana: [Closer — Call ID — Minuto — Descrição do que fez bem]
Maior Oportunidade Perdida: [Closer — Call ID — Minuto — O que poderia ter sido diferente]
Clip para Treinamento: [Call ID — Momento — Por que é um bom exemplo]
```

### Seção 6 — Ações para Próxima Semana
Prioridades derivadas da análise semanal.
**Formato**:
```
1. [Ação — Responsável — Prazo]
2. [Ação — Responsável — Prazo]
3. [Ação — Responsável — Prazo]
```

## Exemplo
```
Período: 10/03 a 14/03/2026
Total de Calls: 32 | Auditadas: 18 (56%)
Conversão: 28% | Ticket Médio: R$ 14.200 | Revenue: R$ 127.800
vs Semana Anterior: +12% revenue, -3% conversão (ticket compensou)

Score Médio: 73/100 | Desvio: 8.2
Padrão Negativo #1: Discovery superficial — 11 de 18 calls — closer pula para apresentação antes de explorar dor
Ação: Treinamento coletivo de discovery na terça — Marcos — 17/03
```

## Agente Responsável
`orchestrator-agent` — Consolida dados e gera o brief semanal.

## Checklists de Qualidade
- `qa-score-calibration-check.md` — Garante que os scores consolidados são confiáveis.
- `qa-evidence-completeness-check.md` — Garante que os padrões são baseados em evidência.
