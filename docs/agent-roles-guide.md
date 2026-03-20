# Guia dos 27 Agentes do Squad

> Referência completa sobre cada agente: função, quando usar, hierarquia de ativação e lógica de routing.

## Hierarquia dos Agentes

Os 27 agentes estão organizados em 5 camadas funcionais que operam em sequência dentro do pipeline de auditoria.

### Camada 1 — Processamento (4 agentes)

1. **Intake Agent**: recebe a call, valida metadados e distribui para o pipeline
2. **Transcript Cleaner**: limpa a transcrição bruta, corrige erros, identifica speakers
3. **Segmentation Agent**: divide a call em 6 etapas canônicas
4. **Context Enricher**: adiciona contexto (ticket, nicho, tipo de lead, histórico)

### Camada 2 — Análise (6 agentes)

5. **Framework Detector**: identifica frameworks de vendas usados em cada segmento
6. **Technique Classifier**: classifica cada técnica como correta, parcial ou incorreta
7. **Objection Mapper**: mapeia objeções levantadas, tipo e resposta dada
8. **Tonality Analyzer**: avalia tom, ritmo, pausas e energia vocal
9. **Talk Ratio Calculator**: calcula proporção de fala closer vs. prospect
10. **Engagement Tracker**: mede sinais de engajamento e desengajamento do prospect

### Camada 3 — Avaliação (5 agentes)

11. **Scoring Agent**: aplica o modelo de 100 pontos em 10 blocos
12. **Benchmark Comparator**: compara score com médias históricas do closer e do time
13. **Root Cause Analyst**: identifica causa raiz dos gaps de performance
14. **Pattern Detector**: encontra padrões recorrentes across calls do mesmo closer
15. **Win/Loss Correlator**: correlaciona comportamentos com resultado (ganhou/perdeu)

### Camada 4 — Prescrição (5 agentes)

16. **Rewrite Agent**: reescreve momentos-chave usando frameworks de autoridade
17. **Script Suggester**: sugere scripts alternativos para situações específicas
18. **Coaching Plan Builder**: cria plano de coaching personalizado
19. **Exercise Designer**: desenha exercícios práticos baseados nos gaps encontrados
20. **Priority Ranker**: prioriza ações por impacto potencial no close rate

### Camada 5 — Governança (7 agentes)

21. **Registry Manager**: atualiza registros de performance e histórico
22. **Calibration Agent**: garante consistência entre auditorias
23. **Quality Checker**: valida que a auditoria está completa e consistente
24. **Report Generator**: compila o relatório final de auditoria
25. **Certification Agent**: avalia closers para certificação
26. **Trend Analyst**: analisa tendências de longo prazo
27. **Integration Agent**: distribui insights para outros squads

## Routing — Quando Ativar Cada Agente

### Auditoria Completa
Ativa todos os 27 agentes em sequência (camada 1 → 2 → 3 → 4 → 5).

### Auditoria Rápida
Ativa apenas: Intake, Transcript Cleaner, Segmentation, Framework Detector, Scoring Agent, Report Generator.

### Coaching Sprint
Foco nos agentes de prescrição: Pattern Detector, Root Cause Analyst, Coaching Plan Builder, Exercise Designer.

### Calibração
Foco nos agentes de governança: Calibration Agent, Quality Checker, Benchmark Comparator.

## Regras de Dependência

- O Segmentation Agent depende do Transcript Cleaner ter finalizado
- O Scoring Agent depende do Framework Detector e do Technique Classifier
- O Rewrite Agent depende do Root Cause Analyst
- O Certification Agent depende de no mínimo 5 auditorias completas do closer
