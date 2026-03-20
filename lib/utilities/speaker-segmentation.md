# Segmentação por Speaker

> Utilitário responsável por identificar e segmentar falas por speaker (closer vs lead) na transcrição.

## Função
Receber transcrição bruta e identificar quem fala em cada trecho, separando falas do closer e do lead.

## Métodos de Detecção
- **Tag explícita**: Transcrição já vem com tags de speaker (ex: "Closer:", "Lead:")
- **Padrão de nome**: Nome do closer/lead identificado por CRM e matching
- **Detecção por padrão de fala**: Perguntas exploratórias = closer, respostas narrativas = lead
- **Detecção por posição**: Primeira fala geralmente é do closer (abertura)
- **Detecção por duração**: Falas longas no discovery = lead, falas longas no pitch = closer

## Lógica de Processamento
1. Verificar se transcrição já tem tags de speaker
2. Se sim, validar consistência das tags (sem atribuição trocada)
3. Se não, aplicar detecção automática:
   - Identificar padrões de abertura (closer)
   - Identificar padrões de resposta (lead)
   - Usar heurística de alternância de turnos
4. Marcar cada turno de fala com: speaker, timestamp início, timestamp fim, duração
5. Detectar momentos de sobreposição (ambos falando ao mesmo tempo)
6. Detectar momentos de silêncio (ninguém falando por 3+ segundos)
7. Validar resultado: verificar se a atribuição faz sentido contextualmente

## Tags Padrão
- **[CLOSER]**: Fala do closer / consultor de vendas
- **[LEAD]**: Fala do lead / prospect / cliente potencial
- **[SILÊNCIO]**: Pausa acima de 3 segundos
- **[SOBREPOSIÇÃO]**: Ambos falando simultaneamente
- **[INDETERMINADO]**: Não foi possível determinar o speaker

## Validações
- Cada turno de fala deve ter exatamente um speaker
- Alternância de speakers deve ser coerente (raramente o mesmo speaker fala 3+ turnos seguidos)
- Duração de cada turno deve ser positiva e não nula
- Total de tempo de todos os turnos deve aproximar a duração total da call

## Integração
- Alimenta a **talk-ratio-engine** (tempo de fala por speaker)
- Alimenta a **stage-segmentation-engine** (padrão de fala por etapa)
- Alimenta a **evidence-tagging-engine** (speaker de cada evidência)
- Usado por todos os scripts de processamento como utilitário base
