# Checklist: Calibração de Score do QA

> Garante que scores são calibrados e consistentes — a mesma call recebe o mesmo score independente de quem audita.

---

## Itens de Verificação

### 1. Escala Padronizada Aplicada
- [ ] O scorecard de 100 pontos com 10 blocos padrão foi utilizado
- [ ] Cada bloco usa a mesma faixa de pontuação definida no padrão (ex: 0-10 por bloco)
- [ ] Não há blocos com peso alterado sem justificativa documentada

**Critério de aprovação**: Scorecard padrão aplicado sem modificações não-autorizadas.
**Evidência necessária**: Comparação do scorecard usado vs. template padrão.

---

### 2. Critérios Objetivos por Faixa
- [ ] Cada faixa de nota tem critérios objetivos (ex: "8-10: executou com excelência, lead engajou, resultado positivo")
- [ ] O auditor aplicou os critérios da faixa, não impressão pessoal
- [ ] Notas limítrofes (ex: 6 vs 7) têm justificativa do critério decisivo

**Critério de aprovação**: Critérios de faixa documentados e aplicados por bloco.
**Evidência necessária**: Mapeamento nota → critério da faixa → evidência da call.

---

### 3. Teste de Consistência Inter-Auditor
- [ ] Calls de calibração foram auditadas por pelo menos 2 auditores/agentes
- [ ] Variação máxima entre auditores é de 5 pontos no score total
- [ ] Variação máxima por bloco individual é de 2 pontos
- [ ] Discrepâncias acima do limite foram discutidas e resolvidas

**Critério de aprovação**: Variação inter-auditor dentro dos limites (5 total, 2 por bloco).
**Evidência necessária**: Tabela comparativa de scores entre auditores para calls de calibração.

---

### 4. Ancoragem em Calls de Referência
- [ ] Calls-âncora estão definidas para cada faixa (ruim, mediana, boa, excelente)
- [ ] O auditor comparou a call atual com as calls-âncora da faixa
- [ ] O score atribuído é coerente com o posicionamento entre as âncoras

**Critério de aprovação**: Calls-âncora consultadas e score coerente com posição relativa.
**Evidência necessária**: Referência às calls-âncora na justificativa do score.

---

### 5. Ausência de Inflação/Deflação Sistemática
- [ ] A distribuição de scores do auditor/agente segue curva esperada (não tudo 80+, não tudo abaixo de 50)
- [ ] Não há tendência de generosidade ou severidade excessiva
- [ ] Média do auditor está dentro de 1 desvio padrão da média geral do squad

**Critério de aprovação**: Distribuição de scores sem viés sistemático.
**Evidência necessária**: Histograma de scores do auditor vs. distribuição geral.

---

### 6. Estabilidade Temporal
- [ ] O mesmo tipo de call recebe score similar ao longo do tempo
- [ ] Mudanças de critério são documentadas e comunicadas (não silenciosas)
- [ ] Re-auditoria de calls antigas produz scores dentro da margem de 5 pontos

**Critério de aprovação**: Variação temporal dentro de 5 pontos para calls equivalentes.
**Evidência necessária**: Re-auditoria periódica de calls antigas como controle.

---

## Resumo de Aprovação

| Item | Status | Observação |
|------|--------|------------|
| Escala padronizada aplicada | ⬜ | |
| Critérios objetivos por faixa | ⬜ | |
| Consistência inter-auditor | ⬜ | |
| Ancoragem em calls de referência | ⬜ | |
| Ausência de inflação/deflação | ⬜ | |
| Estabilidade temporal | ⬜ | |

**Resultado**: ⬜ Aprovado / ⬜ Reprovado — Necessita recalibração

---

## Agente Responsável
`qa-agent` — Executa calibração periódica e valida scores antes de publicar.

## Frequência
- Checagem individual: **100% das auditorias**
- Calibração inter-auditor: **quinzenal** com calls de controle
- Revisão de distribuição: **mensal** com análise estatística
