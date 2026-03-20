# Win-Loss Analysis Quality

> Valida a qualidade da analise de padroes de vitoria e derrota.

## Objetivo

Garantir que a analise identifica padroes replicaveis de sucesso, variaveis correlacionadas com resultado e utiliza amostra suficiente para conclusoes validas.

## Quando Usar

Apos analise agregada de multiplas calls (minimo 10) para identificacao de padroes de win/loss.

## Checklist

### Padroes Replicaveis
- [ ] Minimo de 3 padroes de vitoria identificados com frequencia de ocorrencia
- [ ] Minimo de 3 padroes de derrota identificados com frequencia de ocorrencia
- [ ] Cada padrao tem descricao clara e exemplo concreto de call
- [ ] Padroes diferenciados por tipo de lead, produto e closer
- [ ] Padroes priorizados por impacto no resultado

### Variaveis Correlacionadas
- [ ] Variaveis quantitativas correlacionadas (talk ratio, duracao, n. de perguntas)
- [ ] Variaveis qualitativas correlacionadas (tipo de rapport, profundidade de discovery)
- [ ] Correlacao nao confundida com causalidade (diferenciacao explicita)
- [ ] Variaveis com maior poder preditivo destacadas

### Amostra Suficiente
- [ ] Numero total de calls analisadas declarado
- [ ] Proporcao win/loss da amostra declarada
- [ ] Amostra cobre diferentes closers, produtos e periodos
- [ ] Limitacoes da amostra explicitadas
- [ ] Confianca das conclusoes declarada (alta, media, baixa)

### Insights Acionaveis
- [ ] Cada padrao tem recomendacao pratica associada
- [ ] Recomendacoes priorizadas por facilidade de implementacao e impacto
- [ ] Playbook de boas praticas atualizado com novos padroes
- [ ] Anti-padroes (o que evitar) documentados

## Criterios de Aprovacao

- **Aprovado**: Minimo 3 padroes win e 3 loss com evidencia, amostra declarada, insights acionaveis
- **Revisao necessaria**: Padroes identificados mas sem amostra suficiente ou sem recomendacoes
- **Reprovado**: Conclusoes sem evidencia, amostra nao declarada ou padroes genericos

## Evidencia Requerida

Lista de padroes com frequencia, exemplos de calls, variaveis correlacionadas, tamanho e composicao da amostra, e recomendacoes priorizadas.

## Agente Responsavel

Win-Loss Analysis Agent
