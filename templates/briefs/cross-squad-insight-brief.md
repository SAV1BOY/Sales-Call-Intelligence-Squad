# Brief de Insights Cross-Squad

> Documento que consolida insights extraídos das calls de vendas para envio a outros squads (Copy, Traffic, Offer, Ops).

## Quando Usar
Quando há insights acionáveis suficientes para justificar um handoff formal a outro squad. Cadência mínima: semanal para Copy e Traffic, quinzenal para Offer, a cada deal fechado para Ops.

## Estrutura

### Seção 1 — Cabeçalho do Handoff
Dados de roteamento e contexto.
**Formato**:
```
De: Sales Intelligence Squad
Para: [Copy Squad / Traffic Squad / Offer Squad / Ops Squad / C-Level]
Data: [DD/MM/AAAA]
Período de Referência: [DD/MM a DD/MM/AAAA]
Calls Base: [N calls analisadas]
Urgência: [Alta / Média / Baixa]
Resumo em 1 Frase: [ex: "Leads de Meta Ads estão chegando com expectativa errada sobre o produto"]
```

### Seção 2 — Insights Principais
Os achados mais relevantes para o squad destinatário.
**Formato**:
```
INSIGHT #1:
- Achado: [descrição clara e concisa]
- Evidência: [dados quantitativos — ex: "em 14 de 20 calls (70%)"]
- Trechos de Suporte:
  - Call [ID] — [MM:SS]: "[frase literal do lead]"
  - Call [ID] — [MM:SS]: "[frase literal do lead]"
- Impacto Estimado: [como isso afeta o resultado — ex: "contribui para 40% das objeções de preço"]
- Ação Sugerida: [o que o squad destinatário pode fazer com este insight]

INSIGHT #2:
- [mesmo formato]

INSIGHT #3:
- [mesmo formato]
```

### Seção 3 — Dados de Suporte
Informações adicionais para contexto.
**Formato**:
```
Tabelas de Dados:
[tabelas relevantes — frequência de objeções, distribuição por origem, etc.]

Clips de Referência:
| Call ID    | Minuto  | Descrição                        | Link           |
|------------|---------|----------------------------------|----------------|
| [CALL-XXX] | [MM:SS] | [o que acontece neste momento]   | [URL do clip]  |
```

### Seção 4 — Contexto e Limitações
O que o squad destinatário precisa saber para interpretar corretamente.
**Formato**:
```
Tamanho da Amostra: [N calls — suficiente/insuficiente para conclusão definitiva]
Vieses Possíveis: [ex: "amostra inclui apenas calls do closer X"]
Período Atípico: [sim/não — ex: "semana com promoção ativa"]
Confiança: [Alta / Média / Baixa — justificativa]
```

### Seção 5 — Follow-up
Como acompanhar o impacto do insight.
**Formato**:
```
Métrica de Acompanhamento: [como saber se a ação do outro squad funcionou]
Próximo Check-in: [DD/MM/AAAA]
Contato para Dúvidas: [nome — canal]
```

## Exemplo
```
De: Sales Intelligence | Para: Copy Squad
Período: 03/03 a 14/03/2026 | 28 calls | Urgência: Alta
Resumo: "Leads estão usando a frase 'já tentei e não deu certo' — oportunidade de copy de diferenciação"

INSIGHT #1:
- Achado: 19% dos leads mencionam experiência negativa anterior com solução similar
- Evidência: 8 de 42 calls
- Trecho: CALL-0331 — 04:12: "Já paguei caro por mentoria e não vi resultado"
- Ação Sugerida: Criar ângulo de copy "Por que desta vez é diferente" com prova social específica

Confiança: Média — amostra de 42 calls, tendência crescente
Próximo Check-in: 28/03/2026
```

## Agente Responsável
`cross-squad-agent` — Consolida insights e prepara o handoff.

## Checklists de Qualidade
- `cross-squad-copy-handoff-quality.md` (se para Copy)
- `cross-squad-traffic-handoff-quality.md` (se para Traffic)
- `cross-squad-offer-handoff-quality.md` (se para Offer/C-Level)
- `cross-squad-ops-handoff-quality.md` (se para Ops)
