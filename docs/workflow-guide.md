# Guia de Execução de Workflows

> Como executar playbooks do squad: ordem de operações, inputs necessários, outputs esperados e dependências entre fases.

## Conceito de Workflow

Um workflow é uma sequência ordenada de atividades que transforma um input (ex: transcrição bruta) em um output (ex: coaching pack). Cada workflow tem fases com dependências claras — não é possível pular fases sem comprometer a qualidade.

## Workflow Principal — Auditoria Completa

### Sequência de Execução

| Fase | Input | Output | Dependência |
|------|-------|--------|-------------|
| 00 - Intake | Transcrição bruta + contexto | Call registrada com metadados | Nenhuma |
| 01 - Limpeza | Call registrada | Transcrição limpa e formatada | Fase 00 |
| 02 - Segmentação | Transcrição limpa | Call dividida em 6 etapas | Fase 01 |
| 03 - Framework Detection | Call segmentada | Mapa de frameworks por etapa | Fase 02 |
| 04 - Scoring | Mapa de frameworks + segmentos | Score de 100 pontos em 10 blocos | Fases 02 e 03 |
| 05 - Root Cause | Score + frameworks | Diagnóstico de causa raiz | Fase 04 |
| 06 - Rewrites | Diagnóstico + transcrição | Momentos reescritos (até 8) | Fases 01 e 05 |
| 07 - Coaching Pack | Todos os outputs anteriores | Plano de coaching completo | Fases 04, 05 e 06 |
| 08 - Registry Update | Coaching pack | Registry atualizado | Fase 07 |

### Tempo Estimado por Fase
- Fases 00-02: 10-15 minutos
- Fases 03-04: 15-20 minutos
- Fases 05-06: 10-15 minutos
- Fases 07-08: 5-10 minutos
- Total: 40-60 minutos por call

## Workflow Secundário — Auditoria Rápida

Para quando não há tempo para auditoria completa. Pula as fases 05, 06 e 08.

### Sequência Reduzida
1. Intake → 2. Limpeza → 3. Segmentação → 4. Framework Detection → 5. Scoring → 6. Report

### Limitações
- Sem análise de causa raiz (apenas score)
- Sem rewrites (apenas identificação dos gaps)
- Sem coaching pack (apenas números)
- Útil para triagem: identificar quais calls merecem auditoria completa

## Workflow de Coaching Sprint

### Pré-requisitos
- Mínimo 5 calls auditadas do closer
- Diagnóstico de padrões recorrentes
- Disponibilidade do closer para sessões semanais

### Sequência
1. Assessment inicial → 2. Auditoria de 5 calls → 3. Análise de padrões → 4. Plano de treinamento → 5. Sessões práticas → 6. Certificação

## Regras de Execução

### Regras de Qualidade
- Nunca pular a fase de limpeza de transcrição — erros de transcrição geram análises erradas
- Sempre validar a segmentação antes de prosseguir — segmentação errada invalida todo o restante
- Framework detection deve citar evidências textuais — sem evidência, sem detecção
- Scoring deve seguir os critérios do `scoring-methodology.md` sem exceções

### Regras de Priorização
- Calls perdidas têm prioridade sobre calls ganhas para auditoria
- Closers novos têm prioridade sobre closers experientes para coaching
- Calls com tickets altos têm prioridade sobre tickets baixos
- Calls recentes têm prioridade sobre calls antigas

### Regras de Documentação
- Todo workflow executado deve ser registrado com data, responsável e resultado
- Outputs de cada fase devem ser salvos mesmo que a fase seguinte já tenha sido concluída
- Divergências encontradas durante execução devem ser documentadas como notas

## Troubleshooting

**Transcrição de baixa qualidade**: se a transcrição tem mais de 10% de trechos ininteligíveis, a auditoria será classificada como "baixa confiança" e o score terá asterisco.

**Call muito curta (menos de 10 minutos)**: avaliar apenas as fases que ocorreram. Não penalizar por fases ausentes se a call foi encerrada pelo prospect.

**Call sem fechamento**: pontuar o bloco de Fechamento como zero apenas se houve oportunidade de close que foi perdida. Se o prospect não estava qualificado, registrar como "não aplicável".
