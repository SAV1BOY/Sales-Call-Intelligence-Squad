# Fase 1 — Limpeza de Transcrição

> Transformar a transcrição bruta em um documento limpo, formatado e com speakers identificados para análise precisa.

## Objetivo
Produzir uma transcrição de alta qualidade que permita análise precisa de frameworks, scoring e coaching sem ambiguidades.

## Inputs
- Transcrição bruta da call (output da Fase 0)
- Metadados da call (nome do closer, contexto)
- Áudio original (quando disponível, para verificação)

## Atividades
1. Corrigir erros de transcrição automática (nomes, termos técnicos, números)
2. Identificar e rotular speakers como CLOSER e PROSPECT consistentemente
3. Remover ruídos da transcrição (marcações de sistema, timestamps desnecessários)
4. Marcar trechos ininteligíveis com [INAUDÍVEL] e registrar percentual
5. Padronizar formatação: cada fala em linha separada com speaker identificado
6. Adicionar timestamps aproximados a cada 5 minutos para referência
7. Validar que a transcrição tem início e fim da call (não está cortada)
8. Se percentual de [INAUDÍVEL] for maior que 10%, classificar como "baixa confiança"

## Agentes Responsáveis
- Transcript Cleaner (responsável principal)
- Context Enricher (suporte para termos técnicos do nicho)

## Output
- Transcrição limpa com speakers identificados
- Classificação de qualidade: alta (menos de 3% inaudível), média (3-10%), baixa (mais de 10%)
- Relatório de limpeza: quantas correções, trechos inaudíveis, observações

## Critérios de Conclusão
- [ ] Todos os speakers identificados corretamente
- [ ] Erros de transcrição corrigidos
- [ ] Formatação padronizada
- [ ] Qualidade classificada
- [ ] Trechos inaudíveis marcados e contabilizados

## Próxima Fase
→ Fase 2 — Segmentação
