# Checklist: Completude de Evidências do QA

> Garante que toda afirmação na auditoria tem trecho transcrito e minuto referenciado — sem opinião sem evidência.

---

## Itens de Verificação

### 1. Toda Afirmação com Trecho
- [ ] Cada ponto positivo cita o trecho exato que comprova a boa execução
- [ ] Cada ponto negativo cita o trecho exato onde ocorreu a falha
- [ ] Cada oportunidade perdida cita o momento onde deveria ter acontecido

**Critério de aprovação**: 100% das afirmações com pelo menos 1 trecho de suporte.
**Evidência necessária**: Contagem de afirmações vs. trechos citados.

---

### 2. Todo Trecho com Timestamp
- [ ] Cada trecho citado tem minuto:segundo de referência (ex: "14:23")
- [ ] Timestamps são verificáveis na gravação original
- [ ] Não há trechos "soltos" sem localização temporal

**Critério de aprovação**: 100% dos trechos com timestamp verificável.
**Evidência necessária**: Lista de timestamps e verificação por amostragem (mínimo 20%).

---

### 3. Contexto Suficiente
- [ ] O trecho não está isolado a ponto de perder o significado
- [ ] Pelo menos 1-2 falas anteriores estão incluídas para contexto
- [ ] A interação closer-lead está completa (pergunta e resposta, não só um lado)

**Critério de aprovação**: Trechos com contexto suficiente para compreensão autônoma.
**Evidência necessária**: Revisão de legibilidade dos trechos isoladamente.

---

### 4. Ausência de Opinião sem Suporte
- [ ] Nenhuma frase como "o closer não demonstrou interesse" sem trecho que comprove
- [ ] Nenhuma frase como "o rapport foi bom" sem evidência específica
- [ ] Adjetivos avaliativos sempre acompanhados de fato observável

**Critério de aprovação**: Zero opiniões sem evidência factual vinculada.
**Evidência necessária**: Busca textual por adjetivos avaliativos e verificação de suporte.

---

### 5. Score Justificado por Bloco
- [ ] Cada nota de bloco tem pelo menos 2 evidências de suporte
- [ ] A nota reflete a evidência (nota alta = evidências positivas, nota baixa = evidências de falha)
- [ ] Não há discrepância entre evidência apresentada e nota atribuída

**Critério de aprovação**: Coerência evidência-nota em 100% dos blocos.
**Evidência necessária**: Tabela [Bloco] → [Nota] → [Evidências] com checagem de coerência.

---

### 6. Momentos Ausentes Documentados
- [ ] Se um framework esperado não foi detectado, o relatório explica em que momento deveria ter aparecido
- [ ] A ausência de comportamento é documentada com o timestamp do momento onde era esperado
- [ ] "Não fez" tem a mesma exigência de evidência que "fez"

**Critério de aprovação**: Ausências documentadas com mesmo rigor que presenças.
**Evidência necessária**: Lista de ausências com momento esperado e contexto.

---

## Resumo de Aprovação

| Item | Status | Observação |
|------|--------|------------|
| Toda afirmação com trecho | ⬜ | |
| Todo trecho com timestamp | ⬜ | |
| Contexto suficiente | ⬜ | |
| Ausência de opinião sem suporte | ⬜ | |
| Score justificado por bloco | ⬜ | |
| Momentos ausentes documentados | ⬜ | |

**Resultado**: ⬜ Aprovado / ⬜ Reprovado — Necessita revisão

---

## Agente Responsável
`qa-agent` — Valida toda auditoria antes de publicar.

## Frequência
Aplicar em **100% das auditorias** como validação obrigatória.
