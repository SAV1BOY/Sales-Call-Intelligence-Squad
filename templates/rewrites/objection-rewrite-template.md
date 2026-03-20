# Template de Reescrita de Objeção

> Reescrita de tratamento de objeção com formato [ANTES] → [DEPOIS], framework de referência e justificativa detalhada.

## Quando Usar
Sempre que uma objeção foi mal tratada na call e o coaching precisa fornecer uma alternativa concreta e praticável.

## Estrutura

### Seção 1 — Contexto da Objeção
Localização e circunstâncias.
**Formato**:
```
Call ID: [ID]
Closer: [nome]
Momento: [MM:SS]
Fase da Call: [Discovery / Apresentação / Pricing / Fechamento]
Objeção: "[frase exata do lead]"
Categoria: [Preço / Timing / Autoridade / Necessidade / Confiança / Concorrência]
Tipo: [Real / Cortina de Fumaça / Reflexo]
```

### Seção 2 — O que Aconteceu (ANTES)
A resposta original do closer.
**Formato**:
```
CONTEXTO (3-5 falas anteriores):
Lead: "[fala]"
Closer: "[fala]"
Lead: "[fala — a objeção]"

RESPOSTA DO CLOSER:
"[fala exata do closer ao tratar a objeção]"

REAÇÃO DO LEAD:
"[o que o lead disse/fez depois]"

RESULTADO: [Objeção dissolvida / Persistiu / Piorou / Encerrou a call]

DIAGNÓSTICO:
- Erro Principal: [o que deu errado — ex: "respondeu sem validar", "argumentou sem isolar"]
- Framework Tentado: [qual técnica tentou usar, se identificável]
- Onde Falhou: [em que ponto da técnica errou]
```

### Seção 3 — Como Deveria Ter Sido (DEPOIS)
A resposta reescrita.
**Formato**:
```
FRAMEWORK RECOMENDADO: [nome da técnica — ex: "Isolamento + Reframe"]

PASSO A PASSO:
1. [Primeiro movimento — ex: "Validar a preocupação"]
2. [Segundo movimento — ex: "Isolar a objeção"]
3. [Terceiro movimento — ex: "Reframear com pergunta"]
4. [Quarto movimento — ex: "Oferecer evidência"]

REWRITE COMPLETO:

Lead: "[objeção original]"

Closer: "[fala reescrita — passo 1]"
[pausa natural]
Closer: "[fala reescrita — passo 2]"

Lead (provável): "[resposta esperada do lead]"

Closer: "[fala reescrita — passo 3]"
Closer: "[fala reescrita — passo 4]"
```

### Seção 4 — Justificativa
Por que a nova versão é melhor.
**Formato**:
```
POR QUE FUNCIONA:
1. [Razão 1 — ex: "Valida antes de contra-argumentar, reduzindo resistência"]
2. [Razão 2 — ex: "Isola a objeção para entender se é real ou cortina de fumaça"]
3. [Razão 3 — ex: "Usa pergunta em vez de afirmação, mantendo o lead no controle percebido"]

POR QUE O ORIGINAL NÃO FUNCIONOU:
1. [Razão 1 — ex: "Respondeu defensivamente, criando embate"]
2. [Razão 2 — ex: "Não investigou a raiz da objeção"]

RESULTADO ESPERADO:
[o que provavelmente aconteceria com a nova abordagem]
```

### Seção 5 — Variações
Adaptações para contextos diferentes.
**Formato**:
```
VARIAÇÃO A — Se o lead insistir:
"[fala alternativa para caso a primeira não dissolva]"

VARIAÇÃO B — Se for cortina de fumaça:
"[fala alternativa para quando a objeção esconde outra]"

VARIAÇÃO C — Tom mais direto (closer sênior):
"[versão mais assertiva para closers experientes]"
```

## Exemplo
```
CALL-2026-0342 | Rafael | 28:40

Objeção: "Hmm, tá caro pra mim"
Categoria: Preço | Tipo: Possível cortina de fumaça (discovery insuficiente)

ANTES:
Closer: "Mas na verdade quando você divide por dia fica menos de 40 reais, né? É menos que um almoço..."
Reação: "É, mas mesmo assim... vou pensar."
Resultado: Persistiu — lead não engajou.
Erro: Respondeu com lógica sem validar emoção, não isolou a objeção.

DEPOIS (Isolamento + Investigação):
Framework: Isolamento + Pergunta de Profundidade

Lead: "Hmm, tá caro pra mim"
Closer: "Entendo, Carla. E faz todo sentido pensar no investimento com cuidado."
[pausa 2s]
Closer: "Me diz uma coisa — quando você fala 'tá caro', é que o valor total é alto demais pro seu momento, ou é que você ainda não tá convencida que o retorno justifica?"
Lead (provável): "Acho que não tô 100% convencida..."
Closer: "Justo. Então vamos voltar um passo — quanto você estima que perde por mês por não ter [solução para a dor que ela mencionou na discovery]?"

POR QUE FUNCIONA:
1. Valida sem concordar que é caro
2. Isola entre "não tem dinheiro" e "não vê valor" — respostas diferentes para cada uma
3. Retorna para o custo da inação em vez de justificar o preço
```

## Agente Responsável
`coaching-agent` — Cria rewrites como parte do plano de coaching.

## Checklists de Qualidade
- `coaching-specificity-check.md` — Rewrite específico com contexto da call.
- `coaching-actionability-check.md` — Closer consegue aplicar na prática.
