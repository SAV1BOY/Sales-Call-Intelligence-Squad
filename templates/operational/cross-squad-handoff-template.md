# Template de Handoff Cross-Squad

> Template padronizado para enviar insights acionáveis do Sales Intelligence Squad para qualquer outro squad, com evidência e ação sugerida.

## Quando Usar
Sempre que o squad identifica insight relevante para Copy, Traffic, Offer, Ops ou C-Level. Cada insight deve ser enviado neste formato para garantir acionabilidade.

## Estrutura

### Seção 1 — Cabeçalho
Roteamento e urgência.
**Formato**:
```
Handoff ID: [HO-AAAA-NNNN]
De: Sales Intelligence Squad
Para: [Copy Squad / Traffic Squad / Offer Squad / Ops Squad / C-Level]
Data: [DD/MM/AAAA]
Urgência: [Alta / Média / Baixa]
Categoria: [Objeção / Dor / Linguagem / Segmentação / Pricing / Produto / Processo / Competitivo]
Resumo em 1 Frase: [o que o destinatário precisa saber]
```

### Seção 2 — Insight
O achado principal.
**Formato**:
```
INSIGHT:
[Descrição clara e concisa do que foi descoberto — 2-3 frases]

DADOS:
- Frequência: [em quantas calls apareceu — N de M (XX%)]
- Período: [DD/MM a DD/MM/AAAA]
- Tendência: [crescente / estável / decrescente]
- Confiança: [Alta (>50 calls) / Média (20-50 calls) / Baixa (<20 calls)]
```

### Seção 3 — Evidência
Provas diretas das calls.
**Formato**:
```
TRECHO 1:
Call ID: [CALL-XXXX] | Minuto: [MM:SS] | Closer: [nome] | Lead: [perfil breve]
Lead: "[fala exata do lead]"
Contexto: [o que estava acontecendo na call]

TRECHO 2:
[mesmo formato]

TRECHO 3:
[mesmo formato]

DADOS QUANTITATIVOS:
[tabelas, percentuais, distribuições — conforme aplicável]
```

### Seção 4 — Impacto no Negócio
Por que isso importa.
**Formato**:
```
IMPACTO ATUAL:
- [como este achado afeta os resultados hoje — ex: "contribui para 30% das objeções de preço"]
- Estimativa de Revenue Afetado: [R$ XX.XXX/mês]

IMPACTO POTENCIAL (se corrigido):
- [o que pode melhorar — ex: "reduzir objeções de preço em 30% = +R$ XX.XXX/mês"]
- Estimativa de Ganho: [R$ XX.XXX/mês]
```

### Seção 5 — Ação Sugerida
O que o squad destinatário deve fazer.
**Formato**:
```
AÇÃO SUGERIDA #1:
- O que fazer: [descrição específica e acionável]
- Por que: [justificativa baseada nos dados]
- Como: [sugestão de implementação]
- Prazo Sugerido: [urgente / próxima sprint / próximo mês]
- Métrica de Sucesso: [como saber se funcionou]

AÇÃO SUGERIDA #2:
- [mesmo formato]

MATERIAIS DE APOIO:
- [lista de materiais que acompanham o handoff — clips, dados, análises]
```

### Seção 6 — Follow-up
Como acompanhar o impacto.
**Formato**:
```
Contato do Sales Intelligence Squad: [nome — canal]
Próximo Check-in: [DD/MM/AAAA]
Métrica de Acompanhamento: [o que monitorar para saber se a ação funcionou]
Feedback Esperado: [o que o Sales Intelligence Squad precisa saber de volta]
```

## Exemplo

### Exemplo para Copy Squad:
```
HO-2026-0045
De: Sales Intelligence | Para: Copy Squad
Urgência: Alta | Categoria: Objeção + Linguagem
Resumo: "19% dos leads mencionam experiência negativa anterior — oportunidade de copy de diferenciação"

INSIGHT:
Leads estão chegando às calls com histórico de frustração com soluções concorrentes. A frase "já tentei algo parecido e não funcionou" apareceu em 8 de 42 calls (19%) e está em tendência crescente.

TRECHO 1:
CALL-2026-0331 | 04:12 | Juliana | Lead: CEO, SaaS, 50 funcionários
Lead: "Já paguei R$ 15 mil por uma mentoria e o cara sumiu depois de 2 meses"

TRECHO 2:
CALL-2026-0339 | 07:30 | Rafael | Lead: Fundadora, e-commerce, 20 funcionários
Lead: "Eu tô com o pé atrás porque a última assessoria que contratei não entregou nada do que prometeu"

IMPACTO: Quando esta objeção não é tratada, a taxa de conversão cai para 8% (vs. 31% geral)
Ganho Potencial: Se tratada por copy antes da call, estimamos +4 deals/mês = +R$ 56.000

AÇÃO SUGERIDA #1:
Criar ângulo de copy "Por que desta vez é diferente" com:
- Prova social de entregas reais (não promessas)
- Depoimentos que mencionem experiências anteriores ruins
- Garantia em destaque na landing page

Check-in: 04/04/2026
```

### Exemplo para Ops Squad:
```
HO-2026-0046
De: Sales Intelligence | Para: Ops Squad
Urgência: Alta | Categoria: Processo
Resumo: "Closers estão prometendo prazo de resultado de 30 dias mas o onboarding leva 15 — risco de churn"

INSIGHT:
Em 6 de 10 deals fechados analisados, o closer prometeu "resultado em 30 dias" mas o onboarding padrão leva 15 dias, deixando apenas 15 dias para entregar resultado. Isso cria expectativa irrealista.

AÇÃO SUGERIDA:
1. Alinhar com closers que o prazo de resultado é "30 dias APÓS onboarding completo"
2. Incluir timeline no material de onboarding para alinhar expectativa desde o dia 1
```

## Agente Responsável
`sales-chief` — Prepara e envia handoffs. `qa-guardian` — Valida e roteia.

## Checklists de Qualidade
- `cross-squad-copy-handoff-quality.md` (se para Copy)
- `cross-squad-traffic-handoff-quality.md` (se para Traffic)
- `cross-squad-offer-handoff-quality.md` (se para Offer/C-Level)
- `cross-squad-ops-handoff-quality.md` (se para Ops)
