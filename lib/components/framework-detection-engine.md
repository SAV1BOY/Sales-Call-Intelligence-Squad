# Engine de Detecção de Frameworks

> Engine responsável por identificar quais frameworks de vendas foram aplicados pelo closer durante a call através de pattern matching na transcrição.

## Função
Analisar a transcrição de cada etapa da call e detectar a presença (ou ausência) de frameworks conhecidos, avaliando a qualidade da aplicação.

## Inputs
- Transcrição segmentada por etapa (output da stage-segmentation-engine)
- Catálogo de frameworks por etapa (SPIN, NEPQ, Straight Line, etc.)
- Patterns linguísticos por framework (banco de patterns)
- Threshold de detecção (sensibilidade mínima para considerar framework aplicado)

## Lógica de Processamento
1. Para cada etapa da call, carregar os frameworks esperados:
   - Abertura: rapport funcional, definição de pauta, controle de expectativa
   - Discovery: SPIN, NEPQ, escada de dor, quantificação
   - Pitch: PAS verbal, value stack, segmentação com micro-commits
   - Price Reveal: ancoragem, empilhamento, risk reversal
   - Objeção: isolamento, looping, belief shift, prova social
   - Fechamento: assumptive close, alternative close, urgência contextual
2. Buscar patterns linguísticos de cada framework na transcrição:
   - Perguntas de implicação (SPIN): "o que acontece se...", "qual o impacto de..."
   - Espelhamento (Voss): repetição das últimas palavras do lead
   - Looping (Belfort): retomada da dor antes de tratar objeção
   - Assumptive close: transição direta sem pedir permissão para comprar
3. Avaliar qualidade da aplicação:
   - Framework detectado mas mal aplicado (parcial)
   - Framework detectado e bem aplicado (completo)
   - Framework ausente quando esperado (gap)
4. Calcular score de framework por etapa
5. Identificar padrões recorrentes do closer (frameworks preferidos, frameworks evitados)

## Outputs
- Lista de frameworks detectados por etapa com nível de aplicação
- Frameworks ausentes onde eram esperados (gaps)
- Score de framework por etapa (0-100)
- Padrão de preferência do closer (quais frameworks usa mais/menos)
- Recomendações de frameworks para treinar

## Integração
- Recebe dados da **stage-segmentation-engine** (transcrição por etapa)
- Recebe dados da **evidence-tagging-engine** (trechos com frameworks marcados)
- Alimenta o **scorecard-engine** (score de framework como componente do bloco)
- Alimenta o **rewrite-engine** (sugere framework adequado para reescrita)
- Alimenta o **closer-maturity-engine** (repertório de frameworks do closer)
