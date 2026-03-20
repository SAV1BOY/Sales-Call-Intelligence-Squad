# Template de Biblioteca de Clips de Call

> Template para catalogar momentos marcantes de calls para uso em treinamento, referência e best practices.

## Quando Usar
Para manter uma biblioteca organizada de clips (trechos de calls) que servem como exemplos positivos, negativos ou didáticos para o time.

## Estrutura

### Seção 1 — Metadados do Clip
Identificação e classificação.
**Formato**:
```
Clip ID: [CLIP-AAAA-NNNN]
Call ID de Origem: [CALL-XXXX]
Closer: [nome]
Data da Call: [DD/MM/AAAA]
Momento: [MM:SS a MM:SS]
Duração do Clip: [MM:SS]
Link do Clip: [URL — se disponível]
```

### Seção 2 — Classificação
Como o clip é categorizado na biblioteca.
**Formato**:
```
Categoria Principal: [Discovery / Apresentação / Pricing / Objeção / Fechamento / Rapport / Follow-up]
Subcategoria: [ex: "Pergunta de consequência", "Ancoragem por contraste"]
Framework Demonstrado: [Miner / Belfort / SPIN / Sandler / outro]
Tipo: [Best Practice / Erro Didático / Momento Decisivo / Técnica Avançada]
Nível de Dificuldade: [Básico / Intermediário / Avançado]
```

### Seção 3 — Contexto do Clip
O que acontecia na call neste momento.
**Formato**:
```
Situação: [descrição do contexto — ex: "Lead acabou de levantar objeção de preço"]
Fase da Call: [em que fase estavam]
O que Aconteceu Antes: [contexto imediato — 2-3 falas anteriores]
Lead Profile: [tipo de lead — segmento, nível de consciência, temperatura]
Resultado da Call: [vendeu/não vendeu — para contextualizar]
```

### Seção 4 — Conteúdo do Clip
Transcrição e análise.
**Formato**:
```
TRANSCRIÇÃO:
[MM:SS] Closer: "[fala]"
[MM:SS] Lead: "[fala]"
[MM:SS] Closer: "[fala]"
[MM:SS] Lead: "[fala]"
...

ANÁLISE:
O que Aconteceu: [descrição factual do que o closer fez]
Por que é Relevante: [o que torna este momento digno de clip]
Técnica Utilizada: [descrição da técnica com nome do framework]
Resultado Imediato: [como o lead reagiu]
Score deste Momento: [X/10]
```

### Seção 5 — Uso Recomendado
Como usar este clip em treinamento.
**Formato**:
```
Público-Alvo: [closers júnior / pleno / sênior / todo o time]
Contexto de Treinamento: [em que situação usar — ex: "workshop de discovery"]
Ponto de Ensino: [o que o clip ensina — em 1 frase]
Perguntas para Discussão:
1. [pergunta que provoca reflexão no time]
2. [pergunta que conecta à prática]
3. [pergunta que desafia o closer a adaptar]

Exercício Sugerido:
[como usar o clip como base para um exercício prático]
```

### Seção 6 — Tags e Busca
Para encontrar o clip rapidamente.
**Formato**:
```
Tags: [lista de tags — ex: #discovery #pergunta-consequencia #miner #best-practice #junior]
Palavras-Chave: [termos que aparecem no clip para busca textual]
Relacionado a: [outros Clip IDs relevantes]
```

## Exemplo
```
CLIP-2026-0089
Call: CALL-2026-0298 | Juliana Costa | 12/03/2026
Momento: 14:20 a 16:45 | Duração: 2:25

Categoria: Discovery | Subcategoria: Pergunta de consequência
Framework: Miner — Nível 3 | Tipo: Best Practice | Nível: Intermediário

TRANSCRIÇÃO:
[14:20] Lead: "Nosso problema é que perdemos muitos leads no funil..."
[14:28] Juliana: "E quando você perde esses leads, o que acontece com o investimento que já foi feito pra trazer eles?"
[14:35] Lead: "É... é dinheiro jogado fora, né..."
[14:40] Juliana: "Quanto mais ou menos por mês?"
[14:45] Lead: "Ah, uns 8 mil em ads... mais o tempo do time..."
[14:52] Juliana: "Então são 8 mil em ads mais, sei lá, 3 pessoas gastando tempo nisso?"
[15:00] Lead: "Isso... uns 15 mil por mês no total se contar tudo..."
[15:10] Juliana: "E em 12 meses, são 180 mil. Se metade desses leads tivessem convertido, quanto de revenue a mais vocês teriam?"
[15:25] Lead: "Cara... muito. Muito mais do que 180 mil..."

Ponto de Ensino: Como fazer o lead calcular o custo da própria dor em números concretos.
Tags: #discovery #custo-da-inacao #quantificacao #miner #best-practice
```

## Agente Responsável
`audit-agent` — Identifica momentos dignos de clip. `coaching-agent` — Cataloga e usa em treinamento.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Transcrição precisa e contextualizada.
