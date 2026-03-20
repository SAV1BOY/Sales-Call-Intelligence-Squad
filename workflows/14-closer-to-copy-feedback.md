# 14 — Closer to Copy Feedback

> Insights extraídos das calls para alimentar o Copy Squad com objeções reais e linguagem do lead.

## Objetivo

Produzir relatório de inteligência para o Copy Squad contendo as objeções mais frequentes verbalizadas pelos leads, frases exatas que revelam dores e desejos, linguagem real usada pelo público-alvo e gaps entre a promessa da copy e a realidade percebida na call, permitindo ao Copy Squad refinar páginas, emails e anúncios.

## Quando Executar

- Quinzenalmente ou mensalmente, consolidando insights de múltiplas calls.
- Quando identificada discrepância recorrente entre expectativa do lead e promessa da copy.
- Quando novo produto/oferta está em fase de ajuste de messaging.
- Quando taxa de conversão cai e suspeita-se de mismatch copy×call.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| revenue-intelligence-analyst | Responsável principal pela extração e organização dos insights |
| sales-chief | Valida relevância e prioriza recomendações para Copy Squad |

## Frameworks Utilizados

- voice-of-customer-extraction
- copy-reality-gap-analysis
- objection-to-copy-mapping

## Checklists Obrigatórios

- cross-squad-feedback-quality
- data-anonymization-checklist

## Etapas

### Etapa 1 — Mineração de Linguagem do Lead
**Responsável**: revenue-intelligence-analyst
**Input**: Transcrições segmentadas do período (foco nas fases de diagnóstico e objeção)
**Ação**:
1. Extrair citações diretas do lead em categorias:
   - **Dores**: Como o lead descreve seus problemas nas próprias palavras.
   - **Desejos**: O que o lead quer alcançar, na linguagem dele.
   - **Medos**: Preocupações e riscos mencionados.
   - **Objeções verbatim**: Exatamente como o lead verbaliza cada objeção.
   - **Comparações**: Como o lead compara com alternativas/concorrentes.
   - **Gatilhos de decisão**: O que fez o lead dizer "sim" (em calls ganhas).
2. Registrar cada citação com contexto mínimo (sem identificar o lead).
3. Agrupar por frequência (frases que aparecem em múltiplas calls).
4. Destacar linguagem inesperada que a copy atual não usa.
**Output**: Banco de citações categorizadas e rankeadas por frequência.
**Quality Gate**: Citações exatas (não parafraseadas); anonimizadas; agrupadas por frequência.

### Etapa 2 — Gap Analysis Copy vs. Realidade
**Responsável**: revenue-intelligence-analyst
**Input**: Banco de citações + materiais atuais de copy (se disponíveis)
**Ação**:
1. Comparar as dores mencionadas nas calls com as dores abordadas na copy.
2. Identificar gaps:
   - Dores reais não abordadas na copy.
   - Dores enfatizadas na copy que os leads não mencionam.
   - Linguagem da copy que difere da linguagem real do lead.
   - Promessas da copy que geram objeção na call.
3. Mapear objeções recorrentes para elementos da copy que as geram.
4. Identificar oportunidades: frases poderosas dos leads que poderiam ser usadas na copy.
**Output**: Relatório de gap analysis copy×realidade.
**Quality Gate**: Gaps apoiados por evidência de múltiplas calls; oportunidades identificadas.

### Etapa 3 — Produção do Pacote de Insights para Copy
**Responsável**: revenue-intelligence-analyst
**Input**: Banco de citações + gap analysis
**Ação**:
1. Compilar relatório para Copy Squad:
   - **Top 10 Frases do Lead**: As citações mais frequentes e impactantes.
   - **Top 5 Objeções Reais**: As objeções mais comuns verbatim.
   - **Gaps Identificados**: O que a copy diz vs. o que o lead sente.
   - **Oportunidades de Copy**: Frases e ângulos sugeridos com base na linguagem real.
   - **Palavras-Chave**: Termos que os leads usam e a copy deveria adotar.
   - **Alertas**: Promessas da copy que estão gerando problema na call.
2. Incluir contexto suficiente para o Copy Squad agir sem precisar ler transcrições.
3. Priorizar recomendações por impacto estimado na conversão.
**Output**: Pacote de insights para Copy Squad.
**Quality Gate**: cross-squad-feedback-quality (acionável, baseado em dados, priorizado).

### Etapa 4 — Validação e Entrega Cross-Squad
**Responsável**: sales-chief
**Input**: Pacote de insights
**Ação**:
1. Validar que os insights são precisos e representativos (não baseados em 1 call isolada).
2. Confirmar que recomendações são viáveis para o Copy Squad implementar.
3. Aprovar entrega e definir canal de comunicação.
4. Agendar follow-up para verificar implementação e impacto.
**Output**: Insights aprovados e entregues ao Copy Squad.
**Quality Gate**: Sales-chief aprovou; insights baseados em amostra representativa.

### Etapa 5 — Registro e Loop de Feedback
**Responsável**: revenue-intelligence-analyst
**Input**: Insights entregues
**Ação**:
1. Registrar entrega no cross-squad-feedback-registry.
2. Criar tracking de implementação (quais sugestões foram adotadas).
3. Na próxima rodada, medir se as mudanças na copy impactaram as calls.
4. Fechar loop: reportar resultado de volta ao Copy Squad.
**Output**: Registry atualizado + tracking de implementação criado.
**Quality Gate**: Loop de feedback planejado com métricas de acompanhamento.

## Templates de Output

- copy-intelligence-report (citações + gaps + oportunidades + recomendações)

## Registries Atualizados

- cross-squad-feedback-registry (feedback para Copy registrado)
- voice-of-customer-registry (banco de citações atualizado)

## Critérios de Conclusão

- [ ] Citações do lead extraídas e categorizadas de múltiplas calls
- [ ] Gap analysis copy×realidade realizada com evidências
- [ ] Pacote de insights compilado com top frases, objeções e oportunidades
- [ ] Insights validados pelo sales-chief e entregues ao Copy Squad
- [ ] Tracking de implementação criado para fechar o loop

## Próximo Workflow

→ 15-closer-to-traffic-feedback.md (insights para Traffic Squad)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | Citações categorizadas | Citações exatas (não parafraseadas), anonimizadas e agrupadas por frequência | Voltar a Etapa 1 para corrigir paráfrases ou anonimizar dados |
| Etapa 2 → Etapa 3 | Gaps apoiados por evidência | Gaps identificados com base em múltiplas calls; oportunidades de copy mapeadas | Voltar a Etapa 2 para buscar mais evidências em calls adicionais |
| Etapa 3 → Etapa 4 | cross-squad-feedback-quality | Pacote acionável, baseado em dados e priorizado por impacto | Voltar a Etapa 3 para reescrever recomendações vagas |
| Etapa 4 → Etapa 5 | Sales-chief aprovou | Insights representativos (não baseados em 1 call isolada); recomendações viáveis | Voltar a Etapa 3 para ampliar amostra ou ajustar recomendações |
| Etapa 5 → Conclusão | Loop de feedback planejado | Tracking de implementação criado com métricas de acompanhamento | Voltar a Etapa 5 para definir métricas |

## Decision Points
- Após Etapa 2: se gap crítico é identificado (promessa da copy gerando objeções em 30%+ das calls) → produzir alerta urgente para Copy Squad sem esperar relatório completo; se gaps são moderados → seguir fluxo normal
- Após Etapa 3: se insights revelam oportunidade de novo ângulo de copy com alto potencial → priorizar esta recomendação no topo do pacote; se insights são incrementais → consolidar como melhorias contínuas
- Após Etapa 5: se Copy Squad implementou recomendações anteriores → medir impacto na próxima rodada; se ignorou → escalar para reunião de alinhamento

## Escalation Triggers
- Se copy está gerando expectativa falsa que resulta em perda recorrente de deals → pausar, escalar para sales-chief para comunicação urgente ao Copy Squad e C-Level
- Se linguagem dos leads mudou significativamente (novo perfil de público) e copy está desatualizada → pausar, escalar para sales-chief para solicitar revisão completa de copy
- Se dados de anonimização falham e citações identificáveis são incluídas → pausar, escalar para sales-chief para revisão de compliance antes da entrega
