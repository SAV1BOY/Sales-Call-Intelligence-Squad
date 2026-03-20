# Script: Builder de Pack de Coaching

> Construir automaticamente o pack de coaching personalizado para cada closer com base nos dados de performance.

## Objetivo
Gerar pacote de coaching individualizado contendo diagnóstico, evidências, reescritas e plano de ação baseado nos dados reais do closer.

## Input
- Scorecards das últimas 10-20 calls do closer
- Métricas de talk ratio históricas
- Frameworks detectados e gaps
- Objeções encontradas e taxa de resolução
- Nível de maturidade atual do closer
- Resultado do último coaching (se houver)
- Metas individuais do closer

## Processo
1. Diagnosticar gaps de performance:
   - Identificar os 2-3 blocos com menor score médio
   - Identificar o bloco com maior variabilidade (inconsistência)
   - Identificar frameworks ausentes do repertório
   - Identificar padrões recorrentes de erro
2. Selecionar evidências para coaching:
   - Top 3 momentos positivos (para reforço)
   - Top 3 momentos negativos (para correção)
   - Trechos que demonstram o gap específico
   - Comparação com closer referência no mesmo bloco
3. Gerar reescritas para os momentos negativos:
   - Aplicar framework adequado ao contexto
   - Manter linguagem e tom do closer (adaptar, não substituir)
   - Explicar o que mudou e por quê
4. Construir plano de ação:
   - Foco da próxima semana (1 bloco prioritário)
   - Exercícios de roleplay recomendados
   - Conteúdo de estudo recomendado (swipe-sources)
   - Métricas de acompanhamento (o que medir para saber se melhorou)
5. Selecionar referências do swipe:
   - Exemplos de calls boas no bloco que precisa melhorar
   - Padrões fortes relevantes
   - Reescritas similares aprovadas
6. Calcular meta de evolução:
   - Score alvo por bloco para próximas 10 calls
   - Talk ratio alvo
   - Taxa de conversão alvo
7. Formatar pack em template padronizado

## Output
- Pack de coaching personalizado com:
  - Diagnóstico em 1 parágrafo
  - Score atual vs meta por bloco
  - Evidências selecionadas com timestamps
  - Reescritas de momentos negativos (antes/depois)
  - Plano de ação semanal com exercícios
  - Referências do swipe para estudo
  - Metas mensuráveis para próxima avaliação
- Material de roleplay (cenários baseados nos gaps reais)
- Checklist de acompanhamento para o coach

## Dependências
- Scorecards do closer
- Rewrite engine (lib/components/rewrite-engine)
- Closer maturity engine (lib/components/closer-maturity-engine)
- Swipe files relevantes
- Padrões relevantes (lib/patterns)

## Frequência de Execução
- Gerado semanalmente para closers em coaching ativo
- Gerado quinzenalmente para closers em manutenção
- Gerado sob demanda para intervenções específicas
