# Template de Reescrita de Discovery

> Reescrita de perguntas de discovery com versões mais profundas que revelam dor real, urgência e custo da inação.

## Quando Usar
Quando a discovery foi superficial — perguntas fechadas, sem aprofundamento, sem exploração de consequência — e o closer precisa aprender a fazer perguntas melhores.

## Estrutura

### Seção 1 — Contexto da Discovery
Dados do momento.
**Formato**:
```
Call ID: [ID]
Closer: [nome]
Trecho de Discovery: [MM:SS a MM:SS]
Duração da Discovery: [MM:SS] ([XX%] da call — benchmark: 25-35%)
Total de Perguntas Feitas: [N]
Perguntas Abertas: [N]
Perguntas Fechadas: [N]
Perguntas de Consequência/Implicação: [N]
Score do Bloco Discovery: [X/15]
```

### Seção 2 — Perguntas Originais (ANTES)
As perguntas que o closer fez.
**Formato**:
```
PERGUNTA #[N] — [MM:SS]
Closer: "[pergunta exata]"
Lead: "[resposta]"
Tipo: [Aberta / Fechada]
Profundidade: [Superficial / Intermediária / Profunda]
Framework: [Situação / Problema / Implicação / Necessidade — SPIN] ou [Miner level]

DIAGNÓSTICO:
- O que a pergunta revelou: [informação obtida]
- O que NÃO revelou: [informação que ficou oculta]
- Oportunidade Perdida: [follow-up que deveria ter sido feito]
```

### Seção 3 — Perguntas Reescritas (DEPOIS)
Versões mais profundas organizadas em sequência lógica.
**Formato**:
```
NÍVEL 1 — PERGUNTAS DE SITUAÇÃO (entender o contexto):
Original: "[pergunta fechada do closer]"
Rewrite: "[pergunta aberta que explora o mesmo tema]"
Objetivo: [o que esta pergunta revela]

NÍVEL 2 — PERGUNTAS DE PROBLEMA (explorar a dor):
Original: "[pergunta superficial do closer]"
Rewrite: "[pergunta que vai na raiz do problema]"
Follow-up: "[pergunta de aprofundamento se o lead responder na superfície]"
Objetivo: [o que esta pergunta revela]

NÍVEL 3 — PERGUNTAS DE CONSEQUÊNCIA/IMPLICAÇÃO (sentir o custo):
[geralmente ausentes no original — estas são as perguntas novas]
Rewrite 1: "[pergunta que faz o lead calcular o custo da dor]"
Rewrite 2: "[pergunta que faz o lead projetar o futuro sem resolver]"
Rewrite 3: "[pergunta que conecta a dor a outras áreas afetadas]"
Objetivo: [gerar urgência e percepção de custo]

NÍVEL 4 — PERGUNTAS DE SOLUÇÃO IDEAL (desenhar o futuro):
Rewrite 1: "[pergunta que faz o lead descrever o cenário ideal]"
Rewrite 2: "[pergunta que faz o lead definir critérios de sucesso]"
Objetivo: [criar a régua pela qual o lead avaliará a oferta]
```

### Seção 4 — Sequência Completa Reescrita
A discovery ideal de ponta a ponta.
**Formato**:
```
SCRIPT DE DISCOVERY REESCRITO:

[Transição do rapport para discovery]
Closer: "[frase de transição — ex: 'Carla, antes de te mostrar qualquer coisa, quero entender bem sua situação. Me conta...']"

[Pergunta de Situação]
Closer: "[pergunta 1]"
Lead (provável): "[resposta esperada]"

[Pergunta de Problema]
Closer: "[pergunta 2 — baseada na resposta]"
Lead (provável): "[resposta esperada]"

[Aprofundamento]
Closer: "[pergunta 3 — cavando mais fundo]"
Lead (provável): "[resposta com mais emoção/detalhe]"

[Pergunta de Consequência]
Closer: "[pergunta 4 — custo da inação]"
Lead (provável): "[resposta que revela urgência]"

[Pergunta de Consequência Ampliada]
Closer: "[pergunta 5 — expandindo o impacto]"
Lead (provável): "[resposta que amplifica a dor]"

[Pergunta de Solução Ideal]
Closer: "[pergunta 6 — futuro desejado]"
Lead (provável): "[resposta que define critérios de sucesso]"

[Transição para Apresentação]
Closer: "[ponte — ex: 'Interessante, Carla. É exatamente isso que a gente resolve. Deixa eu te mostrar como...']"

DURAÇÃO ESTIMADA: [MM:SS]
TOTAL DE PERGUNTAS: [N]
```

### Seção 5 — Justificativa
Por que perguntas profundas fazem diferença.
**Formato**:
```
POR QUE FUNCIONA:
1. [Perguntas de consequência fazem o lead SENTIR a dor, não apenas descrevê-la]
2. [Quantificar o custo cria âncora natural para o pricing]
3. [Perguntas de solução ideal criam critérios que a oferta atende]

ERROS DO ORIGINAL:
1. [ex: "Perguntas fechadas geraram respostas de 1 palavra"]
2. [ex: "Não houve nenhuma pergunta de consequência — lead não sentiu urgência"]

IMPACTO NO RESULTADO:
[como a discovery rasa afetou o resto da call — apresentação genérica, objeção de preço, "vou pensar"]
```

## Exemplo
```
CALL-2026-0342 | Rafael | Discovery: 08:30-14:00 (5:30 — 12%)

ANTES:
"Vocês geram leads hoje?" (fechada) → "Sim"
"E qual o maior desafio?" (aberta mas ampla) → "Converter" (resposta vaga)
"Tá, e vocês usam alguma ferramenta?" (situação) → "Usamos o RD"
→ Pulou para apresentação. Zero perguntas de consequência.

DEPOIS — NÍVEL 3 (ausente no original):
Closer: "Você disse que o desafio é converter. Me ajuda a entender — de 100 leads que entram, quantos viram clientes hoje?"
Lead: "Uns 3, talvez 4..."
Closer: "E os outros 96 — o que acontece com eles?"
Lead: "Morrem no funil, a gente perde..."
Closer: "Se cada lead custou, sei lá, R$ 50 pra adquirir... são quase R$ 5.000 por mês que vocês investem pra perder 96% do resultado. Em um ano são R$ 60.000. Isso faz sentido pra você?"
Lead: "Quando você coloca assim... é muito dinheiro jogado fora."
Closer: "E além do dinheiro, como isso afeta o crescimento da empresa? Quanto vocês deixam de faturar por não converter esses leads?"

→ Agora o lead SENTE a dor. O preço de R$ 12k parece barato perto de R$ 60k/ano perdidos.
```

## Agente Responsável
`coaching-agent` — Cria rewrites de discovery como parte do coaching.

## Checklists de Qualidade
- `coaching-specificity-check.md` — Perguntas baseadas no contexto real da call.
- `coaching-actionability-check.md` — Closer consegue praticar as perguntas.
