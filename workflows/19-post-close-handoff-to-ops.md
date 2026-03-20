# 19 — Post-Close Handoff to Ops

> Handoff estruturado pós-venda do closer para o time de Operações/Customer Success.

## Objetivo

Garantir que após o fechamento da venda, todas as informações relevantes da call sejam transmitidas de forma estruturada ao time de Operações/Customer Success, incluindo expectativas alinhadas, promessas feitas, perfil do cliente, dores principais e timeline esperada, prevenindo churn por desalinhamento entre venda e entrega.

## Quando Executar

- Imediatamente após toda call que resultar em venda fechada.
- Dentro de 24h do fechamento, antes que o onboarding comece.
- Quando há upsell ou cross-sell para cliente existente (atualizar contexto).

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| sdr-handoff-analyst | Responsável por extrair, organizar e entregar o pacote de handoff |
| sales-chief | Valida completude e qualidade do handoff antes da entrega |

## Frameworks Utilizados

- post-close-handoff-protocol
- expectation-documentation-model
- promise-tracking-framework

## Checklists Obrigatórios

- handoff-quality
- promise-completeness-checklist

## Etapas

### Etapa 1 — Extração de Informações da Call
**Responsável**: sdr-handoff-analyst
**Input**: Transcrição da call de fechamento + dados do CRM + anotações do closer
**Ação**:
1. Extrair da transcrição as informações críticas para Ops:
   - **Perfil do Cliente**: Quem é, o que faz, tamanho do negócio, experiência prévia.
   - **Dor Principal**: Qual problema motivou a compra (nas palavras do cliente).
   - **Resultado Esperado**: O que o cliente espera alcançar e em que prazo.
   - **Promessas Feitas**: Tudo que o closer comprometeu durante a call (features, suporte, prazos, bônus).
   - **Condições Especiais**: Descontos, parcelamentos, condições únicas negociadas.
   - **Preocupações Residuais**: Medos ou dúvidas que o cliente ainda tinha no momento do close.
   - **Estilo de Comunicação**: Como o cliente prefere ser tratado (formal/informal, detalhista/objetivo).
2. Citar trechos exatos da transcrição para cada informação extraída.
3. Identificar promessas implícitas (coisas que o closer insinuou sem confirmar explicitamente).
**Output**: Dossiê de informações extraídas com citações.
**Quality Gate**: Todas as categorias preenchidas; promessas (explícitas e implícitas) documentadas.

### Etapa 2 — Verificação de Promessas vs. Realidade
**Responsável**: sdr-handoff-analyst
**Input**: Promessas extraídas + termos reais do produto/serviço
**Ação**:
1. Comparar cada promessa feita pelo closer com o que o produto/serviço realmente entrega.
2. Classificar cada promessa:
   - **Alinhada**: Promessa compatível com a entrega real.
   - **Parcialmente alinhada**: Promessa exagerada mas endereçável.
   - **Desalinhada**: Promessa que não pode ser cumprida — risco de churn.
3. Para promessas desalinhadas, criar alerta de risco com recomendação:
   - Ops precisa gerenciar expectativa proativamente.
   - Sales-chief precisa conversar com o closer sobre promessas irreais.
4. Registrar promessas desalinhadas para feedback ao closer (workflow 05).
**Output**: Mapa de promessas com classificação de alinhamento + alertas de risco.
**Quality Gate**: promise-completeness-checklist (todas as promessas verificadas, alertas criados).

### Etapa 3 — Montagem do Pacote de Handoff
**Responsável**: sdr-handoff-analyst
**Input**: Dossiê de informações + mapa de promessas
**Ação**:
1. Compilar pacote de handoff estruturado para Ops:
   - **Resumo do Cliente** (1 parágrafo): Quem é e por que comprou.
   - **Expectativas Documentadas**: O que o cliente espera, com prazos.
   - **Promessas do Closer**: Lista completa com status de alinhamento.
   - **Alertas de Risco**: Pontos que demandam atenção no onboarding.
   - **Recomendações de Abordagem**: Como Ops deve tratar este cliente (tom, frequência, prioridades).
   - **Citações-Chave**: 3-5 frases do cliente que Ops deve conhecer.
   - **Gatilhos de Satisfação**: O que vai fazer este cliente se sentir bem atendido.
   - **Gatilhos de Frustração**: O que pode fazer este cliente se frustar.
2. Formatar para fácil consumo pelo time de Ops (bullet points, não texto corrido).
**Output**: Pacote de handoff formatado e completo.
**Quality Gate**: handoff-quality (todas as seções preenchidas, alertas incluídos, formato consumível).

### Etapa 4 — Validação e Entrega
**Responsável**: sales-chief
**Input**: Pacote de handoff
**Ação**:
1. Revisar completude e precisão do pacote.
2. Validar que alertas de risco estão adequadamente sinalizados.
3. Aprovar entrega ao time de Ops.
4. Entregar pacote ao responsável pelo onboarding do cliente.
5. Confirmar recebimento e entendimento pelo Ops.
**Output**: Pacote entregue e confirmado pelo Ops.
**Quality Gate**: Ops confirmou recebimento e não tem dúvidas pendentes.

### Etapa 5 — Registro e Follow-up
**Responsável**: sdr-handoff-analyst
**Input**: Pacote entregue
**Ação**:
1. Registrar handoff no handoff-registry com data e status.
2. Se houver promessas desalinhadas, criar ticket de feedback para o closer.
3. Agendar check-in com Ops em 7 dias para verificar se informações foram úteis.
4. Registrar feedback do Ops sobre qualidade do handoff para melhoria contínua.
**Output**: Registry atualizado + follow-up agendado.
**Quality Gate**: Handoff registrado; follow-up com Ops planejado.

## Templates de Output

- post-close-handoff-package (resumo + expectativas + promessas + alertas + recomendações)

## Registries Atualizados

- handoff-registry (handoff pós-venda registrado)
- promise-tracking-registry (promessas do closer documentadas)
- closer-feedback-registry (promessas desalinhadas sinalizadas)

## Critérios de Conclusão

- [ ] Informações da call extraídas em todas as categorias obrigatórias
- [ ] Promessas do closer verificadas contra realidade do produto
- [ ] Alertas de risco criados para promessas desalinhadas
- [ ] Pacote de handoff compilado e formatado para Ops
- [ ] Pacote entregue e confirmado pelo time de Ops
- [ ] Follow-up de 7 dias agendado

## Próximo Workflow

→ Nenhum workflow sequencial. Este é um workflow terminal por deal. Feedback de promessas desalinhadas alimenta → 05-coaching-rewrite-loop.md
