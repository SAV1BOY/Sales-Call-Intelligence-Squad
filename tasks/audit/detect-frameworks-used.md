# Detectar Frameworks Usados

> Identificar todos os frameworks de vendas utilizados na call com evidência textual concreta.

## Objetivo
Mapear exatamente quais técnicas e frameworks o closer aplicou (consciente ou inconscientemente), em qual momento, com qual nível de execução — base para scoring e coaching.

## Trigger
- Transcrição segmentada disponível
- Execução do workflow `03-framework-detection-loop`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Framework Detector | Executa varredura completa de frameworks |
| Alex Hormozi | Valida aplicação de Value Equation, Grand Slam Offer |
| Jeremy Miner | Valida aplicação de NEPQ e perguntas de consequência |
| Jordan Belfort | Valida aplicação de Straight Line e looping |
| Cole Gordon | Valida aplicação de Frame Setting e diagnóstico |
| Neil Rackham | Valida aplicação de SPIN Selling |
| Call Auditor | Consolida detecções e resolve conflitos |

## Inputs
- Transcrição segmentada com timestamps
- Biblioteca de frameworks em `frameworks/`
- Mapa de etapas da call

## Processo
1. Varrer cada etapa da call contra a biblioteca de frameworks disponíveis
2. Para cada framework detectado, registrar: nome, etapa, timestamp, trecho exato
3. Avaliar nível de execução: completo, parcial ou incorreto
4. Detectar frameworks ausentes que deveriam estar presentes na etapa
5. Identificar conflitos metodológicos (ex: alta pressão em fase que pedia NEPQ)
6. Consultar especialistas por fase conforme routing do `config.yaml`
7. Consolidar detecções eliminando falsos positivos
8. Gerar relatório de frameworks com evidência por detecção

## Frameworks Aplicados
- SPIN Selling, NEPQ, Straight Line Persuasion
- Closer Four-Part Framework, Doctor Frame
- Value Equation, Grand Slam Offer
- First Pact / Three Intentions

## Checklists de Qualidade
- Cada detecção tem trecho exato da transcrição com timestamp
- Nível de execução avaliado (completo/parcial/incorreto)
- Frameworks ausentes documentados com justificativa
- Conflitos metodológicos identificados e reportados
- Zero detecções sem evidência textual

## Output Esperado
- Relatório de frameworks em `reports/framework-detection-report`
- Lista: framework, etapa, timestamp, trecho, nível de execução
- Frameworks ausentes com recomendação de aplicação

## Registry Atualizado
- `data/registries/framework-detection-registry.yaml`

## Critérios de Conclusão
- [ ] Todas as etapas da call varridas contra frameworks
- [ ] Cada detecção documentada com evidência textual
- [ ] Nível de execução avaliado por framework
- [ ] Frameworks ausentes identificados
- [ ] Conflitos metodológicos reportados
- [ ] Registry de detecção atualizado

---

## Contexto
Saber quais frameworks o closer aplicou (consciente ou inconscientemente) e quais estavam ausentes é a base para scoring preciso e coaching direcionado. Esta task existe para produzir um mapa de cobertura de frameworks com evidência textual — sem ela, o coaching se baseia em impressões subjetivas em vez de dados concretos sobre técnica.

## Especificação de I/O
- **Input**: Transcrição segmentada com timestamps + biblioteca de frameworks em `frameworks/` + mapa de etapas da call
- **Output**: `templates/reports/framework-detection-report.md` + lista: framework, etapa, timestamp, trecho, nível de execução (completo/parcial/incorreto) + frameworks ausentes com recomendação

## Quality Gates Intermediários
- Após análise inicial: cada detecção tem trecho exato da transcrição com timestamp; nível de execução avaliado para cada framework; zero detecções sem evidência textual
- Antes de output final: qa-guardian valida que frameworks ausentes estão alinhados com os blocos fracos do scorecard; especialistas (objection-specialist, pricing-anchoring-analyst) confirmaram detecções nas suas áreas

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar transcrição com segmentação mais precisa)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts (ex: detecção de SPIN vs. NEPQ no mesmo trecho): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- Taxa de falsos positivos na detecção < 5% (validação por especialistas)
- Score de cobertura de frameworks (% de frameworks aplicáveis utilizados) rastreado por closer

## Handoff
- Output entregue a: scorecard-analyst (workflow 04 Etapa 1 — coleta de evidências para scoring) + coaching-rewriter (workflow 05 — seleção de momentos para rewrite com base em gaps de framework)
- Formato de entrega: `templates/reports/framework-detection-report.md` + lista de frameworks detectados/ausentes com evidência textual
- Condição de entrega: checklist obrigatório de Critérios de Conclusão 100% aprovado + qa-guardian valida que frameworks ausentes estão alinhados com blocos fracos do scorecard
- Próximo passo no pipeline: workflow 04-scoring-and-root-cause (scoring dos 10 blocos) e workflow 05-coaching-rewrite-loop (reescrita de momentos críticos)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-8 com revalidação do checklist obrigatório
- Max ciclos: 2
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 2 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/03-framework-detection-loop.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/framework-detector.md`, `agents/experts/alex-hormozi.md`, `agents/experts/jeremy-miner.md`, `agents/experts/jordan-belfort.md`, `agents/experts/cole-gordon.md`, `agents/experts/neil-rackham.md`, `agents/experts/matthew-dixon.md`, `agents/call-auditor.md`
- Templates: `templates/reports/framework-detection-report.md`
- Registries atualizados: `data/registries/framework-detection-registry`
