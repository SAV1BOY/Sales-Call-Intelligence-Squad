# Brief de Análise de Deal Perdido

> Documento de entrada para investigação aprofundada de um deal que não fechou, com contexto, hipóteses e dados disponíveis.

## Quando Usar
Quando um deal de alto valor é perdido, quando há padrão recorrente de perda no mesmo ponto, ou quando o gestor solicita análise root cause de uma perda específica.

## Estrutura

### Seção 1 — Identificação do Deal
Dados do negócio perdido.
**Formato**:
```
Deal ID: [ID do deal no CRM]
Call ID(s): [IDs de todas as calls relacionadas]
Data da Call Final: [DD/MM/AAAA]
Valor Potencial: [R$ XX.XXX]
Closer: [nome]
Lead: [nome — empresa — cargo]
Oferta Apresentada: [produto/serviço — condição]
```

### Seção 2 — Linha do Tempo do Deal
Histórico de todas as interações até a perda.
**Formato**:
```
| Data       | Tipo de Interação | Resumo                        | Resultado         |
|------------|-------------------|-------------------------------|-------------------|
| [DD/MM]    | [SDR Call/Email]   | [o que aconteceu]             | [agendou/seguiu]  |
| [DD/MM]    | [Call de Vendas]   | [o que aconteceu]             | [follow-up/perdeu]|
```

### Seção 3 — Motivo Declarado da Perda
O que o lead disse e o que o closer reportou.
**Formato**:
```
Motivo Declarado pelo Lead: "[frase exata do lead, se disponível]"
Motivo Reportado pelo Closer: [interpretação do closer]
Momento da Perda: [em que ponto da call/jornada o deal morreu]
Houve Follow-up: [sim/não — quantos — resultado]
```

### Seção 4 — Hipóteses Iniciais
Possíveis causas a investigar.
**Formato**:
```
Hipótese 1: [descrição — ex: "Discovery insuficiente não revelou a dor real"]
Evidência Preliminar: [o que sugere esta hipótese]

Hipótese 2: [descrição — ex: "Ancoragem de preço fraca"]
Evidência Preliminar: [o que sugere esta hipótese]

Hipótese 3: [descrição — ex: "Lead não era decisor"]
Evidência Preliminar: [o que sugere esta hipótese]
```

### Seção 5 — Dados Disponíveis para Análise
Materiais que o analista pode consultar.
**Formato**:
```
Gravação(ões): [links]
Transcrição(ões): [links]
CRM Notes: [link ou conteúdo relevante]
Histórico de Email/WhatsApp: [disponível/não disponível]
Proposta Enviada: [link ou "não enviada"]
Score de Auditoria (se já auditada): [XX/100 ou "não auditada"]
```

### Seção 6 — Escopo da Análise
O que se espera da investigação.
**Formato**:
```
Pergunta Central: [o que queremos descobrir]
Profundidade: [análise rápida (30min) / análise completa (2h+)]
Output Esperado: [root cause + recomendação / relatório completo / input para coaching]
Prazo: [DD/MM/AAAA]
Solicitante: [nome — cargo]
```

## Exemplo
```
Deal ID: DEAL-4521
Call ID: CALL-2026-0338
Valor Potencial: R$ 24.000
Closer: Rafael Mendes | Lead: Bruno Almeida — DataCorp — CTO

Motivo Declarado: "Vou pensar com calma e volto semana que vem"
Motivo do Closer: "Lead gostou mas achou caro, pediu para pensar"
Follow-up: 2 tentativas sem resposta

Hipótese 1: Discovery não revelou urgência — lead não sentiu pressão de tempo
Hipótese 2: Value stack não justificou o ticket — comparação implícita com alternativa mais barata

Pergunta Central: Por que o lead não sentiu urgência para decidir na call?
Profundidade: Análise completa
Output: Root cause + rewrite de discovery + input para coaching do Rafael
```

## Agente Responsável
`orchestrator-agent` — Compila o brief e aciona o fluxo de análise de deal perdido.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Garante que a análise resultante é baseada em evidência.
