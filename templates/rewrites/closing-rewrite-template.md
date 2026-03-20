# Template de Reescrita de Fechamento

> Reescrita do momento de fechamento com técnicas de assumptive close, alternativa e next step lock.

## Quando Usar
Quando o closer não pediu a venda, hesitou no momento do fechamento, ou usou uma técnica de fechamento ineficaz.

## Estrutura

### Seção 1 — Contexto do Fechamento
Dados do momento.
**Formato**:
```
Call ID: [ID]
Closer: [nome]
Momento do Fechamento: [MM:SS]
Sinais de Compra Observados: [lista — ex: "perguntou sobre prazo de entrega", "pediu detalhes de pagamento"]
Sinais Ignorados: [sinais de compra que o closer não capitalizou]
Resultado: [vendeu / não vendeu / follow-up]
```

### Seção 2 — Fechamento Original (ANTES)
O que o closer fez (ou não fez).
**Formato**:
```
CONTEXTO (últimas falas antes do fechamento ou não-fechamento):
Lead: "[fala — possível sinal de compra]"
Closer: "[resposta]"
Lead: "[fala]"

TENTATIVA DE FECHAMENTO:
Closer: "[fala exata — ou 'NÃO TENTOU FECHAR']"

REAÇÃO DO LEAD:
Lead: "[resposta — ou 'N/A se não houve tentativa']"

DIAGNÓSTICO:
- Pediu a venda: [Sim / Não]
- Técnica usada: [assumptive / alternativa / direto / urgência / nenhuma]
- Tom: [confiante / hesitante / desesperado / apologético]
- Timing: [no momento certo / muito cedo / muito tarde / não tentou]
- Tratou hesitação: [Sim / Não / N/A]
- Erro principal: [descrição]
```

### Seção 3 — Fechamento Reescrito (DEPOIS)
A versão corrigida com técnica adequada.
**Formato**:
```
TÉCNICA PRIMÁRIA: [Assumptive Close / Alternativa / Próximo Passo Natural / Trial Close]
TÉCNICA DE BACKUP: [caso a primária encontre resistência]

SCRIPT DE FECHAMENTO:

OPÇÃO A — ASSUMPTIVE CLOSE:
Closer: "[fala que assume a compra e vai para os detalhes logísticos]"
Exemplo: "Perfeito, Carla. Então vou te mandar o link de pagamento agora. Você prefere pagar à vista com o desconto ou parcelar em 12x?"

OPÇÃO B — FECHAMENTO POR ALTERNATIVA:
Closer: "[fala que oferece duas opções, ambas sendo 'sim']"
Exemplo: "Carla, pensando no seu momento, faz mais sentido começar com o plano completo ou com a versão acelerada de 90 dias?"

OPÇÃO C — PRÓXIMO PASSO NATURAL:
Closer: "[fala que transiciona naturalmente para ação]"
Exemplo: "Legal, então o próximo passo é eu te enviar o contrato e a gente já agendar sua primeira sessão. Qual o melhor email pra eu mandar?"

SE O LEAD HESITAR:
Closer: "[fala para tratar hesitação sem recuar]"
Exemplo: "Entendo que é uma decisão importante. Me diz — o que exatamente te faria sentir 100% confiante pra avançar agora?"

SE O LEAD PEDIR PARA PENSAR:
Closer: "[fala para investigar sem pressionar]"
Exemplo: "Claro, pensar é importante. Só pra eu entender — pensar sobre o quê especificamente? O investimento, o momento, ou tem algo que eu não expliquei bem?"
```

### Seção 4 — Next Step Lock
Como travar o próximo passo independente do resultado.
**Formato**:
```
SE VENDEU:
"[script de confirmação + próximos passos + onboarding]"
Exemplo: "Feito! Vou te mandar o link agora. Enquanto você faz o pagamento, já vou preparar seu acesso. Na segunda às 10h a gente faz a sessão de onboarding. Funciona pra você?"

SE NÃO VENDEU MAS HÁ INTERESSE:
"[script de follow-up com compromisso real]"
Exemplo: "OK, Carla. Vou te mandar um resumo do que conversamos por email. A gente se fala na quarta às 14h pra você me dizer sua decisão. Anoto aqui e te mando o convite. Combinado?"

SE NÃO VENDEU E SEM INTERESSE CLARO:
"[script de saída elegante com porta aberta]"
Exemplo: "Entendo, Carla. Vou te mandar o material e fico à disposição. Se o cenário mudar, é só me chamar. Posso te mandar um case detalhado da Marina que tem uma situação bem parecida com a sua?"
```

### Seção 5 — Justificativa
Por que cada técnica se aplica.
**Formato**:
```
POR QUE ASSUMPTIVE CLOSE:
[quando usar e por que funciona neste contexto]

POR QUE ALTERNATIVA:
[quando usar e por que funciona neste contexto]

ERROS DO ORIGINAL:
1. [ex: "Não pediu a venda — esperou o lead decidir sozinho"]
2. [ex: "Recuou ao primeiro sinal de hesitação"]
```

## Exemplo
```
CALL-2026-0342 | Rafael | 43:00

ANTES:
Lead: "Interessante... e como funciona o pagamento?"  ← SINAL DE COMPRA
Closer: "Então, pode ser à vista ou parcelado. Aí você me fala..."  ← DEVOLVEU A BOLA
Lead: "Tá, vou pensar e te falo..."
Closer: "Beleza, fico no aguardo!"  ← NÃO TRATOU

Diagnóstico: Lead deu sinal claro (perguntou sobre pagamento). Closer devolveu a decisão em vez de assumir a venda.

DEPOIS (Assumptive):
Lead: "Interessante... e como funciona o pagamento?"
Closer: "Ótima pergunta. Tem duas opções: à vista por R$ 10.800 ou 12x de R$ 1.000. A maioria dos nossos clientes vai de 12x pra não descapitalizar. Qual faz mais sentido pra você?"
Lead: "Acho que 12x..."
Closer: "Perfeito. Vou te mandar o link agora. Qual email você prefere?"
```

## Agente Responsável
`coaching-agent` — Cria rewrites de fechamento como parte do coaching.

## Checklists de Qualidade
- `coaching-specificity-check.md` — Rewrite baseado no contexto real da call.
- `coaching-actionability-check.md` — Scripts praticáveis.
