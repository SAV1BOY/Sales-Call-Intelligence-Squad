# 18 — Preventive Objections Implementation

> Implementar objeções preventivas no pitch para neutralizar resistências antes que surjam.

## Objetivo

Usar os padrões de objeção mais frequentes (workflow 07) para criar blocos de objeção preventiva que são inseridos no pitch do closer antes que o lead tenha chance de levantar a objeção, neutralizando resistências proativamente e aumentando a taxa de conversão.

## Quando Executar

- Após análise de objeções (workflow 07) identificar padrões recorrentes tratáveis preventivamente.
- Quando 3+ calls no período apresentam a mesma objeção que poderia ter sido prevenida.
- Ao lançar novo produto/oferta, para prevenir objeções previsíveis.
- Quando closer específico tem padrão de perda por objeção recorrente.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| objection-specialist | Identifica objeções preveníveis e define estratégia preventiva |
| coaching-rewriter | Produz os blocos de pitch com objeção preventiva incorporada |
| closer-trainer | Valida executabilidade e treina implementação |

## Frameworks Utilizados

- bradley-lea/lea-preventive-objection-system
- preemptive-reframe-protocol
- pitch-integration-model

## Checklists Obrigatórios

- preventive-objection-quality
- pitch-naturalness-checklist

## Etapas

### Etapa 1 — Seleção de Objeções para Prevenção
**Responsável**: objection-specialist
**Input**: Objection-pattern-registry + relatórios de workflow 07
**Ação**:
1. Listar as objeções mais frequentes do período por tipo:
   - Preço ("Está caro", "Preciso pensar no investimento")
   - Timing ("Não é o momento")
   - Confiança ("Como sei que funciona?")
   - Autoridade ("Preciso consultar meu sócio")
   - Comparação ("Vou ver outras opções")
2. Filtrar objeções que são preveníveis (podem ser endereçadas antes de surgir).
3. Priorizar por frequência × impacto na conversão.
4. Para cada objeção selecionada, definir:
   - Em que fase da call a prevenção deve ocorrer.
   - Que tipo de prevenção usar (história, pergunta, reframe, prova social).
5. Selecionar top 3-5 objeções para implementação preventiva.
**Output**: Lista priorizada de objeções com estratégia preventiva definida.
**Quality Gate**: Objeções selecionadas são genuinamente preveníveis; estratégia definida por tipo.

### Etapa 2 — Design dos Blocos Preventivos
**Responsável**: coaching-rewriter + objection-specialist
**Input**: Objeções selecionadas + estratégias preventivas + framework de Bradley Lea
**Ação**:
1. Para cada objeção, criar bloco preventivo seguindo o sistema LEA:
   - **L (Label)**: Nomear a preocupação antes do lead ("A maioria das pessoas que chega aqui se pergunta se...").
   - **E (Explain)**: Explicar por que essa preocupação é natural e esperada.
   - **A (Address)**: Resolver a preocupação com evidência, história ou reframe.
2. Definir o momento exato do pitch onde o bloco deve ser inserido:
   - Objeção de preço → prevenir durante a fase de diagnóstico (amplificar custo de não agir).
   - Objeção de confiança → prevenir antes da apresentação (prova social, cases).
   - Objeção de timing → prevenir durante amplificação de dor (urgência natural).
   - Objeção de autoridade → prevenir no início (incluir decisor na call).
3. Escrever scripts naturais e conversacionais (não roteiro robótico).
4. Incluir transições suaves para entrar e sair do bloco preventivo.
**Output**: Blocos preventivos scriptados com posicionamento no pitch.
**Quality Gate**: Blocos seguem framework LEA; posicionamento correto na fase da call.

### Etapa 3 — Teste de Naturalidade
**Responsável**: coaching-rewriter
**Input**: Blocos preventivos scriptados
**Ação**:
1. Ler cada bloco no contexto do pitch completo para verificar fluxo natural.
2. Verificar que o bloco não soa como "defesa" ou "justificativa" (deve soar consultivo).
3. Testar se o bloco funciona mesmo que o lead não tenha a objeção (não cria objeção nova).
4. Ajustar linguagem para o estilo de cada closer (personalização).
5. Verificar que o bloco não revela informação prematuramente (ex: mencionar preço antes da hora).
**Output**: Blocos validados e ajustados por naturalidade.
**Quality Gate**: pitch-naturalness-checklist (fluxo natural, tom consultivo, não cria objeção).

### Etapa 4 — Treinamento e Role-Play
**Responsável**: closer-trainer
**Input**: Blocos preventivos finalizados
**Ação**:
1. Preparar sessão de treinamento para cada closer.
2. Explicar a lógica por trás de cada bloco preventivo (não apenas o script).
3. Praticar com role-play: closer aplica o bloco em cenário simulado.
4. Dar feedback sobre timing, tom e naturalidade da execução.
5. Ajustar blocos com base no feedback do role-play.
6. Definir período de teste (ex: próximas 10 calls) para medir impacto.
**Output**: Closers treinados + período de teste definido.
**Quality Gate**: Closer consegue executar o bloco de forma natural no role-play.

### Etapa 5 — Medição de Impacto e Iteração
**Responsável**: objection-specialist
**Input**: Calls do período de teste + registro de objeções
**Ação**:
1. Após período de teste, auditar calls para verificar:
   - O closer aplicou o bloco preventivo? (Sim/Não/Parcial)
   - A objeção alvo apareceu mesmo assim? (Sim/Não)
   - Se apareceu, foi com menos intensidade? (Sim/Não)
   - A conversão melhorou no período? (Comparativo)
2. Calcular taxa de prevenção: % de calls onde a objeção foi prevenida.
3. Iterar: ajustar blocos que não funcionaram, manter os eficazes.
4. Registrar resultados no preventive-objection-registry.
**Output**: Relatório de impacto + iteração dos blocos.
**Quality Gate**: preventive-objection-quality (medição objetiva, iteração baseada em dados).

## Templates de Output

- preventive-objection-playbook (blocos + posicionamento + scripts + medição)

## Registries Atualizados

- preventive-objection-registry (blocos implementados e taxa de prevenção)
- closer-pitch-registry (pitch atualizado com blocos preventivos)

## Critérios de Conclusão

- [ ] Top 3-5 objeções preveníveis selecionadas e priorizadas
- [ ] Blocos preventivos desenhados seguindo framework LEA
- [ ] Teste de naturalidade aprovado para todos os blocos
- [ ] Closers treinados via role-play com feedback
- [ ] Período de teste definido e medição de impacto planejada

## Próximo Workflow

→ 07-objection-root-cause-analysis.md (próxima rodada de análise após implementação para medir evolução)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | Objeções genuinamente preveníveis | Top 3-5 objeções selecionadas com frequência × impacto; estratégia preventiva por tipo definida | Voltar a Etapa 1 para refiltrar objeções que não são preveníveis |
| Etapa 2 → Etapa 3 | Blocos seguem framework LEA | Label, Explain e Address completos; posicionamento correto na fase da call | Voltar a Etapa 2 para redesenhar blocos que não seguem o framework |
| Etapa 3 → Etapa 4 | pitch-naturalness-checklist | Fluxo natural no contexto do pitch; tom consultivo; não cria objeção nova | Voltar a Etapa 2 para reescrever blocos que soam artificiais |
| Etapa 4 → Etapa 5 | Closer executa com naturalidade | Closer demonstra domínio no role-play; timing e tom adequados | Voltar a Etapa 4 para mais sessões de role-play |
| Etapa 5 → Conclusão | preventive-objection-quality | Medição objetiva de taxa de prevenção; iteração baseada em dados | Voltar a Etapa 2 para redesenhar blocos ineficazes |

## Decision Points
- Após Etapa 1: se objeção mais frequente é de preço → focar prevenção na fase de diagnóstico (amplificar custo de não agir); se é de confiança → focar prevenção antes da apresentação (prova social)
- Após Etapa 3: se bloco preventivo testa positivo em contexto mas cria objeção nova em teste isolado → ajustar ou descartar o bloco; se passa ambos os testes → prosseguir para treinamento
- Após Etapa 5: se taxa de prevenção é superior a 50% → manter bloco e expandir; se inferior a 20% → iterar ou substituir bloco por abordagem diferente

## Escalation Triggers
- Se bloco preventivo está piorando conversão ao invés de melhorar (efeito reverso) → pausar implementação imediatamente, escalar para objection-specialist para diagnóstico
- Se closer resiste a adotar blocos preventivos após treinamento → pausar, escalar para closer-trainer para sessão individualizada de alinhamento
- Se objeção que estava sendo prevenida muda de forma (lead verbaliza de maneira diferente) → pausar, escalar para objection-specialist para atualizar o bloco
