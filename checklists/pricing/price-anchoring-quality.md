# Price Anchoring Quality

> Valida a efetividade da ancoragem de preco na call.

## Objetivo

Garantir que a ancoragem de preco foi utilizada estrategicamente para fazer o preco real parecer acessivel em comparacao.

## Quando Usar

Apos a analise da apresentacao de preco e antes de pontuar pricing no scorecard.

## Checklist

### Ancora Estabelecida
- [ ] Preco ancora apresentado antes do preco real
- [ ] Ancora e um valor significativamente maior que o preco pedido
- [ ] Ancora e crivel e justificavel (nao um numero inventado)
- [ ] Ancora pode ser o valor total do empilhamento ou preco de tabela
- [ ] Momento da ancora registrado com timestamp

### Tecnica de Ancoragem
- [ ] Preco de mercado ou concorrente usado como ancora (se aplicavel)
- [ ] Custo de resolver o problema de outra forma usado como ancora
- [ ] Custo de nao resolver o problema usado como ancora
- [ ] Investimento anterior do lead em solucoes que falharam mencionado
- [ ] Pelo menos 2 tipos de ancora utilizados

### Contraste Efetivo
- [ ] Diferenca entre ancora e preco real e impactante
- [ ] Lead percebeu o contraste e demonstrou surpresa ou alivio
- [ ] Closer fez pausa entre a ancora e o preco real
- [ ] Preco real apresentado como "investimento" e nao como "custo"
- [ ] Lead sentiu que esta fazendo um bom negocio

### Justificativa do Desconto da Ancora
- [ ] Motivo do preco ser menor que a ancora explicado
- [ ] Justificativa e crivel (condicao especial, lancamento, lote)
- [ ] Escassez ou temporalidade da condicao mencionada (se genuina)
- [ ] Lead nao ficou desconfiado do desconto

### Resultado
- [ ] Objecao de preco foi menor por causa da ancoragem
- [ ] Lead referenciou a ancora ao avaliar o preco ("comparado com X, e justo")
- [ ] Ancoragem contribuiu para o fechamento avaliado
- [ ] Se ancoragem falhou, motivo identificado

## Criterios de Aprovacao

- **Aprovado**: Ancora crivel, contraste claro, lead percebeu valor, contribuiu para fechamento
- **Revisao necessaria**: Ancora usada mas fraca ou lead nao percebeu o contraste
- **Reprovado**: Sem ancoragem, ancora incrivel ou lead ficou desconfiado

## Evidencia Requerida

Valor ancora com timestamp, preco real, reacao do lead, tipo de ancora e avaliacao de efetividade.

## Agente Responsavel

Pricing Analysis Agent
