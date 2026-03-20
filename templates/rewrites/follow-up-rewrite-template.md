# Template de Reescrita de Follow-Up

> Reescrita de mensagens e abordagens de follow-up para manter o momentum e trazer o lead de volta à decisão.

## Quando Usar
Quando o closer perdeu o lead no follow-up (ghosting), quando o follow-up é genérico ("oi, pensou?"), ou quando precisa de estratégia para reengajar leads parados.

## Estrutura

### Seção 1 — Contexto do Follow-Up
Dados da situação.
**Formato**:
```
Call ID Original: [ID]
Closer: [nome]
Lead: [nome — empresa]
Data da Call: [DD/MM/AAAA]
Resultado da Call: [não vendeu — motivo declarado]
Último Contato: [DD/MM/AAAA — canal]
Follow-ups Realizados: [N]
Status Atual: [respondeu / não respondeu / ghosting]
Tempo desde a Call: [N dias]
```

### Seção 2 — Follow-Up Original (ANTES)
O que o closer fez ou planejou fazer.
**Formato**:
```
FOLLOW-UP ENVIADO/PLANEJADO:
Canal: [WhatsApp / Email / Ligação]
Mensagem: "[texto exato da mensagem de follow-up]"
Timing: [quando foi enviado — dias após a call]
Resultado: [respondeu / visualizou sem responder / não visualizou]

DIAGNÓSTICO:
- Personalização: [Alta / Média / Baixa / Genérica]
- Valor Adicionado: [trouxe algo novo / repetiu o que já disse / só cobrou decisão]
- Tom: [consultivo / vendedor / desesperado / profissional]
- Call to Action: [claro / vago / ausente]
- Timing: [adequado / muito cedo / muito tarde]
- Erro principal: [descrição]
```

### Seção 3 — Estratégia de Follow-Up Reescrita (DEPOIS)
Sequência completa de follow-up.
**Formato**:
```
ESTRATÉGIA: [nome — ex: "Sequência de Valor + Urgência Progressiva"]
Duração: [N dias]
Canais: [WhatsApp + Email + Ligação]
Número de Toques: [N]

TOQUE 1 — [Timing: ex: "24h após a call"] — [Canal]
Objetivo: [ex: "Reforçar valor, não cobrar decisão"]
Mensagem:
"[texto completo da mensagem]"
Por que funciona: [justificativa]

TOQUE 2 — [Timing: ex: "3 dias após a call"] — [Canal]
Objetivo: [ex: "Adicionar valor novo — case relevante"]
Mensagem:
"[texto completo]"
Por que funciona: [justificativa]

TOQUE 3 — [Timing: ex: "5 dias após a call"] — [Canal]
Objetivo: [ex: "Criar micro-compromisso — pergunta simples"]
Mensagem:
"[texto completo]"
Por que funciona: [justificativa]

TOQUE 4 — [Timing: ex: "7 dias após a call"] — [Canal]
Objetivo: [ex: "Urgência genuína — prazo ou disponibilidade"]
Mensagem:
"[texto completo]"
Por que funciona: [justificativa]

TOQUE 5 (FINAL) — [Timing: ex: "10 dias após a call"] — [Canal]
Objetivo: [ex: "Fechamento suave — porta aberta sem insistência"]
Mensagem:
"[texto completo]"
Por que funciona: [justificativa]
```

### Seção 4 — Gatilhos de Reengajamento
Motivos legítimos para retomar contato.
**Formato**:
```
GATILHO 1: Novo Conteúdo/Case Relevante
"[mensagem modelo usando case novo como pretexto]"

GATILHO 2: Mudança na Oferta/Condição
"[mensagem modelo comunicando mudança relevante]"

GATILHO 3: Evento ou Deadline
"[mensagem modelo usando evento como gatilho de urgência]"

GATILHO 4: Insight Personalizado
"[mensagem modelo com insight específico para o negócio do lead]"
```

### Seção 5 — O que Evitar
Anti-padrões de follow-up.
**Formato**:
```
NÃO FAÇA:
1. "[exemplo de mensagem ruim]" — Por que não funciona: [razão]
2. "[exemplo de mensagem ruim]" — Por que não funciona: [razão]
3. "[exemplo de mensagem ruim]" — Por que não funciona: [razão]
4. "[exemplo de mensagem ruim]" — Por que não funciona: [razão]
```

## Exemplo
```
CALL-2026-0342 | Rafael → Carla (TechFlow) | "Preciso pensar"
2 follow-ups feitos | Ghosting após o segundo

ANTES:
Follow-up 1 (dia seguinte, WhatsApp): "Oi Carla, tudo bem? Conseguiu pensar sobre nossa conversa?"
Follow-up 2 (4 dias depois): "Carla, alguma novidade? Estou à disposição!"
Resultado: Visualizou, não respondeu.
Erro: Zero valor adicionado, tom de cobrança, sem CTA específico.

DEPOIS:

TOQUE 1 (24h — WhatsApp):
"Carla, obrigado pela conversa de ontem! Fiquei pensando no que você falou sobre perder 3h/dia com prospecção. Separei um case da Marina (TechStar) que estava na mesma situação — ela eliminou a prospecção manual em 45 dias. Posso te mandar o case detalhado?"
→ Adiciona valor, referencia a dor dela, pede micro-compromisso (responder "sim")

TOQUE 2 (3 dias — Email):
Assunto: "O cálculo que eu deveria ter feito com você, Carla"
"Carla, depois da nossa conversa fiz uma conta rápida: 3h/dia x 22 dias x R$ 200/hora = R$ 13.200/mês em tempo perdido. Em 12 meses são R$ 158.400. O investimento que conversamos é menos de 8% disso. Achei que valia compartilhar. Se quiser retomar, estou aqui."
→ Quantifica o custo da inação, coloca o preço em perspectiva sem "cobrar"

NÃO FAÇA:
"Oi, pensou?" — Genérico, zero valor, tom de cobrança
"Última chance!" — Urgência falsa gera desconfiança
"Tá tudo bem? Sumiu rs" — Informal demais, coloca pressão social
```

## Agente Responsável
`coaching-agent` — Cria rewrites de follow-up como parte do coaching.

## Checklists de Qualidade
- `coaching-actionability-check.md` — Mensagens prontas para uso.
- `coaching-specificity-check.md` — Personalização baseada na call real.
