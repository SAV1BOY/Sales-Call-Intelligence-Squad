# 20 — RalphLoop Sales Retro

> Retrospectiva e aprendizado contínuo do squad com ciclo de melhoria perpétua.

## Objetivo

Realizar retrospectiva periódica do Sales-Call-Intelligence-Squad para consolidar aprendizados, revisar eficácia dos frameworks e workflows, identificar oportunidades de melhoria no sistema de análise e garantir que o squad está em ciclo de evolução contínua — não apenas auditando calls, mas melhorando a própria capacidade de auditar.

## Quando Executar

- Ao final de cada mês, após conclusão de todos os workflows do período.
- Ao final de cada ciclo de certificação (workflow 12).
- Quando há mudança significativa no processo de vendas (novo produto, nova equipe, novo script).
- Quando métricas do squad indicam estagnação ou declínio em eficácia.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| sales-chief | Facilitador da retro, responsável por decisões de evolução do sistema |
| win-loss-miner | Fornece insights de padrões acumulados e tendências |
| qa-guardian | Avalia qualidade e consistência das análises produzidas pelo squad |

## Frameworks Utilizados

- ralphloop-sales (loop de aprendizado: Observar → Analisar → Implementar → Medir → Iterar)
- post-call-learning-loop
- system-effectiveness-review

## Checklists Obrigatórios

- retro-completeness-checklist
- improvement-action-viability

## Etapas

### Etapa 1 — Coleta de Métricas do Squad
**Responsável**: sales-chief
**Input**: Todos os registries do período (auditorias, scores, coaching, padrões, feedbacks cross-squad)
**Ação**:
1. Consolidar métricas de produtividade do squad:
   - Calls auditadas no período vs. meta.
   - Tempo médio de auditoria por call.
   - Cobertura de auditorias (% de calls do time que foram auditadas).
2. Consolidar métricas de impacto:
   - Evolução do score médio do time de closers.
   - Taxa de conversão antes vs. depois de coaching.
   - Padrões de vitória novos identificados e adotados.
   - Padrões de perda reduzidos após intervenção.
   - Deals recuperados e revenue recuperado.
3. Consolidar métricas de qualidade do squad:
   - Consistência de scoring entre auditorias (variação).
   - Feedback dos closers sobre relevância do coaching.
   - Feedbacks cross-squad implementados vs. ignorados.
**Output**: Dashboard de métricas do squad no período.
**Quality Gate**: Métricas coletadas de todas as fontes; cálculos verificados.

### Etapa 2 — Análise de Eficácia dos Workflows
**Responsável**: qa-guardian
**Input**: Dashboard de métricas + outputs dos workflows do período
**Ação**:
1. Avaliar cada workflow (00-19) no período:
   - Foi executado conforme projetado? (Sim/Parcial/Não)
   - Produziu output de qualidade? (Nota 1-5)
   - Encontrou gargalos ou problemas de processo? (Listar)
   - Os quality gates foram eficazes em pegar problemas? (Sim/Parcial/Não)
2. Identificar workflows que precisam de atualização ou redesign.
3. Identificar etapas que são consistentemente puladas ou malfeitas.
4. Avaliar se os frameworks utilizados ainda são adequados ou precisam de evolução.
**Output**: Avaliação de eficácia por workflow com recomendações.
**Quality Gate**: Cada workflow avaliado com evidência; recomendações justificadas.

### Etapa 3 — Análise de Tendências de Longo Prazo
**Responsável**: win-loss-miner
**Input**: Registries históricos (3+ meses de dados)
**Ação**:
1. Identificar tendências de longo prazo nos padrões de vitória e derrota:
   - Quais padrões de vitória estão se consolidando (adotados consistentemente)?
   - Quais padrões de perda estão diminuindo (intervenções funcionando)?
   - Quais padrões de perda são persistentes (intervenções não funcionando)?
   - Novos padrões emergindo que ainda não foram endereçados?
2. Avaliar correlação entre intervenções do squad e mudanças nos resultados.
3. Identificar áreas onde o squad está tendo máximo impacto vs. mínimo impacto.
4. Projetar tendências para o próximo período.
**Output**: Análise de tendências com projeções e áreas de impacto.
**Quality Gate**: Tendências baseadas em 3+ meses; correlações significativas.

### Etapa 4 — Retrospectiva e Definição de Melhorias
**Responsável**: sales-chief (com input de todos os agentes)
**Input**: Dashboard + eficácia dos workflows + tendências
**Ação**:
1. Conduzir retrospectiva seguindo o RalphLoop:
   - **O que Observamos**: Dados e fatos do período.
   - **O que Analisamos**: Insights e interpretações.
   - **O que Implementamos**: Mudanças feitas e seu efeito.
   - **O que Medimos**: Resultados das mudanças.
   - **O que Iteramos**: Ajustes necessários para o próximo ciclo.
2. Definir top 3 melhorias para o próximo período:
   - Melhoria de workflow (processo).
   - Melhoria de framework (técnica).
   - Melhoria de qualidade (consistência).
3. Para cada melhoria, definir: responsável, prazo, métrica de sucesso.
4. Atualizar playbooks, checklists ou templates que precisam de revisão.
**Output**: Ata da retro + plano de melhorias com responsáveis e prazos.
**Quality Gate**: improvement-action-viability (melhorias são específicas, mensuráveis, com prazo).

### Etapa 5 — Publicação e Início do Novo Ciclo
**Responsável**: sales-chief
**Input**: Ata da retro + plano de melhorias
**Ação**:
1. Publicar ata da retro para todos os stakeholders.
2. Atualizar workflows, frameworks ou checklists conforme decidido.
3. Registrar no retro-registry para histórico de evolução do squad.
4. Comunicar mudanças aos agentes afetados.
5. Definir metas do próximo ciclo baseadas nas melhorias planejadas.
6. Iniciar novo ciclo de operação com os ajustes implementados.
**Output**: Ata publicada + sistema atualizado + novo ciclo iniciado.
**Quality Gate**: retro-completeness-checklist (retro documentada, melhorias definidas, sistema atualizado).

## Templates de Output

- retro-report (ata + análises + plano de melhorias)
- squad-evolution-dashboard (métricas de evolução ao longo do tempo)

## Registries Atualizados

- retro-registry (retrospectiva registrada)
- workflow-version-registry (versões de workflows atualizadas)
- squad-evolution-registry (métricas de evolução do squad)

## Critérios de Conclusão

- [ ] Métricas de produtividade, impacto e qualidade do squad consolidadas
- [ ] Eficácia de cada workflow avaliada com recomendações
- [ ] Tendências de longo prazo analisadas com projeções
- [ ] Retrospectiva conduzida com RalphLoop completo
- [ ] Top 3 melhorias definidas com responsável, prazo e métrica
- [ ] Sistema atualizado e novo ciclo iniciado

## Próximo Workflow

→ 00-recording-to-transcript.md (o ciclo recomeça — agora com o sistema melhorado)
