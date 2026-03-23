# Relatório de Auditoria de Handoff SDR→Closer

> Relatório que avalia a qualidade da passagem de bastão entre SDR e closer — informações transferidas, alinhamento de expectativas e impacto na call.

## Quando Usar
Quando há suspeita de que a qualidade do handoff SDR está impactando a performance das calls, ou como análise periódica da interface SDR-Closer.

## Estrutura

### Seção 1 — Dados do Handoff
Identificação do caso analisado.
**Formato**:
```
Call de Vendas ID: [ID]
Call/Interação SDR: [ID ou descrição]
SDR: [nome]
Closer: [nome]
Lead: [nome — empresa]
Data do Handoff: [DD/MM/AAAA]
Tempo entre Handoff e Call: [horas/dias]
Canal de Handoff: [CRM / Slack / verbal / outro]
```

### Seção 2 — Informações Transferidas
O que o SDR passou ao closer.
**Formato**:
```
| Informação                    | Transferida | Precisa | Usada pelo Closer |
|-------------------------------|-------------|---------|---------------------|
| Nome e cargo do lead          | [Sim/Não]   | [Sim/Não]| [Sim/Não]          |
| Empresa e segmento            | [Sim/Não]   | [Sim/Não]| [Sim/Não]          |
| Dor/necessidade principal     | [Sim/Não]   | [Sim/Não]| [Sim/Não]          |
| Orçamento/faixa de investimento| [Sim/Não]  | [Sim/Não]| [Sim/Não]          |
| Autoridade de decisão         | [Sim/Não]   | [Sim/Não]| [Sim/Não]          |
| Timeline/urgência             | [Sim/Não]   | [Sim/Não]| [Sim/Não]          |
| Expectativa para a call       | [Sim/Não]   | [Sim/Não]| [Sim/Não]          |
| Objeções já levantadas        | [Sim/Não]   | [Sim/Não]| [Sim/Não]          |
| Contexto pessoal relevante    | [Sim/Não]   | [Sim/Não]| [Sim/Não]          |

Score de Completude: [X/9 campos preenchidos]
Score de Precisão: [X/9 campos corretos]
Score de Utilização pelo Closer: [X/9 campos utilizados na call]
```

### Seção 3 — Alinhamento de Expectativas
O que o lead esperava vs. o que encontrou.
**Formato**:
```
O QUE O SDR PROMETEU/COMUNICOU:
"[o que o SDR disse ao lead sobre a call — se disponível]"
Fonte: [gravação SDR / CRM notes / relato]

O QUE O LEAD ESPERAVA:
"[frase do lead no início da call indicando expectativa]" ([MM:SS])

O QUE O CLOSER ENTREGOU:
[descrição do que aconteceu na call]

ALINHAMENTO: [Total / Parcial / Desalinhado]
Impacto do Desalinhamento: [se houver — como afetou a call]
```

### Seção 4 — Impacto na Call de Vendas
Como a qualidade do handoff afetou o resultado.
**Formato**:
```
IMPACTOS POSITIVOS:
- [informação que ajudou o closer — como — trecho da call]

IMPACTOS NEGATIVOS:
- [informação faltante que prejudicou — como — trecho da call]
- [informação errada que confundiu — como — trecho da call]

TEMPO DESPERDIÇADO:
- [minutos gastos requalificando o lead — MM:SS a MM:SS]
- Percentual da call gasto com informação que deveria ter vindo do SDR: [XX%]

RESULTADO ESTIMADO SEM OS PROBLEMAS DE HANDOFF:
[análise contrafactual — o que teria mudado com handoff perfeito]
```

### Seção 5 — Recomendações
Para SDR, closer e processo.
**Formato**:
```
PARA O SDR:
1. [recomendação específica]
2. [recomendação específica]

PARA O CLOSER:
1. [recomendação específica — como compensar handoff incompleto]

PARA O PROCESSO:
1. [recomendação de processo — ex: "adicionar campo X ao formulário de handoff"]
2. [recomendação de processo — ex: "SDR incluir gravação da qualificação"]
```

## Exemplo
```
Call: CALL-2026-0342 | SDR: Ana Paula | Closer: Rafael | Lead: Carla — TechFlow
Handoff via CRM | 48h entre handoff e call

Completude: 5/9 | Precisão: 4/5 | Utilização: 3/5
Faltou: Orçamento, autoridade, objeções prévias, expectativa para a call

Alinhamento: Parcial
Lead esperava "conversa rápida de 20min sobre preço" — call durou 47min com pitch completo
Rafael gastou 8min requalificando (17% da call)

Impacto: Se Rafael soubesse que Carla já tinha budget definido e era decisora, poderia ter pulado 8min de qualificação e investido em discovery mais profunda.
```

## Agente Responsável
`audit-agent` — Avalia handoff como parte da auditoria ou em análise dedicada.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Análise baseada em evidência das duas interações.

## Preenchido Por

- **Task(s)**: analyze-sdr-handoff
- **Agente(s) responsável(is)**: sdr-handoff-analyst, call-auditor
- **Workflow(s)**: Análise por Fase da Call — Handoff SDR (pipeline per-call)
- **Frequência**: per-call
- **Registro**: data/registries/handoff-registry
