# Certificar Closer

> Avaliar maturidade do closer com base em auditoria estruturada e decidir aprovação ou reprovação.

## Objetivo
Criar processo formal de certificação que garanta que closers na operação atendem padrão mínimo de qualidade — protege a taxa de conversão e identifica quem precisa de desenvolvimento intensivo.

## Trigger
- Execução do workflow `12-monthly-closer-certification`
- Onboarding de novo closer (certificação inicial)
- Solicitação de reavaliação pelo gestor

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Closer Trainer | Executa avaliação de maturidade |
| Scorecard Analyst | Fornece análise estatística de performance |
| QA Guardian | Audita consistência da avaliação |
| Sales Chief | Toma decisão final de aprovação/reprovação |

## Inputs
- Scorecards das últimas 10 calls (mínimo 5)
- Relatórios de causa raiz
- Histórico de coaching e evolução
- Plano de treino vigente e progresso
- Benchmarks da equipe (média, top performers)

## Processo
1. Calcular score médio das últimas 10 calls
2. Analisar evolução: tendência de melhoria, estagnação ou piora
3. Avaliar domínio por bloco: quais blocos estão acima/abaixo do mínimo
4. Verificar se gaps identificados em plano de treino foram superados
5. Avaliar consistência: variação de score entre calls (desvio padrão)
6. Classificar nível de maturidade: Iniciante, Intermediário, Avançado, Expert
7. Aplicar critérios de certificação:
   - Score médio ≥ 65: aprovado nível Intermediário
   - Score médio ≥ 80: aprovado nível Avançado
   - Score médio ≥ 90 + consistência: aprovado nível Expert
   - Score médio < 50: reprovado — plano intensivo obrigatório
8. Documentar decisão com justificativa e evidências
9. Definir próxima data de reavaliação

## Frameworks Aplicados
- Competency Development Framework
- Coaching Progression Check
- Call Scorecard Framework (benchmarks)

## Checklists de Qualidade
- Mínimo 5 calls avaliadas para certificação
- Score médio calculado corretamente
- Evolução temporal analisada (não apenas snapshot)
- Consistência avaliada (desvio padrão)
- Decisão justificada com dados

## Output Esperado
- Certificado em `reports/certification/CLOSER-NAME-certification`
- Nível de maturidade: Iniciante / Intermediário / Avançado / Expert
- Aprovação ou reprovação com justificativa

## Registry Atualizado
- `data/registries/closer-certification-registry.yaml`
- `data/registries/closer-performance-registry.yaml`

## Critérios de Conclusão
- [ ] Score médio calculado (mínimo 5 calls)
- [ ] Evolução temporal analisada
- [ ] Consistência avaliada
- [ ] Nível de maturidade classificado
- [ ] Decisão de aprovação/reprovação documentada
- [ ] Próxima reavaliação agendada
