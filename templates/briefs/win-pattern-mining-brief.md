# Brief para Mineração de Padrões de Vitória

> Documento de entrada para análise de calls ganhas, buscando padrões replicáveis de sucesso.

## Quando Usar
Quando o squad precisa identificar o que os melhores closers fazem de diferente, ao construir playbooks de best practices, ou ao preparar treinamentos baseados em evidência.

## Estrutura

### Seção 1 — Escopo da Mineração
Definição do que será analisado.
**Formato**:
```
Período: [DD/MM a DD/MM/AAAA]
Total de Calls Ganhas no Período: [N]
Calls Selecionadas para Análise: [N] (critério: [score acima de X / ticket acima de Y / etc.])
Closers Incluídos: [nomes]
Oferta(s): [produto/serviço analisado]
Pergunta Central: [ex: "O que os top closers fazem nos primeiros 5 minutos?"]
```

### Seção 2 — Critérios de Seleção
Como as calls foram escolhidas.
**Formato**:
```
Critério Primário: [ex: score acima de 80 + venda fechada]
Critério Secundário: [ex: ticket acima da média]
Exclusões: [ex: calls com lead pré-aquecido por indicação]
Calls Selecionadas:
| Call ID       | Closer   | Score | Ticket     | Duração | Observação     |
|---------------|----------|-------|------------|---------|----------------|
| [CALL-XXXX]   | [Nome]   | [XX]  | [R$ X.XXX] | [MM:SS] | [nota breve]   |
```

### Seção 3 — Hipóteses a Investigar
O que procurar nas calls.
**Formato**:
```
Hipótese 1: [ex: "Closers que vendem fazem mais perguntas de consequência na discovery"]
Como Verificar: [contar perguntas de consequência e comparar com calls perdidas]

Hipótese 2: [ex: "Ancoragem de preço com comparação externa aumenta conversão"]
Como Verificar: [identificar técnica de ancoragem usada e correlacionar com resultado]

Hipótese 3: [ex: "Calls com next step lock claro no minuto X convertem mais"]
Como Verificar: [mapear momento do next step lock e correlacionar]
```

### Seção 4 — Dimensões de Análise
Aspectos a observar em cada call.
**Formato**:
```
- Estrutura da Call: [sequência de fases, tempo em cada fase]
- Técnicas de Discovery: [tipos de perguntas, profundidade, tempo gasto]
- Apresentação: [como conectou à dor, storytelling, prova social]
- Pricing: [momento da revelação, técnica de ancoragem, value stack]
- Fechamento: [técnica usada, momento, resposta do lead]
- Tratamento de Objeção: [tipo, técnica, resultado]
- Linguagem: [palavras que repetem, tom, ritmo]
- Rapport: [técnicas de conexão, personalização]
```

### Seção 5 — Output Esperado
O que se espera como resultado da mineração.
**Formato**:
```
Deliverables:
1. [Lista de padrões identificados com frequência e evidência]
2. [Clips de referência para cada padrão]
3. [Playbook de técnicas replicáveis]
4. [Comparação padrão de calls ganhas vs. calls perdidas]

Formato: [relatório / apresentação / playbook]
Prazo: [DD/MM/AAAA]
Público-Alvo: [time de closers / gestores / treinamento]
```

## Exemplo
```
Período: Fev/2026 | 23 calls ganhas | 8 selecionadas (score > 82 + ticket > R$ 15k)
Closers: Juliana, Rafael, Thiago
Pergunta Central: "Por que esses 3 convertem 2x mais que a média?"

Hipótese 1: Fazem discovery 40% mais longa que a média
Hipótese 2: Usam história de cliente similar em 100% das calls
Hipótese 3: Nunca revelam preço antes de value stack completo

Output: Playbook "Top Closer Patterns" + 8 clips de referência
Prazo: 28/03/2026
```

## Agente Responsável
`audit-agent` — Executa a mineração. `coaching-agent` — Transforma padrões em treinamento.

## Checklists de Qualidade
- `qa-evidence-completeness-check.md` — Garante que padrões são baseados em evidência.
- `qa-bias-detection-check.md` — Garante que não há viés na seleção ou interpretação.
