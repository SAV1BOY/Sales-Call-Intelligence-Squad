# Analisar Profundidade de Discovery

> Avaliar profundidade do discovery: aplicação de SPIN, NEPQ, camadas de investigação e qualidade das perguntas.

## Objetivo
Medir se o closer cavou fundo o suficiente para entender a dor real do lead, ou ficou na superfície — discovery raso é a causa raiz #1 de calls perdidas.

## Trigger
- Transcrição segmentada com etapa de discovery delimitada
- Execução do workflow `06-full-funnel-call-audit`

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Call Auditor | Coordena análise de discovery |
| Neil Rackham | Avalia aplicação de SPIN Selling |
| Jeremy Miner | Avalia aplicação de NEPQ e perguntas de consequência |
| Cole Gordon | Avalia profundidade do diagnóstico |

## Inputs
- Transcrição segmentada: seção de discovery com timestamps
- Frameworks SPIN Selling e NEPQ como referência
- Mapa de perguntas feitas pelo closer
- Informações do ICP e oferta

## Processo
1. Mapear todas as perguntas feitas pelo closer na fase de discovery
2. Classificar cada pergunta: Situação, Problema, Implicação, Necessidade (SPIN)
3. Avaliar progressão NEPQ: perguntas de conexão → situação → problema → consequência → solução
4. Contar camadas de profundidade: o closer fez follow-up nas respostas?
5. Identificar se o closer descobriu: dor principal, causa raiz, impacto emocional, custo da inação
6. Avaliar se lead verbalizou a dor com suas próprias palavras (vs. closer assumindo)
7. Verificar se closer fez perguntas de consequência (o que acontece se não resolver?)
8. Medir proporção closer/lead na fase de discovery (ideal: lead fala 70%+)
9. Identificar gaps: perguntas que deveriam ter sido feitas e não foram

## Frameworks Aplicados
- SPIN Selling (Situação, Problema, Implicação, Necessidade)
- NEPQ (Neuro-Emotional Persuasion Questioning)
- Consequence Questioning Deep Dive (Miner)
- Doctor Frame (diagnóstico antes de prescrição)

## Checklists de Qualidade
- Todas as perguntas do closer mapeadas e classificadas
- Progressão SPIN ou NEPQ avaliada
- Camadas de profundidade contadas (1 camada = superficial, 3+ = profundo)
- Lead verbalizou dor com próprias palavras (sim/não, com trecho)
- Gaps de discovery documentados

## Output Esperado
- Análise de discovery em `reports/analysis/CALL-ID-discovery`
- Mapa de perguntas classificadas por tipo (SPIN/NEPQ)
- Nota de profundidade (0-10) com justificativa

## Registry Atualizado
- `data/registries/calls-registry.yaml` (campo discovery_score)

## Critérios de Conclusão
- [ ] Perguntas mapeadas e classificadas (SPIN/NEPQ)
- [ ] Profundidade avaliada em camadas
- [ ] Dor verbalizada pelo lead identificada ou ausência documentada
- [ ] Gaps de discovery listados
- [ ] Nota atribuída com evidência textual
- [ ] Proporção closer/lead na discovery calculada
