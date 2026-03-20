# Sistema de Quality Gates — Sales Call Intelligence Squad

## Visao Geral

O sistema de Quality Gates do Sales Call Intelligence Squad opera em uma **cascata de 4 niveis** que garante que nenhum output saia do squad sem validacao adequada. Cada nivel funciona como um filtro progressivo de qualidade: quanto mais alto o nivel, mais rigorosa a validacao e maior a autoridade de decisao.

A logica e simples: o agente valida seu proprio trabalho (Nivel 1), o QA Guardian valida a tarefa consolidada (Nivel 2), o Sales Chief valida o deliverable final (Nivel 3), e antes de qualquer handoff para outro squad, o Sales Chief garante que o pacote esta completo e compreensivel (Nivel 4).

Cada nivel tem criterios objetivos, ciclos de rework limitados e regras claras de escalacao. Isso evita loops infinitos de revisao e garante que decisoes sejam tomadas em tempo habil.

---

## Nivel 1 — Agent-Level Gate

### Descricao

Cada agente executa uma **auto-validacao** do seu proprio output antes de submeter ao proximo nivel. Este e o filtro mais rapido e mais frequente — acontece em toda interacao de todo agente.

### Criterios de Passagem

- **Checklist minimo**: o agente deve atingir >= 80% dos itens obrigatorios do checklist associado a sua tarefa
- **Evidencia com timestamp**: toda afirmacao critica deve ser acompanhada de trecho da transcricao com timestamp no formato `[MM:SS]` ou `[HH:MM:SS]`
- **Sem afirmacoes sem suporte**: nenhuma critica, score ou recomendacao pode existir sem evidencia concreta da transcricao
- **Formato padrao**: output deve seguir o template designado no `config.yaml`

### Rework

- **Maximo**: 2 ciclos internos de auto-correcao
- Se apos 2 ciclos o agente nao atingir os criterios, o output e escalado ao **QA Guardian** com flag de dificuldade

### Escalacao

- Destino: **QA Guardian**
- Trigger: 2 ciclos internos sem atingir 80% do checklist

---

## Nivel 2 — Task-Level Gate

### Descricao

O **QA Guardian** valida o output consolidado de uma tarefa inteira. Uma tarefa pode envolver multiplos agentes (ex: `full-call-audit` envolve call-auditor, framework-detector, scorecard-analyst, objection-specialist, pricing-anchoring-analyst e talk-ratio-analyst). O QA Guardian garante que os outputs individuais sao coerentes entre si e que a tarefa como um todo atende aos padroes de qualidade.

### Criterios de Passagem

- **Todos os checklists obrigatorios**: cada checklist listado na tarefa (conforme `config.yaml`) deve ter score >= 80%
- **Sem contradicoes entre agentes**: se dois agentes divergem sobre a mesma fase ou metrica, a contradicao deve ser resolvida antes de aprovacao
- **Campos do template preenchidos**: todos os campos obrigatorios do template de output devem estar completos
- **Score de confianca**: confianca no score >= 0.7 (conforme `score_thresholds.operational.audit_min_confidence`)

### Rework

- **Maximo**: 3 ciclos de volta ao agente owner da etapa que falhou
- Cada ciclo de rework deve ser documentado no `data/registries/lessons-learned-registry`

### Escalacao

- Destino: **Sales Chief**
- Trigger: 3 ciclos sem resolucao, OU conflito entre especialistas que o QA Guardian nao consegue arbitrar

---

## Nivel 3 — Chief-Level Gate

### Descricao

O **Sales Chief** valida o deliverable final antes de ser publicado, entregue ao gestor ou ao closer. Este e o nivel de aprovacao executiva dentro do squad.

### Criterios de Passagem

- **Score thresholds atendidos**: output deve atender aos thresholds definidos em `score_thresholds` do `config.yaml`
  - `critical` (< 40): treinamento imediato obrigatorio
  - `developing` (40-59): coaching semanal
  - `good` (60-79): refinamento tatico
  - `excellent` (80-89): closer referencia
  - `gold_standard` (90-95+): benchmark do squad
- **Coerencia cross-task**: se multiplas tarefas alimentam o mesmo deliverable, os resultados devem ser coerentes
- **Acionabilidade**: toda recomendacao deve ser executavel pelo closer ou gestor no curto prazo
- **Rewrites presentes**: momentos criticos devem ter rewrite no formato antes/depois

### Decisoes Possiveis

| Decisao | Significado | Proxima Acao |
|---------|-------------|--------------|
| **APPROVE** | Output atende todos os criterios | Publicar / entregar |
| **APPROVE WITH NOTES** | Output bom com ressalvas menores | Publicar com observacoes documentadas |
| **REWORK** | Gaps significativos identificados | Retornar ao agente/QA Guardian |
| **ESCALATE** | Problema fora do escopo do squad | Criar handoff brief para squad relevante |

### Escalacao

- Destino: **C-Level Squad** ou **Advisory Board** (conforme `delegation_rules.cross_squad`)
- Trigger: problema estrategico de pricing, oferta ou fit closer-oferta

---

## Nivel 4 — Cross-Squad Gate

### Descricao

Antes de qualquer handoff sair do Sales Call Intelligence Squad para outro squad (Copy, Traffic, Brand, Storytelling, C-Level, Data, Movement ou Advisory Board), o **Sales Chief** valida que o pacote e auto-suficiente para o squad receptor.

### Criterios de Passagem

- **Handoff brief completo**: template `templates/operational/cross-squad-handoff-template` preenchido integralmente
- **Contexto suficiente**: squad receptor consegue agir sem precisar voltar para pedir esclarecimentos
- **Qualidade do output >= GOOD**: output que origina o handoff deve ter classificacao minima GOOD (>= 80%)
- **Shared assets atualizados**: assets compartilhados entre squads (conforme `cross_squad` no `config.yaml`) devem estar atualizados

### Responsavel

- **Sales Chief** e o unico responsavel por aprovar handoffs cross-squad
- Nenhum agente pode enviar informacao para outro squad sem aprovacao do Sales Chief

---

## Protocolo de Rework

### Ciclos Maximos por Nivel

| Nivel | Max Ciclos | Responsavel pelo Rework | Escalacao se Exceder |
|-------|-----------|------------------------|---------------------|
| Nivel 1 — Agent | 2 | Proprio agente | QA Guardian |
| Nivel 2 — Task | 3 | Agente owner da etapa | Sales Chief |
| Nivel 3 — Chief | 1 | QA Guardian + agente | C-Level / Advisory |
| Nivel 4 — Cross-Squad | 1 | Sales Chief | Reuniao cross-squad |

### Quando os Ciclos se Esgotam

1. **Nivel 1 esgotado**: QA Guardian assume a revisao e decide se o problema e do agente ou da tarefa
2. **Nivel 2 esgotado**: Sales Chief decide entre: aprovar com ressalvas, reassignar a outro agente, ou escalar
3. **Nivel 3 esgotado**: handoff para C-Level ou Advisory Board com documentacao completa do problema
4. **Nivel 4 esgotado**: reuniao sincrona entre Sales Chief e chief do squad receptor

### Requisitos de Documentacao

- Todo ciclo de rework deve ser registrado em `data/registries/lessons-learned-registry`
- Registro deve conter: tarefa, agente, motivo da rejeicao, correcao aplicada, resultado
- Padroes recorrentes de rework devem gerar acao preventiva (atualizacao de checklist, treinamento, etc.)

---

## Cadeia de Aprovacao

```
Agente (auto-validacao)
    |
    v
QA Guardian (validacao de tarefa)
    |
    v
Sales Chief (aprovacao final)
    |
    v
[Cross-Squad Handoff] (quando aplicavel)
```

### Autoridade de Decisao por Nivel

| Nivel | Responsavel | Pode Aprovar? | Pode Reprovar? | Pode Escalar? |
|-------|-------------|--------------|----------------|---------------|
| Agent Gate | Agente individual | Sim (auto-pass) | Sim (auto-rework) | Sim → QA Guardian |
| Task Gate | QA Guardian | Sim | Sim | Sim → Sales Chief |
| Chief Gate | Sales Chief | Sim | Sim | Sim → C-Level/Advisory |
| Cross-Squad Gate | Sales Chief | Sim | Sim | Sim → Reuniao cross-squad |

### Regras Especiais

- **Certificacao de closer**: requer aprovacao tripla — `closer-trainer` + `qa-guardian` + `sales-chief`
- **Calibracao de scoring**: requer `qa-guardian` + `scorecard-analyst`
- **Revisao de rewrites**: requer `coaching-rewriter` + `qa-guardian`

---

## Matriz Gate x Task

A tabela abaixo mapeia cada uma das 25 tarefas de roteamento do `config.yaml` aos quality gates aplicaveis.

| Task | Agent Gate | Task Gate | Chief Gate | Cross-Squad Gate |
|------|-----------|-----------|------------|-----------------|
| intake-call-recording | transcript-analyst checklist | transcript-normalization-quality | — | — |
| normalize-and-segment | transcript-analyst checklist | transcript-normalization-quality, minute-by-minute-analysis-quality | — | — |
| full-call-audit | per-agent checklists (6 agentes) | call-audit-quality, minute-by-minute-analysis-quality, framework-detection-quality, call-scorecard-quality, root-cause-analysis-quality | Sales Chief review | — |
| framework-detection | per-agent checklists (7 agentes) | framework-detection-quality, spin-sequence-check, miner-consequence-questions-check, belfort-straight-line-check, cole-frame-check | Sales Chief review | — |
| analyze-rapport-and-frame | per-agent checklists | warm-up-quality, first-pact-quality, cole-frame-check, dan-doctor-frame-check | — | — |
| analyze-discovery | per-agent checklists | spin-situation/problem/implication/need-payoff-quality, nepq-consequence-questions-quality, qualification-depth-quality, diagnosis-depth-quality | — | — |
| analyze-pitch | per-agent checklists | second-pact-quality, company/method/product-presentation-quality, pitch-uses-lead-language-quality, social-proof-quality | — | — |
| analyze-pricing | per-agent checklists | value-stack-quality, price-anchoring-quality, risk-reversal-quality, concession-control-quality, pricing-analysis-quality | — | — |
| analyze-objections | per-agent checklists | objection-isolation-quality, money-objection-quality, looping-quality, belief-shift-quality, preventive-objection-handling-quality, bradley-universal-objections-check | — | — |
| analyze-closing | per-agent checklists | decision-commitment-quality, assumptive-close-quality, next-step-lock-quality, no-maybe-zone-quality | — | — |
| analyze-talk-ratio | per-agent checklists | talk-ratio-analysis-quality | — | — |
| analyze-sdr-handoff | per-agent checklists | handoff-quality | — | — |
| rewrite-critical-moments | per-agent checklists | rewrite-quality, coaching-plan-quality | Sales Chief review | — |
| build-coaching-pack | per-agent checklists | manager-review-quality, coaching-plan-quality | Sales Chief review | — |
| certify-closer | per-agent checklists | rep-certification-quality | Sales Chief review (tripla aprovacao) | — |
| extract-win-patterns | per-agent checklists | win-loss-analysis-quality, best-moments-library-quality | Sales Chief review | — |
| extract-loss-patterns | per-agent checklists | win-loss-analysis-quality, handoff-quality, promise-sanity-check-quality | Sales Chief review | — |
| analyze-offer-fit | per-agent checklists | qualification-analysis-quality, promise-sanity-check-quality | Sales Chief review | — |
| weekly-sales-quality-review | per-agent checklists | manager-review-quality | Sales Chief review | — |
| monthly-closer-certification | per-agent checklists | rep-certification-quality | Sales Chief review (tripla aprovacao) | — |
| cross-squad-intelligence-sync | per-agent checklists | cross-squad-copy/traffic/offer/ops-handoff-quality | Sales Chief review | Sales Chief valida handoff brief |
| update-objections-library | per-agent checklists | objections-library-update-quality | — | — |
| calibrate-scoring | per-agent checklists | qa-score-calibration-check | Sales Chief review | — |

### Legenda

- **Agent Gate**: auto-validacao de cada agente envolvido na tarefa (checklist >= 80%)
- **Task Gate**: QA Guardian valida output consolidado usando os checklists listados
- **Chief Gate**: Sales Chief valida deliverable final (quando marcado)
- **Cross-Squad Gate**: Sales Chief valida handoff para outro squad (apenas `cross-squad-intelligence-sync`)

---

## Scoring Rubric Padrao

Todos os itens de checklist do squad devem ser pontuados utilizando a escala padrao de 0 a 5:

| Score | Significado | Descricao Detalhada |
|-------|------------|---------------------|
| 0 | Ausente | Item nao abordado no output — completamente omitido |
| 1 | Mencionado sem evidencia | Item citado superficialmente, sem trecho de transcricao ou dado concreto |
| 2 | Presente com evidencia fraca | Item presente mas com evidencia generica, sem timestamp ou trecho vago |
| 3 | Presente com evidencia | Item abordado com trecho especifico da transcricao + timestamp. **Este e o nivel minimo aceitavel.** |
| 4 | Forte com evidencia e analise | Trecho + timestamp + analise do impacto + recomendacao concreta |
| 5 | Exemplar / swipe quality | Material de referencia para o squad. Pode ser usado em treinamento e swipe file |

### Calculo do Score

- **Score do checklist** = media aritmetica dos scores de todos os itens
- **Pass**: media >= 3.0
- **Rework trigger**: qualquer item com score 0 OU media < 2.5

---

## Thresholds de Qualidade

Os thresholds de qualidade sao derivados do `score_thresholds` definido no `config.yaml` e se aplicam a todos os outputs do squad.

### Classificacao de Output

| Classificacao | Percentual | Criterio |
|--------------|-----------|---------|
| **WEAK** | < 50% | Falha em quality gates obrigatorios. Rework imediato obrigatorio. Nao pode ser publicado. |
| **FAIR** | 50% - 79% | Passa gates minimos mas falta profundidade, evidencia ou acionabilidade. Revisao recomendada. |
| **GOOD** | 80% - 94% | Completo, evidenciado e acionavel. Padrao esperado para publicacao. Minimo para handoff cross-squad. |
| **GOLD** | 95%+ | Exemplar. Material para swipe file, treinamento e benchmark do squad. |

### Thresholds Operacionais (do config.yaml)

| Metrica | Threshold | Acao |
|---------|----------|------|
| Call quality score < 40 | Critical | Treinamento imediato obrigatorio |
| Call quality score 40-59 | Developing | Coaching semanal com foco nos 3 piores blocos |
| Call quality score 60-79 | Good | Refinamento tatico |
| Call quality score 80-89 | Excellent | Closer referencia, material para swipe |
| Call quality score 90-95+ | Gold Standard | Padrao ouro — benchmark do squad |
| Rework trigger | < 50% | Rework obrigatorio antes de publicar |
| Certificacao minima | >= 70% | Minimo para certificacao de closer |
| Confianca no score | >= 0.7 | Abaixo disso, reanalisar com contexto adicional |
| Checklist pass | >= 80% | Minimo para aprovacao em quality gate |
| Checklist gold | >= 95% | Nivel GOLD de checklist |

### Aplicacao Pratica

1. Todo output e classificado automaticamente ao final da validacao
2. Outputs WEAK nunca sao publicados — entram em rework imediato
3. Outputs FAIR podem ser publicados com flag de "revisao pendente"
4. Outputs GOOD sao o padrao esperado para qualquer deliverable
5. Outputs GOLD sao destacados e adicionados ao swipe file do squad
