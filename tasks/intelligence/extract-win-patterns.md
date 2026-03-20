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
