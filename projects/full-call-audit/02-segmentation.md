# Fase 2 — Segmentação

> Dividir a transcrição limpa nas 6 etapas canônicas da call para análise individual de cada fase.

## Objetivo
Produzir a call segmentada com início e fim de cada etapa claramente demarcados, permitindo análise granular.

## Inputs
- Transcrição limpa e formatada (output da Fase 1)
- Metadados da call

## Atividades
1. Ler a transcrição e identificar o ponto de transição entre cada etapa
2. Marcar início e fim de cada etapa: rapport, discovery, pitch, pricing, objections, closing
3. Classificar cada etapa como presente, parcial ou ausente na call
4. Calcular duração aproximada de cada etapa em minutos
5. Identificar se houve sobreposição de etapas (ex: discovery durante pitch)
6. Registrar transições entre etapas: natural, abrupta ou ausente
7. Se uma etapa está ausente, documentar se foi por contexto (ex: follow-up sem rapport) ou falha do closer

## Agentes Responsáveis
- Segmentation Agent (responsável principal)
- Tonality Analyzer (suporte para identificar mudanças de tom entre etapas)

## Output
- Call segmentada com 6 etapas demarcadas
- Duração de cada etapa
- Classificação de transições
- Lista de etapas ausentes ou parciais

## Critérios de Conclusão
- [ ] Todas as 6 etapas avaliadas (presente, parcial ou ausente)
- [ ] Início e fim de cada etapa marcados
- [ ] Durações calculadas
- [ ] Transições classificadas

## Notas de Execução

- Se a call for muito curta (menos de 15 minutos), algumas etapas podem estar ausentes naturalmente
- Calls de follow-up frequentemente iniciam sem rapport — registrar como "não aplicável", não como "ausente"
- Em casos de sobreposição, registrar o segmento principal e anotar a sobreposição como observação

## Próxima Fase
→ Fase 3 — Detecção de Frameworks
