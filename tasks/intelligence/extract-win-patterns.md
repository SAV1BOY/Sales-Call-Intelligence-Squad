# Extrair Padrões de Calls Ganhas

> Extrair padrões recorrentes de calls ganhas: frameworks mais usados, frases de impacto, sequências vencedoras.

## Objetivo
Identificar o DNA das calls que convertem — quais técnicas, sequências e comportamentos aparecem consistentemente nas vitórias — para replicar sistematicamente.

## Trigger
- Mínimo 5 calls ganhas auditadas no período
- Execução do workflow `09-win-pattern-extraction`
- Review semanal ou mensal de qualidade

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Win-Loss Miner | Executa mineração de padrões de vitória |
| Revenue Intelligence Analyst | Analisa correlações estatísticas |
| Scorecard Analyst | Fornece scores por bloco das calls ganhas |
| Sales Chief | Valida padrões e prioriza disseminação |

## Inputs
- Scorecards de calls ganhas (últimas 20-30)
- Transcrições segmentadas das calls ganhas
- Relatórios de frameworks detectados
- Dados de oferta, ticket, ICP por call

## Processo
1. Filtrar calls ganhas no período (mínimo 5 para significância)
2. Analisar distribuição de scores por bloco: quais blocos são consistentemente altos?
3. Identificar frameworks mais frequentes nas calls ganhas
4. Extrair frases e trechos que apareceram antes do momento de decisão
5. Mapear sequências comuns: ordem de etapas, duração proporcional
6. Identificar padrões de talk ratio nas calls ganhas
7. Correlacionar win patterns com tipo de call, oferta e ICP
8. Comparar com padrões de calls perdidas (contraste)
9. Documentar top 5 padrões de vitória com evidência

## Frameworks Aplicados
- Win Pattern Extraction Framework
- Statistical Correlation Analysis
- Sales Call Stage Taxonomy

## Checklists de Qualidade
- Mínimo 5 calls analisadas para cada padrão
- Cada padrão tem evidência de múltiplas calls (não apenas uma)
- Frases extraídas são representativas (não cherry-picked)
- Correlação com resultado validada estatisticamente
- Contraste com calls perdidas incluído

## Output Esperado
- Relatório de win patterns em `reports/intelligence/win-patterns-PERIODO`
- Top 5 padrões com evidência e frequência
- Frases e trechos de impacto catalogados

## Registry Atualizado
- `data/registries/intelligence-registry.yaml`
- `data/libraries/best-moments-library.yaml`

## Critérios de Conclusão
- [ ] Mínimo 5 calls ganhas analisadas
- [ ] Top 5 padrões identificados com evidência
- [ ] Frameworks mais frequentes documentados
- [ ] Frases de impacto catalogadas
- [ ] Contraste com calls perdidas realizado
- [ ] Biblioteca de melhores momentos atualizada

---

## Contexto
Vitórias em vendas raramente são acidentais. Esta task existe para identificar o DNA das calls que convertem -- quais frameworks, sequências, frases e comportamentos aparecem consistentemente nas vitórias -- permitindo replicar sistematicamente o que funciona.

## Especificação de I/O
- **Input**: Scorecards de calls ganhas (últimas 20-30) + transcrições segmentadas + relatórios de frameworks detectados + dados de oferta/ticket/ICP
- **Output**: `templates/reports/win-loss-analysis-report` (relatório de win patterns com top 5 padrões e frases de impacto)

## Quality Gates Intermediários
- Após extração de padrões e frases (steps 2-5): checklist `win-loss-analysis-quality` — cada padrão tem evidência de 3+ calls, correlação com resultado validada
- Antes de output final: checklist `best-moments-library-quality` — frases representativas (não cherry-picked), contraste com calls perdidas incluído

## Escalation & Rework
- Se amostra insuficiente (< 5 calls ganhas no período): escalar para `revenue-intelligence-analyst` para ampliar janela temporal
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `score_improvement_rate`: evolução do score médio do time após disseminação dos padrões
- `framework_usage_rate`: % de calls onde frameworks vencedores identificados são aplicados

## Referências Cruzadas
- Workflow: `workflows/09-win-pattern-extraction.md`
- Agents: `agents/win-loss-miner.md`, `agents/revenue-intelligence-analyst.md`, `agents/framework-detector.md`
- Templates: `templates/reports/win-loss-analysis-report.md`
- Registries atualizados: `data/registries/win-patterns-registry`, `data/libraries/best-moments-library.yaml`

## Handoff
- **Output entregue a**: Closer Trainer para disseminação dos padrões vencedores em plano de treinamento + Sales Chief para validação e priorização
- **Formato de entrega**: `templates/reports/win-loss-analysis-report` (relatório de win patterns com top 5 padrões e frases de impacto catalogadas)
- **Condição de entrega**: cada padrão com evidência de 3+ calls, correlação com resultado validada, frases representativas (não cherry-picked), contraste com calls perdidas incluído
- **Próximo passo no pipeline**: atualização da biblioteca de melhores momentos (`tasks/intelligence/update-best-moments-library.md`) + plano de treinamento via coaching sessions

## Rework Loop
- **Definição de ciclo**: re-execução completa dos steps que falharam no quality gate
- **Max ciclos**: 2
- **Trigger de rework**: checklist obrigatório < 80% OU rejeição pelo QA Guardian
- **Após max ciclos**: escalar para sales-chief com evidência de tentativas
- **Registro**: toda rework registrada em data/registries/lessons-learned-registry.yaml
