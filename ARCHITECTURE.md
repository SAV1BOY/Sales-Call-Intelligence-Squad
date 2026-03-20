# ARCHITECTURE.md — Sales Call Intelligence Squad

## Visão Geral

O Sales Call Intelligence Squad é o sistema operacional de inteligência comercial do MMOS.
Ele transforma calls de vendas high ticket em diagnósticos acionáveis, coaching específico,
padrões replicáveis e melhoria contínua — conectando-se a 8 squads para otimizar o funil inteiro.

**Fluxo central:**
```
Call/Transcrição → Diagnóstico por etapa → Framework detection → Score →
Root cause → Rewrite → Playbook update → Registry → Coaching → Melhoria
```

---

## Princípios Arquiteturais

### 1. phase-first
Cada framework entra na fase correta da call. SPIN opera em discovery, não em closing.
Belfort opera em certeza e looping, não em rapport. Cole Gordon opera em frame e diagnóstico.
O `config.yaml` roteia especialistas por fase para evitar conflitos metodológicos.

### 2. evidence-over-opinion
Toda crítica aponta trecho exato da transcrição, minuto/timestamp e evidência concreta.
Sem evidência, a análise não é publicada. "Achei que o rapport foi fraco" não existe —
existe "No minuto 2:14, o closer não fez pergunta de conexão e foi direto ao produto".

### 3. score-before-advice
Primeiro pontua com o scorecard de 100 pontos (10 blocos), depois aconselha.
Sem score, não há coaching válido. O score é a base objetiva para qualquer feedback.

### 4. rewrite-the-moment
Sempre reescreve a fala ideal para os momentos críticos (antes/depois).
Closer aprende mais vendo a reescrita da própria fala do que recebendo conselho genérico.
Formato obrigatório: [ANTES — trecho real] → [DEPOIS — reescrita ideal] + justificativa.

### 5. objection-is-a-symptom
Objeção é efeito, não causa. "Não tenho dinheiro" pode ser discovery rasa, falta de valor percebido,
pitch desconectado da dor, ou rapport insuficiente. O squad diagnostica a causa raiz, não a objeção.

### 6. the-call-starts-before-the-call
Briefing, handoff SDR→closer e contexto do lead importam tanto quanto a call.
Um handoff ruim contamina toda a call. O squad audita o pré-call também.

### 7. post-call-learning-is-mandatory
Toda call ensina algo para o sistema. Win patterns, loss patterns, objeções novas,
frases que funcionaram — tudo é registrado e alimenta o sistema.

### 8. closer-performance-is-systemic
O problema pode estar no lead (tráfego), na oferta (C-Level), no pitch (copy),
no SDR (handoff), no pricing (estratégia) ou no closer (skill). O squad diagnostica
em qual camada está o problema, não culpa automaticamente o closer.

---

## Scorecard Mestre — 100 Pontos / 10 Blocos

O scorecard é a espinha dorsal de toda auditoria. Cada call é pontuada em 10 blocos:

| # | Bloco | Pontos | O que avalia |
|---|-------|--------|-------------|
| 1 | Rapport / Abertura | 8 | Quebra de gelo, postura, conexão, energia |
| 2 | Primeiro Pacto / Frame | 8 | 3 intenções, agenda, frame de liderança |
| 3 | Diagnóstico SPIN / Profundidade | 18 | Situação, problema, implicação, need-payoff, NEPQ |
| 4 | Ampliação da Dor / Implicação | 8 | Consequências, urgência, custo da inação |
| 5 | Segundo Pacto | 5 | "Sim ou não no final", comprometimento antes do pitch |
| 6 | Empresa / Método / Produto | 12 | Compra da empresa, compra do método, compra do produto |
| 7 | Pitch Amarrado à Fala do Lead | 9 | Pitch usa palavras exatas do lead no diagnóstico |
| 8 | Ancoragem / Preço | 10 | Value stack, ancoragem, risk reversal, condição |
| 9 | Objeções | 12 | Isolamento, looping, belief shift, prevenção |
| 10 | Fechamento / Próximos Passos | 10 | Decisão clara, assumptive close, next step lock |
| | **TOTAL** | **100** | |

### Interpretação do Score
- **< 40** — Crítico: treinamento imediato obrigatório
- **40–60** — Em desenvolvimento: coaching semanal com foco nos 3 piores blocos
- **60–80** — Bom: refinamento tático, foco em objeções e fechamento
- **80+** — Excelente: closer referência, material para swipe file

### Output Obrigatório de Toda Auditoria
1. Score total
2. Score por bloco (10 blocos)
3. Técnicas/frameworks detectados (com evidência)
4. Análise minuto a minuto
5. 3 maiores acertos (com trecho)
6. 3 maiores falhas (com trecho)
7. 3 falas reescritas (antes/depois)
8. Causa raiz principal
9. Ação para a próxima call

---

## Resolução de Conflitos Metodológicos

### O Problema
Dan Lok (alta pressão, doctor frame, qualificação dura) e Jeremy Miner (zero pressão, NEPQ,
perguntas socráticas) são opostos em abordagem. Belfort (controle de linha, looping agressivo)
e Eli Wilde (mudança de crença, influência sutil) também divergem.

### A Solução: Routing por Fase
O `config.yaml` roteia cada especialista para a fase onde sua metodologia é mais eficaz:

| Fase | Especialistas Primários | Justificativa |
|------|------------------------|---------------|
| Rapport / Frame | Cole Gordon, Dan Lok | Frame nos primeiros minutos |
| Discovery | Neil Rackham, Jeremy Miner, Cole Gordon | SPIN + NEPQ = diagnóstico profundo |
| Pitch | Cole Gordon, Alex Hormozi, Sabri Suby | Ponte diagnóstico→pitch, value equation, oferta |
| Ancoragem / Preço | Alex Hormozi, Sabri Suby | Value stack, ancoragem, risk reversal |
| Objeções | Jordan Belfort, Bradley Lea, Eli Wilde | Looping, prevenção, belief shift |
| Fechamento | Jordan Belfort, Cole Gordon | Straight line, certainty triad |

### Regras de Arbitragem
1. **Sales Chief** é o árbitro final de conflitos metodológicos
2. **QA Guardian** detecta feedback contraditório antes de publicar
3. Se dois experts divergem na mesma fase, o config.yaml define quem tem prioridade
4. O output final é unificado — o closer recebe UMA recomendação coerente, não N opiniões

---

## Orquestração de Agentes

### Hierarquia
```
Sales Chief (orquestrador)
├── Call Auditor (executor central — decompõe a call fase a fase)
├── Transcript Analyst (normaliza, limpa, segmenta)
├── Framework Detector (identifica técnicas com evidência)
├── Scorecard Analyst (pontua por bloco)
├── Objection Specialist (diagnostica e taxonomiza objeções)
├── Pricing Anchoring Analyst (analisa valor, preço, concessões)
├── Talk Ratio Analyst (equilíbrio closer vs lead)
├── Deal Risk Doctor (risco de perda, desalinhamento)
├── Coaching Rewriter (reescreve falas críticas)
├── Closer Trainer (converte auditoria em plano de treino)
├── QA Guardian (garante qualidade, evita contradições)
├── Revenue Intelligence Analyst (liga call ao pipeline)
├── SDR Handoff Analyst (audita handoff SDR→closer)
├── Offer Fit Analyst (verifica aderência oferta↔dor↔ICP)
├── Win-Loss Miner (extrai padrões de calls ganhas/perdidas)
└── 11 Especialistas (Hormozi, Miner, Belfort, Cole Gordon, Eli Wilde,
    Dan Lok, Rackham, Dixon, Adamson, Sabri, Bradley)
```

### Fluxo de Execução
1. **Intake**: Transcript Analyst normaliza a call
2. **Segmentação**: Call Auditor decompõe por fase
3. **Detecção**: Framework Detector identifica técnicas usadas
4. **Scoring**: Scorecard Analyst pontua 10 blocos
5. **Diagnóstico**: Specialists analisam suas fases específicas
6. **Root Cause**: Deal Risk Doctor + Offer Fit Analyst identificam causa raiz
7. **Rewrite**: Coaching Rewriter reescreve momentos críticos
8. **QA**: QA Guardian valida coerência e elimina contradições
9. **Coaching**: Closer Trainer monta plano de treino
10. **Intelligence**: Win-Loss Miner + Revenue Intelligence extraem padrões
11. **Aprovação**: Sales Chief revisa e aprova entrega final

---

## Cross-Squad Integration

O squad se conecta bidirecionalmente com 8 squads:

| Squad | O que ENVIA | O que RECEBE |
|-------|------------|-------------|
| **Copy** | Objeções reais, frases do lead sobre dor, palavras que ativam | Novas variações de pitch, respostas de objeção mais fortes |
| **Traffic** | Qualidade do lead por origem, promessas que geram lead ruim | Canal/origem/campanha, CPL/CPA vs close rate |
| **Brand** | Percepção de marca na call, confiança/desconfiança | Posicionamento atualizado, provas sociais |
| **Storytelling** | Cases de sucesso, frases de conexão | Narrativas de case |
| **C-Level** | Objeções de pricing, mismatch oferta × mercado | Mudanças de pricing, novos stacks/garantias |
| **Data** | Scorecards, close rates | Cohort analysis, closer benchmarking |
| **Movement** | Linguagem do lead | Cultural insights |
| **Advisory** | Pricing strategy questions, offer fit analysis | Strategic guidance |

---

## Estrutura de Diretórios

```
squads/sales-call-intelligence/
├── agents/          # 27 agentes (11 especialistas + 16 funcionais)
├── archive/         # Calls icônicas, evolução, falhas e lições
├── authority/       # Resumos de especialistas, cases, workshops
├── checklists/      # ~130+ quality gates (macro, fase, expert, operacional)
├── data/            # Registries, métricas, transcrições, scorecards
├── docs/            # Documentação completa
├── frameworks/      # ~85+ frameworks (universais, proprietários, intelectuais)
├── lib/             # Componentes, padrões, utilitários, taxonomias
├── phrases/         # ~18 bibliotecas de frases por fase
├── projects/        # 8 tipos de projeto com fases numeradas
├── reference/       # Livros, vendas, psicologia, negociação, cases, indústrias
├── scripts/         # Automação (processing, analysis, reporting)
├── swipe/           # Best/worst calls, rewrites, scorecards, coaching
├── swipe-sources/   # Fontes curadas (Hormozi, Cole Gordon, Miner, etc.)
├── tasks/           # ~45+ tarefas executáveis
├── templates/       # ~40+ entregáveis padronizados
├── voice/           # Tom, linguagem, calibração, canais
├── workflows/       # 20 playbooks numerados (00–20)
├── ARCHITECTURE.md  # Este arquivo
├── config.yaml      # Cérebro de roteamento
├── README.md        # Visão geral e quick start
└── swipe.config     # Configuração de swipe files
```

---

## Convenções

### Nomenclatura de Arquivos
- Kebab-case: `call-audit-quality.md`
- Especialistas: `hormozi-closer-checklist.md` (sobrenome primeiro)
- Workflows: `00-recording-to-transcript.md` (número + descrição)
- Projects: `00-intake.md` (fase numerada)
- Registries: `.yaml` para dados estruturados
- Tudo mais: `.md` para conteúdo

### Formato de Evidência
```
[MM:SS] "trecho exato da transcrição" — análise do que ocorreu
```

### Formato de Reescrita
```
ANTES (MM:SS): "fala real do closer"
DEPOIS: "fala ideal reescrita"
JUSTIFICATIVA: por que a reescrita é mais eficaz
FRAMEWORK: qual framework embasa a reescrita
```

---

## Quality Gate Cascade

O squad opera com **4 níveis de quality gate** em cascata. Nenhum output avança sem passar no gate do seu nível.

### Nível 1 — Agent-Level Gate
Cada agente valida seu próprio output antes de entregar.
- **Critério**: checklist obrigatório do agente ≥ 80% dos items
- **Evidência**: todo item deve ter trecho + timestamp da transcrição
- **Rework**: se falha, o agente refaz (max 2 ciclos internos)
- **Escalation**: se não resolve em 2 ciclos → sobe para QA Guardian

### Nível 2 — Task-Level Gate
QA Guardian valida o output consolidado da task.
- **Critério**: todos os checklists obrigatórios da task passam em ≥ 80%
- **Coerência**: sem contradições entre outputs de diferentes agentes
- **Completude**: todos os campos obrigatórios do template preenchidos
- **Rework**: se falha → retorna ao agente owner (max 3 ciclos)
- **Escalation**: se 3 ciclos falham → Sales Chief decide

### Nível 3 — Chief-Level Gate
Sales Chief valida o entregável final antes de publicar.
- **Critério**: output atende score_thresholds do config.yaml
- **Coerência cross-task**: outputs de diferentes tasks se complementam
- **Acionabilidade**: closer/manager consegue agir com base no output
- **Decisão**: APROVAR / APROVAR COM NOTAS / REWORK / ESCALAR

### Nível 4 — Cross-Squad Gate
Antes de qualquer handoff sair do squad.
- **Critério**: handoff brief completo (template/operational/cross-squad-handoff-template)
- **Contexto**: squad receptor tem informação suficiente para agir
- **Qualidade**: output atende padrão GOOD ou superior
- **Registro**: handoff registrado em data/registries/lessons-learned-registry
- **Responsável**: Sales Chief aprova todo handoff cross-squad

---

## Escalation Protocol

### Quando Escalar
| Situação | Escalar Para | SLA |
|----------|-------------|-----|
| Score com confiança < 70% | Sales Chief | Mesmo dia |
| Experts divergem na mesma fase | QA Guardian → Sales Chief | Mesmo dia |
| Task fora do escopo do squad | Sales Chief → Squad relevante | 24h |
| Quality gate falha 3x | Sales Chief | Mesmo dia |
| Closer score < 40 (crítico) | Sales Chief + C-Level Squad | 24h |
| Variância > 15% entre auditores | QA Guardian (calibration) | 1 semana |

### O que Documentar na Escalation
1. Contexto: o que aconteceu e por que não foi resolvido no nível atual
2. Tentativas: o que já foi tentado (rework cycles)
3. Evidência: trechos, scores, análises que suportam a escalation
4. Recomendação: o que o agente sugere como resolução
5. Registro: toda escalation é registrada em data/registries/lessons-learned-registry

---

## Handling de Tasks Fora do Escopo

### Como Identificar
Uma task está fora do escopo quando:
- Requer decisão estratégica de pricing/oferta (→ C-Level Squad)
- Requer criação de copy/messaging (→ Copy Squad)
- Requer análise de tráfego/lead source (→ Traffic Squad)
- Requer mudança de marca/posicionamento (→ Brand Squad)
- Requer análise estatística/cohort (→ Data Squad)
- Requer criação de narrativa/case (→ Storytelling Squad)

### Protocolo de Handoff
1. Sales Chief identifica que task saiu do escopo
2. Preenche `templates/operational/cross-squad-handoff-template.md`
3. Inclui: contexto, evidências coletadas, recomendação, urgência
4. Registra em `data/registries/lessons-learned-registry.yaml`
5. Envia para chief do squad receptor
6. Monitora retorno e integra ao pipeline quando volta

---

## Learning & Memory System (RalphLoop)

### Como o Squad Aprende
```
Execução → Output → Registry → Análise de Padrões → Ajuste de Processo → Próxima Execução
```

### Ciclo de Aprendizado
1. **Per-call**: Cada auditoria registra win patterns, loss patterns, objeções e rewrites em registries
2. **Semanal**: weekly-sales-quality-review consolida padrões da semana
3. **Mensal**: certification review identifica gaps sistêmicos de closers
4. **Trimestral**: intelligence extraction atualiza frameworks e checklists baseado em dados acumulados

### Registries como Memória Operacional
| Registry | O que armazena | Alimenta |
|----------|---------------|----------|
| calls-registry | Metadata de todas as calls | Seleção de calls para análise |
| scorecards-registry | Scores por call/closer/time | Benchmarking e trends |
| objections-registry | Objeções classificadas | Treinamento e frameworks |
| win-patterns-registry | Padrões de calls ganhas | Swipe files e coaching |
| loss-patterns-registry | Padrões de calls perdidas | Prevenção e alertas |
| lessons-learned-registry | Aprendizados do sistema | Melhoria contínua |
| framework-detection-registry | Frameworks detectados por call | Calibração de detecção |

### Regra de Feedback Loop
- Todo output de auditoria DEVE atualizar pelo menos 1 registry
- Todo padrão que aparece 3+ vezes DEVE virar item de checklist ou framework update
- Toda objeção nova DEVE ser classificada e adicionada ao objections-registry
- Todo rewrite que melhora score em 10+ pontos DEVE ir para swipe/best-rewrites/

---

## Go/No-Go Rules

### Quando um Output Está Pronto para Publicar
| Tipo de Output | Critério Go | Critério No-Go |
|---------------|-------------|----------------|
| Full audit report | Score calculado + 10 blocos + evidências + causa raiz + 3 rewrites | Falta evidência em qualquer bloco |
| Scorecard | Todos 10 blocos pontuados + justificativa | Bloco sem evidência |
| Coaching pack | Top 3 prioridades + rewrites + plano de ação | Sem rewrites ou sem plano |
| Rewrite | Antes/depois + framework + justificativa | Sem justificativa ou sem framework |
| Intelligence report | Dados de 10+ calls + padrões estatísticos | < 10 calls ou sem tendência |
| Cross-squad handoff | Brief completo + contexto + evidências | Brief incompleto |

### Threshold de Qualidade
- **WEAK** (< 50% checklist): bloqueado — rework obrigatório
- **FAIR** (50-79%): publicável com flag "needs improvement"
- **GOOD** (80-94%): publicável — padrão operacional
- **GOLD** (95%+): publicável + vai para swipe como referência

---

## HRM Layer — Integração com Camada Superior

### Quando o Squad Reporta para Cima
O Sales Call Intelligence Squad reporta para a camada HRM/Central Command quando:
1. **Decisão estratégica**: pricing, oferta ou modelo de vendas precisa mudar
2. **Performance sistêmica**: close rate do time cai abaixo de threshold por 2+ semanas
3. **Conflito cross-squad**: dois squads divergem sobre responsabilidade
4. **Resource gap**: squad precisa de capability que não possui
5. **Escalation terminal**: rework loops esgotados sem resolução

### O que Sobe para HRM
- Relatório executivo mensal (executive-sales-intelligence-report)
- Alertas de performance crítica (closer score < 40 por 2+ calls)
- Pedidos de decisão estratégica (com contexto + recomendação + evidência)
- Propostas de melhoria de processo (com ROI estimado)

### O que Desce do HRM
- Mudanças de pricing/oferta → atualizar registries e frameworks
- Novos closers → onboarding via onboard-new-closer task
- Mudanças de processo → atualizar workflows e checklists
- Metas de performance → atualizar score_thresholds no config.yaml
