# Fase 8 — Registry Update

> Atualizar o registro oficial do closer com os resultados da auditoria e encerrar o pipeline.

## Objetivo
Registrar todos os dados da auditoria no registry para construir histórico, permitir análise de tendências e alimentar futuras auditorias com contexto.

## Inputs
- Coaching pack completo (output da Fase 7)
- Scorecard (output da Fase 4)
- Metadados da call (output da Fase 0)
- ID da auditoria e ID da call

## Atividades
1. Registrar score total e scores por bloco no perfil do closer
2. Atualizar média histórica do closer com o novo dado
3. Calcular tendência (melhoria, estabilidade ou degradação) comparando com últimas 5 auditorias
4. Registrar frameworks detectados e classificação de aplicação
5. Registrar causa raiz identificada e prioridades de coaching
6. Atualizar status da auditoria de "em auditoria" para "concluída"
7. Se o score atingir Gold Standard (90+), marcar a call como referência
8. Se o score estiver em faixa crítica (abaixo de 40), gerar alerta para o gestor
9. Gerar relatório de tendência do closer com gráfico de evolução
10. Verificar se o closer está próximo de certificação ou renovação

## Agentes Responsáveis
- Registry Manager (responsável principal)
- Trend Analyst (suporte para análise de tendências)
- Certification Agent (suporte para verificação de elegibilidade)

## Output
- Registry atualizado com todos os dados da auditoria
- Tendência calculada (melhoria/estabilidade/degradação)
- Alerta gerado se score crítico
- Call marcada como referência se Gold Standard
- Relatório de evolução do closer atualizado

## Critérios de Conclusão
- [ ] Score registrado no perfil do closer
- [ ] Média histórica atualizada
- [ ] Tendência calculada
- [ ] Status da auditoria atualizado para "concluída"
- [ ] Alertas gerados se aplicável
- [ ] Relatório de evolução atualizado

## Próxima Fase
→ Pipeline concluído. Retornar à Fase 0 para próxima call ou iniciar Coaching Sprint se indicado.
