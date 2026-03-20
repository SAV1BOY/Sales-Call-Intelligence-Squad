# Como Começar com o Sales Call Intelligence Squad

> Guia prático para configurar, entender e executar sua primeira auditoria de call usando o squad.

## Pré-requisitos

Antes de iniciar, certifique-se de que você possui:

- Acesso ao repositório do squad com permissões de leitura e escrita
- Pelo menos uma gravação ou transcrição de call de vendas disponível
- Familiaridade básica com conceitos de vendas high ticket
- Entendimento do glossário oficial (consulte `glossary.md`)

## Setup Inicial

### Passo 1 — Clonar o Repositório

Clone o repositório e navegue até o diretório raiz. Verifique se todas as pastas estão presentes: `docs/`, `authority/`, `projects/`, `archive/`. Cada pasta contém artefatos essenciais para o funcionamento do squad.

### Passo 2 — Conhecer a Estrutura

O squad está organizado em quatro camadas principais:

- **Docs**: documentação de referência, metodologia e guias operacionais
- **Authority**: base de conhecimento de especialistas, cases e workshops
- **Projects**: playbooks fase a fase para cada tipo de projeto
- **Archive**: exemplos reais, evoluções históricas e lições aprendidas

### Passo 3 — Escolher o Projeto Certo

Para sua primeira execução, recomendamos o projeto `full-call-audit`. Ele cobre o fluxo completo: intake, limpeza de transcrição, segmentação, detecção de frameworks, scoring, análise de causa raiz, rewrites e coaching pack.

## Primeiro Uso — Auditoria Rápida

### Preparação

1. Selecione uma call recente com duração entre 20 e 60 minutos
2. Obtenha a transcrição limpa (ou use o agente de limpeza)
3. Identifique o closer, o lead e o produto/serviço vendido

### Execução

1. Inicie pelo `00-intake.md` do projeto `full-call-audit`
2. Siga cada fase sequencialmente, preenchendo inputs e gerando outputs
3. Use os agentes indicados em cada fase para executar as atividades
4. Ao final, você terá um coaching pack completo com score, diagnóstico e plano de ação

## Workflow Básico Diário

O workflow recomendado para times que fazem auditoria contínua:

1. **Manhã**: selecionar 2-3 calls do dia anterior para auditoria
2. **Execução**: rodar o fluxo completo de auditoria em cada call
3. **Consolidação**: atualizar o registry com scores e padrões encontrados
4. **Feedback**: enviar coaching pack ao closer com debrief de 15 minutos
5. **Semanal**: analisar tendências, atualizar playbooks, recalibrar scores

## Erros Comuns no Início

- **Pular a fase de segmentação**: sem segmentar a call em etapas, a análise perde profundidade
- **Não calibrar scores**: scores sem calibração entre auditores geram inconsistência
- **Ignorar o contexto**: cada call tem contexto (produto, ticket, lead) que afeta a avaliação
- **Focar só no negativo**: o coaching eficaz equilibra pontos fortes e áreas de melhoria

## Próximos Passos

Após sua primeira auditoria, explore:

- `squad-overview.md` para entender a visão completa
- `agent-roles-guide.md` para conhecer os 27 agentes
- `scoring-methodology.md` para dominar o sistema de pontuação
- `coaching-methodology.md` para transformar dados em desenvolvimento
