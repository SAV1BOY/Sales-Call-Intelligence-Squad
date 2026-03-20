# Script: Classificador de Objeções

> Classificar objeções detectadas em calls de vendas por tipo, categoria, causa raiz e qualidade do tratamento.

## Objetivo
Identificar todas as objeções levantadas pelo lead, classificá-las usando a taxonomia padrão e avaliar como o closer as tratou.

## Input
- Transcrição tagueada por etapa e speaker
- Taxonomia de objeções (lib/taxonomies/objection-taxonomy)
- Catálogo de patterns linguísticos de objeção
- Contexto do discovery (dor identificada, informações do lead)

## Processo
1. Detectar objeções na transcrição por patterns linguísticos:
   - Frases de hesitação: "preciso pensar", "não sei", "vou avaliar"
   - Frases de preço: "está caro", "não tenho budget", "é muito"
   - Frases de autoridade: "preciso falar com", "não decido sozinho"
   - Frases de timing: "agora não", "depois", "não é o momento"
   - Frases de confiança: "já tentei", "não acredito", "funciona mesmo?"
2. Para cada objeção detectada, classificar:
   - **Tipo**: Real, Social, Reflexo, Mista
   - **Categoria**: Preço, Autoridade, Timing, Confiança, Necessidade, Experiência
   - **Severidade**: Baixa, Média, Alta, Crítica
   - **Etapa onde surgiu**: Em qual momento da call
3. Identificar causa raiz provável:
   - Discovery insuficiente (dor não explorada)
   - Pitch desconectado (valor não demonstrado)
   - Rapport fraco (confiança não estabelecida)
   - Fator externo genuíno
4. Avaliar qualidade do tratamento pelo closer:
   - Validou o sentimento? (sim/não)
   - Isolou a objeção real? (sim/não)
   - Explorou causa raiz? (sim/não)
   - Usou evidência ou reframe? (sim/não)
   - Confirmou resolução? (sim/não)
   - Resultado: resolvida, parcialmente resolvida, não resolvida, agravada
5. Calcular score de tratamento por objeção (0-100)
6. Identificar padrões: objeções recorrentes por closer, por nicho, por etapa

## Output
- Lista de objeções detectadas com classificação completa
- Score de tratamento por objeção
- Causa raiz identificada por objeção
- Padrões de objeção recorrentes
- Recomendações de melhoria para o closer
- Objeções não resolvidas sinalizadas para follow-up

## Dependências
- Transcrição tagueada (output do stage-tagger)
- Taxonomia de objeções (lib/taxonomies/objection-taxonomy)
- Objection taxonomy engine (lib/components/objection-taxonomy-engine)

## Frequência de Execução
- Executado automaticamente para cada call processada
- Tempo médio de processamento: menos de 10 segundos
- Resultados alimentam scorecard, coaching pack e banco de objeções
