# Construir Relatório Minuto a Minuto

> Construir relatório completo minuto a minuto: o que aconteceu, avaliação e recomendação por momento.

## Objetivo
Criar o artefato mais granular da auditoria — um mapa temporal completo que permite ao gestor e ao closer verem exatamente o que aconteceu em cada momento, com avaliação e sugestão de melhoria.

## Trigger
- Todas as análises de etapa concluídas (rapport, discovery, pitch, pricing, objeções, close)
- Execução do workflow `02-minute-by-minute-analysis`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Consolida análises em linha temporal |
| Scorecard Analyst | Vincula momentos a blocos do scorecard |
| Framework Detector | Marca frameworks aplicados por minuto |
| Coaching Rewriter | Prepara sugestões de melhoria por momento |

## Inputs
- Transcrição segmentada com timestamps
- Todas as análises de etapa concluídas
- Relatório de frameworks detectados
- Scorecard da call

## Processo
1. Dividir a call em intervalos de 1 minuto (ou por turno de fala, o que for mais granular)
2. Para cada minuto, registrar: etapa, quem fala, o que acontece, framework usado
3. Classificar cada momento: positivo (acerto), neutro, negativo (erro/oportunidade perdida)
4. Vincular momentos negativos com blocos do scorecard impactados
5. Para cada momento negativo, incluir recomendação de melhoria
6. Marcar os 5 momentos mais críticos da call (decisivos para o resultado)
7. Incluir análise de momentum: quando o closer ganhou/perdeu controle
8. Gerar timeline visual com código de cores (verde/amarelo/vermelho)
9. Adicionar notas de coaching nos momentos mais críticos

## Frameworks Aplicados
- Minute-by-Minute Analysis Framework
- Todos os frameworks detectados na call (referência cruzada)
- Sales Call Stage Taxonomy

## Checklists de Qualidade
- Todos os minutos da call cobertos sem gaps
- Cada momento classificado (positivo/neutro/negativo)
- Momentos negativos têm recomendação de melhoria
- 5 momentos mais críticos destacados
- Timeline visual gerada com código de cores

## Output Esperado
- Relatório minuto a minuto em `reports/minute-by-minute/CALL-ID-mxm`
- Timeline visual com classificação por cores
- Lista dos 5 momentos mais críticos com contexto e recomendação

## Registry Atualizado
- `data/registries/calls-registry.yaml` (status "relatório completo")

## Critérios de Conclusão
- [ ] Todos os minutos mapeados com etapa e ação
- [ ] Momentos classificados (positivo/neutro/negativo)
- [ ] Recomendações incluídas para momentos negativos
- [ ] 5 momentos mais críticos destacados
- [ ] Timeline visual gerada
- [ ] Relatório consolidado e salvo

---

## Contexto
O relatório minuto a minuto é o artefato mais granular da auditoria — permite que gestor e closer vejam exatamente o que aconteceu em cada momento da call com avaliação e sugestão de melhoria. Sem ele, o feedback fica abstrato e o closer não consegue localizar onde errou no fluxo temporal da conversa.

## Especificação de I/O
- **Input**: Transcrição segmentada com timestamps + todas as análises de etapa concluídas (rapport, discovery, pitch, pricing, objeções, close) + relatório de frameworks detectados + scorecard da call
- **Output**: `templates/reports/minute-by-minute-audit-report.md` + timeline visual com código de cores (verde/amarelo/vermelho) + lista dos 5 momentos mais críticos com contexto e recomendação

## Quality Gates Intermediários
- Após análise inicial: 100% dos minutos da call cobertos sem gaps; cada momento classificado (positivo/neutro/negativo) com evidência; frameworks detectados vinculados ao minuto correspondente
- Antes de output final: qa-guardian valida que os 5 momentos mais críticos destacados são coerentes com os blocos mais fracos do scorecard; timeline visual gerada e legível

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar transcrição com timestamps mais granulares)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre análise minuto a minuto e scorecard (momento classificado como positivo mas bloco com nota baixa): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- Cobertura temporal: 100% dos minutos mapeados em cada auditoria
- Utilidade percebida pelo closer: taxa de consulta do relatório minuto a minuto > 70%

## Referências Cruzadas
- Workflow: `workflows/02-minute-by-minute-analysis.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/call-auditor.md`, `agents/scorecard-analyst.md`, `agents/framework-detector.md`, `agents/coaching-rewriter.md`
- Templates: `templates/reports/minute-by-minute-audit-report.md`
- Registries atualizados: `data/registries/calls-registry`

## Handoff
- **Output entregue a**: scoring pipeline (scorecard-analyst para vincular momentos a blocos do scorecard) e coaching pipeline (closer-trainer/coaching-rewriter para sessões de coaching baseadas nos momentos críticos)
- **Formato de entrega**: relatório minuto a minuto em `reports/minute-by-minute/CALL-ID-mxm` usando `templates/reports/minute-by-minute-audit-report.md` + timeline visual com código de cores + lista dos 5 momentos mais críticos
- **Condição de entrega**: 100% dos minutos da call cobertos sem gaps, cada momento classificado com evidência, 5 momentos mais críticos coerentes com blocos mais fracos do scorecard, timeline visual gerada e legível
- **Próximo passo no pipeline**: relatório alimenta build-manager-coaching-pack (momentos críticos viram material de coaching); scoring pipeline usa momentos vinculados aos blocos do scorecard; calls-registry atualizado com status "relatório completo"

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
