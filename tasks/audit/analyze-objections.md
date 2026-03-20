# Analisar Objeções

> Analisar objeções levantadas: tipo, causa raiz, resposta do closer e eficácia da resolução.

## Objetivo
Mapear cada objeção, classificar sua causa raiz real, avaliar a qualidade da resposta do closer e determinar se a objeção foi resolvida — objeções mal tratadas são a causa direta de deals perdidos.

## Trigger
- Transcrição segmentada com etapa de objeções delimitada
- Execução do workflow `07-objection-root-cause-analysis`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Objection Specialist | Classifica objeções e avalia respostas |
| Call Auditor | Consolida análise e identifica padrões |
| Dan Lok | Valida técnicas de resolução de objeções de alto ticket |
| Jordan Belfort | Avalia uso de looping e re-enquadramento |
| Jeremy Miner | Avalia uso de perguntas para dissolver objeções |

## Inputs
- Transcrição segmentada: seção de objeções com timestamps
- Biblioteca de objeções em `data/libraries/objections-library.yaml`
- Relatório de frameworks detectados
- Contexto de pricing apresentado

## Processo
1. Listar todas as objeções verbalizadas pelo lead com timestamp e trecho exato
2. Classificar cada objeção por tipo: preço, timing, decisor, confiança, concorrência, fit
3. Identificar causa raiz real: discovery fraco, pitch genérico, falta de prova, preço sem valor
4. Avaliar resposta do closer: técnica usada, timing, tom
5. Classificar eficácia da resposta: resolvida, parcialmente resolvida, não resolvida, piorada
6. Verificar se closer antecipou objeções preventivamente (antes de surgirem)
7. Identificar objeções não verbalizadas mas inferidas pelo comportamento do lead
8. Registrar novas objeções ou variações não presentes na biblioteca
9. Avaliar se objeções recorrentes indicam problema sistêmico (oferta, copy, SDR)

## Frameworks Aplicados
- Objection Root Cause Framework
- Straight Line Persuasion: Looping (Belfort)
- NEPQ: perguntas de dissolução (Miner)
- Hormozi Price-to-Value Gap

## Checklists de Qualidade
- Cada objeção registrada com trecho exato e timestamp
- Causa raiz identificada (não apenas o tipo superficial)
- Resposta do closer avaliada com técnica e eficácia
- Objeções preventivas verificadas (presentes/ausentes)
- Novas objeções sinalizadas para biblioteca

## Output Esperado
- Análise de objeções em `reports/analysis/CALL-ID-objections`
- Tabela: objeção, tipo, causa raiz, resposta, eficácia
- Recomendações de melhoria por objeção não resolvida

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo objections_score)
- `data/libraries/objections-library.yaml` (se novas objeções encontradas)

## Critérios de Conclusão
- [ ] Todas as objeções listadas com trecho e timestamp
- [ ] Tipo e causa raiz classificados por objeção
- [ ] Resposta do closer avaliada com técnica e eficácia
- [ ] Objeções preventivas verificadas
- [ ] Novas objeções sinalizadas para biblioteca
- [ ] Nota atribuída com justificativa
