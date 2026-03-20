# Template de Trava de Próximo Passo

> Template para documentar e travar o próximo passo após cada call — contrato, pagamento, onboarding ou follow-up estruturado.

## Quando Usar
Ao final de toda call de vendas, independente do resultado. Toda call deve terminar com um próximo passo travado e documentado.

## Estrutura

### Seção 1 — Dados da Call
Identificação rápida.
**Formato**:
```
Call ID: [ID]
Closer: [nome]
Lead: [nome — empresa]
Data: [DD/MM/AAAA]
Resultado: [Vendeu / Follow-up / Perdido]
```

### Seção 2 — Próximo Passo Travado
O compromisso firmado ao final da call.
**Formato**:

**Se Vendeu:**
```
TIPO: VENDA FECHADA

Contrato:
- Enviado: [Sim / Não] — Canal: [email / WhatsApp]
- Prazo para Assinatura: [DD/MM/AAAA HH:MM]
- Status: [assinado / pendente]

Pagamento:
- Forma: [à vista / parcelado — detalhes]
- Valor: [R$ XX.XXX]
- Link/Boleto Enviado: [Sim / Não]
- Prazo: [DD/MM/AAAA]
- Status: [pago / pendente / processando]

Onboarding:
- Sessão Agendada: [Sim / Não]
- Data/Hora: [DD/MM/AAAA HH:MM]
- Responsável pelo Onboarding: [nome]
- Materiais Enviados: [kit de boas-vindas / acesso / etc.]
- O que o Cliente Precisa Preparar: [lista]

Promessas Feitas na Call:
- [promessa 1 — prazo — responsável]
- [promessa 2 — prazo — responsável]

Trecho de Confirmação:
"[fala do lead confirmando o acordo]" ([MM:SS])
```

**Se Follow-up:**
```
TIPO: FOLLOW-UP AGENDADO

Data do Follow-up: [DD/MM/AAAA HH:MM]
Canal: [call / WhatsApp / email]
Pauta Definida: [o que será discutido — ex: "decisão final após conversar com sócio"]
Convite Enviado: [Sim / Não]
Lead Confirmou: [Sim / Não]

O que o Lead Vai Fazer até Lá:
- [ação 1 — ex: "conversar com sócio sobre investimento"]
- [ação 2 — ex: "revisar proposta enviada"]

O que o Closer Vai Enviar/Fazer até Lá:
- [ação 1 — ex: "enviar case study detalhado"]
- [ação 2 — ex: "preparar proposta personalizada"]

Material de Suporte a Enviar:
| Material                  | Canal   | Prazo    | Status   |
|---------------------------|---------|----------|----------|
| [resumo da call]          | [email] | [DD/MM]  | [⬜/✅]  |
| [case study]              | [WhApp] | [DD/MM]  | [⬜/✅]  |
| [proposta personalizada]  | [email] | [DD/MM]  | [⬜/✅]  |

Trecho de Confirmação:
"[fala do lead confirmando o follow-up]" ([MM:SS])
```

**Se Perdido:**
```
TIPO: DEAL PERDIDO

Motivo: [motivo declarado pelo lead]
Porta Aberta: [Sim / Não]
Quando Recontatar: [prazo sugerido — ou "não recontatar"]
Gatilho para Recontato: [evento que justificaria novo contato]
Lead Nurturing: [adicionar a sequência de nurturing / não]

Trecho Final:
"[última fala relevante do lead]" ([MM:SS])
```

### Seção 3 — Checklist de Verificação
Confirmação de que o next step está sólido.
**Formato**:
```
- [ ] Data e hora específica definida (não "semana que vem")
- [ ] Lead confirmou verbalmente na call
- [ ] Convite/lembrete enviado por escrito (email ou WhatsApp)
- [ ] Pauta do próximo contato está clara para ambos
- [ ] Closer tem ação definida para o intervalo
- [ ] CRM atualizado com próximo passo e data
```

### Seção 4 — Alerta de Risco
Sinais de que o next step pode não acontecer.
**Formato**:
```
RISCO ALTO:
- [ ] Lead não confirmou com entusiasmo (hesitante)
- [ ] Data muito distante (>7 dias)
- [ ] Nenhuma ação intermediária do lead

MITIGAÇÃO:
- [ação para reduzir o risco — ex: "enviar mensagem de confirmação 24h antes"]
```

## Exemplo
```
CALL-2026-0342 | Rafael → Carla | Follow-up

Data: 20/03/2026 às 15:00 — Call de 15min
Pauta: Decisão final — Carla vai conversar com sócio antes
Convite: Enviado pelo Google Calendar
Lead confirmou: Sim — "Pode ser quinta às 3, anoto aqui" (45:10)

Rafael vai enviar: Case TechStar detalhado (até 19/03)
Carla vai fazer: Alinhar budget com sócio

RISCO: Médio — Lead engajada mas sócio é incógnita
Mitigação: Rafael envia mensagem de confirmação quarta à noite
```

## Agente Responsável
`audit-agent` — Verifica se next step lock foi executado. `coaching-agent` — Treina execução.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Next step tem evidência da call.
