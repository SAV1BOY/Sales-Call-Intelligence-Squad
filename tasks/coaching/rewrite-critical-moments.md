# Reescrever Momentos Críticos

> Reescrever os momentos decisivos da call em formato antes/depois com fundamentação técnica.

## Objetivo
Transformar os erros identificados na auditoria em exemplos concretos de melhoria — o closer vê exatamente o que disse, o que deveria ter dito e por quê, acelerando o aprendizado.

## Trigger
- Relatório minuto a minuto concluído com momentos críticos identificados
- Execução do workflow `05-coaching-rewrite-loop`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Coaching Rewriter | Executa reescrita dos momentos críticos |
| Call Auditor | Fornece contexto e análise de cada momento |
| Cole Gordon | Valida reescrita de momentos de diagnóstico e pitch |
| Jeremy Miner | Valida reescrita de perguntas e técnicas NEPQ |
| QA Guardian | Audita qualidade e especificidade das reescritas |

## Inputs
- Relatório minuto a minuto com 5 momentos mais críticos
- Transcrição segmentada com timestamps
- Scorecard da call (blocos mais fracos)
- Frameworks que deveriam ter sido aplicados

## Processo
1. Selecionar os 5 momentos mais críticos do relatório minuto a minuto
2. Para cada momento, extrair o trecho exato da transcrição (ANTES)
3. Identificar o framework ou técnica que deveria ter sido aplicado
4. Reescrever o trecho aplicando a técnica correta (DEPOIS)
5. Incluir explicação técnica: por que a versão original falhou e por que a nova funciona
6. Validar que a reescrita é realista e natural (não robótica)
7. Adaptar tom e vocabulário ao estilo do closer (não parecer outro vendedor)
8. Priorizar reescritas pelo impacto no resultado da call
9. Formatar em cards visuais: ANTES → DEPOIS → POR QUÊ

## Frameworks Aplicados
- Rewrite Quality Checklist
- Framework específico de cada momento (SPIN, NEPQ, Straight Line, etc.)
- Coaching Specificity Check

## Checklists de Qualidade
- Cada reescrita tem trecho ANTES exato da transcrição
- Versão DEPOIS aplica framework correto
- Explicação técnica clara e educativa (POR QUÊ)
- Reescrita natural e adaptada ao estilo do closer
- Mínimo 3, máximo 7 reescritas por call

## Output Esperado
- Documento de reescritas em `reports/coaching/CALL-ID-rewrites`
- Cards: ANTES (trecho real) → DEPOIS (versão melhorada) → POR QUÊ (framework)
- Priorização por impacto no resultado

## Registry Atualizado
- `data/registries/coaching-registry.yaml`
- `data/libraries/best-moments-library.yaml` (se reescrita for exemplar)

## Critérios de Conclusão
- [ ] 3-7 momentos críticos reescritos
- [ ] Cada reescrita tem ANTES, DEPOIS e POR QUÊ
- [ ] Frameworks corretos aplicados nas reescritas
- [ ] Reescritas naturais e adaptadas ao closer
- [ ] QA Guardian validou qualidade
- [ ] Documento formatado e salvo

---

## Contexto
Feedback genérico ("melhore seu discovery") não muda comportamento. Esta task existe para transformar erros reais da call em exemplos concretos ANTES/DEPOIS com fundamentação técnica, acelerando o aprendizado do closer com material específico e praticável.

## Especificação de I/O
- **Input**: Relatório minuto a minuto com 5 momentos mais críticos + transcrição segmentada com timestamps + scorecard da call
- **Output**: `templates/rewrites/objection-rewrite-template`, `templates/rewrites/pitch-rewrite-template`, `templates/rewrites/closing-rewrite-template`, `templates/rewrites/discovery-rewrite-template` (conforme fase do momento)

## Quality Gates Intermediários
- Após seleção dos momentos e reescrita (steps 1-6): checklist `rewrite-quality` — cada reescrita tem ANTES exato, DEPOIS com framework, POR QUE educativo
- Antes de output final: checklist `coaching-plan-quality` — reescritas naturais, adaptadas ao estilo do closer, priorizadas por impacto

## Escalation & Rework
- Se momento crítico envolve objeção complexa: escalar para `objection-specialist` para validação de técnica
- Se quality gate falha: rework loop (max 3 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `rewrite_adoption_rate`: % de reescritas que o closer implementou nas calls seguintes
- `coaching_impact_score`: melhoria no score do bloco correspondente à reescrita

## Handoff
- Output entregue a: `closer-trainer` (task `build-coaching-pack`) para construção do pacote de coaching
- Formato de entrega: `templates/rewrites/objection-rewrite-template`, `templates/rewrites/pitch-rewrite-template`, `templates/rewrites/closing-rewrite-template`, `templates/rewrites/discovery-rewrite-template` (conforme fase do momento)
- Condição de entrega: checklist `rewrite-quality` aprovado (cada reescrita tem ANTES exato, DEPOIS com framework, POR QUÊ educativo) E checklist `coaching-plan-quality` aprovado (reescritas naturais, priorizadas por impacto)
- Próximo passo no pipeline: Etapa 4 do workflow `05-coaching-rewrite-loop` (Construção do Pacote de Coaching)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-9 com revalidação do checklist obrigatório
- Max ciclos: 3
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 3 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/05-coaching-rewrite-loop.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/coaching-rewriter.md`, `agents/closer-trainer.md`, `agents/objection-specialist.md`
- Templates: `templates/rewrites/objection-rewrite-template.md`, `templates/rewrites/pitch-rewrite-template.md`, `templates/rewrites/closing-rewrite-template.md`, `templates/rewrites/discovery-rewrite-template.md`
- Registries atualizados: `data/rewrites`, `data/registries/lessons-learned-registry`
