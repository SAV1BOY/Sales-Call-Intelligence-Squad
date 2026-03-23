# Sync de Inteligência com Outros Squads

> Sincronizar inteligência de vendas com outros squads: copy, tráfego, produto, operações.

## Objetivo
Garantir que insights das calls cheguem aos times que podem agir sobre eles — objeções recorrentes viram ajustes de copy, dores do ICP viram features, handoff ruim vira processo novo.

## Trigger
- Review semanal ou mensal concluída com insights cross-squad
- Padrão identificado cuja causa raiz está fora do squad de vendas
- Execução dos workflows `14-closer-to-copy-feedback`, `15-closer-to-traffic-feedback`, `16-closer-to-offer-feedback`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Revenue Intelligence Analyst | Prepara inteligência para compartilhamento |
| Sales Chief | Prioriza e direciona feedback para squads corretos |
| Offer Fit Analyst | Fornece análise de fit para time de oferta |
| SDR Handoff Analyst | Fornece feedback para time de SDR |

## Inputs
- Relatórios de win/loss patterns
- Análises de fit oferta-dor-ICP
- Objeções recorrentes com causa raiz "externa"
- Feedback de handoff SDR→closer
- Dores mais frequentes verbalizadas pelos leads

## Processo
1. Filtrar insights que têm ação fora do squad de vendas
2. Classificar por squad destino: copy, tráfego, produto, operações, SDR
3. Para cada squad, preparar briefing: insight, evidência, ação sugerida
4. Para copy: objeções que indicam messaging desalinhado, frases que funcionam
5. Para tráfego: segmentos de ICP que não convertem, origem dos melhores leads
6. Para produto/oferta: gaps de fit, features solicitadas, pricing feedback
7. Para SDR: qualidade do handoff, informações faltantes, qualificação
8. Formatar feedback como acionável (não como crítica)
9. Definir canal e cadência de compartilhamento por squad

## Frameworks Aplicados
- Cross-Squad Feedback Loop
- Closer-to-Copy Feedback
- Closer-to-Traffic Feedback
- Closer-to-Offer Feedback

## Checklists de Qualidade
- Cada insight tem evidência de múltiplas calls (não anedótico)
- Feedback classificado por squad destino
- Ações sugeridas são específicas e implementáveis
- Tom construtivo (feedback, não reclamação)
- Priorização por impacto na conversão

## Output Esperado
- Briefings por squad em `reports/intelligence/cross-squad-sync-PERIODO`
- Lista de ações sugeridas por squad com prioridade
- Registro de feedbacks enviados e status

## Registry Atualizado
- `data/registries/intelligence-registry.yaml`
- `data/registries/cross-squad-feedback-registry.yaml`

## Critérios de Conclusão
- [ ] Insights cross-squad identificados e classificados
- [ ] Briefings preparados por squad destino
- [ ] Ações sugeridas são específicas e acionáveis
- [ ] Feedback compartilhado com squads relevantes
- [ ] Status de feedbacks anteriores verificado
- [ ] Registry atualizado

---

## Contexto
Esta task existe para garantir que insights extraídos das calls cheguem aos times que podem agir sobre eles. Objeções recorrentes devem virar ajustes de copy, leads ruins devem virar ajustes de tráfego, e gaps de oferta devem subir para o C-level — sem esse sync, inteligência de vendas morre dentro do squad.

## Especificação de I/O
- **Input**: Relatórios de win/loss patterns, análises de fit oferta-dor-ICP, objeções com causa raiz externa, feedback de handoff SDR→closer
- **Output**: Briefings por squad em `reports/intelligence/cross-squad-sync-PERIODO` usando `templates/operational/cross-squad-handoff-template.md`

## Quality Gates Intermediários
- Após classificação por squad destino (step 2): cada insight tem evidência de múltiplas calls (não anedótico)
- Antes de output final: ações sugeridas são específicas e implementáveis, tom construtivo, priorização por impacto na conversão

## Escalation & Rework
- Se insight requer decisão estratégica (ex: mudança de pricing ou oferta): escalar para sales-chief para handoff ao c_level_squad
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para sales-chief

## Métricas de Sucesso
- cross_squad_delivery_rate (taxa de entrega de insights aos squads destino)
- Taxa de implementação dos insights entregues (feedback loop)

## Referências Cruzadas
- Workflow: `workflows/14-closer-to-copy-feedback.md`, `workflows/15-closer-to-traffic-feedback.md`, `workflows/16-closer-to-offer-feedback.md`, `workflows/13-sdr-to-closer-feedback-loop.md`
- Agents: `agents/revenue-intelligence-analyst.md`, `agents/sales-chief.md`, `agents/offer-fit-analyst.md`, `agents/sdr-handoff-analyst.md`
- Templates: `templates/operational/cross-squad-handoff-template.md`, `templates/briefs/cross-squad-insight-brief.md`
- Registries atualizados: `data/registries/intelligence-registry.yaml`, `data/registries/cross-squad-feedback-registry.yaml`

## Handoff
- **Output entregue a**: sales-chief para priorização e direcionamento aos squads destino (copy, tráfego, produto, operações, SDR)
- **Formato de entrega**: briefings por squad em `reports/intelligence/cross-squad-sync-PERIODO` usando `templates/operational/cross-squad-handoff-template.md`
- **Condição de entrega**: cada insight tem evidência de múltiplas calls, ações sugeridas são específicas e implementáveis, tom construtivo validado
- **Próximo passo no pipeline**: sales-chief distribui briefings aos squads destino e monitora implementação via cross-squad-feedback-registry

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
