# Script: Minerador de Padrões Win/Loss

> Minerar padrões de vitória e derrota em batch de calls para identificar o que diferencia deals ganhos de deals perdidos.

## Objetivo
Analisar lotes de calls (mínimo 30) categorizadas como ganhas ou perdidas e extrair padrões estatisticamente significativos.

## Input
- Batch de calls processadas com scorecard completo
- Classificação de resultado: ganha (fechou), perdida (não fechou), pendente
- Metadados: closer, nicho, ticket, canal de origem, data
- Mínimo de 30 calls para análise estatisticamente relevante

## Processo
1. Separar calls em dois grupos: ganhas e perdidas (excluir pendentes)
2. Para cada grupo, calcular métricas agregadas:
   - Score médio total e por bloco
   - Talk ratio médio geral e por etapa
   - Duração média total e por etapa
   - Frameworks mais usados e menos usados
   - Tipos de objeção mais comuns e taxa de resolução
3. Comparar os dois grupos e identificar diferenças significativas:
   - Em quais blocos o score é mais diferente entre wins e losses?
   - Qual talk ratio está associado a mais wins?
   - Quais frameworks aparecem mais em wins do que em losses?
   - Quais objeções quando não resolvidas levam a loss?
   - Quanto tempo de discovery está associado a mais wins?
4. Identificar padrões preditivos:
   - Score de discovery acima de X = Y% de chance de win
   - Talk ratio do closer abaixo de X% = Y% de chance de win
   - Presença de quantificação de dor = Y% de chance de win
5. Segmentar análise por dimensão:
   - Por closer: quem converte mais e por quê?
   - Por nicho: quais nichos têm padrões diferentes?
   - Por ticket: alto ticket tem padrões distintos?
   - Por canal: leads de indicação vs tráfego pago?
6. Gerar insights acionáveis (top 5 padrões de win, top 5 padrões de loss)
7. Atualizar benchmarks do squad com base nos novos dados

## Output
- Relatório de padrões win/loss com evidências estatísticas
- Top 5 padrões que diferenciam wins de losses
- Benchmarks atualizados por bloco do scorecard
- Insights segmentados por closer, nicho, ticket e canal
- Recomendações de coaching baseadas nos padrões identificados
- Gráficos de correlação entre métricas e resultado

## Dependências
- Calls processadas com scorecard completo
- Todos os scripts de análise (talk ratio, frameworks, objeções)
- Classificação de resultado por call (CRM ou manual)

## Frequência de Execução
- Executado mensalmente para análise estratégica
- Executado sob demanda quando há mudança significativa na taxa de conversão
- Requer mínimo de 30 calls para resultados confiáveis (ideal: 100+)
