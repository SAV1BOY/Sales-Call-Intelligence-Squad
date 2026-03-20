# 05 — Coaching Rewrite Loop

> Reescrever momentos críticos da call com versões before/after para treinamento do closer.

## Objetivo

Selecionar os momentos mais impactantes da call (erros, oportunidades perdidas, objeções mal tratadas) e produzir versões reescritas que demonstrem como o closer deveria ter conduzido cada momento, criando material de coaching prático e acionável.

## Quando Executar

- Após conclusão do workflow 04 (scoring e causa raiz disponíveis).
- Como parte do workflow 06 (Full Funnel Call Audit).
- Quando solicitado coaching específico sobre uma call.
- Quando um closer apresenta padrão recorrente de erro identificado em múltiplas calls.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| coaching-rewriter | Responsável principal pela reescrita dos momentos críticos |
| objection-specialist | Consultor para reescrita de momentos envolvendo objeções |
| pricing-anchoring-analyst | Consultor para reescrita de momentos envolvendo preço e ancoragem |

## Frameworks Utilizados

- rewrite-the-moment-framework
- coaching-feedback-model (situação → comportamento → impacto → alternativa)
- Frameworks específicos do gap identificado (ex: SPIN para diagnóstico fraco)

## Checklists Obrigatórios

- rewrite-quality
- coaching-delivery-standards

## Etapas

### Etapa 1 — Seleção de Momentos para Reescrita
**Responsável**: coaching-rewriter
**Input**: Relatório minuto a minuto (workflow 02) + scorecard (workflow 04) + gap analysis (workflow 03)
**Ação**:
1. Identificar os 3-5 momentos mais críticos da call (flags vermelhos e amarelos do workflow 02).
2. Priorizar por impacto: momentos que, se executados diferente, teriam mudado o resultado.
3. Categorizar cada momento: objeção mal tratada, diagnóstico superficial, ancoragem ausente, close prematuro, etc.
4. Extrair o trecho exato da transcrição (com 30s de contexto antes e depois).
5. Registrar o framework que deveria ter sido aplicado em cada momento.
**Output**: Lista priorizada de momentos com trechos extraídos e frameworks mapeados.
**Quality Gate**: Momentos priorizados por impacto real; trechos incluem contexto suficiente.

### Etapa 2 — Reescrita Before/After
**Responsável**: coaching-rewriter (com input de specialists)
**Input**: Momentos selecionados + frameworks aplicáveis
**Ação**:
1. Para cada momento, produzir:
   - **BEFORE (O que aconteceu)**: Transcrição exata do que o closer disse/fez.
   - **Análise**: Por que isso não funcionou — qual foi o erro técnico.
   - **AFTER (Como deveria ter sido)**: Versão reescrita aplicando o framework correto.
   - **Por que funciona**: Explicação da lógica por trás da versão corrigida.
   - **Framework aplicado**: Referência ao framework utilizado na reescrita.
2. Manter o tom e estilo natural do closer na reescrita (não criar um roteiro artificial).
3. Para momentos de objeção, acionar objection-specialist para validar a reescrita.
4. Para momentos de preço, acionar pricing-anchoring-analyst para validar a reescrita.
**Output**: Documento de rewrites com before/after para cada momento.
**Quality Gate**: rewrite-quality (reescrita realista, framework corretamente aplicado, explicação clara).

### Etapa 3 — Validação de Realismo
**Responsável**: coaching-rewriter
**Input**: Documento de rewrites
**Ação**:
1. Revisar cada reescrita verificando se é realista e executável pelo closer.
2. Verificar se o tom da reescrita é compatível com o estilo do closer.
3. Confirmar que a reescrita leva em conta o contexto completo (o que o lead disse antes).
4. Testar mentalmente: "Se o closer dissesse exatamente isso, o lead responderia de forma diferente?"
5. Ajustar rewrites que soem artificiais ou desconectados do fluxo da conversa.
**Output**: Rewrites validados e ajustados para realismo.
**Quality Gate**: Cada rewrite passa no teste de realismo e naturalidade.

### Etapa 4 — Construção do Pacote de Coaching
**Responsável**: coaching-rewriter
**Input**: Rewrites validados + scorecard + causa raiz
**Ação**:
1. Organizar rewrites em ordem de prioridade de treinamento.
2. Adicionar contexto de coaching para cada rewrite:
   - Padrão comportamental que gerou o erro.
   - Exercício prático para treinar a correção.
   - Métrica para medir melhoria nas próximas calls.
3. Incluir resumo executivo com tema central de coaching (ex: "Closer precisa aprofundar diagnóstico antes de apresentar solução").
4. Gerar versão condensada (1 página) para feedback rápido.
**Output**: Pacote de coaching completo + versão condensada.
**Quality Gate**: coaching-delivery-standards (acionável, específico, respeitoso, com exercícios práticos).

### Etapa 5 — Registro e Disponibilização
**Responsável**: coaching-rewriter
**Input**: Pacote de coaching finalizado
**Ação**:
1. Registrar temas de coaching no histórico do closer.
2. Atualizar closer-skill-registry com áreas trabalhadas.
3. Disponibilizar pacote para o gestor e para o closer.
4. Criar entrada no coaching-log com data, temas e exercícios atribuídos.
**Output**: Pacote publicado + registries atualizados.
**Quality Gate**: Coaching registrado, closer notificado, exercícios com prazo definido.

## Templates de Output

- coaching-rewrite-package (before/after com análise e exercícios)
- coaching-summary-one-pager (versão condensada para feedback rápido)

## Registries Atualizados

- coaching-log-registry (sessão de coaching registrada)
- closer-skill-registry (gaps e temas trabalhados atualizados)

## Critérios de Conclusão

- [ ] 3-5 momentos críticos selecionados e priorizados por impacto
- [ ] Reescrita before/after completa para cada momento
- [ ] Rewrites validados por specialists nas áreas relevantes
- [ ] Teste de realismo aprovado para todos os rewrites
- [ ] Pacote de coaching com exercícios práticos gerado
- [ ] Registries atualizados e coaching disponibilizado

## Próximo Workflow

→ 06-full-funnel-call-audit.md (auditoria completa end-to-end — este workflow alimenta o master)
