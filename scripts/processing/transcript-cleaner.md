# Script: Limpeza de Transcrição

> Limpar e normalizar transcrições brutas de calls de vendas para formato padronizado do Squad.

## Objetivo
Receber transcrições brutas de diferentes fontes (Zoom, Google Meet, ferramentas de transcrição) e normalizar para o formato padrão usado por todas as engines de análise.

## Input
- Arquivo de transcrição bruta (TXT, SRT, VTT, JSON)
- Metadados da call (data, closer, lead, duração)
- Formato de origem (qual ferramenta gerou a transcrição)

## Processo
1. Detectar formato de entrada e parsear conforme tipo de arquivo
2. Remover artefatos de transcrição automática:
   - Tags de formatação HTML/XML residuais
   - Caracteres especiais não relevantes
   - Linhas duplicadas consecutivas
   - Timestamps redundantes em formatos SRT/VTT
3. Normalizar texto:
   - Corrigir capitalização (início de frase em maiúscula)
   - Padronizar pontuação (adicionar pontos finais quando ausentes)
   - Corrigir erros comuns de transcrição automática no contexto de vendas
   - Manter gírias e expressões coloquiais (não formalizar)
4. Normalizar timestamps para formato padrão [MM:SS]
5. Identificar e marcar turnos de fala com tags [CLOSER] e [LEAD]
6. Remover ruídos de áudio transcritos ("ãã", "humm" repetitivos — manter se estratégicos)
7. Validar resultado: texto legível, timestamps sequenciais, speakers identificados
8. Gerar arquivo de saída no formato padrão

## Output
- Transcrição limpa em formato padrão (.md ou .json)
- Relatório de limpeza (quantas correções feitas, percentual de confiança)
- Arquivo original preservado como backup
- Metadados enriquecidos (duração calculada, número de turnos, words per minute)

## Dependências
- Parser de timestamps (lib/utilities/timestamp-parser)
- Segmentação por speaker (lib/utilities/speaker-segmentation)
- Catálogo de erros comuns de transcrição automática em português

## Frequência de Execução
- Executado automaticamente para cada nova transcrição recebida
- Tempo médio de processamento: menos de 30 segundos por transcrição
- Pode ser executado em batch para processar múltiplas transcrições de uma vez
