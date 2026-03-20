# Atualizar Biblioteca de Melhores Momentos

> Atualizar biblioteca de melhores momentos com novos exemplos de excelência extraídos das auditorias.

## Objetivo
Construir acervo curado de momentos excepcionais das calls — trechos reais que demonstram execução de elite e servem como referência para treinamento e inspiração.

## Trigger
- Momento de excelência identificado em auditoria (score ≥ 9 no bloco)
- Reescrita exemplar criada pelo Coaching Rewriter
- Extração de win patterns concluída

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Win-Loss Miner | Identifica e cataloga momentos de excelência |
| Coaching Rewriter | Contribui com reescritas exemplares |
| Call Auditor | Valida qualidade técnica do momento |
| Sales Chief | Aprova inclusão na biblioteca oficial |

## Inputs
- Análises de etapa com notas ≥ 9 por bloco
- Reescritas exemplares do coaching
- Transcrições com timestamps dos momentos
- Biblioteca atual em `data/libraries/best-moments-library.yaml`

## Processo
1. Coletar momentos candidatos: notas ≥ 9 em blocos do scorecard
2. Incluir reescritas que demonstram aplicação exemplar de frameworks
3. Para cada momento, documentar: closer, etapa, framework, trecho, contexto
4. Classificar por categoria: rapport, discovery, pitch, objeção, close, pricing
5. Verificar duplicatas ou momentos muito similares a existentes
6. Avaliar se o momento é replicável (não dependente de contexto único)
7. Adicionar tag de framework aplicado para busca futura
8. Incluir nota explicativa: por que este momento é exemplar
9. Ordenar por impacto e frequência de uso em treinamentos

## Frameworks Aplicados
- Framework específico de cada momento catalogado
- Rewrite Quality Checklist (para reescritas incluídas)

## Checklists de Qualidade
- Cada momento tem trecho real e contexto documentado
- Framework aplicado identificado e correto
- Momento é replicável (não depende de contexto único)
- Nota explicativa clara e educativa
- Duplicatas verificadas antes de inclusão

## Output Esperado
- Biblioteca atualizada em `data/libraries/best-moments-library.yaml`
- Log de novos momentos incluídos com classificação
- Estatísticas: total por categoria e framework

## Registry Atualizado
- `data/libraries/best-moments-library.yaml`
- `data/registries/intelligence-registry.yaml`

## Critérios de Conclusão
- [ ] Novos momentos incluídos com trecho e contexto
- [ ] Classificação por categoria e framework completa
- [ ] Duplicatas eliminadas
- [ ] Nota explicativa incluída por momento
- [ ] Replicabilidade validada
- [ ] Biblioteca versionada com data
