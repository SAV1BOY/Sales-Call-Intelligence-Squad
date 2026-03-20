# Script: Builder de Dashboard Executivo

> Construir o dashboard executivo com visão consolidada de performance do squad, pipeline e ROI.

## Objetivo
Gerar visualização executiva que permite aos gestores tomar decisões estratégicas sobre o squad de vendas.

## Input
- Scorecards agregados (semanal e mensal)
- Dados de pipeline do CRM (deals por estágio, valor, previsão)
- Dados de conversão por closer, por nicho, por canal
- Métricas de coaching (efetividade, horas investidas)
- Dados financeiros (revenue, ticket médio, CAC)
- Metas definidas para o período

## Processo
1. Consolidar métricas de performance do squad:
   - Score médio do squad com tendência (últimas 4 semanas)
   - Taxa de conversão geral e por closer
   - Revenue total e por closer
   - Ticket médio e evolução
   - Total de calls realizadas vs meta
2. Gerar visão de pipeline:
   - Deals por nível de risco (baixo, médio, alto, crítico)
   - Valor total do pipeline por estágio
   - Previsão de fechamento para os próximos 30 dias
   - Deals parados há mais de 7 dias
   - Deals com follow-up atrasado
3. Montar painel de closers:
   - Ranking por score médio
   - Ranking por taxa de conversão
   - Ranking por revenue gerado
   - Distribuição de maturidade do squad (quantos em cada nível)
   - Closers em ascensão vs em queda
4. Analisar ROI do coaching:
   - Horas investidas em coaching no período
   - Melhoria de score pós-coaching
   - Impacto na conversão pós-coaching
   - Custo por ponto de melhoria
5. Comparar com metas:
   - Meta de conversão vs realizado
   - Meta de revenue vs realizado
   - Meta de score médio vs realizado
   - Projeção para fim do mês/trimestre
6. Gerar alertas executivos:
   - Closers que precisam de intervenção urgente
   - Deals de alto valor em risco
   - Tendências negativas que exigem ação
7. Formatar dashboard com visualizações

## Output
- Dashboard executivo com seções:
  - Resumo executivo em 3 bullet points
  - Métricas-chave em cards visuais
  - Gráfico de tendência de score e conversão
  - Visão de pipeline por risco
  - Ranking de closers
  - Alertas e ações recomendadas
- Versão exportável em PDF para reuniões
- Dados brutos em formato de tabela para análise ad-hoc

## Dependências
- Relatórios semanais acumulados
- Dados do CRM
- Deal risk scoring engine (lib/components/deal-risk-scoring-engine)
- Closer maturity engine (lib/components/closer-maturity-engine)
- Coaching effectiveness rubric (lib/utilities/coaching-effectiveness-rubric)

## Frequência de Execução
- Atualizado diariamente com dados do dia anterior
- Versão completa gerada toda segunda-feira
- Versão mensal com análise aprofundada na primeira semana do mês
