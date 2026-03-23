# Analisar Objeções

> Analisar objeções levantadas: tipo, causa raiz, resposta do closer e eficácia da resolução.

## Objetivo
Mapear cada objeção, classificar sua causa raiz real, avaliar a qualidade da resposta do closer e determinar se a objeção foi resolvida — objeções mal tratadas são a causa direta de deals perdidos.

## Trigger
- Transcrição segmentada com etapa de objeções delimitada
- Execução do workflow `07-objection-root-cause-analysis`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Objection Specialist | Classifica objeções e avalia respostas |
| Call Auditor | Consolida análise e identifica padrões |
| Dan Lok | Valida técnicas de resolução de objeções de alto ticket |
| Jordan Belfort | Avalia uso de looping e re-enquadramento |
| Jeremy Miner | Avalia uso de perguntas para dissolver objeções |

## Inputs
- Transcrição segmentada: seção de objeções com timestamps
- Biblioteca de objeções em `data/libraries/objections-library.yaml`
- Relatório de frameworks detectados
- Contexto de pricing apresentado

## Processo
1. Listar todas as objeções verbalizadas pelo lead com timestamp e trecho exato
2. Classificar cada objeção por tipo: preço, timing, decisor, confiança, concorrência, fit
3. Identificar causa raiz real: discovery fraco, pitch genérico, falta de prova, preço sem valor
4. Avaliar resposta do closer: técnica usada, timing, tom
5. Classificar eficácia da resposta: resolvida, parcialmente resolvida, não resolvida, piorada
6. Verificar se closer antecipou objeções preventivamente (antes de surgirem)
7. Identificar objeções não verbalizadas mas inferidas pelo comportamento do lead
8. Registrar novas objeções ou variações não presentes na biblioteca
9. Avaliar se objeções recorrentes indicam problema sistêmico (oferta, copy, SDR)

## Frameworks Aplicados
- Objection Root Cause Framework
- Straight Line Persuasion: Looping (Belfort)
- NEPQ: perguntas de dissolução (Miner)
- Hormozi Price-to-Value Gap

## Checklists de Qualidade
- Cada objeção registrada com trecho exato e timestamp
- Causa raiz identificada (não apenas o tipo superficial)
- Resposta do closer avaliada com técnica e eficácia
- Objeções preventivas verificadas (presentes/ausentes)
- Novas objeções sinalizadas para biblioteca

## Output Esperado
- Análise de objeções em `reports/analysis/CALL-ID-objections`
- Tabela: objeção, tipo, causa raiz, resposta, eficácia
- Recomendações de melhoria por objeção não resolvida

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo objections_score)
- `data/libraries/objections-library.yaml` (se novas objeções encontradas)

## Critérios de Conclusão
- [ ] Todas as objeções listadas com trecho e timestamp
- [ ] Tipo e causa raiz classificados por objeção
- [ ] Resposta do closer avaliada com técnica e eficácia
- [ ] Objeções preventivas verificadas
- [ ] Novas objeções sinalizadas para biblioteca
- [ ] Nota atribuída com justificativa

---

## Contexto
Objeções mal tratadas são a causa direta de deals perdidos. Esta task existe para mapear cada objeção com sua causa raiz real (não apenas o sintoma declarado), avaliar a qualidade da resposta do closer e alimentar a biblioteca de objeções — permitindo coaching específico e prevenção de objeções recorrentes.

## Especificação de I/O
- **Input**: Transcrição segmentada no formato `[MM:SS] [SPEAKER]: text`, seção de objeções + biblioteca de objeções em `data/libraries/objections-library.yaml` + relatório de frameworks detectados
- **Output**: `templates/reports/objection-analysis-report.md` + `templates/rewrites/objection-rewrite-template.md` (para objeções não resolvidas) + tabela objeção/tipo/causa raiz/resposta/eficácia

## Quality Gates Intermediários
- Após análise inicial: cada objeção registrada com trecho exato, timestamp e classificação por tipo (preço, timing, decisor, confiança, concorrência, fit); causa raiz identificada para cada uma
- Antes de output final: qa-guardian valida coerência entre causa raiz das objeções e notas de discovery/pitch (objeção de preço com discovery raso deve ser sinalizada como problema de discovery, não de pricing)

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar seção de objeções)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts (ex: Belfort vs. Miner sobre técnica de resolução): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- 100% das objeções com causa raiz classificada (não apenas tipo superficial)
- Taxa de novas objeções identificadas e adicionadas à biblioteca por ciclo

## Handoff
- Output entregue a: call-auditor (consolidação no full-call-audit, workflow 06) + objection-specialist (análise profunda no workflow 07-objection-root-cause-analysis)
- Formato de entrega: `templates/reports/objection-analysis-report.md` + `templates/rewrites/objection-rewrite-template.md`
- Condição de entrega: checklist obrigatório de Critérios de Conclusão 100% aprovado + qa-guardian valida coerência entre causa raiz das objeções e notas de discovery/pitch
- Próximo passo no pipeline: workflow 07 Etapa 3 (análise de causa raiz por objeção) e workflow 06 Etapa 2 (consolidação no pipeline de análise completa)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-9 com revalidação do checklist obrigatório
- Max ciclos: 2
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 2 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/07-objection-root-cause-analysis.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/objection-specialist.md`, `agents/call-auditor.md`, `agents/experts/jordan-belfort.md`, `agents/experts/jeremy-miner.md`, `agents/experts/bradley-lea.md`, `agents/experts/eli-wilde.md`
- Templates: `templates/reports/objection-analysis-report.md`, `templates/rewrites/objection-rewrite-template.md`
- Registries atualizados: `data/registries/objections-registry`, `data/registries/deal-risk-registry`
