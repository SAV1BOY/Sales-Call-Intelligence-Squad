# Transcript Normalization Quality

> Valida a qualidade da normalizacao e limpeza da transcricao.

## Objetivo

Garantir que a transcricao esteja limpa, segmentada corretamente, com timestamps precisos, speaker tags corretos e transicoes de fase marcadas.

## Quando Usar

Apos o processamento inicial de qualquer transcricao bruta antes de alimentar os agentes de analise.

## Checklist

### Limpeza do Texto
- [ ] Ruidos de audio removidos (uhm, ah, uh) sem perder sentido
- [ ] Repeticoes involuntarias eliminadas mantendo repeticoes intencionais
- [ ] Erros de transcricao automatica corrigidos (nomes proprios, termos tecnicos)
- [ ] Pontuacao adicionada para facilitar leitura
- [ ] Palavras cortadas ou incompletas sinalizadas com [inaudivel]

### Segmentacao
- [ ] Paragrafos separados por turno de fala
- [ ] Blocos longos quebrados em unidades semanticas de no maximo 4 frases
- [ ] Silencio significativo (acima de 3s) marcado com [pausa Xs]
- [ ] Sobreposicoes de fala marcadas com [sobreposicao]

### Timestamps
- [ ] Timestamp no inicio de cada turno de fala no formato [MM:SS]
- [ ] Timestamps verificados por amostragem (minimo 5 pontos checados)
- [ ] Desvio maximo de 3 segundos entre timestamp e audio real
- [ ] Inicio e fim da call com timestamp exato

### Speaker Tags
- [ ] Cada participante identificado com nome ou papel (Closer, Lead, Observador)
- [ ] Tags consistentes ao longo de toda a transcricao
- [ ] Nenhuma fala atribuida ao speaker errado (verificar por amostragem)
- [ ] Participantes adicionais (conjuge, socio) identificados quando presentes

### Transicoes de Fase
- [ ] Transicao rapport para discovery marcada
- [ ] Transicao discovery para pitch marcada
- [ ] Transicao pitch para objecoes marcada
- [ ] Transicao objecoes para fechamento marcada
- [ ] Momentos de retorno a fases anteriores sinalizados

## Criterios de Aprovacao

- **Aprovado**: Texto limpo, timestamps precisos, speakers corretos, transicoes marcadas
- **Revisao necessaria**: 1-2 speakers trocados ou timestamps com desvio acima de 5s
- **Reprovado**: Falta de speaker tags, timestamps ausentes ou transicoes nao marcadas

## Evidencia Requerida

Amostragem de 5 timestamps verificados contra o audio, lista de speakers identificados e marcacoes de transicao de fase com minuto.

## Agente Responsavel

Transcript Normalization Agent
