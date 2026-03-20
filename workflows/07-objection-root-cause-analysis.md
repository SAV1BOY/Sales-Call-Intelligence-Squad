# 07 — Objection Root Cause Analysis

> Análise de causa raiz das objeções levantadas na call, classificação por taxonomia e recomendações de prevenção.

## Objetivo

Dissecar cada objeção levantada pelo lead durante a call, identificar a causa raiz real por trás de cada uma (a objeção declarada vs. a objeção real), classificar por taxonomia de objeções high-ticket e produzir estratégias de tratamento e prevenção.

## Quando Executar

- Quando uma call apresenta 2+ objeções significativas não resolvidas.
- Quando a causa raiz da perda da call (workflow 04) foi classificada como "objeção não tratada".
- Como input para o workflow 18 (implementação de objeções preventivas).
- Quando o gestor solicita análise profunda de padrões de objeção de um closer.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| objection-specialist | Responsável principal pela análise, classificação e diagnóstico das objeções |
| deal-risk-doctor | Suporte na análise de causa raiz e fatores contextuais |

## Frameworks Utilizados

- objection-isolation-protocol
- high-ticket-objection-taxonomy
- objection-root-cause-model (objeção declarada → objeção real → necessidade não atendida)

## Checklists Obrigatórios

- objection-analysis-quality
- root-cause-evidence-checklist

## Etapas

### Etapa 1 — Extração e Inventário de Objeções
**Responsável**: objection-specialist
**Input**: Transcrição segmentada + relatório de auditoria (workflows 01-02)
**Ação**:
1. Percorrer a transcrição identificando cada momento de objeção, resistência ou hesitação do lead.
2. Registrar cada objeção com: timestamp, trecho exato, fase da call onde ocorreu.
3. Classificar severidade inicial: objeção leve (hesitação), moderada (resistência verbal), forte (recusa explícita).
4. Identificar objeções implícitas (mudança de tom, respostas evasivas, silêncio prolongado).
5. Registrar como o closer respondeu a cada objeção.
**Output**: Inventário completo de objeções com metadata.
**Quality Gate**: Todas as objeções (explícitas e implícitas) identificadas; trechos exatos citados.

### Etapa 2 — Classificação Taxonômica
**Responsável**: objection-specialist
**Input**: Inventário de objeções
**Ação**:
1. Classificar cada objeção pela taxonomia high-ticket:
   - Preço/Investimento ("Está caro", "Não tenho budget")
   - Timing ("Não é o momento", "Preciso pensar")
   - Autoridade ("Preciso falar com meu sócio/cônjuge")
   - Confiança ("Não sei se funciona para mim")
   - Necessidade ("Não sei se preciso disso")
   - Comparação ("Estou vendo outras opções")
   - Medo/Risco ("E se não der certo?")
2. Identificar se a objeção declarada é a objeção real ou uma "cortina de fumaça".
3. Mapear a necessidade não atendida por trás de cada objeção real.
**Output**: Objeções classificadas com camadas: declarada → real → necessidade não atendida.
**Quality Gate**: Cada objeção classificada em todas as 3 camadas; cortinas de fumaça identificadas.

### Etapa 3 — Análise de Causa Raiz por Objeção
**Responsável**: objection-specialist + deal-risk-doctor
**Input**: Objeções classificadas + transcrição completa
**Ação**:
1. Para cada objeção principal, aplicar análise de causa raiz:
   - A objeção surgiu por falha do closer (diagnóstico fraco, ancoragem ausente)?
   - A objeção surgiu por fator externo (lead genuinamente sem fit)?
   - A objeção foi plantada antes da call (copy, SDR, expectativa incorreta)?
2. Rastrear na transcrição o momento onde a semente da objeção foi plantada.
3. Avaliar se o closer teve oportunidade de prevenir a objeção antes que surgisse.
4. Classificar controlabilidade: prevenível pelo closer, prevenível pelo processo, não controlável.
**Output**: Diagnóstico de causa raiz por objeção com classificação de controlabilidade.
**Quality Gate**: Causa raiz apoiada por evidência textual; momento da semente identificado.

### Etapa 4 — Avaliação do Tratamento Dado
**Responsável**: objection-specialist
**Input**: Inventário de objeções + respostas do closer
**Ação**:
1. Para cada objeção, avaliar a resposta do closer:
   - Usou isolamento antes de responder? (Sim/Não)
   - Respondeu à objeção real ou à declarada? (Real/Declarada/Nenhuma)
   - Técnica utilizada: reframe, prova social, pergunta de retorno, desconto, ignorou.
   - Eficácia da resposta (1-5): o lead ficou mais convencido, menos convencido ou igual?
2. Identificar padrões de resposta do closer (ex: sempre oferece desconto, nunca isola).
3. Comparar com best practice para cada tipo de objeção.
**Output**: Avaliação de tratamento com notas e padrões identificados.
**Quality Gate**: Cada resposta avaliada com critérios objetivos; padrões documentados.

### Etapa 5 — Recomendações e Playbook de Prevenção
**Responsável**: objection-specialist
**Input**: Análise completa de todas as objeções
**Ação**:
1. Gerar playbook de tratamento ideal para cada objeção encontrada.
2. Listar objeções que poderiam ter sido prevenidas e como (objeção preventiva no pitch).
3. Produzir scripts sugeridos para tratamento de cada tipo de objeção.
4. Recomendar ajustes no pitch/apresentação que preveniriam as objeções mais comuns.
5. Disponibilizar dados para workflow 18 (implementação de objeções preventivas).
**Output**: Playbook de prevenção e tratamento + scripts sugeridos.
**Quality Gate**: Playbook é específico para as objeções encontradas; scripts são realistas.

## Templates de Output

- objection-analysis-report (inventário + taxonomia + causa raiz + tratamento + playbook)

## Registries Atualizados

- objection-pattern-registry (padrões de objeção por closer e por produto)
- closer-skill-registry (gaps de tratamento de objeção atualizados)

## Critérios de Conclusão

- [ ] Todas as objeções (explícitas e implícitas) inventariadas
- [ ] Classificação taxonômica em 3 camadas para cada objeção
- [ ] Causa raiz identificada com momento da semente rastreado
- [ ] Tratamento do closer avaliado com nota e padrões
- [ ] Playbook de prevenção e tratamento gerado

## Próximo Workflow

→ 18-preventive-objections-implementation.md (implementar objeções preventivas no pitch)
