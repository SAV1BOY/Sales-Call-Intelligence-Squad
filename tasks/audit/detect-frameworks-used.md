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
