# Brief de Review de Closer

> Documento que consolida o histórico, scores e áreas de foco de um closer para uma revisão de performance.

## Quando Usar
Antes de reuniões de review de performance, ao iniciar um novo ciclo de coaching, ou quando um gestor solicita análise aprofundada de um closer específico.

## Estrutura

### Seção 1 — Identificação do Closer
Dados cadastrais e contextuais do closer.
**Formato**:
```
Nome: [nome completo]
Time/Squad: [nome do time]
Gestor Direto: [nome do gestor]
Data de Início: [DD/MM/AAAA]
Tempo de Empresa: [X meses/anos]
Ofertas que Trabalha: [lista de produtos/serviços]
Ticket Médio: [R$ XX.XXX]
```

### Seção 2 — Histórico de Scores
Evolução quantitativa ao longo do tempo.
**Formato**:
```
| Período       | Score | Calls Auditadas | Conversão | Ticket Médio |
|---------------|-------|-----------------|-----------|--------------|
| [Semana/Mês]  | [XX]  | [N]             | [XX%]     | [R$ X.XXX]   |
| [Semana/Mês]  | [XX]  | [N]             | [XX%]     | [R$ X.XXX]   |
| [Semana/Mês]  | [XX]  | [N]             | [XX%]     | [R$ X.XXX]   |

Tendência: [Ascendente / Estável / Descendente]
Score Médio Geral: [XX/100]
Melhor Score: [XX — Call ID: XXXX]
Pior Score: [XX — Call ID: XXXX]
```

### Seção 3 — Performance por Bloco
Desempenho detalhado por competência do scorecard.
**Formato**:
```
| Bloco                  | Média | Tendência    | Classificação       |
|------------------------|-------|--------------|---------------------|
| [Ex: Rapport]          | [X.X] | [↑ / → / ↓] | [Forte/Médio/Fraco] |
| [Ex: Discovery]        | [X.X] | [↑ / → / ↓] | [Forte/Médio/Fraco] |
| [Ex: Apresentação]     | [X.X] | [↑ / → / ↓] | [Forte/Médio/Fraco] |
...

Blocos Fortes (top 3): [lista]
Blocos Fracos (bottom 3): [lista]
```

### Seção 4 — Coaching Anterior
Resumo dos ciclos de coaching já realizados.
**Formato**:
```
Último Ciclo: [datas — foco — resultado]
Ciclo Anterior: [datas — foco — resultado]
Pontos que Melhoraram: [lista com evidência]
Pontos que Não Melhoraram: [lista com hipótese de por quê]
Exercícios Realizados: [lista com status de conclusão]
```

### Seção 5 — Contexto Atual
Situação presente e circunstâncias relevantes.
**Formato**:
```
Volume de Calls Semanal: [N calls]
Mix de Leads: [% por origem ou temperatura]
Mudanças Recentes: [nova oferta, novo script, mudança de processo]
Observações do Gestor: [notas livres]
Foco Desejado para o Review: [área específica ou review geral]
```

## Exemplo
```
Nome: Juliana Costa
Time: Sales — High Ticket
Gestor: Marcos Oliveira
Data de Início: 01/06/2025
Ofertas: Mentoria Premium, Aceleração 90D
Ticket Médio: R$ 15.000

| Período  | Score | Calls | Conversão | Ticket Médio |
|----------|-------|-------|-----------|--------------|
| Sem 10   | 74    | 4     | 25%       | R$ 14.500    |
| Sem 11   | 71    | 5     | 20%       | R$ 13.000    |
| Sem 12   | 78    | 4     | 50%       | R$ 16.200    |

Tendência: Ascendente
Blocos Fortes: Rapport, Apresentação, Follow-up
Blocos Fracos: Discovery, Ancoragem de Preço, Tratamento de Objeção
Foco do Review: Evolução em discovery após coaching
```

## Agente Responsável
`orchestrator-agent` — Compila o brief a partir do histórico do closer.

## Checklists de Qualidade
- `coaching-progression-check.md` — Valida se os dados de evolução estão completos e confiáveis.
