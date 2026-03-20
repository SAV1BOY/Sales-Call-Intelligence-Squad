# Script: Segmentação por Speaker

> Segmentar transcrição limpa por speaker, identificando quem fala em cada trecho da call.

## Objetivo
Receber transcrição limpa e aplicar segmentação por speaker (closer vs lead), gerando output com atribuição confiável para uso em análises posteriores.

## Input
- Transcrição limpa (output do transcript-cleaner)
- Dados do CRM: nome do closer atribuído à call
- Dados de áudio (se disponível): perfil de voz por speaker
- Heurísticas de detecção por padrão de fala

## Processo
1. Verificar se a transcrição já possui tags de speaker da ferramenta de origem
2. Se possui tags, validar consistência:
   - Verificar se os nomes correspondem ao closer e lead corretos
   - Corrigir inversões detectadas por padrão de fala
   - Marcar trechos com atribuição incerta
3. Se não possui tags, aplicar detecção automática:
   - Identificar primeira fala como closer (99% das calls, closer abre)
   - Aplicar heurística de alternância de turnos
   - Classificar por padrão linguístico (perguntas exploratórias = closer, respostas narrativas = lead)
   - Usar contexto para resolver ambiguidades
4. Marcar cada turno com metadados:
   - Speaker: [CLOSER] ou [LEAD]
   - Timestamp início e fim
   - Duração do turno em segundos
   - Contagem de palavras
5. Detectar momentos especiais:
   - Sobreposição de fala (ambos ao mesmo tempo)
   - Silêncio prolongado (3+ segundos)
   - Monólogo (fala contínua acima de 90 segundos)
6. Calcular métricas preliminares de talk ratio
7. Validar resultado e gerar relatório de confiança

## Output
- Transcrição segmentada com tags de speaker
- Métricas de talk ratio preliminar (closer% vs lead%)
- Lista de momentos especiais (sobreposição, silêncio, monólogo)
- Relatório de confiança da segmentação (percentual de certeza por trecho)
- Trechos marcados como incertos para revisão manual

## Dependências
- Transcrição limpa (output do transcript-cleaner)
- Dados do CRM (nome do closer)
- Utilitário de speaker segmentation (lib/utilities/speaker-segmentation)

## Frequência de Execução
- Executado automaticamente após limpeza de transcrição
- Tempo médio de processamento: menos de 20 segundos
- Resultados com confiança abaixo de 85% são enviados para revisão manual
