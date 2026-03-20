# Sales Call Intelligence Squad

> Squad de inteligência comercial do MMOS — auditoria de calls high ticket, coaching de closers, extração de padrões de fechamento, scoring e melhoria contínua.

## O que este squad faz

Transforma calls de vendas em diagnósticos acionáveis:

```
Call → Transcrição → Diagnóstico por etapa → Framework detection → Score (100pts) →
Root cause → Rewrite de momentos críticos → Coaching → Registry → Melhoria contínua
```

## Princípios

1. **phase-first** — cada framework opera na fase correta da call
2. **evidence-over-opinion** — toda crítica com trecho, minuto e evidência
3. **score-before-advice** — primeiro pontua, depois aconselha
4. **rewrite-the-moment** — sempre reescreve a fala ideal (antes/depois)
5. **objection-is-a-symptom** — objeção é efeito, não causa
6. **post-call-learning-mandatory** — toda call ensina algo ao sistema
7. **closer-performance-is-systemic** — problema pode estar no lead, oferta, pitch, SDR ou pricing

## Agentes (27)

### 11 Especialistas (autoridades)
| Agente | Especialidade |
|--------|--------------|
| Alex Hormozi | Value Equation, ancoragem, CLOSER, Grand Slam Offer |
| Jeremy Miner | NEPQ, perguntas socráticas, baixa pressão |
| Jordan Belfort | Straight Line, certeza, looping, tonalidade |
| Cole Gordon | Frame, liderança de call, diagnóstico profundo |
| Eli Wilde | PNL, crenças, mudança de identidade, influência |
| Dan Lok | Doctor frame, qualificação dura, autoridade |
| Neil Rackham | SPIN Selling, diagnóstico consultivo |
| Matthew Dixon | Challenger Sale, tensão construtiva |
| Brent Adamson | Challenger co-author, insight selling |
| Sabri Suby | Oferta irrecusável, value stack, risk reversal |
| Bradley Lea | Objeções preventivas, clareza brutal |

### 16 Agentes Funcionais
| Agente | Função |
|--------|--------|
| Sales Chief | Orquestrador e árbitro de conflitos |
| Call Auditor | Executor central — decompõe call por fase |
| Transcript Analyst | Normaliza, limpa e segmenta transcrições |
| Framework Detector | Detecta técnicas usadas com evidência |
| Scorecard Analyst | Calcula score por bloco (100pts/10 blocos) |
| Objection Specialist | Diagnóstico e taxonomia de objeções |
| Pricing Anchoring Analyst | Analisa valor, preço e concessões |
| Talk Ratio Analyst | Equilíbrio closer vs lead |
| Deal Risk Doctor | Risco de perda e desalinhamento |
| Coaching Rewriter | Reescreve falas críticas (antes/depois) |
| Closer Trainer | Converte auditoria em plano de treino |
| QA Guardian | Garante qualidade, evita feedback contraditório |
| Revenue Intelligence Analyst | Liga call ao pipeline |
| SDR Handoff Analyst | Audita handoff SDR→closer |
| Offer Fit Analyst | Verifica aderência oferta↔dor↔ICP |
| Win-Loss Miner | Extrai padrões de calls ganhas/perdidas |

## Scorecard — 100 Pontos / 10 Blocos

| Bloco | Pts |
|-------|-----|
| Rapport / Abertura | 8 |
| Primeiro Pacto / Frame | 8 |
| Diagnóstico SPIN / Profundidade | 18 |
| Ampliação da Dor | 8 |
| Segundo Pacto | 5 |
| Empresa / Método / Produto | 12 |
| Pitch Amarrado à Fala do Lead | 9 |
| Ancoragem / Preço | 10 |
| Objeções | 12 |
| Fechamento / Próximos Passos | 10 |
| **TOTAL** | **100** |

## Estrutura de Diretórios — 653 arquivos

```
├── agents/          # 27 agentes (11 especialistas + 16 funcionais)
├── archive/         # 16 — calls icônicas, evolução, falhas
├── authority/       # 18 — resumos de especialistas, cases, workshops
├── checklists/      # 131 quality gates (macro, por fase, por expert, operacionais)
├── data/            # 31 — registries (YAML), métricas, research
├── docs/            # 20 — documentação + quality gates system + audit report
├── frameworks/      # 84 frameworks (universais, proprietários, intelectuais)
├── lib/             # 33 — componentes, padrões, utilitários, taxonomias
├── phrases/         # 18 — bibliotecas de frases por fase
├── projects/        # 44 — 8 tipos de projeto com fases numeradas
├── reference/       # 80 — livros, vendas, psicologia, negociação, objeções, pricing
├── scripts/         # 14 — automação
├── swipe/           # 16 — best/worst calls, rewrites, scorecards
├── swipe-sources/   # 8 — fontes curadas
├── tasks/           # 38 — tarefas executáveis
├── templates/       # 32 — entregáveis padronizados
├── voice/           # 21 — tom, linguagem, calibração
├── workflows/       # 21 playbooks numerados
├── ARCHITECTURE.md  # Princípios e decisões arquiteturais
├── config.yaml      # Cérebro de roteamento (25+ tasks)
└── swipe.config     # Configuração de swipe files
```

## Cross-Squad Integration

Conecta-se bidirecionalmente com: **Copy**, **Traffic**, **Brand**, **Storytelling**, **C-Level**, **Data**, **Movement**, **Advisory**.

Ver `config.yaml` para detalhes dos handoffs.

## Quick Start

1. Leia `ARCHITECTURE.md` para entender princípios e scorecard
2. Consulte `config.yaml` para ver roteamento de tarefas
3. Execute workflows em `workflows/` na ordem numérica (00→20)
4. Use `templates/` para formatar entregáveis
5. Registre resultados em `data/registries/`
