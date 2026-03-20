# Template de Lições Aprendidas

> Template para documentar o que aconteceu, por que aconteceu e o que aprendemos — transformando cada call em conhecimento reutilizável.

## Quando Usar
Após calls com resultado surpreendente (ganho inesperado ou perda evitável), após ciclos de coaching, ou ao final de cada sprint/período para consolidar aprendizados.

## Estrutura

### Seção 1 — Identificação
Dados do evento que gerou o aprendizado.
**Formato**:
```
Lição ID: [LL-AAAA-NNNN]
Origem: [Call ID / Ciclo de Coaching / Análise Semanal / Outro]
Data do Evento: [DD/MM/AAAA]
Data do Registro: [DD/MM/AAAA]
Registrado por: [nome/agente]
Categoria: [Técnica de Vendas / Processo / Oferta / Mercado / Coaching / Operacional]
```

### Seção 2 — O que Aconteceu
Descrição factual do evento.
**Formato**:
```
CONTEXTO:
[descrição objetiva da situação — quem, o quê, quando, onde]

EVENTO:
[o que aconteceu de fato — descrição cronológica]

RESULTADO:
[qual foi o desfecho — positivo ou negativo]
Resultado Esperado: [o que esperávamos que acontecesse]
Resultado Real: [o que de fato aconteceu]
Gap: [diferença entre esperado e real]
```

### Seção 3 — Por que Aconteceu
Análise de causa raiz.
**Formato**:
```
CAUSA RAIZ:
[a razão fundamental — não o sintoma]

CADEIA CAUSAL:
1. [primeiro fator] → levou a
2. [segundo fator] → que causou
3. [terceiro fator] → resultando em
4. [resultado final]

FATORES CONTRIBUINTES:
- [fator 1 — ex: "falta de treinamento em X"]
- [fator 2 — ex: "processo não previa esta situação"]
- [fator 3 — ex: "informação indisponível no momento da call"]

EVIDÊNCIA:
- "[trecho ou dado que comprova a análise]"
- Call/Fonte: [referência]
```

### Seção 4 — O que Aprendemos
O insight extraído do evento.
**Formato**:
```
LIÇÃO PRINCIPAL:
[afirmação clara e concisa do aprendizado — ex: "Perguntas de consequência antes de revelar preço reduzem objeção de preço em 60%"]

LIÇÕES SECUNDÁRIAS:
1. [aprendizado adicional]
2. [aprendizado adicional]

REGRA DERIVADA:
[se puder transformar em regra operacional — ex: "SEMPRE fazer pelo menos 2 perguntas de consequência antes de pricing"]

APLICABILIDADE:
- Se aplica a: [quais closers / situações / ofertas / tipos de lead]
- NÃO se aplica a: [exceções conhecidas]
```

### Seção 5 — Ações Decorrentes
O que muda a partir deste aprendizado.
**Formato**:
```
| Ação                              | Tipo      | Responsável | Prazo  | Status |
|-----------------------------------|-----------|-------------|--------|--------|
| [mudança de processo]             | Processo  | [nome]      | [DD/MM]| ⬜     |
| [novo treinamento]                | Coaching  | [nome]      | [DD/MM]| ⬜     |
| [atualização de playbook]         | Documento | [nome]      | [DD/MM]| ⬜     |
| [comunicação ao time]             | Operação  | [nome]      | [DD/MM]| ⬜     |

COMO PREVENIR RECORRÊNCIA:
[descrição de mecanismo preventivo — ex: "checklist de pricing adicionado ao pre-call"]

COMO VERIFICAR QUE A LIÇÃO FOI ABSORVIDA:
[métrica ou observação — ex: "monitorar % de calls com pergunta de consequência nas próximas 2 semanas"]
```

### Seção 6 — Disseminação
Como o aprendizado será compartilhado.
**Formato**:
```
Compartilhado com: [time / gestor / outro squad]
Canal: [reunião semanal / Slack / documento / training]
Data: [DD/MM/AAAA]
Adicionado ao Playbook: [Sim / Não — qual seção]
Clip de Referência: [Clip ID, se houver]
```

## Exemplo
```
LL-2026-0034 | Origem: CALL-2026-0342 + CALL-2026-0351
Categoria: Técnica de Vendas

O QUE ACONTECEU:
Dois deals perdidos na mesma semana com a mesma objeção: "preciso pensar". Em ambos os casos, o closer revelou preço sem value stack e sem quantificar o custo da inação.

POR QUE:
Os closers estavam pulando de discovery diretamente para preço, sem construir valor. A pressa para "não perder o lead" gerou o efeito oposto.

LIÇÃO: "Nunca revelar preço antes de: (1) quantificar custo da inação, (2) apresentar value stack completo, (3) confirmar que o lead entende o valor. A pressa para fechar é o maior inimigo do fechamento."

AÇÃO: Adicionar checkpoint de "value stack completo" antes de pricing no scorecard do audit-agent.
```

## Agente Responsável
`coaching-agent` — Registra lições de coaching. `audit-agent` — Identifica padrões que geram lições.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Lição baseada em evidência, não opinião.
