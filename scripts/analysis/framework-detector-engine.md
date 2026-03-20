# Script: Detector de Frameworks

> Detectar quais frameworks de vendas foram aplicados pelo closer em cada etapa da call por pattern matching.

## Objetivo
Analisar a transcrição por etapa e identificar a presença, ausência e qualidade de aplicação de frameworks conhecidos.

## Input
- Transcrição tagueada por etapa e speaker
- Catálogo de frameworks com patterns linguísticos (lib/taxonomies/framework-taxonomy)
- Threshold de detecção (sensibilidade mínima para considerar framework presente)
- Histórico de frameworks do closer (para detectar evolução)

## Processo
1. Para cada etapa da call, carregar frameworks esperados:
   - Abertura: rapport funcional, pauta, permissão para perguntas
   - Discovery: SPIN, NEPQ, gap selling, espelhamento, quantificação
   - Pitch: segmentação, micro-commits, PAS verbal, cases
   - Price Reveal: value stack, ancoragem, risk reversal
   - Objeção: isolamento, looping, belief shift, validação
   - Fechamento: assumptive, alternative, silencioso, urgência contextual
2. Buscar patterns linguísticos na transcrição:
   - Perguntas de implicação SPIN: "o que acontece se", "qual o impacto"
   - Espelhamento: repetição exata das últimas palavras do lead
   - Isolamento de objeção: "quando você diz X, é sobre A, B ou C?"
   - Assumptive close: transição direta sem pergunta de permissão
   - Value stack: menção a componentes com valor individual
3. Para cada framework detectado, avaliar qualidade:
   - Completo (todos os elementos presentes): 80-100
   - Parcial (alguns elementos presentes): 40-79
   - Tentativa (intenção sem execução adequada): 1-39
   - Ausente: 0
4. Identificar gaps:
   - Frameworks esperados mas ausentes
   - Etapas sem nenhum framework detectado
   - Frameworks aplicados na etapa errada
5. Gerar perfil de frameworks do closer:
   - Frameworks mais usados (preferidos)
   - Frameworks nunca usados (gaps de repertório)
   - Evolução comparada com análises anteriores

## Output
- Lista de frameworks detectados por etapa com score de qualidade
- Gaps identificados (frameworks ausentes onde esperados)
- Perfil de repertório do closer
- Recomendações de frameworks para treinar
- Comparativo com média do squad

## Dependências
- Transcrição tagueada por etapa (output do stage-tagger)
- Framework taxonomy (lib/taxonomies/framework-taxonomy)
- Framework detection engine (lib/components/framework-detection-engine)

## Frequência de Execução
- Executado automaticamente para cada call processada
- Tempo médio de processamento: menos de 10 segundos
- Resultados alimentam scorecard e coaching pack
