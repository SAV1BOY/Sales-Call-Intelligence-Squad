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

---

## Contexto
Esta task existe para garantir que o momento mais decisivo da call — o fechamento — seja avaliado com rigor. Sem análise estruturada do close, não é possível distinguir se a perda ocorreu por falha técnica do closer ou por fatores anteriores (discovery fraco, pricing mal ancorado).

## Especificação de I/O
- **Input**: Transcrição segmentada no formato `[MM:SS] [SPEAKER]: text`, seção de closing delimitada + análises prévias de pricing e objeções
- **Output**: `templates/reports/full-call-audit-report.md`, seção "Fechamento e Próximos Passos" + nota do bloco closing no scorecard

## Quality Gates Intermediários
- Após análise inicial: pedido de decisão identificado com timestamp exato; next steps listados com prazos concretos; 100% dos trechos com citação e minuto
- Antes de output final: qa-guardian valida coerência entre nota de closing e notas de pricing/objeções; score de closing alinhado com resultado real da call (ganhou/perdeu)

## Escalation & Rework
- Se dados insuficientes para análise: escalar para transcript-analyst (reprocessar seção de closing com timestamps corrigidos)
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief
- Se conflito entre experts (ex: Belfort vs. Gordon sobre assertividade): escalar para qa-guardian para arbitragem

## Métricas de Sucesso
- Taxa de concordância entre nota de closing e resultado real da call > 85%
- 100% das análises de close com next steps documentados (presentes ou ausentes)

## Handoff
- Output entregue a: call-auditor / sales-chief (consolidação no full-call-audit, workflow 06 Etapa 3 — relatório executivo)
- Formato de entrega: `templates/reports/full-call-audit-report.md`, seção "Fechamento e Próximos Passos" + nota do bloco closing no scorecard
- Condição de entrega: checklist obrigatório de Critérios de Conclusão 100% aprovado + qa-guardian valida coerência entre nota de closing e notas de pricing/objeções
- Próximo passo no pipeline: workflow 06 Etapa 3 (consolidação do relatório executivo pelo sales-chief)

## Rework Loop
- Definição de ciclo: re-execução completa dos steps 1-9 com revalidação do checklist obrigatório
- Max ciclos: 2
- Trigger de rework: checklist obrigatório < 80% OU qa-guardian rejeita output
- Após max ciclos: escalar para sales-chief com evidência das 2 tentativas anteriores
- Registro: toda rework registrada em data/registries/lessons-learned-registry.yaml

## Referências Cruzadas
- Workflow: `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/call-auditor.md`, `agents/experts/jordan-belfort.md`, `agents/experts/cole-gordon.md`, `agents/experts/eli-wilde.md`
- Templates: `templates/reports/full-call-audit-report.md`, `templates/scorecards/call-scorecard-template.md`
- Registries atualizados: `data/registries/scorecards-registry`
