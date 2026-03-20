# Engine de Taxonomia de Objeções

> Engine responsável por classificar objeções detectadas em calls de vendas por tipo, causa raiz e nível de severidade.

## Função
Receber trechos de transcrição contendo objeções, classificar cada uma por tipo taxonômico, identificar a causa raiz e avaliar a qualidade do tratamento dado pelo closer.

## Inputs
- Trecho de transcrição contendo a objeção
- Timestamp do momento da objeção
- Contexto anterior (últimas 5 falas antes da objeção)
- Resposta do closer à objeção
- Resultado observado (objeção resolvida, parcialmente resolvida, não resolvida)

## Lógica de Processamento
1. Detectar a objeção no trecho de transcrição por patterns linguísticos
2. Classificar por tipo primário:
   - Objeção Real: preocupação genuína com fundamento (preço, tempo, autoridade)
   - Objeção Social: desculpa educada para sair da call ("vou pensar", "agora não")
   - Objeção Reflexo: reação automática de defesa sem reflexão real
   - Objeção Mista: combinação de tipos
3. Classificar por categoria temática:
   - Preço/Investimento, Tempo/Urgência, Autoridade/Decisor, Confiança/Credibilidade, Necessidade/Fit, Experiência anterior
4. Identificar causa raiz provável:
   - Falha no discovery (dor não explorada suficientemente)
   - Falha no pitch (valor não conectado à dor)
   - Falha no rapport (confiança não estabelecida)
   - Fator externo genuíno (realmente não tem budget, não é decisor)
5. Avaliar qualidade do tratamento (0-100):
   - Validação presente? Isolamento feito? Causa raiz explorada? Evidência usada? Resolução confirmada?
6. Registrar resultado: resolvida, parcialmente resolvida, não resolvida, agravada

## Outputs
- Classificação da objeção (tipo + categoria + causa raiz)
- Score de qualidade do tratamento (0-100)
- Resultado do tratamento
- Recomendação de melhoria para o closer
- Padrão detectado (objeção recorrente neste closer ou neste nicho)

## Integração
- Recebe dados da **evidence-tagging-engine** (trechos marcados como objeção)
- Recebe dados da **stage-segmentation-engine** (em qual etapa surgiu)
- Alimenta o **scorecard-engine** com score do bloco de objeção
- Alimenta o **rewrite-engine** com objeções para reescrita
- Alimenta a taxonomia de objeções com novos padrões identificados
