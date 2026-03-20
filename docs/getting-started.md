# Como Começar com o Sales Call Intelligence Squad

> Guia prático para configurar o squad, executar sua primeira auditoria e estabelecer o workflow básico de análise de calls.

## Pré-requisitos

Antes de iniciar, certifique-se de ter:

- Acesso ao repositório do squad com permissões de leitura e escrita
- Transcrições de calls em formato texto (mínimo 1 call para teste)
- Familiaridade básica com os conceitos de vendas high ticket
- Ambiente configurado com os agentes do squad disponíveis

## Setup Inicial

### Passo 1 — Clonar e Configurar o Repositório

Clone o repositório e verifique que todas as pastas de referência estão presentes: `docs/`, `authority/`, `projects/`, `archive/`. Cada pasta contém materiais essenciais para o funcionamento dos agentes.

### Passo 2 — Conhecer os Agentes Disponíveis

O squad possui 27 agentes especializados. Para o primeiro uso, os mais importantes são:
- **Transcript Cleaner**: limpa e formata transcrições brutas
- **Segmentation Agent**: divide a call em etapas
- **Framework Detector**: identifica frameworks de vendas utilizados
- **Scoring Agent**: pontua a call em 10 blocos

### Passo 3 — Preparar sua Primeira Call

Selecione uma call representativa do seu processo de vendas. Idealmente, escolha uma call que teve resultado definido (ganhou ou perdeu) para que a análise tenha contexto completo.

## Primeiro Uso — Auditoria Rápida

### Executando a Primeira Auditoria

1. Forneça a transcrição bruta ao Transcript Cleaner
2. O agente de Segmentação dividirá a call em etapas (rapport, discovery, pitch, pricing, objections, closing)
3. O Framework Detector identificará quais técnicas foram usadas (SPIN, NEPQ, Straight Line, etc.)
4. O Scoring Agent atribuirá nota de 0 a 100 distribuída em 10 blocos de avaliação
5. Revise o output e valide se os achados fazem sentido com sua percepção da call

### Interpretando os Resultados

O score final é composto por 10 blocos com pesos diferentes. Um score acima de 75 indica performance sólida. Entre 50 e 75, há áreas claras de melhoria. Abaixo de 50, a call precisa de intervenção estrutural.

## Workflow Básico Recomendado

### Ciclo Semanal

1. **Segunda**: selecionar 3-5 calls da semana anterior para auditoria
2. **Terça-Quarta**: executar auditorias completas com todos os agentes
3. **Quinta**: compilar padrões e insights cross-call
4. **Sexta**: criar coaching pack e plano de ação para o closer

### Ciclo Mensal

1. Auditar no mínimo 15-20 calls por closer
2. Atualizar o registry de performance com scores históricos
3. Identificar tendências de melhoria ou degradação
4. Recalibrar benchmarks se necessário

## Erros Comuns no Início

- **Auditar calls demais sem profundidade**: melhor 5 auditorias profundas do que 20 superficiais
- **Ignorar o contexto**: o score sem contexto (tipo de lead, ticket, momento) perde valor
- **Pular a calibração**: antes de auditar em escala, calibre o scoring com 3-5 calls de referência
- **Não fechar o loop**: auditoria sem coaching é desperdício — sempre gere o plano de ação

## Próximos Passos

Após completar sua primeira auditoria com sucesso:
- Leia o `squad-overview.md` para entender a arquitetura completa
- Consulte o `agent-roles-guide.md` para conhecer todos os 27 agentes
- Explore o `scoring-methodology.md` para dominar o sistema de pontuação
- Veja exemplos reais em `archive/iconic-calls/` para calibrar sua percepção
