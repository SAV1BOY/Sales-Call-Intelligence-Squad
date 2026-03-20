# 03 — Framework Detection Loop

> Detectar frameworks de vendas usados e não-usados durante a call, com evidência textual e gap analysis.

## Objetivo

Analisar a transcrição segmentada para identificar quais frameworks de vendas foram aplicados pelo closer (com que qualidade), quais deveriam ter sido aplicados mas não foram, e produzir um mapa de cobertura de frameworks com evidências textuais.

## Quando Executar

- Após conclusão do workflow 02 (análise minuto a minuto disponível).
- Como parte do workflow 06 (Full Funnel Call Audit).
- Quando solicitada análise específica de aderência a frameworks.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| framework-detector | Coordena a detecção, mapeia frameworks aos trechos da call |
| objection-specialist | Analisa trechos de objeção para verificar frameworks de tratamento |
| pricing-anchoring-analyst | Analisa trechos de preço para verificar frameworks de ancoragem |
| coaching-rewriter | Consultado para sugerir aplicação correta quando framework foi ausente |

## Frameworks Utilizados

- framework-detection-protocol
- sales-call-phase-model (referência cruzada com fases)
- Todos os frameworks do repositório são candidatos à detecção

## Checklists Obrigatórios

- framework-detection-quality
- evidence-citation-standards

## Etapas

### Etapa 1 — Inventário de Frameworks Aplicáveis
**Responsável**: framework-detector
**Input**: Transcrição segmentada + mapa de fases do workflow 01 + contexto da call (tipo de lead, produto, resultado)
**Ação**:
1. Listar todos os frameworks do repositório que se aplicam ao tipo de call analisada.
2. Mapear cada framework à fase da call onde deveria ter sido aplicado.
3. Definir indicadores de presença para cada framework (frases-chave, estrutura de perguntas, sequência esperada).
4. Criar matriz framework x fase com status inicial "não verificado".
**Output**: Matriz de frameworks aplicáveis com indicadores de detecção definidos.
**Quality Gate**: Todos os frameworks relevantes listados; indicadores de presença são específicos e verificáveis.

### Etapa 2 — Varredura de Detecção por Fase
**Responsável**: framework-detector
**Input**: Transcrição segmentada + matriz de frameworks
**Ação**:
1. Percorrer cada fase da call buscando evidências de aplicação dos frameworks mapeados.
2. Para cada framework detectado, registrar:
   - Timestamp e trecho exato onde foi aplicado.
   - Qualidade da aplicação: completa, parcial ou distorcida.
   - Nota de execução (1-5) com justificativa.
3. Para cada framework não detectado, registrar:
   - Fase onde deveria ter aparecido.
   - Momento específico onde a aplicação era indicada.
   - Impacto estimado da ausência.
4. Acionar specialists para validação em suas áreas (objeções, pricing).
**Output**: Matriz preenchida com status detectado/ausente + evidências.
**Quality Gate**: Cada célula da matriz tem status + justificativa; specialists consultados nas áreas relevantes.

### Etapa 3 — Validação por Especialistas
**Responsável**: objection-specialist, pricing-anchoring-analyst
**Input**: Trechos relevantes da transcrição + detecções preliminares
**Ação**:
1. Objection-specialist valida detecção de frameworks de objeção (isolamento, reframe, preemptive).
2. Pricing-anchoring-analyst valida detecção de frameworks de ancoragem e valor.
3. Cada especialista confirma ou corrige a nota de execução.
4. Especialistas adicionam observações técnicas sobre nuances que o detector geral pode ter perdido.
**Output**: Detecções validadas e enriquecidas por especialistas.
**Quality Gate**: Todas as detecções em áreas especializadas foram revisadas pelo specialist correspondente.

### Etapa 4 — Gap Analysis e Impacto
**Responsável**: framework-detector
**Input**: Matriz completa e validada
**Ação**:
1. Listar todos os gaps (frameworks ausentes ou parcialmente aplicados).
2. Classificar cada gap por severidade: crítico, moderado, menor.
3. Estimar impacto de cada gap no resultado da call.
4. Identificar padrões de gap (ex: closer nunca aplica ancoragem antes de revelar preço).
5. Priorizar gaps por frequência e impacto para coaching.
**Output**: Relatório de gaps priorizado com estimativa de impacto.
**Quality Gate**: Todos os gaps classificados por severidade; padrões identificados.

### Etapa 5 — Compilação do Relatório de Detecção
**Responsável**: framework-detector
**Input**: Matriz completa + gap analysis
**Ação**:
1. Compilar relatório com seções: Frameworks Detectados, Frameworks Ausentes, Gap Analysis, Recomendações.
2. Incluir score de cobertura de frameworks (% de frameworks aplicáveis que foram utilizados).
3. Gerar mapa visual (tabela) de cobertura por fase.
4. Listar top 3 frameworks que o closer mais precisa treinar.
5. Disponibilizar dados para o workflow 04 (scoring).
**Output**: Relatório completo de detecção de frameworks.
**Quality Gate**: framework-detection-quality (evidências citadas, gaps priorizados, recomendações acionáveis).

## Templates de Output

- framework-detection-report (mapa de cobertura + gap analysis)

## Registries Atualizados

- framework-detection-registry (detecções por closer e call)
- closer-skill-registry (gaps de framework atualizados)

## Critérios de Conclusão

- [ ] Todos os frameworks aplicáveis inventariados e mapeados por fase
- [ ] Varredura completa com evidência textual para cada detecção
- [ ] Validação por especialistas nas áreas de objeção e pricing
- [ ] Gap analysis com classificação de severidade e impacto
- [ ] Score de cobertura calculado e relatório compilado

## Próximo Workflow

→ 04-scoring-and-root-cause.md (pontuação dos 10 blocos e análise de causa raiz)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | Inventário de frameworks completo | Todos os frameworks relevantes listados; indicadores de presença são específicos e verificáveis; matriz framework x fase criada | Voltar a Etapa 1 (revisar repositório de frameworks e completar mapeamento) |
| Etapa 2 → Etapa 3 | Varredura de detecção concluída | Cada célula da matriz tem status (detectado/ausente) + justificativa com evidência textual | Voltar a Etapa 2 (completar varredura em fases não analisadas) |
| Etapa 3 → Etapa 4 | Validação por especialistas concluída | Todas as detecções em áreas de objeção e pricing revisadas pelos specialists correspondentes | Voltar a Etapa 3 (acionar specialist faltante para validação) |
| Etapa 4 → Etapa 5 | Gap analysis completo | Todos os gaps classificados por severidade (crítico/moderado/menor); padrões identificados | Voltar a Etapa 4 (revisar classificação de severidade com evidências adicionais) |
| Etapa 5 → Conclusão | framework-detection-quality | Evidências citadas, gaps priorizados, score de cobertura calculado, recomendações acionáveis | Voltar a Etapa 5 (refinar relatório e completar seções faltantes) |

## Decision Points
- Após Etapa 2: se cobertura de frameworks > 70% → closer demonstra boa aderência, focar em qualidade de execução; se cobertura < 40% → closer necessita treinamento fundamental em frameworks, priorizar gaps críticos
- Após Etapa 3: se specialists concordam com as detecções preliminares → prosseguir para gap analysis; se há divergência significativa entre detector e specialists → reunir evidências adicionais e arbitrar com base em citações textuais
- Após Etapa 4: se gaps são predominantemente de execução (framework tentado mas mal aplicado) → direcionar para coaching de refinamento; se gaps são de ausência (framework sequer tentado) → direcionar para treinamento básico

## Escalation Triggers
- Se cobertura de frameworks < 30% em call perdida → escalar para sales-chief para avaliação de capacitação do closer e possível suspensão temporária de calls até treinamento
- Se há conflito entre objection-specialist e pricing-anchoring-analyst sobre a mesma detecção → escalar para qa-guardian para arbitragem
- Se padrão de gap se repete em 3+ calls do mesmo closer (mesmo framework ausente) → escalar para sales-chief para inclusão em plano de desenvolvimento individual
