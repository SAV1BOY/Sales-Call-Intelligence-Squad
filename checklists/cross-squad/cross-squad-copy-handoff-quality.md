# Checklist: Qualidade do Handoff para Copy Squad

> Garante que os insights enviados ao Copy Squad são acionáveis — objeções reais, frases literais do lead e palavras de ativação extraídas das calls.

---

## Itens de Verificação

### 1. Objeções Reais Documentadas
- [ ] Objeções são transcritas literalmente, não parafraseadas
- [ ] Cada objeção tem frequência (em quantas calls apareceu)
- [ ] Objeções estão categorizadas (preço, timing, autoridade, necessidade, confiança)
- [ ] O contexto da objeção está claro (em que momento da call surge)

**Critério de aprovação**: Mínimo de 5 objeções reais com frequência e categoria.
**Evidência necessária**: Tabela de objeções com trecho literal, frequência e categoria.

---

### 2. Frases Literais do Lead
- [ ] Frases exatas que o lead usa para descrever seu problema estão transcritas
- [ ] Frases de resistência estão separadas de frases de interesse
- [ ] Vocabulário recorrente está destacado (as palavras que os leads realmente usam)
- [ ] Frases estão agrupadas por tema/dor

**Critério de aprovação**: Mínimo de 10 frases literais categorizadas.
**Evidência necessária**: Biblioteca de frases com fonte (call ID e minuto).

---

### 3. Palavras de Ativação Identificadas
- [ ] Palavras que geraram engajamento visível do lead estão mapeadas
- [ ] Palavras que causaram resistência ou desconexão estão sinalizadas
- [ ] Há contraste entre linguagem que funciona vs. linguagem que repele

**Critério de aprovação**: Lista de palavras de ativação positiva e negativa com evidência.
**Evidência necessária**: Pares [Palavra/Frase] → [Reação do Lead] → [Timestamp].

---

### 4. Ângulos de Dor Validados
- [ ] As dores mencionadas nas copies estão validadas (leads realmente mencionam?)
- [ ] Dores não previstas pelo Copy Squad estão documentadas como oportunidade
- [ ] Há ranking de dores por frequência e intensidade emocional

**Critério de aprovação**: Mapa de dores validadas vs. não-validadas com dados de frequência.
**Evidência necessária**: Tabela de dores com status de validação e contagem.

---

### 5. Formato Acionável para o Copy Squad
- [ ] O documento está organizado por tipo de peça (headline, lead, body, CTA)
- [ ] Cada insight tem sugestão de aplicação ("use esta frase como headline de...")
- [ ] O Copy Squad não precisa interpretar — a ação está clara

**Critério de aprovação**: 100% dos insights com sugestão de aplicação prática.
**Evidência necessária**: Mapeamento insight → aplicação sugerida → peça de copy.

---

## Resumo de Aprovação

| Item | Status | Observação |
|------|--------|------------|
| Objeções reais documentadas | ⬜ | |
| Frases literais do lead | ⬜ | |
| Palavras de ativação | ⬜ | |
| Ângulos de dor validados | ⬜ | |
| Formato acionável | ⬜ | |

**Resultado**: ⬜ Aprovado / ⬜ Reprovado — Necessita revisão

---

## Agente Responsável
`cross-squad-agent` — Valida antes de enviar insights ao Copy Squad.

## Frequência
Aplicar em **100% dos handoffs para Copy Squad** (tipicamente semanal ou quinzenal).
