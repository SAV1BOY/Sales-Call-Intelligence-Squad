# Engine de Maturidade do Closer

> Engine responsável por avaliar e classificar o nível de maturidade de cada closer com base em critérios multidimensionais de performance.

## Função
Consolidar múltiplas métricas de performance ao longo do tempo para classificar o closer em um nível de maturidade e identificar caminhos de evolução.

## Inputs
- Histórico de scores no scorecard (últimas 30 calls mínimo)
- Taxa de conversão histórica (últimos 30, 60, 90 dias)
- Variabilidade de scores (consistência)
- Diversidade de frameworks aplicados
- Capacidade de adaptação a diferentes perfis de lead
- Feedback de coaching recebido e implementado
- Resultado de certificações (aprovado, reprovado, pendente)

## Lógica de Processamento
1. Calcular métricas base:
   - Score médio últimas 30 calls
   - Desvio padrão do score (consistência)
   - Taxa de conversão média (30, 60, 90 dias)
   - Tendência (subindo, estável, caindo)
2. Avaliar dimensões de maturidade:
   - **Técnica** (peso 30%): domínio de frameworks, execução de processo
   - **Adaptabilidade** (peso 20%): performance com diferentes perfis de lead
   - **Consistência** (peso 20%): baixa variabilidade de performance
   - **Resiliência** (peso 15%): recuperação após calls ruins, sequências de "não"
   - **Autonomia** (peso 15%): capacidade de resolver situações novas sem coaching
3. Classificar em nível de maturidade:
   - **Iniciante** (0-3 meses): Score médio 40-55, alta variabilidade, frameworks básicos
   - **Praticante** (3-6 meses): Score médio 55-70, variabilidade moderada, 3+ frameworks
   - **Profissional** (6-12 meses): Score médio 70-80, baixa variabilidade, 5+ frameworks
   - **Avançado** (12-18 meses): Score médio 80-88, consistência alta, adaptável
   - **Elite** (18+ meses): Score médio 88+, consistência excepcional, mentor de outros
4. Identificar gaps para próximo nível:
   - Listar critérios não atendidos para a próxima classificação
   - Sugerir ações específicas para cada gap
5. Comparar com pares do mesmo nível no squad

## Outputs
- Nível de maturidade atual (Iniciante → Elite)
- Score por dimensão de maturidade
- Gaps para o próximo nível com ações sugeridas
- Tendência de evolução (trajetória)
- Comparativo com pares do squad
- Previsão de tempo para próximo nível (se mantiver tendência)
- Recomendação de coaching personalizada

## Integração
- Recebe dados do **scorecard-engine** (histórico de scores)
- Recebe dados da **framework-detection-engine** (diversidade de frameworks)
- Recebe dados da **talk-ratio-engine** (evolução de talk ratio)
- Alimenta o processo de certificação (elegibilidade para certificação)
- Alimenta o coaching pack (recomendações personalizadas)
- Alimenta o dashboard executivo (distribuição de maturidade do squad)
- Alimenta decisões de alocação (closers por nível de ticket)
