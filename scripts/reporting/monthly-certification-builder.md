# Script: Builder de Certificação Mensal

> Construir automaticamente o pacote de certificação mensal para cada closer elegível.

## Objetivo
Consolidar dados de 30 dias de performance do closer e gerar o pacote de avaliação para o processo de certificação.

## Input
- Scorecards de todas as calls do closer nos últimos 30 dias
- Histórico de maturidade do closer
- Resultados de coaching do período
- Taxa de conversão dos últimos 30, 60 e 90 dias
- Feedback de pares e gestores (se disponível)
- Resultado de certificação anterior (se aplicável)

## Processo
1. Verificar elegibilidade para certificação:
   - Mínimo de 20 calls avaliadas no período
   - Participação em todas as sessões de coaching obrigatórias
   - Nenhuma penalização grave (nível 3) no período
   - Score médio acima do mínimo para o nível pretendido
2. Consolidar performance do período:
   - Score médio total e por bloco (últimas 30 calls)
   - Desvio padrão (consistência)
   - Tendência de evolução (subindo, estável, caindo)
   - Taxa de conversão do período
   - Talk ratio médio e evolução
3. Selecionar calls para avaliação:
   - 5-10 calls representativas (não apenas as melhores)
   - Incluir pelo menos 1 call com objeção complexa
   - Incluir pelo menos 1 call de alto ticket (se aplicável)
   - Incluir a melhor e a pior call do período
4. Gerar análise de competência por bloco:
   - Score médio do bloco vs mínimo exigido
   - Evidências positivas destacadas
   - Gaps identificados com recomendação
5. Avaliar dimensões de maturidade:
   - Técnica, Adaptabilidade, Consistência, Resiliência, Autonomia
   - Score por dimensão comparado ao nível pretendido
6. Gerar parecer preliminar:
   - Aprovado (todos os critérios atendidos)
   - Aprovado com ressalvas (critérios atendidos com pontos de atenção)
   - Reprovado com plano (critérios não atendidos com plano de ação)
7. Formatar pacote de certificação

## Output
- Pacote de certificação formatado com:
  - Resumo de performance (métricas e gráficos)
  - Análise por bloco com evidências
  - Calls selecionadas para avaliação com timestamps
  - Avaliação de dimensões de maturidade
  - Parecer preliminar e recomendação
  - Plano de ação (se reprovado)
- Formulário de avaliação para o certificador humano
- Histórico comparativo com certificação anterior

## Dependências
- Scorecards do período
- Closer maturity engine (lib/components/closer-maturity-engine)
- Closer maturity rubric (lib/utilities/closer-maturity-rubric)
- Dados de coaching e feedback

## Frequência de Execução
- Executado na última semana de cada mês para closers elegíveis
- Certificação é avaliada por humano após geração do pacote automatizado
- Resultado comunicado até o 5o dia útil do mês seguinte
