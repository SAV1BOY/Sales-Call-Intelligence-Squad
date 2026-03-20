# Atualizar Biblioteca de Objeções

> Atualizar biblioteca de objeções com novas objeções encontradas, melhores respostas e taxas de resolução.

## Objetivo
Manter a biblioteca de objeções viva e atualizada — cada call auditada pode revelar novas objeções ou melhores respostas, criando vantagem competitiva cumulativa.

## Trigger
- Nova objeção identificada em auditoria (não presente na biblioteca)
- Resposta com eficácia superior encontrada para objeção existente
- Review semanal de qualidade

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Objection Specialist | Curadoria e atualização da biblioteca |
| Win-Loss Miner | Identifica respostas de alto impacto em calls ganhas |
| Call Auditor | Fornece objeções classificadas das auditorias |
| Sales Chief | Aprova inclusão de novas respostas recomendadas |

## Inputs
- Análises de objeções das últimas auditorias
- Objeções classificadas: tipo, causa raiz, resposta, eficácia
- Biblioteca atual em `data/libraries/objections-library.yaml`
- Win patterns (respostas que funcionaram em calls ganhas)

## Processo
1. Coletar todas as objeções novas das auditorias do período
2. Verificar se já existem na biblioteca (evitar duplicatas)
3. Para objeções novas: classificar tipo, definir causa raiz, documentar contexto
4. Para objeções existentes: comparar novas respostas com as catalogadas
5. Atualizar taxa de resolução por resposta (quantas vezes funcionou)
6. Promover respostas com alta taxa de resolução para "resposta recomendada"
7. Rebaixar respostas com baixa eficácia comprovada
8. Adicionar variações de objeção (mesma essência, formulação diferente)
9. Vincular objeções a causas preventivas (o que evitaria que surgissem)
10. Versionar a biblioteca com data de atualização

## Frameworks Aplicados
- Objection Root Cause Framework
- Hormozi Price-to-Value Gap (para objeções de preço)
- Straight Line: Looping (para técnicas de resposta)

## Checklists de Qualidade
- Novas objeções têm tipo, causa raiz e contexto documentados
- Taxa de resolução atualizada com dados reais
- Resposta recomendada baseada em evidência (não em teoria)
- Duplicatas verificadas antes de inclusão
- Biblioteca versionada com data

## Output Esperado
- Biblioteca atualizada em `data/libraries/objections-library.yaml`
- Log de alterações: novas inclusões, promoções, rebaixamentos
- Estatísticas: total de objeções, taxa média de resolução

## Registry Atualizado
- `data/libraries/objections-library.yaml`
- `data/registries/intelligence-registry.yaml`

## Critérios de Conclusão
- [ ] Novas objeções incluídas com classificação completa
- [ ] Taxas de resolução atualizadas
- [ ] Respostas recomendadas revisadas
- [ ] Duplicatas eliminadas
- [ ] Biblioteca versionada
- [ ] Log de alterações documentado
