# Relatório de Detecção de Frameworks

> Relatório que mapeia quais frameworks e técnicas de vendas foram detectados ou ausentes na call, com evidência e avaliação de execução.

## Quando Usar
Como componente da auditoria completa, ou isoladamente quando o foco é avaliar a aderência do closer às metodologias ensinadas.

## Estrutura

### Seção 1 — Resumo de Detecção
Visão consolidada dos frameworks encontrados.
**Formato**:
```
Call ID: [ID] | Closer: [nome] | Score: [XX/100]

Frameworks Detectados: [N de M possíveis]
Execução Média: [Alta / Média / Baixa]

| Framework        | Detectado | Momento   | Execução      | Score |
|------------------|-----------|-----------|---------------|-------|
| [Miner]          | [Sim/Não] | [MM:SS]   | [Alta/Méd/Bx] | [X/10]|
| [Belfort SLS]    | [Sim/Não] | [MM:SS]   | [Alta/Méd/Bx] | [X/10]|
| [SPIN]           | [Sim/Não] | [MM:SS]   | [Alta/Méd/Bx] | [X/10]|
| [Sandler]        | [Sim/Não] | [MM:SS]   | [Alta/Méd/Bx] | [X/10]|
| [Challenger]     | [Sim/Não] | [MM:SS]   | [Alta/Méd/Bx] | [X/10]|
```

### Seção 2 — Frameworks Detectados — Análise Detalhada
Para cada framework encontrado, análise profunda.
**Formato**:
```
FRAMEWORK: [Nome do Framework]
Status: DETECTADO
Momento(s): [MM:SS a MM:SS]
Componentes Executados:
  - [Componente 1]: [Sim/Não] — "[trecho que comprova]" ([MM:SS])
  - [Componente 2]: [Sim/Não] — "[trecho que comprova]" ([MM:SS])
  - [Componente 3]: [Sim/Não] — "[trecho que comprova]" ([MM:SS])

Score de Execução: [X/10]
Justificativa: [por que este score — o que fez bem e o que faltou]
Impacto no Resultado: [como a execução deste framework afetou a call]
```

### Seção 3 — Frameworks Ausentes — Análise de Lacunas
Frameworks esperados mas não aplicados.
**Formato**:
```
FRAMEWORK: [Nome do Framework]
Status: AUSENTE
Momento Esperado: [MM:SS — fase da call onde deveria ter aparecido]
Contexto: [o que estava acontecendo que pedia este framework]
Fala do Closer no Momento: "[o que o closer fez/disse em vez disso]"
Impacto da Ausência: [como a não-aplicação afetou o resultado]
Recomendação: [como aplicar este framework neste contexto]
```

### Seção 4 — Conflitos entre Frameworks
Momentos onde frameworks se chocaram.
**Formato**:
```
CONFLITO: [Framework A] vs [Framework B]
Momento: [MM:SS]
Descrição: [como os frameworks se contradisseram na prática]
Resolução Recomendada: [qual deveria ter prevalecido e por quê]
```

### Seção 5 — Recomendações de Desenvolvimento
Prioridades baseadas nos gaps de framework.
**Formato**:
```
1. [Framework] — [componente específico] — [ação de desenvolvimento]
2. [Framework] — [componente específico] — [ação de desenvolvimento]
3. [Framework] — [componente específico] — [ação de desenvolvimento]
```

## Exemplo
```
CALL-2026-0342 | Rafael | 64/100 | Detectados: 2 de 5

FRAMEWORK: Miner — DETECTADO (parcial)
Momento: 09:00 a 14:00
- Perguntas de situação: Sim — "Quantos leads vocês geram por mês?" (09:15)
- Perguntas de problema: Sim — "E qual o maior desafio?" (10:30)
- Perguntas de consequência: Não — pulou direto para apresentação
- Perguntas de solução ideal: Não
Score: 4/10
Impacto: Discovery ficou na superfície, lead não sentiu urgência

FRAMEWORK: SPIN — AUSENTE
Momento Esperado: 10:30-14:00
Contexto: Lead mencionou problema mas closer não aprofundou implicação
Impacto: Sem implicação, o lead não percebeu o custo de não resolver
```

## Agente Responsável
`audit-agent` — Detecta e analisa frameworks durante a auditoria.

## Checklists de Qualidade
- `qa-methodology-consistency-check.md` — Garante coerência entre frameworks analisados.
- `qa-evidence-completeness-check.md` — Todo framework detectado/ausente tem evidência.

## Preenchido Por

- **Task(s)**: framework-detection
- **Agente(s) responsável(is)**: framework-detector, alex-hormozi, jeremy-miner, jordan-belfort, cole-gordon, neil-rackham, matthew-dixon
- **Workflow(s)**: Auditoria Completa — Detecção de Frameworks (pipeline per-call)
- **Frequência**: per-call
- **Registro**: data/registries/framework-detection-registry
