# Relatório de Auditoria Minuto a Minuto

> Relatório cronológico detalhado que analisa cada momento significativo da call em sequência temporal.

## Quando Usar
Quando é necessária uma análise granular da call, para treinamento detalhado, ou quando o gestor quer entender exatamente o que aconteceu em cada fase.

## Estrutura

### Seção 1 — Dados da Call
Identificação rápida.
**Formato**:
```
Call ID: [ID] | Closer: [nome] | Lead: [nome]
Data: [DD/MM/AAAA] | Duração: [MM:SS] | Resultado: [vendeu/não vendeu]
Score Total: [XX/100]
```

### Seção 2 — Mapa de Fases
Visão macro da estrutura temporal da call.
**Formato**:
```
| Fase                   | Início  | Fim     | Duração | % da Call | Benchmark |
|------------------------|---------|---------|---------|-----------|-----------|
| Abertura/Rapport       | [00:00] | [MM:SS] | [MM:SS] | [XX%]     | [5-10%]   |
| Qualificação           | [MM:SS] | [MM:SS] | [MM:SS] | [XX%]     | [5-10%]   |
| Discovery              | [MM:SS] | [MM:SS] | [MM:SS] | [XX%]     | [25-35%]  |
| Apresentação           | [MM:SS] | [MM:SS] | [MM:SS] | [XX%]     | [15-20%]  |
| Pricing/Value Stack    | [MM:SS] | [MM:SS] | [MM:SS] | [XX%]     | [10-15%]  |
| Objeções               | [MM:SS] | [MM:SS] | [MM:SS] | [XX%]     | [10-15%]  |
| Fechamento             | [MM:SS] | [MM:SS] | [MM:SS] | [XX%]     | [5-10%]   |

Observação: [desvios significativos do benchmark — ex: "Discovery ocupou apenas 12% quando deveria ser 30%"]
```

### Seção 3 — Análise Minuto a Minuto
Cada momento significativo em detalhe.
**Formato**:
```
---
⏱️ [MM:SS] — [FASE] — [MOMENTO-CHAVE ou descrição curta]

CONTEXTO: [o que estava acontecendo na conversa neste ponto]

CLOSER: "[fala exata do closer]"
LEAD: "[resposta do lead]"

ANÁLISE:
- O que aconteceu: [descrição factual do comportamento]
- Framework aplicável: [qual técnica se aplica a este momento]
- Execução: [como o closer executou — bem, parcialmente, não executou]
- Impacto: [como este momento afetou o rumo da call]
- Oportunidade: [o que poderia ter sido feito diferente, se aplicável]

CLASSIFICAÇÃO: [✓ Positivo / ✗ Negativo / — Neutro / ⚠ Oportunidade Perdida]
---
```

### Seção 4 — Momentos Decisivos
Os 3-5 momentos que mais impactaram o resultado.
**Formato**:
```
MOMENTO DECISIVO #1 — [MM:SS]
- O que aconteceu: [descrição]
- Por que foi decisivo: [impacto no resultado]
- O que mudaria o resultado: [ação alternativa]

MOMENTO DECISIVO #2 — [mesmo formato]
```

### Seção 5 — Padrões Observados
Comportamentos recorrentes ao longo da call.
**Formato**:
```
Padrão Positivo: [comportamento que se repetiu e ajudou — ex: "sempre validou antes de responder"]
Frequência: [X vezes ao longo da call]

Padrão Negativo: [comportamento que se repetiu e prejudicou — ex: "interrompeu o lead 6 vezes"]
Frequência: [X vezes ao longo da call]
```

## Exemplo
```
CALL-2026-0342 | Rafael | Carla — TechFlow | 47:22 | Não Vendeu | 64/100

Discovery: 08:30 a 14:00 (5:30 — 12%) — ABAIXO DO BENCHMARK (25-35%)

---
⏱️ 09:15 — DISCOVERY — Pergunta fechada sobre dor

CLOSER: "Então você tem problema com geração de leads, certo?"
LEAD: "É, mais ou menos..."

ANÁLISE:
- Pergunta fechada limitou a resposta do lead
- Framework: Miner — deveria usar pergunta aberta de exploração
- Execução: Não executou — pergunta fechada em vez de aberta
- Impacto: Lead não elaborou a dor, discovery ficou superficial

CLASSIFICAÇÃO: ✗ Negativo
---

MOMENTO DECISIVO #1 — 14:00
O closer encerrou discovery prematuramente e partiu para apresentação sem ter entendido a dor real. Isso gerou uma apresentação genérica que não ressoou.
```

## Agente Responsável
`audit-agent` — Executa a análise minuto a minuto como parte da auditoria completa.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Todo momento analisado tem trecho e timestamp.
- `qa-bias-detection-check.md` — Cobertura equilibrada de toda a call, sem viés de recência.

## Preenchido Por

- **Task(s)**: normalize-and-segment
- **Agente(s) responsável(is)**: transcript-analyst
- **Workflow(s)**: Ingestão (pipeline per-call)
- **Frequência**: per-call
- **Registro**: data/transcripts/cleaned, data/transcripts/segmented
