# 12 — Monthly Closer Certification

> Certificação mensal de closers baseada em performance, aderência a frameworks e evolução contínua.

## Objetivo

Realizar avaliação mensal completa de cada closer do time, consolidando scores, padrões, evolução, aderência a coaching e competência em frameworks, produzindo certificação com nível (Bronze, Prata, Ouro, Diamante) e plano de desenvolvimento individualizado.

## Quando Executar

- Último dia útil de cada mês.
- Pode ser antecipado para closers em período probatório.
- Triggered por solicitação do gestor para avaliação extraordinária.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| sales-chief | Coordena a certificação, emite parecer final e define nível |
| closer-trainer | Avalia evolução técnica e aderência ao treinamento |
| qa-guardian | Valida qualidade e consistência da avaliação |
| scorecard-analyst | Fornece dados agregados de scoring do mês |

## Frameworks Utilizados

- closer-certification-model (critérios por nível)
- competency-progression-matrix
- coaching-effectiveness-measurement

## Checklists Obrigatórios

- certification-assessment-completeness
- certification-fairness-checklist (anti-viés)

## Etapas

### Etapa 1 — Compilação do Dossiê do Closer
**Responsável**: scorecard-analyst
**Input**: Registries do mês (scores, auditorias, coaching, padrões)
**Ação**:
1. Coletar todos os scores de calls do closer no mês.
2. Calcular score médio, mediana, desvio padrão e tendência (melhoria/piora).
3. Listar todas as auditorias realizadas com resultados.
4. Consolidar sessões de coaching e aderência (exercícios realizados vs. atribuídos).
5. Levantar taxa de conversão individual vs. meta e vs. time.
6. Identificar blocos de scoring com melhoria e blocos estagnados.
**Output**: Dossiê quantitativo completo do closer.
**Quality Gate**: Dados de pelo menos 4 calls auditadas no mês; métricas calculadas corretamente.

### Etapa 2 — Avaliação de Competências Técnicas
**Responsável**: closer-trainer
**Input**: Dossiê quantitativo + auditorias detalhadas + relatórios de framework detection
**Ação**:
1. Avaliar cada competência na competency-progression-matrix:
   - Rapport e Conexão (1-5)
   - Diagnóstico e Descoberta (1-5)
   - Amplificação de Dor (1-5)
   - Apresentação de Solução (1-5)
   - Ancoragem e Preço (1-5)
   - Tratamento de Objeções (1-5)
   - Controle de Frame (1-5)
   - Técnica de Close (1-5)
   - Adaptabilidade (1-5)
   - Consistência (1-5)
2. Comparar notas com mês anterior (delta por competência).
3. Identificar top 2 forças e top 2 áreas de desenvolvimento.
4. Avaliar aderência a frameworks: % de frameworks recomendados que o closer incorporou.
**Output**: Matriz de competências preenchida com deltas e destaques.
**Quality Gate**: Cada competência avaliada com evidência de pelo menos 2 calls; deltas calculados.

### Etapa 3 — Validação de Qualidade (QA)
**Responsável**: qa-guardian
**Input**: Dossiê + matriz de competências + avaliações anteriores
**Ação**:
1. Verificar consistência das avaliações (notas alinhadas com evidências).
2. Aplicar certification-fairness-checklist para detectar vieses.
3. Comparar avaliação com closers de performance similar (calibração).
4. Validar que critérios de nível foram aplicados corretamente.
5. Sinalizar discrepâncias para revisão.
**Output**: Validação de QA com status aprovado ou ajustes necessários.
**Quality Gate**: Avaliação aprovada pelo QA sem discrepâncias significativas.

### Etapa 4 — Determinação do Nível de Certificação
**Responsável**: sales-chief
**Input**: Dossiê + competências + validação QA
**Ação**:
1. Aplicar critérios de certificação:
   - **Diamante**: Score médio 85+, conversão acima da meta, 8+ competências nota 4+, aderência coaching 90%+.
   - **Ouro**: Score médio 70-84, conversão na meta, 6+ competências nota 4+, aderência coaching 75%+.
   - **Prata**: Score médio 55-69, conversão abaixo da meta mas em tendência de melhoria, aderência coaching 60%+.
   - **Bronze**: Score médio abaixo de 55, necessita acompanhamento intensivo.
2. Comparar com nível do mês anterior (promoção, manutenção ou rebaixamento).
3. Emitir parecer qualitativo sobre o closer (pontos fortes, riscos, potencial).
4. Definir plano de desenvolvimento para o próximo mês.
**Output**: Certificação com nível + parecer + plano de desenvolvimento.
**Quality Gate**: Nível justificado com dados; plano de desenvolvimento é específico e acionável.

### Etapa 5 — Emissão do Certificado e Registro
**Responsável**: sales-chief
**Input**: Certificação finalizada
**Ação**:
1. Produzir relatório de certificação no formato closer-certification-report.
2. Registrar no closer-certification-registry (histórico de níveis).
3. Comunicar resultado ao closer e ao gestor.
4. Publicar ranking mensal do time.
5. Programar coaching prioritário para closers Bronze e Prata.
**Output**: Certificado emitido + registries atualizados + comunicação feita.
**Quality Gate**: certification-assessment-completeness 100% aprovado.

## Templates de Output

- closer-certification-report (dossiê + competências + nível + plano)
- monthly-team-ranking (ranking comparativo)

## Registries Atualizados

- closer-certification-registry (nível mensal registrado)
- closer-development-plan-registry (plano do próximo mês)
- team-metrics-registry (ranking atualizado)

## Critérios de Conclusão

- [ ] Dossiê quantitativo compilado com pelo menos 4 calls analisadas
- [ ] Matriz de competências preenchida com evidências e deltas
- [ ] Validação de QA aprovada sem vieses
- [ ] Nível de certificação determinado e justificado
- [ ] Plano de desenvolvimento do próximo mês definido
- [ ] Certificado emitido e comunicado ao closer e gestor

## Próximo Workflow

→ 13-sdr-to-closer-feedback-loop.md (feedbacks cross-squad mensais)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | Dossiê quantitativo completo | Pelo menos 4 calls auditadas no mês; métricas calculadas corretamente | Voltar a Etapa 1 para completar coleta |
| Etapa 2 → Etapa 3 | Competências avaliadas com evidência | Cada competência com evidência de pelo menos 2 calls; deltas calculados | Voltar a Etapa 2 para revisar avaliações sem evidência |
| Etapa 3 → Etapa 4 | Validação QA aprovada | Sem discrepâncias significativas; certification-fairness-checklist aprovado | Voltar a Etapa 2 para recalibrar avaliações com viés |
| Etapa 4 → Etapa 5 | Nível justificado | Nível de certificação alinhado com dados; plano de desenvolvimento específico e acionável | Voltar a Etapa 4 para ajustar nível ou plano |
| Etapa 5 → Conclusão | certification-assessment-completeness | 100% das seções preenchidas; comunicação realizada | Voltar a Etapa 5 para completar registro |

## Decision Points
- Após Etapa 3: se QA identifica viés ou discrepância → retornar à Etapa 2 para recalibração; se aprovado sem ressalvas → prosseguir para determinação de nível
- Após Etapa 4: se closer sofre rebaixamento de nível → acionar coaching intensivo (workflow 05) imediatamente; se closer é promovido a Diamante → considerar como mentor para closers Bronze/Prata
- Após Etapa 4: se closer está em Bronze por 2+ meses consecutivos → escalar decisão sobre continuidade ao gestor

## Escalation Triggers
- Se closer tem menos de 4 calls auditadas no mês → pausar certificação, escalar para sales-chief para decisão sobre certificar com dados parciais ou adiar
- Se QA reprova avaliação por viés comprovado → pausar, escalar para sales-chief para reassignment do avaliador
- Se mais de 30% do time cai de nível no mesmo mês → pausar, escalar para sales-chief para investigar causa sistêmica (problema de oferta, tráfego ou processo)
