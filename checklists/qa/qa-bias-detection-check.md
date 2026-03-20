# Checklist: Detecção de Viés do QA

> Garante que vieses do auditor são detectados e neutralizados — favorecimento de método, halo effect, viés de confirmação.

---

## Itens de Verificação

### 1. Viés de Favorecimento de Framework
- [ ] O auditor não supervaloriza um framework em detrimento de outros igualmente válidos
- [ ] Calls que usam frameworks diferentes do preferido do auditor não são penalizadas
- [ ] A avaliação reconhece execução competente independente do framework escolhido pelo closer

**Critério de aprovação**: Scores equilibrados entre calls de diferentes frameworks quando a execução é equivalente.
**Evidência necessária**: Comparação de scores médios por framework do auditor — variação máxima de 5 pontos.

---

### 2. Halo Effect
- [ ] Um bom início de call não infla automaticamente os scores dos blocos seguintes
- [ ] Uma venda fechada não resulta em nota alta automática para todos os blocos
- [ ] Cada bloco é avaliado independentemente, sem contaminação dos outros

**Critério de aprovação**: Blocos avaliados com evidência independente, sem correlação artificial.
**Evidência necessária**: Verificação de que blocos fracos recebem nota baixa mesmo em calls com resultado positivo.

---

### 3. Viés de Resultado (Outcome Bias)
- [ ] Calls ganhas não recebem automaticamente score alto
- [ ] Calls perdidas não recebem automaticamente score baixo
- [ ] A análise separa qualidade de execução de resultado comercial
- [ ] Calls perdidas com boa execução são reconhecidas como tal

**Critério de aprovação**: Correlação entre resultado e score não é 1:1 — existem calls ganhas com score médio e perdidas com score alto.
**Evidência necessária**: Matriz resultado (ganhou/perdeu) vs. score com exemplos de cada quadrante.

---

### 4. Viés de Confirmação
- [ ] O auditor não busca apenas evidências que confirmem sua impressão inicial
- [ ] Evidências que contradizem o diagnóstico inicial são documentadas
- [ ] O relatório inclui pontos positivos mesmo em calls ruins e pontos negativos mesmo em calls boas

**Critério de aprovação**: Todo relatório tem pelo menos 2 pontos positivos E 2 pontos de melhoria.
**Evidência necessária**: Contagem de pontos positivos e negativos por relatório.

---

### 5. Viés de Recência
- [ ] O final da call não tem peso desproporcional na avaliação
- [ ] Blocos do início (rapport, discovery) recebem a mesma atenção que blocos do fim (fechamento)
- [ ] O auditor não é excessivamente influenciado pelo último momento marcante

**Critério de aprovação**: Distribuição equilibrada de evidências ao longo de toda a call.
**Evidência necessária**: Mapa de timestamps citados — cobertura mínima de 80% da duração da call.

---

### 6. Viés de Afinidade com o Closer
- [ ] O closer não recebe tratamento diferente por ser "favorito" ou "problemático"
- [ ] Closers novos não são avaliados com mais severidade que veteranos
- [ ] O histórico do closer não contamina a avaliação da call individual

**Critério de aprovação**: Score da call avaliado isoladamente, sem ajuste por histórico.
**Evidência necessária**: Blindagem de identidade em calls de calibração (auditar sem saber quem é o closer).

---

## Resumo de Aprovação

| Item | Status | Observação |
|------|--------|------------|
| Favorecimento de framework | ⬜ | |
| Halo effect | ⬜ | |
| Viés de resultado | ⬜ | |
| Viés de confirmação | ⬜ | |
| Viés de recência | ⬜ | |
| Viés de afinidade | ⬜ | |

**Resultado**: ⬜ Aprovado / ⬜ Reprovado — Necessita revisão e recalibração

---

## Agente Responsável
`qa-agent` — Auto-avaliação em cada auditoria + revisão cruzada mensal.

## Frequência
- Auto-checagem: **100% das auditorias**
- Análise de viés estatístico: **mensal** com revisão de distribuição de scores por closer, framework e resultado
