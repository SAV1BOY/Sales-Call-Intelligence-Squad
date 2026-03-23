# Normalizar Transcrição

> Limpar, padronizar e enriquecer transcrição bruta com speaker tags e timestamps precisos.

## Objetivo
Transformar transcrição bruta em documento limpo, padronizado e navegável — base confiável para todas as análises downstream.

## Trigger
- Transcrição bruta disponível após intake de gravação
- Reprocessamento solicitado por QA Guardian (qualidade insuficiente)

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Transcript Analyst | Executa limpeza, normalização e enriquecimento |
| QA Guardian | Valida qualidade final da transcrição normalizada |

## Inputs
- Transcrição bruta em `data/transcripts/raw/`
- Metadata da call (closer, lead) do `calls-registry.yaml`
- Gravação original (para conferência de trechos ambíguos)

## Processo
1. Remover artefatos de transcrição automática (repetições de máquina, caracteres inválidos)
2. Corrigir erros óbvios de reconhecimento de fala (nomes próprios, termos técnicos)
3. Atribuir speaker tags consistentes: `[CLOSER]` e `[LEAD]` em toda a transcrição
4. Inserir timestamps no formato `[MM:SS]` a cada mudança de speaker
5. Marcar trechos inaudíveis com `[INAUDÍVEL - MM:SS]`
6. Preservar pausas significativas com `[PAUSA - Xs]` quando > 3 segundos
7. Formatar parágrafos por turno de fala (um parágrafo por speaker turn)
8. Validar coerência: timestamps em ordem crescente, sem gaps > 2 minutos sem explicação
9. Gerar resumo executivo da call (5-7 linhas) com duração, participantes e resultado
10. Salvar transcrição normalizada em `data/transcripts/cleaned/`

## Frameworks Aplicados
- Minute-by-Minute Analysis Framework (para estrutura de timestamps)
- Sales Call Stage Taxonomy (para validação de coerência)

## Checklists de Qualidade
- Speaker tags `[CLOSER]` e `[LEAD]` consistentes em 100% dos turnos
- Timestamps `[MM:SS]` presentes em cada mudança de speaker
- Zero artefatos de transcrição automática remanescentes
- Trechos inaudíveis marcados (não inventados)
- Resumo executivo presente e coerente com conteúdo

## Output Esperado
- Transcrição normalizada em `data/transcripts/cleaned/CALL-ID.md`
- Resumo executivo no header da transcrição
- Log de alterações realizadas (quantidade de correções, trechos inaudíveis)

## Registry Atualizado
- `data/transcripts/cleaned/`
- `data/registries/calls-registry.yaml` (status atualizado para "normalizada")

## Critérios de Conclusão
- [ ] Speaker tags aplicados em 100% dos turnos
- [ ] Timestamps inseridos em cada mudança de speaker
- [ ] Artefatos de transcrição removidos
- [ ] Trechos inaudíveis marcados corretamente
- [ ] Resumo executivo gerado
- [ ] Transcrição salva em `data/transcripts/cleaned/`
- [ ] QA Guardian validou qualidade

---

## Contexto
Transcrições brutas de ferramentas automáticas contêm artefatos, speakers misturados e timestamps inconsistentes. Esta task existe para criar uma base textual confiável e padronizada que todas as análises downstream possam usar sem ambiguidade.

## Especificação de I/O
- **Input**: Transcrição bruta em `data/transcripts/raw/CALL-ID` + metadata da call do `calls-registry.yaml` + gravação original para conferência
- **Output**: Transcrição normalizada em `data/transcripts/cleaned/CALL-ID.md` (formato `templates/reports/minute-by-minute-audit-report`)

## Quality Gates Intermediários
- Após aplicação de speaker tags e timestamps (steps 3-4): checklist `transcript-normalization-quality` — 100% dos turnos com tags, timestamps em ordem crescente
- Antes de output final: QA Guardian valida zero artefatos remanescentes, trechos inaudíveis marcados, resumo executivo coerente

## Escalation & Rework
- Se transcrição < 80% audível: escalar para `transcript-analyst` com flag `low_audio_confidence`; `call-auditor` ajusta score
- Se quality gate falha: rework loop (max 3 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `audit_cycle_time`: tempo de gravação bruta até transcrição normalizada pronta
- `discovery_depth_score`: qualidade da transcrição impacta profundidade da análise downstream

## Referências Cruzadas
- Workflow: `workflows/00-recording-to-transcript.md`, `workflows/01-transcript-cleaning-and-segmentation.md`
- Agents: `agents/transcript-analyst.md`, `agents/qa-guardian.md`
- Templates: `templates/reports/minute-by-minute-audit-report.md`
- Registries atualizados: `data/transcripts/cleaned/`, `data/registries/calls-registry.yaml`

## Handoff
- **Output entregue a**: Transcript Analyst / Call Auditor para segmentação da call por etapa (`tasks/intake/segment-call-by-stage.md`)
- **Formato de entrega**: Transcrição normalizada em `data/transcripts/cleaned/CALL-ID.md` (formato `templates/reports/minute-by-minute-audit-report`)
- **Condição de entrega**: speaker tags 100% consistentes, timestamps em ordem crescente, zero artefatos remanescentes, QA Guardian validou qualidade
- **Próximo passo no pipeline**: segmentação da call por etapa via `workflows/01-transcript-cleaning-and-segmentation.md`

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
