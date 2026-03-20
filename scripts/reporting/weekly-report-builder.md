# Script: Builder de Relatório Semanal

> Construir automaticamente o relatório semanal do squad com métricas, tendências e insights acionáveis.

## Objetivo
Consolidar dados de todas as calls da semana e gerar relatório padronizado para gestores e closers.

## Input
- Scorecards de todas as calls da semana
- Métricas de talk ratio agregadas
- Classificação de resultado (win/loss/pendente)
- Dados do CRM (pipeline, revenue, atividades)
- Relatório da semana anterior (para comparativo)

## Processo
1. Consolidar métricas da semana:
   - Total de calls analisadas
   - Score médio do squad (total e por bloco)
   - Taxa de conversão da semana
   - Revenue gerado
   - Talk ratio médio
2. Calcular tendências (comparativo com semana anterior):
   - Score subiu ou caiu? Quanto?
   - Conversão subiu ou caiu?
   - Quais blocos melhoraram e quais pioraram?
3. Gerar ranking de closers:
   - Top 3 scores da semana (com calls destaque)
   - Closers abaixo da média (com gaps identificados)
   - Maior evolução da semana (quem mais melhorou)
4. Identificar padrões da semana:
   - Objeções mais frequentes
   - Frameworks mais e menos usados
   - Etapas com maior gap em relação ao benchmark
5. Selecionar highlights:
   - Melhor call da semana (maior score) com trecho destaque
   - Pior call da semana (menor score) com lição aprendida
   - Melhor turnaround da semana (se houver)
6. Gerar recomendações:
   - Foco de coaching da próxima semana (baseado nos dados)
   - Closers que precisam de atenção imediata
   - Padrões que precisam ser corrigidos em grupo
7. Formatar relatório em template padrão

## Output
- Relatório semanal formatado (.md) com seções:
  - Resumo executivo (5 linhas)
  - Métricas da semana em tabela
  - Tendências e comparativo
  - Ranking de closers
  - Highlights (melhor, pior, turnaround)
  - Recomendações para próxima semana
- Dashboard visual (se integrado com ferramenta de BI)
- Alertas automáticos para closers abaixo do esperado

## Dependências
- Scorecards processados da semana
- Dados do CRM
- Relatório da semana anterior
- Template de relatório semanal

## Frequência de Execução
- Executado toda segunda-feira às 8h (cobrindo segunda a sexta anterior)
- Distribuído automaticamente para gestores e closers
- Tempo médio de geração: menos de 2 minutos
