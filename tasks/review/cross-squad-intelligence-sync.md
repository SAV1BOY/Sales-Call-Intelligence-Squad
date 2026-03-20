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
