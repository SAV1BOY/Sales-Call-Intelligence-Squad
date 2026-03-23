# Minute-by-Minute Analysis Framework

> Analisar a call minuto a minuto comparando o que aconteceu com o que deveria ter acontecido, identificando gaps de execução.

## Origem

Framework de análise de performance derivado de metodologias de coaching esportivo (análise de vídeo frame-by-frame) adaptado para sales coaching. Utilizado por organizações de sales enablement e treinadores de closers de high-ticket para feedback granular e acionável.

## Conceito Central

A análise minuto a minuto transforma uma call de 45 minutos em 45 micro-momentos avaliáveis. Para cada minuto (ou bloco de 2-3 minutos), o analista registra três coisas:

1. **O que aconteceu** — Transcrição/resumo factual do momento
2. **O que deveria ter acontecido** — Baseado nos frameworks e melhores práticas
3. **Gap** — A diferença entre o real e o ideal, com diagnóstico da causa

Isso elimina feedback vago ("a call foi boa") e substitui por feedback preciso ("no minuto 12:30, quando o lead disse X, o closer deveria ter feito Y, mas fez Z").

## Fase da Call Onde se Aplica

**Pós-call (análise)**. Este não é um framework de execução — é um framework de análise e coaching. Aplica-se a QUALQUER call, ganha ou perdida, para extrair aprendizados.

## Como Funciona

### Passo 1 — Segmentação Temporal
Dividir a call em blocos temporais alinhados às fases da taxonomia:

| Bloco | Fase | Minutos |
|-------|------|---------|
| 1 | Abertura + Frame | 0:00–2:00 |
| 2 | Discovery Inicial | 2:00–8:00 |
| 3 | Discovery Profundo | 8:00–15:00 |
| 4 | Transição + Pitch | 15:00–25:00 |
| 5 | Preço + Ancoragem | 25:00–30:00 |
| 6 | Objeções + Fechamento | 30:00–45:00 |

### Passo 2 — Análise por Bloco
Para cada bloco, registrar:
- **Eventos-chave:** O que o closer disse/perguntou. O que o lead respondeu.
- **Framework esperado:** Qual framework deveria estar ativo nesse momento.
- **Execução real vs. ideal:** Aderência ao framework.
- **Impacto:** Como a execução (ou falha) afetou o resto da call.

### Passo 3 — Identificação de Momentos Críticos
Nem todo minuto é igual. Identificar os 3-5 momentos que mais impactaram o resultado:
- Momento de perda de frame
- Momento de ativação emocional (ou falta dela)
- Momento de transição mal executada
- Momento de objeção mal tratada
- Momento de fechamento (ou tentativa)

### Passo 4 — Rewrite dos Momentos Críticos
Para cada momento crítico, escrever o que o closer DEVERIA ter dito/feito. Isso alimenta o framework "Rewrite the Moment".

### Passo 5 — Score e Recomendações
Atribuir score ao bloco e gerar 2-3 recomendações acionáveis por bloco.

## Aplicação Prática na Call

O analista (IA ou humano) recebe a transcrição e/ou áudio e executa a análise sistemática. O output é um relatório com:

1. Timeline visual com marcações de momentos-chave
2. Score por bloco (0-10)
3. Momentos críticos destacados com before/after
4. 3-5 recomendações prioritárias para a próxima call
5. Padrões recorrentes (se comparado com calls anteriores)

## Sinais de Boa Execução

- Análise identifica momentos que o closer não percebeu — valor do olhar externo
- Recomendações são específicas e acionáveis — "no minuto 12, fazer pergunta de implicação"
- Closer melhora nas próximas calls nos pontos identificados — ciclo de melhoria ativo
- Padrões entre calls são identificados — "você sempre perde o frame no minuto 5-8"

## Sinais de Falha

- Análise vaga — "a call foi mais ou menos" sem momentos específicos
- Excesso de crítica sem rewrite — apontar erros sem mostrar alternativa
- Não priorizar — listar 30 problemas em vez de focar nos 3-5 mais impactantes
- Análise sem contexto — ignorar que o lead era difícil ou que havia problemas técnicos

## Critérios de Avaliação no Scorecard

| Critério | Peso | Evidência esperada |
|----------|------|-------------------|
| Segmentação temporal clara | 2 | Call dividida em blocos por fase |
| Momentos críticos identificados | 4 | 3-5 momentos de maior impacto destacados |
| Gap real vs. ideal documentado | 3 | Para cada momento, o que fez vs. deveria fazer |
| Recomendações acionáveis | 3 | 3-5 ações específicas para próxima call |
| Padrões recorrentes identificados | 2 | Comparação com calls anteriores |

## Frameworks Complementares

- **Rewrite the Moment** — Reescreve os momentos críticos identificados
- **Call Scoring Model** — O score por bloco alimenta o score geral
- **Win-Loss Pattern Mining** — A análise minuto a minuto alimenta a mineração de padrões
- **Talk Ratio Analysis** — Análise de proporção de fala por bloco

## Exemplo de Evidência na Transcrição

```
[12:30] Closer: "Legal, e vocês faturam quanto?"
→ Análise: Pergunta de Situação (SPIN - S) feita no minuto 12, quando o closer já deveria estar em Implicação (SPIN - I). O discovery ficou preso em perguntas de situação por 10 minutos. Gap: faltou transição para perguntas de problema e implicação.
→ Rewrite: "Você mencionou que o faturamento oscila. O que acontece nos meses ruins? Como isso afeta suas decisões?"
→ Impacto: Discovery superficial resultou em pitch desconectado e objeção de preço no minuto 30.
```

## Erros Comuns

1. **Análise genérica** — "O discovery poderia ser melhor" sem dizer QUANDO e COMO. A análise precisa de timestamps.
2. **Foco só nos erros** — Ignorar o que o closer fez bem. A análise deve incluir momentos de excelência para reforço positivo.
3. **Recomendações vagas** — "Melhorar o discovery" não é acionável. "No minuto 5, após identificar a dor, fazer 2 perguntas de implicação antes de avançar" é acionável.
4. **Não comparar com padrões** — Analisar uma call isolada perde o poder de identificar tendências. A análise deve comparar com calls anteriores.
5. **Excesso de detalhes** — Analisar cada segundo de uma call de 45 minutos gera relatório de 20 páginas que ninguém lê. Focar nos 3-5 momentos mais impactantes.

## Usado Em

- **Tasks**: normalize-and-segment, full-call-audit
- **Workflows**: per_call (ingestão e auditoria completa)
- **Config routing**: `normalize-and-segment.frameworks`, `full-call-audit.frameworks`
