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
