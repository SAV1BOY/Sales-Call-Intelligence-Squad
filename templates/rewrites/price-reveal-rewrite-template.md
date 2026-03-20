# Template de Reescrita de Revelação de Preço

> Reescrita do momento de revelação de preço com ancoragem adequada, value stack completo e técnica de apresentação.

## Quando Usar
Quando o closer revelou o preço de forma inadequada — sem ancoragem, sem value stack, muito cedo, ou de forma que gerou choque de preço no lead.

## Estrutura

### Seção 1 — Contexto do Momento de Preço
Dados do momento.
**Formato**:
```
Call ID: [ID]
Closer: [nome]
Momento da Revelação: [MM:SS] ([XX%] da call)
Preço Apresentado: [R$ XX.XXX]
Condições: [à vista / parcelado / opções]
Reação do Lead: [aceitação / hesitação / choque / objeção]
Value Stack Apresentado Antes: [Sim / Não / Parcial]
Ancoragem Usada: [tipo ou "nenhuma"]
```

### Seção 2 — Revelação Original (ANTES)
Como o closer apresentou o preço.
**Formato**:
```
CONTEXTO (últimas 3-5 falas antes do preço):
Closer: "[fala]"
Lead: "[fala]"
...

MOMENTO DA REVELAÇÃO:
Closer: "[fala exata de revelação do preço]"

REAÇÃO DO LEAD:
Lead: "[resposta exata]"
Tom/Pausa: [descrição — ex: "silêncio de 5 segundos, tom mudou"]

DIAGNÓSTICO:
- Value stack antes do preço: [completo / parcial / ausente]
- Ancoragem: [presente / ausente — tipo se presente]
- Contextualização: [por dia / por mês / ROI / comparação — ou "preço solto"]
- Técnica de revelação: [sanduíche / direto / contraste / decrescente]
- Tom do closer: [confiante / hesitante / apologético]
- Timing: [adequado / prematuro / tardio]
```

### Seção 3 — Revelação Reescrita (DEPOIS)
A versão com ancoragem e value stack.
**Formato**:
```
TÉCNICA: [Ancoragem por Contraste / Sanduíche / Valor Empilhado / Fragmentação]

ETAPA 1 — CUSTO DA INAÇÃO (âncora negativa):
Closer: "[fala que quantifica o custo de não resolver o problema]"
Objetivo: Estabelecer que NÃO comprar também tem um custo.

ETAPA 2 — VALUE STACK (empilhamento de valor):
Closer: "[apresentação de cada componente com valor individual]"

| Componente                 | Valor Individual | Acumulado   |
|----------------------------|------------------|-------------|
| [Componente principal]     | R$ [X.XXX]       | R$ [X.XXX]  |
| [Componente 2]             | R$ [X.XXX]       | R$ [XX.XXX] |
| [Bônus 1]                  | R$ [X.XXX]       | R$ [XX.XXX] |
| [Bônus 2]                  | R$ [X.XXX]       | R$ [XX.XXX] |
| [Garantia]                 | [inestimável]    | —           |
| VALOR TOTAL EMPILHADO      |                  | R$ [XX.XXX] |

ETAPA 3 — REVELAÇÃO COM CONTRASTE:
Closer: "[fala que revela o preço real em contraste com o valor empilhado]"

ETAPA 4 — CONTEXTUALIZAÇÃO:
Closer: "[fala que coloca o preço em perspectiva — por dia, por resultado, comparado a X]"

ETAPA 5 — TRANSIÇÃO PARA FECHAMENTO:
Closer: "[fala que move para o próximo passo sem pausar no preço]"

SCRIPT COMPLETO:
"[script fluido combinando todas as etapas]"
```

### Seção 4 — Justificativa
Análise de por que funciona.
**Formato**:
```
POR QUE FUNCIONA:
1. [Custo da inação cria referência — o lead compara o preço com o custo de não agir]
2. [Value stack faz o preço parecer pequeno em relação ao valor total]
3. [Contextualização por dia/por resultado torna o número mais digerível]
4. [Transição rápida para fechamento não dá tempo para objeção de preço]

ERROS DO ORIGINAL:
1. [Erro — ex: "preço revelado sem contexto, pareceu alto sem referência"]
2. [Erro — ex: "pausou depois do preço esperando reação, deu espaço para resistência"]
```

## Exemplo
```
CALL-2026-0342 | Rafael | R$ 12.000

ANTES (32:15):
"Então, o investimento é de 12 mil, que pode ser em 12x de mil no cartão."
Reação: Silêncio de 4s → "hmm, preciso pensar"

DEPOIS:
"Carla, você me disse que perde 3 horas por dia prospectando sem resultado. São 60h/mês. Se o seu tempo vale R$ 200/hora — e vale mais — são R$ 12.000 por mês que você tá queimando.

Agora, o que você leva:
- O sistema completo de captação (empresas cobram R$ 8.000 só por isso)
- As 12 sessões individuais (R$ 1.500 cada = R$ 18.000)
- O grupo de mastermind por 12 meses (R$ 6.000/ano)
- Acesso ao banco de templates (R$ 3.000)
- Garantia de 30 dias: se não fizer sentido, devolvemos 100%

Tudo isso junto, o valor real é mais de R$ 35.000. Mas como a gente quer que você comece agora, o investimento total é R$ 12.000. E se fechar hoje, parcelo em 12x de mil — menos do que você perde em um dia com o problema atual.

Faz sentido a gente fechar agora e eu já te mando o acesso?"
```

## Agente Responsável
`coaching-agent` — Cria rewrites de pricing como parte do coaching.

## Checklists de Qualidade
- `coaching-specificity-check.md` — Rewrite usa dados da call real.
- `coaching-actionability-check.md` — Script praticável pelo closer.
