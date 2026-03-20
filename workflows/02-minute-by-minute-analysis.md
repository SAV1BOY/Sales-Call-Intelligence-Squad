# 02 — Minute-by-Minute Analysis

> Análise minuto a minuto completa da call com avaliação de técnica, engajamento e oportunidades perdidas.

## Objetivo

Produzir um relatório detalhado que examina cada minuto da call, avaliando a performance do closer em termos de técnica de vendas, controle de frame, engajamento do lead e identificação de oportunidades perdidas ou momentos críticos.

## Quando Executar

- Após conclusão do workflow 01 (transcrição segmentada disponível).
- Quando solicitada auditoria detalhada de uma call específica.
- Como parte do workflow 06 (Full Funnel Call Audit).

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| call-auditor | Executa a análise minuto a minuto, avalia técnica e identifica momentos críticos |

## Frameworks Utilizados

- minute-by-minute-analysis-framework
- sales-call-phase-model (referência para contexto de fase)

## Checklists Obrigatórios

- minute-by-minute-audit-quality
- call-auditor-standards

## Etapas

### Etapa 1 — Preparação do Audit Canvas
**Responsável**: call-auditor
**Input**: Transcrição segmentada do workflow 01
**Ação**:
1. Carregar transcrição segmentada e confirmar integridade.
2. Revisar resumo executivo para contexto geral (tipo de lead, produto, resultado).
3. Criar canvas de auditoria com um bloco por minuto da call.
4. Definir critérios de avaliação por minuto: técnica utilizada, engajamento do lead (1-5), controle de frame (1-5), oportunidade aproveitada/perdida.
5. Registrar duração total e número de blocos a auditar.
**Output**: Canvas de auditoria preparado com blocos vazios prontos para preenchimento.
**Quality Gate**: Canvas cobre 100% da duração da call; critérios de avaliação definidos.

### Etapa 2 — Análise Sequencial Minuto a Minuto
**Responsável**: call-auditor
**Input**: Canvas de auditoria + transcrição segmentada
**Ação**:
1. Para cada bloco de ~1 minuto, analisar e registrar:
   - **O que aconteceu**: Resumo factual do conteúdo discutido.
   - **Técnica utilizada**: Qual técnica de vendas o closer aplicou (ou deveria ter aplicado).
   - **Qualidade da execução**: Nota 1-5 para a execução da técnica.
   - **Engajamento do lead**: Nota 1-5 baseada em respostas, tom, profundidade.
   - **Controle de frame**: Nota 1-5 — quem está conduzindo a conversa?
   - **Oportunidade identificada**: O closer aproveitou ou perdeu uma abertura?
   - **Citação-chave**: Frase mais relevante do bloco (closer ou lead).
   - **Flag de atenção**: Vermelho (erro crítico), amarelo (oportunidade perdida), verde (bem executado).
2. Manter consistência de critérios ao longo de toda a call.
3. Identificar padrões que se repetem ao longo dos minutos (ex: closer sempre perde controle após objeção).
**Output**: Canvas preenchido com análise de cada minuto.
**Quality Gate**: 100% dos blocos analisados; notas justificadas com evidência textual.

### Etapa 3 — Identificação de Momentos Críticos
**Responsável**: call-auditor
**Input**: Canvas preenchido
**Ação**:
1. Extrair todos os blocos com flag vermelho (erros críticos).
2. Extrair todos os blocos com flag amarelo (oportunidades perdidas).
3. Extrair os 3-5 melhores momentos da call (flags verdes mais altos).
4. Para cada momento crítico, detalhar:
   - Timestamp exato e contexto.
   - O que o closer fez vs. o que deveria ter feito.
   - Impacto estimado na progressão da call.
5. Rankear momentos críticos por impacto potencial na conversão.
**Output**: Lista rankeada de momentos críticos com análise de impacto.
**Quality Gate**: Todos os flags vermelhos e amarelos extraídos e analisados.

### Etapa 4 — Análise de Padrões e Tendências
**Responsável**: call-auditor
**Input**: Canvas completo + momentos críticos
**Ação**:
1. Calcular médias por fase da call: engajamento, técnica, controle de frame.
2. Identificar tendência ao longo da call (melhora, piora, irregular).
3. Mapear correlação entre queda de engajamento do lead e ações do closer.
4. Identificar o "ponto de virada" da call (momento onde a direção foi definida).
5. Calcular distribuição de flags: % verde, % amarelo, % vermelho.
**Output**: Análise de padrões com gráficos de tendência (textual) e correlações.
**Quality Gate**: Tendências documentadas com dados dos blocos; ponto de virada identificado.

### Etapa 5 — Compilação do Relatório
**Responsável**: call-auditor
**Input**: Canvas + momentos críticos + análise de padrões
**Ação**:
1. Compilar relatório no formato minute-by-minute-audit-report.
2. Incluir seções: Resumo Executivo, Análise Minuto a Minuto, Momentos Críticos, Padrões Identificados, Recomendações.
3. Gerar score preliminar de performance (será refinado no workflow 04).
4. Listar top 3 recomendações de coaching prioritárias.
5. Incluir tabela-resumo com métricas agregadas.
**Output**: Relatório completo de auditoria minuto a minuto.
**Quality Gate**: minute-by-minute-audit-quality (todas as seções preenchidas, evidências citadas, recomendações acionáveis).

## Templates de Output

- minute-by-minute-audit-report (relatório completo com todas as seções)

## Registries Atualizados

- audit-registry (nova auditoria registrada com score preliminar)
- call-log-registry (status atualizado para "auditada — minuto a minuto")

## Critérios de Conclusão

- [ ] Todos os minutos da call analisados individualmente
- [ ] Momentos críticos identificados e rankeados por impacto
- [ ] Padrões de performance documentados com evidências
- [ ] Ponto de virada da call identificado
- [ ] Relatório compilado no formato padrão
- [ ] Score preliminar calculado e registrado

## Próximo Workflow

→ 03-framework-detection-loop.md (detecção de frameworks utilizados e não-utilizados)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | Canvas de auditoria preparado | Canvas cobre 100% da duração da call; critérios de avaliação definidos por minuto | Voltar a Etapa 1 (recarregar transcrição ou ajustar blocos) |
| Etapa 2 → Etapa 3 | Análise sequencial completa | 100% dos blocos analisados; notas (1-5) justificadas com evidência textual | Voltar a Etapa 2 (preencher blocos faltantes ou revisar notas sem justificativa) |
| Etapa 3 → Etapa 4 | Momentos críticos extraídos | Todos os flags vermelhos e amarelos extraídos; cada momento tem análise de impacto | Voltar a Etapa 3 (revisar canvas para flags não identificados) |
| Etapa 4 → Etapa 5 | Padrões e tendências documentados | Tendências documentadas com dados; ponto de virada identificado; correlações mapeadas | Voltar a Etapa 4 (aprofundar análise de correlação com dados dos blocos) |
| Etapa 5 → Conclusão | minute-by-minute-audit-quality | Todas as seções preenchidas, evidências citadas, recomendações acionáveis, score preliminar calculado | Voltar a Etapa 5 (completar seções faltantes ou refinar recomendações) |

## Decision Points
- Após Etapa 2: se mais de 50% dos blocos possuem flag verde → call de boa qualidade, focar análise em oportunidades de refinamento; se mais de 30% dos blocos possuem flag vermelho → call crítica, priorizar identificação de padrões de erro sistêmico
- Após Etapa 3: se momentos críticos concentram-se em uma única fase da call → direcionar coaching para fase específica; se estão distribuídos ao longo de toda a call → indicar necessidade de treinamento abrangente
- Após Etapa 4: se tendência mostra piora progressiva ao longo da call → sinalizar perda de controle de frame como tema central; se tendência mostra melhora → reconhecer capacidade de recuperação do closer

## Escalation Triggers
- Se score médio de engajamento do lead < 2.0 em 3+ blocos consecutivos → pausar workflow, escalar para sales-chief para avaliação de gravidade e possível intervenção imediata
- Se 5+ blocos consecutivos possuem flag vermelho → escalar para sales-chief como call de performance crítica que demanda coaching urgente
- Se há divergência significativa entre notas de técnica e notas de engajamento (técnica alta, engajamento baixo) → escalar para deal-risk-doctor para investigar se o problema é do lead ou da abordagem
