# Checklist: Especificidade do Coaching

> Garante que todo feedback de coaching é específico, referenciando minuto, trecho literal e evidência concreta — nunca genérico.

---

## Itens de Verificação

### 1. Referência Temporal Precisa
- [ ] Todo ponto de coaching menciona o minuto exato da call (ex: "aos 12:34")
- [ ] Momentos críticos são delimitados com início e fim (ex: "de 08:20 a 09:45")
- [ ] Não há referências vagas como "no meio da call" ou "lá pra frente"

**Critério de aprovação**: 100% dos pontos de coaching com timestamp preciso.
**Evidência necessária**: Lista de timestamps referenciados no documento de coaching.

---

### 2. Trecho Literal da Call
- [ ] Cada ponto de feedback inclui a fala exata do closer (entre aspas)
- [ ] A fala do lead correspondente também está transcrita quando relevante
- [ ] Contexto imediato (2-3 falas antes/depois) está presente para entendimento

**Critério de aprovação**: Mínimo de 1 trecho literal por ponto de coaching.
**Evidência necessária**: Trechos transcritos lado a lado com o feedback.

---

### 3. Diagnóstico Baseado em Evidência
- [ ] O problema identificado é descrito com base no que foi dito/feito, não em suposição
- [ ] A causa raiz está conectada a um comportamento observável na gravação
- [ ] Não há linguagem interpretativa sem suporte factual ("parece que você não se importou")

**Critério de aprovação**: Zero afirmações sem evidência direta da call.
**Evidência necessária**: Mapeamento causa-raiz → trecho da call.

---

### 4. Comparação com Framework Esperado
- [ ] O feedback mostra o que foi feito vs. o que o framework recomenda
- [ ] A técnica correta é nomeada (ex: "Miner — pergunta de consequência")
- [ ] O gap entre execução e padrão está quantificado quando possível

**Critério de aprovação**: Framework de referência explícito em cada ponto.
**Evidência necessária**: Tabela [Feito] vs [Esperado] por ponto.

---

### 5. Ausência de Generalismo
- [ ] Nenhum feedback usa frases como "melhore sua escuta ativa" sem exemplo
- [ ] Nenhum feedback diz "precisa melhorar o rapport" sem apontar o momento específico
- [ ] Nenhum feedback lista habilidades genéricas sem vincular a um trecho da call

**Critério de aprovação**: Zero instâncias de feedback genérico.
**Evidência necessária**: Revisão textual do documento de coaching completo.

---

## Resumo de Aprovação

| Item | Status | Observação |
|------|--------|------------|
| Referência temporal precisa | ⬜ | |
| Trecho literal da call | ⬜ | |
| Diagnóstico baseado em evidência | ⬜ | |
| Comparação com framework | ⬜ | |
| Ausência de generalismo | ⬜ | |

**Resultado**: ⬜ Aprovado / ⬜ Reprovado — Necessita revisão

---

## Agente Responsável
`coaching-agent` — Valida antes de entregar feedback ao closer.

## Frequência
Aplicar em **100% dos documentos de coaching** antes da entrega.
