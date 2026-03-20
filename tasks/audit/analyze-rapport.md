# Analisar Rapport

> Avaliar qualidade do rapport: quebra de gelo, frame setting e aplicação das 3 intenções.

## Objetivo
Determinar se o closer estabeleceu conexão genuína, assumiu controle do frame e comunicou as 3 intenções do First Pact — fundação que condiciona todo o resto da call.

## Trigger
- Transcrição segmentada com etapa de rapport delimitada
- Execução do workflow `06-full-funnel-call-audit`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Executa análise detalhada da etapa de rapport |
| Cole Gordon | Valida frame setting e posicionamento de autoridade |
| Eli Wilde | Avalia energia, tonalidade e conexão emocional |
| Framework Detector | Confirma detecção de First Pact e Three Intentions |

## Inputs
- Transcrição segmentada: seção de rapport com timestamps
- Framework First Pact / Three Intentions como referência
- Doctor Frame como referência de posicionamento
- Score de talk ratio na fase de rapport

## Processo
1. Identificar se houve quebra de gelo genuína (não apenas cumprimento protocolar)
2. Avaliar se o closer estabeleceu frame de autoridade (Doctor Frame vs. vendedor)
3. Verificar aplicação das 3 intenções do First Pact: entender situação, ver se posso ajudar, ser honesto
4. Analisar se o closer tomou controle da conversa nos primeiros 2 minutos
5. Verificar se houve construção de rapport real (perguntas pessoais, espelhamento, interesse genuíno)
6. Avaliar transição do rapport para discovery (natural vs. abrupta)
7. Medir duração do rapport: curto demais (<1min) ou longo demais (>5min)
8. Identificar red flags: closer falando demais, lead desconfortável, frame perdido

## Frameworks Aplicados
- First Pact / Three Intentions
- Doctor Frame
- Straight Line Persuasion (certeza inicial)
- Tonality Mastery (Miner)

## Checklists de Qualidade
- Quebra de gelo avaliada com evidência textual
- Frame setting analisado: Doctor Frame vs. vendedor
- 3 intenções verificadas individualmente (presente/ausente/parcial)
- Duração do rapport documentada e avaliada
- Transição para discovery analisada

## Output Esperado
- Análise de rapport em `reports/analysis/CALL-ID-rapport`
- Nota do bloco rapport (0-10) com justificativa
- Status de cada intenção: aplicada, parcial ou ausente

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo rapport_score)

## Critérios de Conclusão
- [ ] Quebra de gelo avaliada
- [ ] Frame setting analisado com evidência
- [ ] 3 intenções verificadas individualmente
- [ ] Duração e proporção do rapport documentadas
- [ ] Transição para discovery avaliada
- [ ] Nota atribuída com justificativa textual
