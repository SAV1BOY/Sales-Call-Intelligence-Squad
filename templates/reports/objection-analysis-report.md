# Relatório de Análise de Objeções

> Relatório que analisa cada objeção levantada na call — tipo, causa raiz, resposta do closer e avaliação da eficácia.

## Quando Usar
Como componente da auditoria completa, ou isoladamente quando o foco é avaliar a capacidade de tratamento de objeções do closer.

## Estrutura

### Seção 1 — Resumo de Objeções
Visão consolidada das objeções na call.
**Formato**:
```
Call ID: [ID] | Closer: [nome] | Resultado: [vendeu/não vendeu]
Total de Objeções: [N]
Objeções Tratadas com Sucesso: [N] ([XX%])
Objeções Não Tratadas: [N] ([XX%])
Objeção Fatal (que custou o deal): [sim/não — qual]
Score do Bloco de Objeções: [X/15]
```

### Seção 2 — Análise Individual por Objeção
Cada objeção em detalhe.
**Formato**:
```
OBJEÇÃO #[N] — [MM:SS]
Fala do Lead: "[frase exata da objeção]"
Categoria: [Preço / Timing / Autoridade / Necessidade / Confiança / Concorrência]
Tipo: [Real / Cortina de Fumaça / Reflexo]

CAUSA RAIZ:
[Por que esta objeção surgiu — falha anterior na call ou condição legítima]
Momento de Origem: [MM:SS — onde o problema que gerou a objeção começou]

RESPOSTA DO CLOSER:
"[fala exata do closer ao tratar a objeção]"
Framework Usado: [nome da técnica — ex: Feel-Felt-Found, Isolamento, Reframe]
Tempo de Resposta: [imediata / pausa / hesitação]

AVALIAÇÃO:
- Técnica Correta: [Sim / Não / Parcialmente]
- Execução: [Alta / Média / Baixa]
- Resultado: [Objeção dissolvida / Parcialmente tratada / Não tratada / Piorou]
- O que Faltou: [componente não executado, se aplicável]

REWRITE SUGERIDO:
"[como deveria ter respondido]"
Framework Recomendado: [técnica ideal para esta objeção]
Justificativa: [por que este approach é melhor]
```

### Seção 3 — Padrão de Objeções
Análise de padrões recorrentes.
**Formato**:
```
Objeções Preveníveis: [objeções que não teriam surgido se X tivesse sido feito antes]
- [Objeção] — Prevenção: [o que evitaria — ex: "discovery mais profunda teria revelado urgência"]

Sequência de Objeções: [como as objeções se encadearam]
- [Objeção 1] não tratada → gerou [Objeção 2] → resultou em [desfecho]

Momento Crítico: [a objeção que definiu o resultado — e por quê]
```

### Seção 4 — Benchmarks
Comparação com padrões do time.
**Formato**:
```
| Métrica                          | Esta Call | Média do Time | Benchmark |
|----------------------------------|-----------|---------------|-----------|
| Total de objeções                | [N]       | [N]           | [N]       |
| Taxa de tratamento com sucesso   | [XX%]     | [XX%]         | [>70%]    |
| Tempo médio de resposta          | [Xs]      | [Xs]          | [<3s]     |
| Objeções preveníveis             | [N]       | [N]           | [<2]      |
```

## Exemplo
```
CALL-2026-0342 | Rafael | Não Vendeu
Objeções: 3 | Tratadas: 1 (33%) | Fatal: Sim — "Preciso pensar"

OBJEÇÃO #1 — 28:40
Lead: "Tá, mas isso é muito parecido com o que o [concorrente] oferece"
Categoria: Concorrência | Tipo: Real

CAUSA RAIZ: Apresentação não diferenciou o produto — foi genérica
RESPOSTA: "Ah, mas a gente é diferente porque..." — resposta vaga sem prova
Framework: Nenhum identificável
Avaliação: Execução Baixa — objeção parcialmente tratada

REWRITE: "Interessante você mencionar isso. O que exatamente você viu no [concorrente]? [pausa] Na prática, a diferença principal que nossos clientes relatam é [diferencial específico]. Por exemplo, o [cliente similar] tinha exatamente essa dúvida e depois de 90 dias..."
Framework: Isolamento + Prova Social Específica
```

## Agente Responsável
`audit-agent` — Analisa objeções como parte da auditoria.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Toda objeção com trecho e timestamp.
- `coaching-specificity-check.md` — Rewrites são específicos e contextualizados.
