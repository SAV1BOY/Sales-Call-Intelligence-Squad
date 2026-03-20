# Root Cause Analysis Quality

> Valida a qualidade da analise de causa raiz da call.

## Objetivo

Garantir que a causa raiz do resultado (ganho ou perda) esta corretamente identificada, diferenciando entre erro do closer, problema do lead, oferta inadequada, pricing ou handoff.

## Quando Usar

Apos a identificacao das causas raiz e antes de gerar o coaching plan e as recomendacoes.

## Checklist

### Identificacao da Causa Raiz
- [ ] Causa raiz principal declarada de forma explicita e objetiva
- [ ] Causa raiz classificada em categoria (closer, lead, oferta, pricing, handoff)
- [ ] Maximo de 3 causas raiz listadas em ordem de impacto
- [ ] Cada causa raiz acompanhada de trecho da transcricao com timestamp
- [ ] Diferenciar sintoma (o que apareceu) da causa real (o que provocou)

### Analise do Closer
- [ ] Erros tecnicos do closer identificados (perguntas fracas, pitch generico, etc.)
- [ ] Erros comportamentais identificados (nervosismo, pressa, falta de escuta)
- [ ] Momentos onde o closer acertou tambem documentados
- [ ] Padrao recorrente identificado quando ha historico de calls

### Analise do Lead
- [ ] Perfil do lead avaliado (decisor, influenciador, pesquisador)
- [ ] Nivel de qualificacao real do lead avaliado
- [ ] Sinais de compra e sinais de desinteresse mapeados com minuto
- [ ] Lead estava no momento certo de compra ou foi abordado cedo/tarde

### Analise da Oferta e Pricing
- [ ] Oferta era adequada para o perfil e dor do lead
- [ ] Pricing estava dentro da faixa de aceitacao do lead
- [ ] Concessoes feitas foram necessarias ou desnecessarias
- [ ] Valor percebido pelo lead era suficiente antes do preco

### Analise do Handoff
- [ ] Informacoes do SDR para o closer estavam completas
- [ ] Expectativas do lead alinhadas com o que foi prometido no agendamento
- [ ] Qualificacao previa estava precisa ou houve surpresas na call

## Criterios de Aprovacao

- **Aprovado**: Causa raiz clara com evidencia, categoria definida, analise multicamada
- **Revisao necessaria**: Causa raiz identificada mas sem evidencia suficiente
- **Reprovado**: Causa raiz ausente, confusao entre sintoma e causa, ou sem trecho de evidencia

## Evidencia Requerida

Declaracao da causa raiz, categoria, trechos da transcricao com timestamp, e diferenciacao explicita entre sintoma e causa real.

## Agente Responsavel

Root Cause Analysis Agent

---

## Scoring Rubric

Cada item acima deve ser pontuado de 0 a 5:

| Score | Significado |
|-------|------------|
| 0 | Ausente — item nao abordado |
| 1 | Mencionado sem evidencia |
| 2 | Presente com evidencia fraca ou generica |
| 3 | Presente com evidencia especifica (trecho + timestamp) |
| 4 | Forte — evidencia + analise + recomendacao |
| 5 | Exemplar — material para swipe file |

### Thresholds
- **Pass minimo**: media >= 3.0 (todos os items)
- **GOOD**: media >= 3.5
- **GOLD**: media >= 4.5
- **Rework trigger**: qualquer item com score 0 OU media < 2.5
- **Aprovacao**: QA Guardian valida; Sales Chief aprova output final
