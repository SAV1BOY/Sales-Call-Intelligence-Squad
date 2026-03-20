# Tagueamento de Evidência — Formato Padrão

> Utilitário que define o formato padrão de tags de evidência usadas em todo o sistema para marcar trechos relevantes da transcrição.

## Função
Padronizar como evidências são marcadas, categorizadas e referenciadas em scorecards, relatórios e packs de coaching.

## Formato Padrão de Tag
Cada evidência segue este formato:
- **ID**: Identificador único (CALL-XXX-EVD-NNN)
- **Trecho**: Texto exato da transcrição (máximo 200 palavras)
- **Timestamp**: [MM:SS] início — [MM:SS] fim
- **Speaker**: CLOSER ou LEAD
- **Etapa**: Abertura, Discovery, Pitch, Price Reveal, Objeção, Fechamento
- **Tipo**: Positiva, Negativa, Neutra
- **Subtipo**: Framework aplicado, Objeção detectada, Pergunta profunda, Monólogo, etc.
- **Relevância**: 0-100 (score de importância para avaliação)
- **Bloco do Scorecard**: Qual bloco esta evidência suporta

## Tipos de Evidência
1. **Positiva**: Demonstra competência ou boa prática do closer
2. **Negativa**: Demonstra gap ou erro do closer
3. **Neutra**: Momento informativo sem impacto claro na avaliação
4. **Crítica**: Evidência de prática proibida (penalização automática)
5. **Exemplar**: Evidência de prática excepcional (bonificação automática)

## Subtipos Detalhados
- Framework aplicado (qual framework, nível de execução)
- Pergunta de aprofundamento (camada atingida)
- Objeção detectada (tipo, categoria)
- Monólogo (duração, impacto)
- Silêncio estratégico (duração, contexto)
- Espelhamento (qualidade da execução)
- Sinal de compra (tipo, intensidade)
- Sinal de rejeição (tipo, causa provável)

## Regras de Tagueamento
1. Cada trecho deve ter no máximo uma tag principal (evitar duplicação)
2. Cada bloco do scorecard precisa de no mínimo 2 evidências para avaliação válida
3. Evidências críticas e exemplares devem ser revisadas por humano antes de aplicar
4. Relevância acima de 80 indica evidência prioritária para coaching
5. Trechos com mais de 200 palavras devem ser resumidos mantendo contexto

## Integração
- Usado pela **evidence-tagging-engine** como especificação de formato
- Alimenta o **scorecard-engine** (evidências por bloco)
- Alimenta packs de coaching (evidências priorizadas)
- Alimenta swipe files (evidências exemplares e críticas)
