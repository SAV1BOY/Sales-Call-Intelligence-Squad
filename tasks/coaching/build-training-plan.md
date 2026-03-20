# Construir Plano de Treino

> Construir plano de treino individualizado: top 3 prioridades, exercícios práticos e métricas de progresso.

## Objetivo
Criar plano de desenvolvimento estruturado para o closer baseado em padrões identificados em múltiplas calls — não é sobre uma call específica, mas sobre gaps recorrentes que precisam de treino sistemático.

## Trigger
- Mínimo de 3 calls auditadas do mesmo closer
- Padrões recorrentes identificados nas causas raiz
- Solicitação de plano de desenvolvimento pelo gestor

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Closer Trainer | Constrói o plano de treino completo |
| Scorecard Analyst | Fornece análise de tendências de scores |
| Sales Chief | Aprova plano e define prazos |
| QA Guardian | Valida que o plano é específico e mensurável |

## Inputs
- Scorecards das últimas 5-10 calls do closer
- Relatórios de causa raiz (padrões recorrentes)
- Histórico de coaching anterior
- Perfil de maturidade do closer
- Frameworks mais deficientes

## Processo
1. Analisar tendências de score por bloco nas últimas 5-10 calls
2. Identificar os 3 gaps mais recorrentes e de maior impacto
3. Priorizar por impacto na taxa de conversão × facilidade de correção
4. Para cada prioridade, definir:
   - Habilidade específica a desenvolver
   - Framework de referência para estudo
   - Exercício prático (role-play, drill, análise de call modelo)
   - Métrica de progresso (score do bloco, comportamento observável)
   - Prazo para reavaliação
5. Definir cadência de acompanhamento: semanal para gaps críticos
6. Incluir calls de referência (exemplos positivos do próprio closer ou de top performers)
7. Definir critério de graduação: quando o closer superou o gap
8. Vincular plano ao scorecard para tracking automático

## Frameworks Aplicados
- Coaching Progression Check
- Coaching Priority Check
- Scorecard-to-Coaching Bridge
- Competency Development Framework

## Checklists de Qualidade
- Top 3 prioridades baseadas em dados (não em impressão)
- Cada prioridade tem exercício prático e métrica
- Prazos definidos e realistas
- Calls de referência incluídas
- Critério de graduação claro e mensurável

## Output Esperado
- Plano de treino em `reports/training/CLOSER-NAME-training-plan`
- Top 3 prioridades com exercícios, métricas e prazos
- Cadência de acompanhamento definida

## Registry Atualizado
- `data/registries/coaching-registry.yaml`
- `data/registries/closer-performance-registry.yaml`

## Critérios de Conclusão
- [ ] Tendências de score analisadas (mínimo 3 calls)
- [ ] Top 3 gaps identificados com dados
- [ ] Exercício prático e métricas definidos por prioridade
- [ ] Prazos, cadência estabelecidos e plano aprovado pelo Sales Chief
