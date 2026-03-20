# 17 — Lost Deal Recovery

> Recuperação de deals perdidos com diagnóstico, estratégia e script de reativação.

## Objetivo

Analisar deals perdidos para identificar quais são recuperáveis, diagnosticar o que precisa mudar na abordagem, produzir estratégia de reativação personalizada e script de follow-up, maximizando a recuperação de revenue de leads que já demonstraram interesse.

## Quando Executar

- Após auditoria de call perdida (workflow 06 + workflow 10) quando o deal é classificado como "potencialmente recuperável".
- Semanalmente, como revisão de pipeline de deals perdidos na semana.
- Quando há mudança na oferta que resolve objeção que causou perdas anteriores.
- Quando closer diferente está disponível para tentar abordagem alternativa.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| win-loss-miner | Avalia recuperabilidade e identifica ângulo de reativação |
| deal-risk-doctor | Diagnostica o que precisa mudar para a recuperação funcionar |
| coaching-rewriter | Produz script de reativação personalizado |

## Frameworks Utilizados

- deal-risk-diagnosis
- deal-recovery-protocol
- reactivation-strategy-model

## Checklists Obrigatórios

- deal-recovery-viability-checklist
- reactivation-script-quality

## Etapas

### Etapa 1 — Triagem de Recuperabilidade
**Responsável**: win-loss-miner
**Input**: Deals perdidos do período + auditorias + causa raiz (workflow 04/10)
**Ação**:
1. Listar todos os deals perdidos no período com metadados (closer, lead, produto, ticket, causa raiz).
2. Avaliar recuperabilidade de cada deal com critérios:
   - A dor do lead ainda existe? (Sim/Provável/Improvável)
   - O lead tem capacidade de investir? (Sim/Parcial/Não)
   - O relacionamento foi preservado? (Bom/Neutro/Danificado)
   - A causa da perda é endereçável? (Sim/Parcial/Não)
   - Quanto tempo desde a perda? (<7 dias / 7-30 dias / 30+ dias)
3. Classificar: alta recuperabilidade, média, baixa, não recuperável.
4. Priorizar pela combinação de recuperabilidade × ticket.
**Output**: Lista priorizada de deals com score de recuperabilidade.
**Quality Gate**: deal-recovery-viability-checklist (cada critério avaliado com evidência).

### Etapa 2 — Diagnóstico de Mudança Necessária
**Responsável**: deal-risk-doctor
**Input**: Deals priorizados + auditorias + transcrições originais
**Ação**:
1. Para cada deal de alta/média recuperabilidade, diagnosticar:
   - O que causou a perda (causa raiz do workflow 04).
   - O que precisa ser diferente na nova abordagem.
   - Que informação nova pode ser alavancada.
   - Que objeção precisa ser preemptivamente endereçada.
   - Se deve ser o mesmo closer ou um diferente.
2. Definir a estratégia de reativação para cada deal:
   - Abordagem direta (novo contato com proposta ajustada).
   - Abordagem indireta (conteúdo de valor antes de proposta).
   - Abordagem por evento (mudança na oferta, promoção, case novo).
3. Registrar precauções (ex: lead pediu para não ser contatado, lead escolheu concorrente).
**Output**: Diagnóstico + estratégia de reativação por deal.
**Quality Gate**: Estratégia alinhada com causa raiz; precauções documentadas.

### Etapa 3 — Produção de Script de Reativação
**Responsável**: coaching-rewriter
**Input**: Diagnóstico + transcrição original + estratégia definida
**Ação**:
1. Para cada deal priorizado, produzir script de reativação:
   - **Abertura**: Como reabrir contato sem parecer desesperado (referência a algo da conversa original).
   - **Reconexão**: Demonstrar que lembra do lead e de sua situação.
   - **Novo ângulo**: Apresentar o que mudou (na oferta, no contexto ou na abordagem).
   - **Endereçamento preemptivo**: Tratar a objeção que causou a perda antes que ressurja.
   - **Call to action**: Proposta clara de próximo passo.
2. Personalizar com citações da call original (mostrar que ouviu).
3. Manter tom respeitoso e não-pressurante.
4. Produzir versões para diferentes canais (WhatsApp, email, ligação).
**Output**: Scripts de reativação personalizados por deal e canal.
**Quality Gate**: reactivation-script-quality (personalizado, respeitoso, endereça causa raiz).

### Etapa 4 — Briefing do Closer
**Responsável**: deal-risk-doctor
**Input**: Diagnóstico + scripts + transcrição original
**Ação**:
1. Produzir briefing para o closer que fará a reativação:
   - Resumo da call original (o que deu certo e o que deu errado).
   - O que o lead disse que importa (citações-chave).
   - Estratégia aprovada e script sugerido.
   - Armadilhas a evitar (erros da call original que não devem se repetir).
   - Resultado esperado e critérios de sucesso.
2. Se o closer for diferente do original, incluir contexto completo.
**Output**: Briefing do closer pronto para execução.
**Quality Gate**: Briefing é autocontido; closer pode executar sem ler a transcrição inteira.

### Etapa 5 — Tracking e Registro
**Responsável**: win-loss-miner
**Input**: Deals em recuperação
**Ação**:
1. Registrar cada tentativa de recuperação no deal-recovery-registry.
2. Criar tracking de resultado: contactou, respondeu, agendou nova call, fechou, não recuperou.
3. Após resultado, registrar e calcular taxa de recuperação do período.
4. Alimentar workflow 09 ou 10 se houver nova call (ganha ou perdida novamente).
**Output**: Registry atualizado + tracking de resultado ativo.
**Quality Gate**: Todos os deals em recuperação estão sendo rastreados.

## Templates de Output

- deal-recovery-package (triagem + diagnóstico + scripts + briefing)

## Registries Atualizados

- deal-recovery-registry (deals em recuperação com status)
- revenue-recovery-metrics (taxa de recuperação e revenue recuperado)

## Critérios de Conclusão

- [ ] Deals perdidos triados por recuperabilidade com critérios objetivos
- [ ] Diagnóstico de mudança necessária para cada deal priorizado
- [ ] Scripts de reativação personalizados produzidos
- [ ] Briefing do closer preparado para execução
- [ ] Tracking de resultado ativo para cada deal em recuperação

## Próximo Workflow

→ 06-full-funnel-call-audit.md (se a call de reativação acontecer, auditar normalmente)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | deal-recovery-viability-checklist | Cada critério de recuperabilidade avaliado com evidência; priorização por recuperabilidade × ticket | Voltar a Etapa 1 para reavaliar deals sem evidência suficiente |
| Etapa 2 → Etapa 3 | Estratégia alinhada com causa raiz | Diagnóstico claro do que precisa mudar; precauções documentadas | Voltar a Etapa 2 para aprofundar diagnóstico |
| Etapa 3 → Etapa 4 | reactivation-script-quality | Script personalizado, respeitoso e que endereça causa raiz; versões por canal | Voltar a Etapa 3 para reescrever scripts genéricos ou pressurantes |
| Etapa 4 → Etapa 5 | Briefing autocontido | Closer pode executar sem ler transcrição inteira; armadilhas sinalizadas | Voltar a Etapa 4 para completar contexto faltante |
| Etapa 5 → Conclusão | Tracking ativo | Todos os deals em recuperação rastreados com status atualizado | Voltar a Etapa 5 para incluir deals não rastreados |

## Decision Points
- Após Etapa 1: se deal é classificado como "não recuperável" → arquivar e alimentar banco de padrões de perda; se "alta recuperabilidade" → priorizar para Etapa 2 imediata
- Após Etapa 2: se causa da perda foi relacionamento danificado → designar closer diferente para reativação; se causa foi objeção endereçável → manter mesmo closer com novo ângulo
- Após Etapa 3: se lead pediu explicitamente para não ser contatado → respeitar e não prosseguir com reativação; se lead está aberto → seguir com script aprovado

## Escalation Triggers
- Se deal de alto ticket (top 10% do pipeline) é perdido e classificado como recuperável → pausar, escalar para sales-chief para supervisão direta da estratégia de recuperação
- Se taxa de recuperação do período cai abaixo de 10% → pausar, escalar para sales-chief para revisar qualidade dos diagnósticos e scripts
- Se closer reporta que lead reagiu negativamente à tentativa de reativação → pausar, escalar para deal-risk-doctor para reavaliar abordagem antes de nova tentativa
