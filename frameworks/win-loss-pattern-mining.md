# Win-Loss Pattern Mining — Mineração de Padrões Ganho/Perda

> Comparar sistematicamente calls ganhas vs. perdidas para identificar variáveis que correlacionam com conversão.

## Origem

Derivado de Win-Loss Analysis, prática comum em B2B enterprise sales e formalizada por empresas como Clozd e Gartner. Adaptado para high-ticket com foco em padrões comportamentais do closer, não apenas razões declaradas pelo lead.

## Conceito Central

Todo time de vendas tem padrões invisíveis. Calls que fecham compartilham características que calls perdidas não têm — e vice-versa. O Win-Loss Pattern Mining identifica essas variáveis estatisticamente.

Não é sobre "por que ESSA call foi perdida", mas sobre "o que as calls ganhas têm em comum que as perdidas não têm". A diferença é individual vs. sistêmico.

Variáveis analisadas:
- **Comportamentais:** Talk ratio, quantidade de perguntas, uso de frameworks
- **Estruturais:** Duração da call, duração de cada fase, ordem dos blocos
- **Emocionais:** Nível de ativação emocional, consequence questioning usado
- **Processuais:** First Pact feito, Second Pact feito, objeção isolada

## Fase da Call Onde se Aplica

**Análise macro (múltiplas calls)**. Este framework não analisa uma call — analisa dezenas ou centenas para encontrar padrões. É a camada analítica mais estratégica do sistema.

## Como Funciona

### Passo 1 — Coleta de Dados
Para cada call (ganha e perdida), registrar:
- Score total e por bloco
- Talk ratio por fase
- Frameworks executados (sim/não para cada)
- Duração total e por fase
- Tipo de objeção principal
- Perfil do lead (ticket, segmento, nível de consciência)

### Passo 2 — Segmentação
Dividir em dois grupos: GANHAS e PERDIDAS. Calcular médias de cada variável para cada grupo.

### Passo 3 — Comparação
Identificar variáveis com maior diferença entre os grupos.

**Exemplo de findings:**
- Calls ganhas: First Pact feito em 95% → Perdidas: 60%
- Calls ganhas: Talk ratio médio 31% → Perdidas: 52%
- Calls ganhas: Consequence Questioning em 88% → Perdidas: 35%
- Calls ganhas: Objeção isolada em 90% → Perdidas: 40%
- Calls ganhas: Duração média 42 min → Perdidas: 28 min

### Passo 4 — Hipóteses Causais
Para cada correlação forte, formular hipótese causal:
- "Calls com First Pact fecham mais porque o frame de liderança é estabelecido desde o início"
- "Calls com talk ratio baixo fecham mais porque o lead revelou mais dores utilizáveis"

### Passo 5 — Ação
Transformar findings em treinamento:
- "Todo closer deve executar First Pact em 100% das calls"
- "Meta de talk ratio: máximo 35% no discovery"

## Aplicação Prática na Call

O Win-Loss Mining não se aplica NA call — se aplica ENTRE calls. O output alimenta:
1. Treinamentos focados nas variáveis mais impactantes
2. Scorecards com pesos ajustados baseados em dados reais
3. Playbooks atualizados com as práticas que mais convertem
4. Metas individuais para closers baseadas em gaps específicos

## Sinais de Boa Execução

- Padrões claros emergem da análise — variáveis com forte correlação identificadas
- Treinamentos são direcionados por dados — não por intuição
- Taxa de conversão do time sobe após implementar findings — dados se traduzem em resultado
- Closers entendem POR QUE certas práticas são exigidas — base em evidência

## Sinais de Falha

- Análise com amostra pequena — menos de 20 calls por grupo não é estatisticamente significativo
- Correlação confundida com causalidade — "calls longas fecham mais" não significa "fazer calls longas"
- Findings não viram ação — análise fica em relatório, nada muda
- Variáveis irrelevantes analisadas — o horário da call provavelmente não importa

## Critérios de Avaliação no Scorecard

| Critério | Peso | Evidência esperada |
|----------|------|-------------------|
| Amostra suficiente (20+ por grupo) | 3 | Volume de calls adequado |
| Variáveis relevantes analisadas | 3 | Foco em comportamento, não em fatores aleatórios |
| Correlações fortes identificadas | 3 | Diferença significativa entre ganhas e perdidas |
| Hipóteses causais formuladas | 2 | Explicação de POR QUE a correlação existe |
| Ações concretas geradas | 3 | Findings traduzidos em treinamento/processo |

## Frameworks Complementares

- **Call Scoring Model** — Fornece dados padronizados para mineração
- **Minute-by-Minute Analysis** — Dados granulares por call
- **Post-Call Learning Loop** — O mining alimenta o loop de aprendizado
- **RalphLoop Sales** — Ciclo de melhoria que usa findings como input

## Exemplo de Evidência na Transcrição

```
RELATÓRIO DE PATTERN MINING — Janeiro 2024
Amostra: 47 calls ganhas / 63 calls perdidas

Variável com maior impacto: CONSEQUENCE QUESTIONING
- Calls com CQ: 72% conversão
- Calls sem CQ: 18% conversão
- Diferença: 54 pontos percentuais

Variável #2: OBJECTION ISOLATION
- Calls com isolamento: 65% conversão
- Calls sem isolamento: 22% conversão
- Diferença: 43 pontos percentuais

Variável #3: TALK RATIO (discovery)
- Calls com TR < 30%: 61% conversão
- Calls com TR > 45%: 15% conversão

→ Ação: Treinamento intensivo em Consequence Questioning para closers com taxa < 50%. Meta: 100% das calls com CQ no discovery.
```

## Erros Comuns

1. **Amostra insuficiente** — Analisar 5 calls ganhas e 5 perdidas não gera padrões confiáveis. Mínimo 20 por grupo.
2. **Viés de confirmação** — Procurar apenas variáveis que confirmam o que já se acredita. A análise deve ser aberta.
3. **Ignorar variáveis de lead** — O perfil do lead importa. Comparar calls com leads qualificados vs. desqualificados distorce a análise.
4. **Não atualizar** — Padrões mudam. O mining deve ser refeito mensalmente ou trimestralmente.
5. **Correlação como verdade absoluta** — "First Pact correlaciona com vitória" não prova causalidade. Pode haver variável confundidora (closers melhores fazem First Pact E fecham mais).

## Usado Em

- **Tasks**: extract-win-patterns, extract-loss-patterns
- **Workflows**: monthly (extração de padrões de vitória e perda)
- **Config routing**: `extract-win-patterns.frameworks`, `extract-loss-patterns.frameworks`
