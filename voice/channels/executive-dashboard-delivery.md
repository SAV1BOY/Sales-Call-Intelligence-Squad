# Canal: Apresentação de Dashboard Executivo

## Princípio
O dashboard executivo traduz dados complexos de performance de vendas em decisões simples. O executivo (diretor, VP, C-Level) não quer entender como o score é calculado — quer saber se está vendendo mais ou menos, por que, e o que fazer. O dashboard deve ser lido e compreendido em 60 segundos sem explicação verbal.

## Estrutura do Dashboard

### Seção 1: KPIs Principais (Topo — Visão Imediata)
Quatro blocos visuais com semáforo (verde/amarelo/vermelho):

```
| KPI | Atual | Meta | Status |
|-----|-------|------|--------|
| Taxa de Fechamento | 22% | 25% | Amarelo |
| Receita Mensal | R$310K | R$350K | Amarelo |
| Score Médio de Call | 64/100 | 68/100 | Amarelo |
| Pipeline Qualificado | 52 opp | 40 opp | Verde |
```

**Critérios de semáforo**:
- Verde: dentro ou acima da meta
- Amarelo: 5-15% abaixo da meta
- Vermelho: mais de 15% abaixo da meta

### Seção 2: Tendências (Meio — Contexto Temporal)
Gráfico de linha com últimas 8-12 semanas mostrando:
- Taxa de fechamento (linha principal)
- Score médio de call (linha secundária)
- Volume de leads qualificados (barras)

**O que o executivo busca**: A tendência é mais importante que o número pontual. Subindo é bom. Estável é aceitável. Caindo exige ação.

### Seção 3: Performance por Closer (Meio — Detalhe Operacional)
Tabela ranqueada:

```
| Closer | Score | Taxa Close | Receita | Tendência |
|--------|-------|-----------|---------|-----------|
| Maria | 78 | 32% | R$96K | Subindo |
| João | 71 | 28% | R$84K | Estável |
| Pedro | 64 | 22% | R$66K | Subindo |
| Ana | 58 | 18% | R$42K | Caindo |
| Carlos | 45 | 12% | R$22K | Estável |
```

**O que o executivo busca**: Quem está performando, quem precisa de atenção, distribuição de receita.

### Seção 4: Diagnóstico e Ação (Base — Decisão)
```
Diagnóstico do mês:
- Gap principal: Discovery superficial (4.8/10, meta 7.0)
- Causa: Volume de leads subiu 35% sem aumento de equipe
- Impacto: Taxa de close caiu 3 pontos

Ação em andamento:
- Treinamento semanal de discovery (iniciado semana 2)
- Limite de 7 calls/dia por closer (implementado)
- Resultado parcial: score de discovery subiu de 4.8 para 5.3

Decisão necessária:
- Aprovação para contratação de 2 closers adicionais (ROI projetado: 4x em 90 dias)
```

## Regras de Design do Dashboard

### Hierarquia Visual
1. **Números grandes**: KPIs no topo — o olho vai primeiro para lá
2. **Cores claras**: Verde/amarelo/vermelho — decisão instantânea
3. **Gráficos limpos**: Máximo 3 linhas por gráfico — sem poluição
4. **Texto mínimo**: Legendas curtas, sem parágrafos no dashboard

### Princípio dos 60 Segundos
- O executivo deve entender a situação em 60 segundos olhando o dashboard
- Se precisar de explicação, o design falhou
- Teste: mostre para alguém que não conhece o contexto. Entendeu em 1 minuto?

### O Que Incluir
- Métricas com comparação (atual vs. meta vs. anterior)
- Tendência visual (gráfico de linha ou seta para cima/baixo)
- Semáforo de status (verde/amarelo/vermelho)
- Máximo 1 parágrafo de texto (diagnóstico + ação)

### O Que Excluir
- Detalhes de calls individuais (nível errado de granularidade)
- Mais de 6 KPIs (sobrecarga cognitiva)
- Métricas sem benchmark (números sem contexto não significam nada)
- Jargão de vendas não-universal ("NEPQ score", "Pain Funnel depth")

## Narrativa do Dashboard

### Se Está Bom
```
Resumo: Equipe acima da meta pelo 2o mês consecutivo. Score subiu 6 pontos.
Destaque: Treinamento de discovery mostrando resultado mensurável.
Atenção: Pipeline pode secar em 30 dias se volume de leads não mantiver.
Ação: Manter treinamento + monitorar pipeline de entrada.
```

### Se Está Regular
```
Resumo: Equipe próxima da meta, com tendência estável.
Diagnóstico: Discovery melhorando, close ainda inconsistente.
Ação: Intensificar coaching de close nas próximas 2 semanas.
Risco: Sem melhora em close, projeção de receita fica 10% abaixo.
```

### Se Está Ruim
```
Resumo: Equipe 20% abaixo da meta. Tendência de queda em 3 semanas.
Causa raiz: Mudança no perfil de leads + 2 closers em performance crítica.
Ação em andamento: Recalibração de qualificação + coaching intensivo.
Decisão necessária: Realocação ou substituição de closers abaixo do mínimo.
Projeção: Com ações implementadas, recuperação estimada em 4-6 semanas.
```

## Frequência de Apresentação
- **Semanal**: Dashboard atualizado automaticamente (visual, sem reunião)
- **Mensal**: Apresentação de 15 minutos com dashboard + diagnóstico + estratégia
- **Trimestral**: Revisão estratégica de 30 minutos com tendências e planejamento

## Perguntas que o Dashboard Deve Responder
1. Estamos batendo a meta? (KPIs)
2. A tendência é positiva ou negativa? (Gráficos)
3. Quem está performando e quem precisa de atenção? (Tabela de closers)
4. O que está causando os resultados? (Diagnóstico)
5. O que estamos fazendo a respeito? (Ação)
6. O que precisa de aprovação? (Decisão)
