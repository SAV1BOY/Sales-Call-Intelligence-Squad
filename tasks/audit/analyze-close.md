# Analisar Fechamento

> Avaliar fechamento: pedido de decisão clara, definição de next steps e condução do post-close.

## Objetivo
Verificar se o closer conduziu o fechamento com clareza e segurança — pedindo a decisão, definindo próximos passos concretos e executando post-close para reduzir buyer's remorse.

## Trigger
- Transcrição segmentada com etapa de closing delimitada
- Análises de pricing e objeções concluídas

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Avalia estrutura e eficácia do fechamento |
| Jordan Belfort | Valida técnica de fechamento e assertividade |
| Cole Gordon | Avalia clareza de next steps e post-close |
| Eli Wilde | Avalia energia e convicção no momento do close |

## Inputs
- Transcrição segmentada: seção de closing com timestamps
- Resultado da call (ganhou/perdeu/follow-up)
- Análises de pricing e objeções
- Framework Closer Four-Part (fase de fechamento)

## Processo
1. Identificar se o closer fez pedido de decisão explícito (vs. esperar o lead decidir)
2. Avaliar timing do pedido: momento certo ou prematuro/tardio
3. Verificar se ofereceu escolha binária ("vamos começar?" vs. opções confusas)
4. Analisar como lidou com hesitação final do lead
5. Verificar se definiu next steps concretos: prazos, pagamento, onboarding
6. Avaliar execução de post-close: reforço de decisão, expectativas, boas-vindas
7. Verificar se reduziu buyer's remorse com reafirmação de valor
8. Identificar se houve tentativa de upsell/cross-sell (quando aplicável)
9. Em caso de perda: verificar se propôs follow-up estruturado ou deixou morrer

## Frameworks Aplicados
- Closer Four-Part Framework (fase closing)
- Straight Line Persuasion: certeza final (Belfort)
- Low-Pressure Closing (Miner)
- Post-Close Buyer's Remorse Prevention

## Checklists de Qualidade
- Pedido de decisão explícito verificado (sim/não, trecho)
- Timing do close avaliado
- Next steps definidos com clareza (prazos, ações)
- Post-close executado (reforço de decisão, expectativas)
- Em caso de perda: follow-up proposto documentado

## Output Esperado
- Análise de fechamento em `reports/analysis/CALL-ID-close`
- Avaliação: pedido de decisão, timing, next steps, post-close
- Nota do bloco closing (0-10) com justificativa

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo close_score)

## Critérios de Conclusão
- [ ] Pedido de decisão avaliado (presente/ausente/fraco)
- [ ] Timing do close analisado
- [ ] Next steps verificados (concretos vs. vagos)
- [ ] Post-close avaliado
- [ ] Tratamento de perda documentado (se aplicável)
- [ ] Nota atribuída com evidência textual
