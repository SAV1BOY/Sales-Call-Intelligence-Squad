# 01 — Transcript Cleaning and Segmentation

> Limpeza avançada da transcrição e segmentação por fases da sales call (rapport, diagnóstico, apresentação, objeções, close).

## Objetivo

Pegar a transcrição normalizada do workflow 00 e aplicar segmentação semântica por fases da call, identificando onde cada etapa do processo de vendas começa e termina, permitindo análise granular por fase.

## Quando Executar

- Imediatamente após conclusão do workflow 00 (Recording to Transcript).
- Quando uma transcrição existente precisar ser re-segmentada por mudança no framework de fases.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| transcript-analyst | Executa limpeza avançada, identifica fases da call e produz segmentação semântica final |

## Frameworks Utilizados

- sales-call-phase-model (rapport → diagnóstico → apresentação → objeções → close → próximos passos)
- transcript-normalization-standard

## Checklists Obrigatórios

- transcript-normalization-quality
- phase-segmentation-checklist

## Etapas

### Etapa 1 — Recebimento e Validação da Transcrição Base
**Responsável**: transcript-analyst
**Input**: Transcrição normalizada do workflow 00
**Ação**:
1. Confirmar que a transcrição passou pelo quality gate do workflow 00.
2. Verificar que speakers estão nomeados e timestamps estão no formato HH:MM:SS.
3. Fazer leitura rápida para identificar problemas remanescentes de transcrição.
4. Listar termos técnicos, nomes de produtos e valores que precisam de verificação cruzada.
**Output**: Transcrição validada + lista de termos para verificação.
**Quality Gate**: Transcrição legível, speakers identificados, sem blocos faltantes.

### Etapa 2 — Limpeza Semântica Avançada
**Responsável**: transcript-analyst
**Input**: Transcrição validada
**Ação**:
1. Identificar e corrigir termos técnicos do produto/oferta usando glossário interno.
2. Verificar nomes de concorrentes, ferramentas e referências mencionadas pelo lead.
3. Marcar citações exatas do lead com tag `[citação-lead]` para uso em coaching.
4. Identificar momentos de emoção evidente: frustração, entusiasmo, hesitação — marcar com tags `[emoção: frustração]`.
5. Consolidar falas fragmentadas do mesmo speaker que foram divididas por micro-pausas.
6. Remover repetições de transcrição (eco de áudio, duplicatas de engine).
**Output**: Transcrição semanticamente limpa com tags de citação e emoção.
**Quality Gate**: Zero termos técnicos errados; citações do lead marcadas; emoções tagueadas.

### Etapa 3 — Identificação de Fases da Call
**Responsável**: transcript-analyst
**Input**: Transcrição limpa
**Ação**:
1. Percorrer a transcrição cronologicamente identificando transições de fase.
2. Mapear cada trecho para uma das fases padrão:
   - **Fase 0 — Abertura/Rapport**: Cumprimentos, quebra de gelo, estabelecimento de conexão.
   - **Fase 1 — Diagnóstico/Descoberta**: Perguntas sobre situação atual, dor, impacto, tentativas anteriores.
   - **Fase 2 — Implicação/Amplificação**: Aprofundamento da dor, projeção de consequências.
   - **Fase 3 — Apresentação da Solução**: Explicação do produto/serviço, mecanismo, diferencial.
   - **Fase 4 — Ancoragem de Valor/Preço**: Construção de valor, apresentação de investimento.
   - **Fase 5 — Objeções**: Resistências do lead, negociação, tratamento de objeções.
   - **Fase 6 — Close/Decisão**: Tentativa de fechamento, decisão do lead.
   - **Fase 7 — Próximos Passos/Wrap-up**: Alinhamento pós-decisão, despedida.
3. Registrar timestamp exato de início e fim de cada fase.
4. Identificar fases ausentes ou fora de ordem.
**Output**: Mapa de fases com timestamps e notas sobre sequenciamento.
**Quality Gate**: Todas as fases presentes na call estão mapeadas; fases ausentes estão documentadas.

### Etapa 4 — Segmentação e Marcação
**Responsável**: transcript-analyst
**Input**: Transcrição limpa + mapa de fases
**Ação**:
1. Inserir delimitadores visuais entre fases: `---` + header com nome da fase e timestamps.
2. Calcular duração de cada fase e percentual do tempo total da call.
3. Gerar tabela-resumo de distribuição temporal das fases.
4. Identificar proporção talk-time closer vs. lead por fase.
5. Destacar momentos-chave em cada fase (pergunta mais poderosa, objeção mais forte, momento de decisão).
**Output**: Transcrição segmentada por fases com métricas de distribuição temporal.
**Quality Gate**: phase-segmentation-checklist (fases delimitadas, durações calculadas, momentos-chave destacados).

### Etapa 5 — Geração de Resumo Executivo da Call
**Responsável**: transcript-analyst
**Input**: Transcrição segmentada
**Ação**:
1. Produzir resumo de 5-10 linhas cobrindo: contexto do lead, principais dores, solução apresentada, objeções, resultado.
2. Listar top 3 citações mais reveladoras do lead.
3. Registrar resultado da call: fechou, não fechou, follow-up agendado.
4. Calcular talk-time ratio geral (closer vs. lead).
5. Inserir resumo no header do documento final.
**Output**: Transcrição final com resumo executivo no topo.
**Quality Gate**: Resumo cobre todos os pontos obrigatórios; talk-time calculado; resultado registrado.

### Etapa 6 — Exportação e Handoff
**Responsável**: transcript-analyst
**Input**: Transcrição final segmentada
**Ação**:
1. Exportar documento final em Markdown com estrutura padronizada.
2. Atualizar transcript-registry com status "segmentada — pronta para auditoria".
3. Disponibilizar para os workflows downstream (02, 03, 04).
4. Se a call foi identificada como "fechou" ou "perdeu", criar flag para workflows 09/10.
**Output**: Documento final publicado + registry atualizado + flags de roteamento.
**Quality Gate**: Arquivo exportado corretamente; status no registry atualizado; flags criadas.

## Templates de Output

- segmented-transcript-template (transcrição com fases, métricas e resumo)

## Registries Atualizados

- transcript-registry (status atualizado para "segmentada")
- call-log-registry (metadados de fases e resultado atualizados)

## Critérios de Conclusão

- [ ] Limpeza semântica completa com tags de citação e emoção
- [ ] Todas as fases da call identificadas e mapeadas com timestamps
- [ ] Distribuição temporal calculada por fase
- [ ] Talk-time ratio calculado (geral e por fase)
- [ ] Resumo executivo gerado e inserido no header
- [ ] Transcrição exportada e registry atualizado

## Próximo Workflow

→ 02-minute-by-minute-analysis.md (análise minuto a minuto da call)
