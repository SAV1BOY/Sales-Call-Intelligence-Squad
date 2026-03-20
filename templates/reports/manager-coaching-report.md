# Relatório Executivo de Coaching para Gestor

> Relatório resumido para o gestor de vendas com as top 3 prioridades do closer, ações definidas e métricas de acompanhamento.

## Quando Usar
Após cada ciclo de auditoria/coaching, para comunicar ao gestor as prioridades de desenvolvimento do closer de forma concisa e acionável.

## Estrutura

### Seção 1 — Snapshot do Closer
Visão rápida em 10 segundos.
**Formato**:
```
Closer: [nome]
Período: [DD/MM a DD/MM/AAAA]
Calls Auditadas: [N]
Score Médio: [XX/100] (anterior: [XX] | delta: [+/-XX])
Conversão: [XX%] (anterior: [XX%])
Ticket Médio: [R$ XX.XXX] (anterior: [R$ XX.XXX])
Classificação: [Excelente / Bom / Mediano / Crítico]
Tendência: [Ascendente / Estável / Descendente]
```

### Seção 2 — Top 3 Prioridades
As 3 ações mais impactantes para o próximo ciclo.
**Formato**:
```
🔴 PRIORIDADE 1 — [Nome da Competência]
Situação Atual: [score do bloco — descrição do gap em 1 frase]
Evidência: "[trecho da call]" (Call [ID] — [MM:SS])
Impacto: [estimativa de impacto no resultado — ex: "contribui para 50% das perdas"]
Ação: [o que o closer precisa fazer — instrução operacional]
Meta: [de X para Y até DD/MM]

🟡 PRIORIDADE 2 — [mesmo formato]

🟢 PRIORIDADE 3 — [mesmo formato]
```

### Seção 3 — O que Está Funcionando
Reconhecimento do que o closer faz bem (essencial para engajamento).
**Formato**:
```
Ponto Forte #1: [competência — score — evidência breve]
Ponto Forte #2: [competência — score — evidência breve]
Recomendação: [como potencializar o que já funciona]
```

### Seção 4 — Plano de Ação Resumido
Para o gestor acompanhar.
**Formato**:
```
| Ação                    | Responsável | Prazo    | Métrica de Sucesso      | Status |
|-------------------------|-------------|----------|-------------------------|--------|
| [ação 1]                | [closer]    | [DD/MM]  | [como medir]            | ⬜     |
| [ação 2]                | [closer]    | [DD/MM]  | [como medir]            | ⬜     |
| [ação 3]                | [closer]    | [DD/MM]  | [como medir]            | ⬜     |
| [acompanhamento gestor] | [gestor]    | [DD/MM]  | [checkpoint]            | ⬜     |
```

### Seção 5 — Alertas (se aplicável)
Sinais que exigem atenção imediata do gestor.
**Formato**:
```
⚠️ ALERTA: [descrição — ex: "Score em queda livre por 3 semanas consecutivas"]
Recomendação: [ação imediata sugerida]
```

## Exemplo
```
Closer: Rafael Mendes | 10-14/03/2026 | 4 calls auditadas
Score: 72/100 (anterior: 69 | +3) | Conversão: 25% | Tendência: Ascendente leve

🔴 PRIORIDADE 1 — Discovery Profunda (5/15)
Rafael pula para apresentação antes de explorar consequência da dor.
Evidência: "E qual o maior desafio?" → pula para slide (CALL-0342 — 10:30)
Impacto: 3 de 4 calls perdidas tiveram discovery superficial
Ação: Fazer mínimo 3 perguntas de consequência antes de apresentar
Meta: Score de 5 para 8 até 28/03

Forte #1: Rapport (9/10) — conexão natural e autêntica
Forte #2: Prova social (8/10) — usa cases de forma convincente

⚠️ ALERTA: Taxa de desconto proativo subiu — Rafael ofereceu desconto sem pedido em 2 de 4 calls
```

## Agente Responsável
`coaching-agent` — Gera o relatório executivo para o gestor.

## Checklists de Qualidade
- `coaching-priority-check.md` — Prioridades corretas e focadas.
- `coaching-specificity-check.md` — Feedback específico com evidência.
- `coaching-actionability-check.md` — Ações concretas e mensuráveis.
