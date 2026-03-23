# Analisar Profundidade de Discovery

> Avaliar profundidade do discovery: aplicação de SPIN, NEPQ, camadas de investigação e qualidade das perguntas.

## Objetivo
Medir se o closer cavou fundo o suficiente para entender a dor real do lead, ou ficou na superfície — discovery raso é a causa raiz #1 de calls perdidas.

## Trigger
- Transcrição segmentada com etapa de discovery delimitada
- Execução do workflow `06-full-funnel-call-audit`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Coordena análise de discovery |
| Neil Rackham | Avalia aplicação de SPIN Selling |
| Jeremy Miner | Avalia aplicação de NEPQ e perguntas de consequência |
| Cole Gordon | Avalia profundidade do diagnóstico |

## Inputs
- Transcrição segmentada: seção de discovery com timestamps
- Frameworks SPIN Selling e NEPQ como referência
- Mapa de perguntas feitas pelo closer
- Informações do ICP e oferta

## Processo
1. Mapear todas as perguntas feitas pelo closer na fase de discovery
2. Classificar cada pergunta: Situação, Problema, Implicação, Necessidade (SPIN)
3. Avaliar progressão NEPQ: perguntas de conexão → situação → problema → consequência → solução
4. Contar camadas de profundidade: o closer fez follow-up nas respostas?
5. Identificar se o closer descobriu: dor principal, causa raiz, impacto emocional, custo da inação
6. Avaliar se lead verbalizou a dor com suas próprias palavras (vs. closer assumindo)
7. Verificar se closer fez perguntas de consequência (o que acontece se não resolver?)
8. Medir proporção closer/lead na fase de discovery (ideal: lead fala 70%+)
9. Identificar gaps: perguntas que deveriam ter sido feitas e não foram

## Frameworks Aplicados
- SPIN Selling (Situação, Problema, Implicação, Necessidade)
- NEPQ (Neuro-Emotional Persuasion Questioning)
- Consequence Questioning Deep Dive (Miner)
- Doctor Frame (diagnóstico antes de prescrição)

## Checklists de Qualidade
- Todas as perguntas do closer mapeadas e classificadas
- Progressão SPIN ou NEPQ avaliada
- Camadas de profundidade contadas (1 camada = superficial, 3+ = profundo)
- Lead verbalizou dor com próprias palavras (sim/não, com trecho)
- Gaps de discovery documentados

## Output Esperado
- Análise de discovery em `reports/analysis/CALL-ID-discovery`
- Mapa de perguntas classificadas por tipo (SPIN/NEPQ)
- Nota de profundidade (0-10) com justificativa

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo discovery_score)

## Critérios de Conclusão
- [ ] Perguntas mapeadas e classificadas (SPIN/NEPQ)
- [ ] Profundidade avaliada em camadas
- [ ] Dor verbalizada pelo lead identificada ou ausência documentada
- [ ] Gaps de discovery listados
- [ ] Nota atribuída com evidência textual
- [ ] Proporção closer/lead na discovery calculada

---

## Contexto
Discovery raso é a causa raiz #1 de calls perdidas em high ticket. Esta task existe para medir objetivamente se o closer investigou a dor real do lead com profundidade suficiente — sem essa análise, o coaching fica genérico e o closer repete os mesmos erros.

## Especificação de I/O
- **Input**: Transcrição segmentada no formato `[MM:SS] [SPEAKER]: text`, seção de discovery delimitada + frameworks SPIN/NEPQ como referência
- **Output**: `templates/reports/full-call-audit-report.md`, seção "Diagnóstico e Descoberta" + mapa de perguntas classificadas (SPIN/NEPQ)

## Quality Gates Intermediários
- Após análise inicial: 100% das perguntas do closer mapeadas e classificadas por tipo (S/P/I/N ou NEPQ); camadas de profundidade contadas com evidência
- Antes de output final: qa-guardian valida que a nota de discovery é coerente com a nota de pitch (discovery fraco deve refletir em pitch genérico)

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar seção de discovery, verificar speaker tags)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts (ex: Rackham vs. Miner sobre classificação de pergunta): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- Precisão da classificação de perguntas: concordância entre experts > 90%
- Correlação entre nota de discovery e taxa de conversão da call > 0.6

## Handoff
- Output entregue a: call-auditor (consolidação do full-call-audit na Etapa 3 do workflow 06)
- Formato de entrega: `templates/reports/full-call-audit-report.md`, seção "Diagnóstico e Descoberta"
- Condição de entrega: checklist de qualidade aprovado com 100% das perguntas mapeadas e classificadas, camadas de profundidade contadas, e qa-guardian valida coerência entre nota de discovery e nota de pitch
- Próximo passo no pipeline: Etapa 3 — Consolidação do Relatório Executivo (workflow 06-full-funnel-call-audit)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-9 com revalidação do checklist obrigatório
- Max ciclos: 2
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 2 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/call-auditor.md`, `agents/experts/neil-rackham.md`, `agents/experts/jeremy-miner.md`, `agents/experts/cole-gordon.md`
- Templates: `templates/reports/full-call-audit-report.md`
- Registries atualizados: `data/registries/scorecards-registry`, `data/registries/deal-risk-registry`
