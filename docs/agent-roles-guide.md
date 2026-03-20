# Guia dos 27 Agentes do Squad

> Cada agente tem um papel específico, contexto de ativação e regras de routing. Este guia detalha quando usar cada um e como eles se conectam.

## Hierarquia de Agentes

Os 27 agentes estão organizados em 5 camadas hierárquicas:

### Camada 1 — Orquestração (1 agente)
- **Orchestrator Agent**: coordena o fluxo entre todos os agentes, decide routing, gerencia dependências e garante que outputs de uma fase alimentem inputs da próxima

### Camada 2 — Análise Core (6 agentes)
- **Transcript Cleaner**: limpa e normaliza transcrições, remove ruídos, identifica speakers
- **Segmentation Agent**: divide a call em etapas (rapport, discovery, pitch, pricing, objections, closing)
- **Framework Detector**: identifica frameworks usados pelo closer em cada etapa
- **Scoring Agent**: aplica a metodologia de 100 pontos com 10 blocos ponderados
- **Root Cause Analyst**: conecta falhas de score a causas raiz comportamentais
- **Pattern Miner**: extrai padrões recorrentes de múltiplas calls

### Camada 3 — Produção de Conteúdo (5 agentes)
- **Rewrite Agent**: gera versões melhoradas de momentos críticos da call
- **Coaching Pack Builder**: compila diagnóstico, rewrites e plano de ação em pacote coeso
- **Script Builder**: cria scripts baseados em padrões de sucesso identificados
- **Objection Mapper**: mapeia objeções por tipo, frequência e causa raiz
- **Swipe File Curator**: seleciona e organiza exemplos de excelência para referência

### Camada 4 — Especialistas de Domínio (10 agentes)
Cada um domina a metodologia de um especialista específico:
- **Hormozi Specialist**: Value Equation, Grand Slam Offer, CLOSER framework
- **Miner Specialist**: NEPQ, perguntas de consequência, zero pressure
- **Belfort Specialist**: Straight Line, tonalidade, looping, certeza
- **Gordon Specialist**: Frame control, ponte diagnóstico-pitch, isolamento
- **Wilde Specialist**: Belief shift, estados emocionais, identidade
- **Lok Specialist**: Doctor frame, qualificação, autoridade, premium
- **Rackham Specialist**: SPIN Selling, venda consultiva, implicações
- **Dixon-Adamson Specialist**: Challenger Sale, ensinar-adaptar-controlar
- **Suby Specialist**: Godfather offer, value stack, risk reversal
- **Lea Specialist**: Objeções preventivas, clareza brutal, decisão binária

### Camada 5 — Suporte (5 agentes)
- **Registry Agent**: mantém registros atualizados de auditorias, scores e padrões
- **Calibration Agent**: garante consistência de scores entre diferentes auditores
- **Certification Agent**: avalia closers para certificação por nível
- **Integration Agent**: conecta outputs do squad com outros squads
- **Quality Assurance Agent**: valida qualidade dos outputs antes da entrega

## Quando Usar Cada Agente

### Para Auditoria Completa
Ativar sequencialmente: Orchestrator → Transcript Cleaner → Segmentation → Framework Detector → Scoring → Root Cause → Rewrite → Coaching Pack Builder → Registry

### Para Análise de Padrões
Ativar: Orchestrator → Pattern Miner → Objection Mapper → Swipe File Curator

### Para Coaching Individual
Ativar: Scoring → Root Cause → especialistas de domínio relevantes → Coaching Pack Builder

### Para Certificação
Ativar: Scoring → Calibration → Certification → Registry

## Regras de Routing

1. Nenhum agente de Camada 3 pode ser ativado sem output da Camada 2
2. Especialistas de domínio são ativados sob demanda, conforme frameworks detectados
3. O Registry Agent é sempre o último a ser ativado em qualquer fluxo
4. O Calibration Agent deve ser ativado pelo menos uma vez por semana
5. O QA Agent valida outputs antes de qualquer entrega externa ao squad
