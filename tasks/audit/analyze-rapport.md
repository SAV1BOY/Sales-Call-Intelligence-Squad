# Analisar Rapport

> Avaliar qualidade do rapport: quebra de gelo, frame setting e aplicação das 3 intenções.

## Objetivo
Determinar se o closer estabeleceu conexão genuína, assumiu controle do frame e comunicou as 3 intenções do First Pact — fundação que condiciona todo o resto da call.

## Trigger
- Transcrição segmentada com etapa de rapport delimitada
- Execução do workflow `06-full-funnel-call-audit`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Executa análise detalhada da etapa de rapport |
| Cole Gordon | Valida frame setting e posicionamento de autoridade |
| Eli Wilde | Avalia energia, tonalidade e conexão emocional |
| Framework Detector | Confirma detecção de First Pact e Three Intentions |

## Inputs
- Transcrição segmentada: seção de rapport com timestamps
- Framework First Pact / Three Intentions como referência
- Doctor Frame como referência de posicionamento
- Score de talk ratio na fase de rapport

## Processo
1. Identificar se houve quebra de gelo genuína (não apenas cumprimento protocolar)
2. Avaliar se o closer estabeleceu frame de autoridade (Doctor Frame vs. vendedor)
3. Verificar aplicação das 3 intenções do First Pact: entender situação, ver se posso ajudar, ser honesto
4. Analisar se o closer tomou controle da conversa nos primeiros 2 minutos
5. Verificar se houve construção de rapport real (perguntas pessoais, espelhamento, interesse genuíno)
6. Avaliar transição do rapport para discovery (natural vs. abrupta)
7. Medir duração do rapport: curto demais (<1min) ou longo demais (>5min)
8. Identificar red flags: closer falando demais, lead desconfortável, frame perdido

## Frameworks Aplicados
- First Pact / Three Intentions
- Doctor Frame
- Straight Line Persuasion (certeza inicial)
- Tonality Mastery (Miner)

## Checklists de Qualidade
- Quebra de gelo avaliada com evidência textual
- Frame setting analisado: Doctor Frame vs. vendedor
- 3 intenções verificadas individualmente (presente/ausente/parcial)
- Duração do rapport documentada e avaliada
- Transição para discovery analisada

## Output Esperado
- Análise de rapport em `reports/analysis/CALL-ID-rapport`
- Nota do bloco rapport (0-10) com justificativa
- Status de cada intenção: aplicada, parcial ou ausente

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo rapport_score)

## Critérios de Conclusão
- [ ] Quebra de gelo avaliada
- [ ] Frame setting analisado com evidência
- [ ] 3 intenções verificadas individualmente
- [ ] Duração e proporção do rapport documentadas
- [ ] Transição para discovery avaliada
- [ ] Nota atribuída com justificativa textual

---

## Contexto
Rapport e frame setting nos primeiros minutos condicionam todo o resto da call. Esta task existe para avaliar se o closer estabeleceu autoridade (Doctor Frame), conexão genuína e comunicou as 3 intenções do First Pact — sem essa fundação, discovery vira interrogatório e pitch vira apresentação forçada.

## Especificação de I/O
- **Input**: Transcrição segmentada no formato `[MM:SS] [SPEAKER]: text`, seção de rapport delimitada (primeiros 2-5 minutos) + score de talk ratio na fase de rapport
- **Output**: `templates/reports/full-call-audit-report.md`, seções "Rapport e Abertura" e "Primeiro Pacto e Frame" + status de cada intenção (aplicada/parcial/ausente)

## Quality Gates Intermediários
- Após análise inicial: quebra de gelo avaliada com evidência textual; frame setting classificado (Doctor Frame vs. vendedor); 3 intenções verificadas individualmente com trecho e timestamp
- Antes de output final: qa-guardian valida coerência entre nota de rapport e engajamento do lead nas fases seguintes (rapport forte com discovery desengajado é sinal de inconsistência)

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar primeiros minutos, verificar speaker tags e timestamps)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts (ex: Gordon vs. Wilde sobre qualidade do frame): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- Taxa de closers com First Pact completo (3 intenções presentes) rastreada por período
- Correlação entre nota de rapport e nota global da call > 0.4

## Handoff
- Output entregue a: call-auditor (consolidação do full-call-audit na Etapa 3 do workflow 06)
- Formato de entrega: `templates/reports/full-call-audit-report.md`, seções "Rapport e Abertura" e "Primeiro Pacto e Frame"
- Condição de entrega: checklist de qualidade aprovado com quebra de gelo avaliada, frame setting classificado, 3 intenções verificadas individualmente, e qa-guardian valida coerência entre nota de rapport e engajamento nas fases seguintes
- Próximo passo no pipeline: Etapa 3 — Consolidação do Relatório Executivo (workflow 06-full-funnel-call-audit)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-8 com revalidação do checklist obrigatório
- Max ciclos: 2
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 2 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/call-auditor.md`, `agents/experts/cole-gordon.md`, `agents/experts/dan-lok.md`, `agents/framework-detector.md`
- Templates: `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/scorecards-registry`
