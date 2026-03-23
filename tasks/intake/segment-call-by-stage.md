# Segmentar Call por Etapa

> Dividir a call em etapas estruturais: rapport, discovery, pitch, pricing, objeções e fechamento.

## Objetivo
Criar mapa estrutural da call para que cada agente especialista analise apenas a fase relevante, seguindo o princípio `phase-first` da arquitetura.

## Trigger
- Transcrição normalizada disponível em `data/transcripts/cleaned/`
- Execução do workflow `01-transcript-cleaning-and-segmentation`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Transcript Analyst | Identifica transições e delimita cada etapa |
| Call Auditor | Valida segmentação e identifica etapas ausentes |
| Framework Detector | Confirma coerência entre etapa e frameworks detectados |

## Inputs
- Transcrição normalizada com timestamps e speaker tags
- Sales Call Stage Taxonomy (referência de etapas padrão)
- Metadata da call (tipo, duração, resultado)

## Processo
1. Ler transcrição completa e identificar marcadores de transição entre etapas
2. Segmentar nas 6 etapas padrão: Rapport → Discovery → Pitch → Pricing → Objeções → Closing
3. Registrar timestamp de início e fim de cada etapa (`[MM:SS]` a `[MM:SS]`)
4. Calcular duração de cada etapa em minutos e percentual do total
5. Identificar etapas ausentes ou atípicas (ex: discovery inexistente, pitch antes de discovery)
6. Marcar sub-etapas quando aplicável (ex: First Pact dentro de Rapport, Segundo Pacto entre Discovery e Pitch)
7. Detectar "saltos" entre etapas (closer pulou discovery e foi direto ao pitch)
8. Gerar mapa visual de tempo por etapa (barra de distribuição percentual)
9. Salvar transcrição segmentada em `data/transcripts/segmented/`
10. Registrar anomalias de sequência para análise do Call Auditor

## Frameworks Aplicados
- Sales Call Stage Taxonomy
- First Pact / Three Intentions (para delimitação de rapport)
- Closer Four-Part Framework (para estrutura geral)

## Checklists de Qualidade
- Todas as 6 etapas padrão identificadas ou marcadas como ausentes
- Timestamps de início/fim corretos e sem sobreposição
- Percentual de tempo por etapa calculado e coerente (soma = 100%)
- Etapas ausentes documentadas com nota explicativa
- Sub-etapas marcadas quando identificáveis

## Output Esperado
- Transcrição segmentada em `data/transcripts/segmented/CALL-ID.md`
- Mapa de etapas com timestamps, durações e percentuais
- Lista de anomalias de sequência (etapas puladas, ordem invertida)

## Registry Atualizado
- `data/transcripts/segmented/`
- `data/registries/calls-registry.yaml` (status atualizado para "segmentada")

## Critérios de Conclusão
- [ ] 6 etapas padrão delimitadas ou marcadas como ausentes
- [ ] Timestamps de início e fim registrados por etapa
- [ ] Duração e percentual calculados
- [ ] Anomalias de sequência documentadas
- [ ] Transcrição segmentada salva no diretório correto
- [ ] Mapa de distribuição temporal gerado

---

## Contexto
O princípio `phase_first` da arquitetura exige que cada agente especialista analise apenas a fase relevante da call. Esta task existe para criar o mapa estrutural que viabiliza análise granular por etapa, detectando anomalias de sequência que impactam o resultado.

## Especificação de I/O
- **Input**: Transcrição normalizada com timestamps e speaker tags em `data/transcripts/cleaned/CALL-ID.md` + Sales Call Stage Taxonomy + metadata da call
- **Output**: Transcrição segmentada em `data/transcripts/segmented/CALL-ID.md` + mapa de etapas com timestamps, durações e percentuais

## Quality Gates Intermediários
- Após segmentação das 6 etapas (steps 2-3): todas as etapas delimitadas ou marcadas como ausentes, timestamps sem sobreposição, soma = 100%
- Antes de output final: `call-auditor` valida segmentação e identifica etapas ausentes; `framework-detector` confirma coerência entre etapa e frameworks

## Escalation & Rework
- Se call tem estrutura atípica (< 3 etapas identificáveis): escalar para `call-auditor` para análise manual com contexto adicional
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `audit_cycle_time`: tempo de transcrição normalizada até segmentação pronta
- `framework_usage_rate`: % de calls segmentadas corretamente na primeira tentativa

## Referências Cruzadas
- Workflow: `workflows/01-transcript-cleaning-and-segmentation.md`
- Agents: `agents/transcript-analyst.md`, `agents/call-auditor.md`, `agents/framework-detector.md`
- Templates: `templates/reports/minute-by-minute-audit-report.md`
- Registries atualizados: `data/transcripts/segmented/`, `data/registries/calls-registry.yaml`

## Handoff
- **Output entregue a**: Call Auditor (`agents/call-auditor.md`) para auditoria por etapa + classify-call-type para classificação
- **Formato de entrega**: Transcrição segmentada em `data/transcripts/segmented/CALL-ID.md` + mapa de etapas com timestamps, durações e percentuais
- **Condição de entrega**: 6 etapas delimitadas ou marcadas como ausentes, timestamps sem sobreposição, soma = 100%, anomalias documentadas
- **Próximo passo no pipeline**: classificação de tipo de call (`tasks/intake/classify-call-type.md`) e auditoria completa via `workflows/06-full-funnel-call-audit.md`

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
