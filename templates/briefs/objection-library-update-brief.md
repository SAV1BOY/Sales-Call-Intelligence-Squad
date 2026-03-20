# Brief para Atualização da Biblioteca de Objeções

> Documento que consolida novas objeções identificadas nas calls para atualizar a biblioteca central de objeções do squad.

## Quando Usar
Quando novas objeções são identificadas com frequência suficiente para merecer inclusão na biblioteca, ou quando objeções existentes precisam de atualização nas respostas recomendadas. Cadência sugerida: quinzenal.

## Estrutura

### Seção 1 — Período e Escopo
Dados do período analisado.
**Formato**:
```
Período de Análise: [DD/MM a DD/MM/AAAA]
Total de Calls Analisadas: [N]
Total de Objeções Identificadas: [N]
Novas Objeções (não estão na biblioteca): [N]
Objeções Atualizadas (resposta melhorada): [N]
```

### Seção 2 — Novas Objeções para Inclusão
Objeções que precisam entrar na biblioteca.
**Formato**:
```
OBJEÇÃO NOVA #1:
- Frase Literal: "[exatamente como o lead falou]"
- Variações: ["outras formas que leads usaram para dizer o mesmo"]
- Categoria: [preço / timing / autoridade / necessidade / confiança / concorrência]
- Frequência: [apareceu em X de Y calls (XX%)]
- Momento Típico: [em que fase da call surge — discovery / apresentação / pricing / fechamento]
- Causa Raiz Identificada: [por que essa objeção surge]
- Resposta Recomendada: [script sugerido com framework de referência]
- Evidência de Eficácia: [Call ID — Minuto — closer que tratou bem]
- Calls de Referência: [Call IDs onde apareceu]
```

### Seção 3 — Objeções Existentes para Atualização
Respostas que precisam ser revisadas.
**Formato**:
```
OBJEÇÃO EXISTENTE — ATUALIZAÇÃO:
- Objeção: "[frase da objeção já catalogada]"
- Resposta Atual na Biblioteca: [script atual]
- Por que Atualizar: [não está funcionando / contexto mudou / resposta melhor encontrada]
- Nova Resposta Recomendada: [novo script]
- Evidência: [Call ID — Minuto — resultado com nova abordagem]
- Taxa de Sucesso Atual vs. Nova: [XX% → YY%]
```

### Seção 4 — Objeções para Remoção/Arquivo
Objeções que não aparecem mais.
**Formato**:
```
OBJEÇÃO PARA ARQUIVO:
- Objeção: "[frase]"
- Última Ocorrência: [DD/MM/AAAA]
- Motivo da Remoção: [oferta mudou / mercado mudou / não é mais relevante]
```

### Seção 5 — Análise de Tendências
Padrões nas objeções ao longo do tempo.
**Formato**:
```
Objeções em Alta (frequência crescente): [lista]
Objeções em Baixa (frequência decrescente): [lista]
Nova Categoria Emergente: [se houver]
Hipótese: [por que o padrão está mudando]
```

## Exemplo
```
Período: 01/03 a 14/03/2026 | 42 calls | 67 objeções | 3 novas | 2 atualizações

OBJEÇÃO NOVA #1:
- Frase: "Já tentei algo parecido e não funcionou"
- Categoria: Confiança
- Frequência: 8 de 42 calls (19%)
- Momento: Após apresentação do método
- Causa Raiz: Concorrente entregou mal e queimou o mercado
- Resposta: "Entendo — e o que exatamente não funcionou? [pausa] Na maioria dos casos que vejo, o problema foi [X], e a diferença aqui é [Y]..."
- Evidência: CALL-0331 — 18:45 — Juliana tratou com excelência

Tendência: Objeções de confiança subiram 40% — possível impacto de concorrente novo no mercado
```

## Agente Responsável
`audit-agent` — Identifica objeções durante auditoria. `coaching-agent` — Valida e sugere respostas.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Garante que toda objeção tem evidência.
- `cross-squad-copy-handoff-quality.md` — Garante que insights são acionáveis para o Copy Squad.
