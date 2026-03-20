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
| 1 | Rapport / Abertura | 10 | Quebra de gelo, postura, conexão, energia |
| 2 | Primeiro Pacto / Frame | 10 | 3 intenções, agenda, frame de liderança |
| 3 | Diagnóstico SPIN / Profundidade | 20 | Situação, problema, implicação, need-payoff, NEPQ |
| 4 | Ampliação da Dor / Implicação | 10 | Consequências, urgência, custo da inação |
| 5 | Segundo Pacto | 5 | "Sim ou não no final", comprometimento antes do pitch |
| 6 | Empresa / Método / Produto | 15 | Compra da empresa, compra do método, compra do produto |
| 7 | Pitch Amarrado à Fala do Lead | 10 | Pitch usa palavras exatas do lead no diagnóstico |
| 8 | Ancoragem / Preço | 10 | Value stack, ancoragem, risk reversal, condição |
| 9 | Objeções | 15 | Isolamento, looping, belief shift, prevenção |
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
