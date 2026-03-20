# Checklist: Consistência Metodológica do QA

> Garante que não há conflito entre métodos aplicados na mesma auditoria — Miner e Belfort não contradizem, frameworks coexistem sem incoerência.

---

## Itens de Verificação

### 1. Frameworks Identificados sem Conflito
- [ ] Todos os frameworks detectados na call estão listados (Miner, Belfort, SPIN, Sandler, etc.)
- [ ] Não há recomendação de um framework que contradiz outro usado na mesma análise
- [ ] Quando dois frameworks se aplicam ao mesmo momento, a prioridade está justificada

**Critério de aprovação**: Zero contradições entre frameworks na mesma auditoria.
**Evidência necessária**: Mapa de frameworks aplicados por momento da call com checagem de conflito.

---

### 2. Critérios de Avaliação Uniformes
- [ ] O mesmo comportamento é avaliado pelo mesmo critério ao longo de toda a auditoria
- [ ] Não há mudança de régua no meio do relatório (ex: exigir SPIN no início e Miner no fim para o mesmo tipo de pergunta)
- [ ] O padrão de avaliação está declarado no início do relatório

**Critério de aprovação**: Régua de avaliação consistente do início ao fim.
**Evidência necessária**: Declaração do padrão no cabeçalho e checagem cruzada.

---

### 3. Terminologia Padronizada
- [ ] Os mesmos termos são usados de forma consistente (não alterna entre "rapport" e "conexão inicial" sem definir)
- [ ] Labels de score usam a mesma nomenclatura do scorecard padrão
- [ ] Frameworks são referenciados pelo nome oficial, não apelidos ambíguos

**Critério de aprovação**: Glossário respeitado ao longo de todo o documento.
**Evidência necessária**: Checagem de termos contra o glossário padrão do squad.

---

### 4. Coerência entre Diagnóstico e Recomendação
- [ ] Se o diagnóstico aponta falha em discovery (Miner), a recomendação não sugere apenas técnica de fechamento (Belfort)
- [ ] A recomendação ataca a causa raiz, não um sintoma de outro framework
- [ ] O framework da recomendação é compatível com o framework do diagnóstico

**Critério de aprovação**: 100% das recomendações alinhadas ao framework do diagnóstico.
**Evidência necessária**: Tabela [Diagnóstico + Framework] → [Recomendação + Framework].

---

### 5. Pesos e Pontuações sem Sobreposição
- [ ] Nenhum comportamento é pontuado duas vezes por frameworks diferentes
- [ ] Se um momento é avaliado por dois frameworks, o peso total não excede o máximo do bloco
- [ ] A soma dos pontos é consistente com a escala (total = 100)

**Critério de aprovação**: Soma dos pontos válida sem dupla contagem.
**Evidência necessária**: Planilha de pontuação com verificação de sobreposição.

---

## Resumo de Aprovação

| Item | Status | Observação |
|------|--------|------------|
| Frameworks sem conflito | ⬜ | |
| Critérios uniformes | ⬜ | |
| Terminologia padronizada | ⬜ | |
| Coerência diagnóstico-recomendação | ⬜ | |
| Pesos sem sobreposição | ⬜ | |

**Resultado**: ⬜ Aprovado / ⬜ Reprovado — Necessita revisão

---

## Agente Responsável
`qa-agent` — Valida toda auditoria antes de publicar.

## Frequência
Aplicar em **100% das auditorias** antes de liberar o relatório final.
