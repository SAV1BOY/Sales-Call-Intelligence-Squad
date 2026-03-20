# Classificar Tipo de Call

> Classificar a call como first call, follow-up, closing call ou discovery only para ajustar critérios de auditoria.

## Objetivo
Determinar o tipo exato da call para que o scorecard, os frameworks e os critérios de avaliação sejam ajustados corretamente — uma follow-up não pode ser penalizada por falta de rapport extenso.

## Trigger
- Após segmentação da call por etapa
- Metadata incompleta sobre tipo de call no momento do intake

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Transcript Analyst | Analisa conteúdo e estrutura para classificar |
| Call Auditor | Valida classificação e ajusta critérios de auditoria |
| SDR Handoff Analyst | Fornece contexto sobre histórico de interações |

## Inputs
- Transcrição segmentada com mapa de etapas
- Metadata da call (resultado declarado, closer, lead)
- Histórico de calls anteriores com o mesmo lead (se existir)
- Informações de handoff do SDR

## Processo
1. Verificar se existe histórico de calls anteriores com o mesmo lead no registry
2. Analisar conteúdo da abertura: closer faz referência a conversa anterior?
3. Avaliar estrutura da call: quais etapas estão presentes e em que proporção?
4. Classificar em uma das 4 categorias:
   - **First Call**: primeira interação, fluxo completo (rapport → closing)
   - **Follow-up**: referência a call anterior, foco em objeções pendentes ou decisão
   - **Closing Call**: objetivo principal é fechar, pricing e decisão dominam
   - **Discovery Only**: apenas diagnóstico, sem pitch ou pricing
5. Registrar evidências da classificação (trechos que confirmam o tipo)
6. Ajustar pesos do scorecard conforme tipo:
   - Follow-up: rapport peso reduzido, objeções peso aumentado
   - Discovery Only: pitch e pricing não pontuados
   - Closing Call: discovery peso reduzido, fechamento peso aumentado
7. Documentar ajustes de peso no brief de auditoria

## Frameworks Aplicados
- Sales Call Stage Taxonomy
- Closer Four-Part Framework (para validação de estrutura)

## Checklists de Qualidade
- Classificação baseada em evidência textual (não em opinião)
- Histórico do lead verificado no registry
- Pesos do scorecard ajustados conforme tipo
- Evidências da classificação documentadas com trechos

## Output Esperado
- Tipo de call registrado no `calls-registry.yaml`
- Ajustes de peso do scorecard documentados no brief de auditoria
- Evidências textuais da classificação (2-3 trechos)

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo `call_type` atualizado)

## Critérios de Conclusão
- [ ] Tipo de call classificado em uma das 4 categorias
- [ ] Evidências textuais documentadas
- [ ] Histórico do lead verificado
- [ ] Pesos do scorecard ajustados conforme tipo
- [ ] Registry atualizado com classificação
- [ ] Brief de auditoria atualizado com ajustes
