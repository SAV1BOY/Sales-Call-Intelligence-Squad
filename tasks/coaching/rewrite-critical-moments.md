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
