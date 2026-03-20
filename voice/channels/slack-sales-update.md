# Canal: Update de Vendas no Slack

## Princípio
O Slack é canal de comunicação rápida. Updates de vendas no Slack devem ser escaneáveis em 10 segundos, memoráveis em 30 e acionáveis em 1 minuto. Ninguém lê parágrafos no Slack. Formato curto, visual, com ação clara. Se precisa de mais contexto, linkar para documento externo.

## Formato Padrão de Update

### Update Diário de Performance
```
Resumo do dia — [data]

Calls realizadas: 32
Fechamentos: 7
Taxa: 21.8%
Ticket médio: R$8.500
Receita do dia: R$59.500

Destaque: [Nome] fechou deal de R$25K com discovery de Nível 5
Atenção: Taxa de show caiu para 68% (meta: 80%)

Ação: Operações — revisar confirmação de calls para amanhã
```

### Update Semanal de Score
```
Scorecard da semana — Semana [X]

Score médio da equipe: 62/100 (anterior: 59)

Top 3:
1. [Nome] — 78/100 (+5)
2. [Nome] — 74/100 (+2)
3. [Nome] — 71/100 (=)

Maior evolução: [Nome] — de 48 para 56 (+8)
Foco da semana: Discovery (4.8/10 abaixo do benchmark de 7)

Ação: Sessão de treino quinta 10h — tema: perguntas de implicação
```

### Alerta de Padrão
```
Alerta — Padrão identificado

O quê: Objeção "preciso pensar" em 45% das calls esta semana
Por quê: Discovery média de 6 min (benchmark: 15 min)
Impacto: Taxa de close caiu de 25% para 18%
Ação: Treino emergencial de discovery — amanhã 9h

cc: @gestor @equipe
```

### Celebração de Resultado
```
Fechamento do mês

Meta: R$350K
Realizado: R$382K (109%)

Destaques:
- [Nome]: R$98K (melhor mês)
- Equipe: score médio subiu de 56 para 64
- Discovery: de Nível 2.3 médio para Nível 3.1

Parabéns a todos! Briefing completo amanhã.
```

## Regras de Formatação no Slack

### Usar
- Negrito para dados-chave: **22% taxa de close**
- Emojis com moderação para escaneabilidade visual
- Listas com bullet points ou números
- Seções curtas com quebra de linha
- Menções (@nome) quando ação é necessária
- Threads para discussão (não poluir canal principal)

### Evitar
- Parágrafos longos (ninguém lê)
- Mais de 3 emojis por mensagem (poluição visual)
- Update sem ação (informar por informar)
- Dados sem comparação ("32 calls" — é bom ou ruim?)
- Tom negativo sem solução ("resultados péssimos essa semana")

## Tipos de Mensagem por Situação

### Boa Notícia
```
Meta batida! Equipe fechou R$382K (109% da meta)

Top closer: [Nome] com R$98K
Maior salto: [Nome] subiu 12 pontos no score

Detalhes no relatório semanal. Bom trabalho!
```
**Tom**: Celebratório, reconhecimento específico, breve.

### Notícia Neutra
```
Update semanal — Semana 12

Taxa: 22% (meta: 25%)
Pipeline: saudável, 45 opp abertas
Score: 61/100 (estável)

Foco: discovery precisa subir 2 pontos. Treino quinta.
```
**Tom**: Factual, sem drama, com direção.

### Notícia Negativa
```
Atenção — Taxa de close em queda

Última semana: 16% (meta: 25%)
Causa identificada: leads de novo canal com qualidade inferior
Score de qualificação: 3.2/10

Ação imediata: reunião amanhã 9h com Marketing + Sales para alinhar qualificação.
```
**Tom**: Direto, sem pânico, com causa e ação. Nunca culpar pessoas no canal público.

### Insight Cross-Squad
```
Para: #marketing

Insight do Sales Intelligence:
35% dos leads de [campanha X] não sabem o que oferecemos na call. 
Taxa de close desse canal: 12% (vs. 26% orgânico).

Sugestão: revisar copy da landing page.
Dados completos: [link para doc]
```
**Tom**: Colaborativo, baseado em dados, com sugestão clara.

## Frequência Recomendada
| Tipo | Frequência | Canal |
|------|-----------|-------|
| Update diário | Todo dia útil, 18h | #sales-daily |
| Scorecard semanal | Segunda-feira, 10h | #sales-performance |
| Alerta de padrão | Quando identificado | #sales-alerts |
| Celebração | Quando meta é batida | #sales-wins |
| Insight cross-squad | 1-2x por semana | Canal do squad receptor |

## O Que NUNCA Postar no Slack
- Feedback negativo individual (fazer em privado)
- Score de closer específico em canal público (apenas ranking positivo)
- Críticas à qualidade de leads sem dados (gera conflito)
- Comparações depreciativas entre closers
- Informação confidencial de deals ou prospects
