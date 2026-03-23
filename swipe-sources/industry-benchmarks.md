# Benchmarks e Fontes de Dados da Indústria

> Fontes externas de benchmarks que contextualizam as métricas do squad.

## Fontes de Benchmark

### Plataformas de Call Intelligence
| Fonte | Dados Relevantes | Aplicação no Squad |
|-------|-----------------|-------------------|
| Gong.io | Talk ratio ideal (43:57), durée par étape, winning behaviors | `data/metrics/talk-ratio-metrics.yaml`, `frameworks/talk-ratio-analysis-framework.md` |
| Chorus.ai | Discovery question count, objection frequency, competitive mentions | `data/metrics/objection-frequency-metrics.yaml` |
| SalesLoft | Cadence effectiveness, follow-up conversion rates | `data/metrics/follow-up-conversion-rate.yaml` |

### Plataformas de CRM e Pipeline
| Fonte | Dados Relevantes | Aplicação no Squad |
|-------|-----------------|-------------------|
| HubSpot Research | Close rates by industry, sales cycle length, lead response time | `data/metrics/close-rate-by-closer.yaml` |
| Salesforce State of Sales | Win rates, pipeline velocity, deal size trends | `data/metrics/close-rate-by-offer.yaml` |
| LinkedIn Sales Solutions | Social selling index, buyer engagement patterns | Contexto para rapport/discovery |

### Benchmarks de Referência Usados

| Métrica | Benchmark | Fonte | Usado em |
|---------|-----------|-------|----------|
| Talk ratio ideal | 43% closer / 57% lead | Gong.io (2023) | `frameworks/talk-ratio-analysis-framework.md` |
| Discovery questions (won deals) | 11-14 por call | Gong.io | `checklists/discovery/` |
| Objection handling (won deals) | 3-4 objeções tratadas | Chorus.ai | `checklists/objections/` |
| Price discussion timing | Após 40 min (ideal) | Gong.io | `frameworks/price-anchoring.md` |
| Follow-up conversion | 80% das vendas precisam 5+ follow-ups | HubSpot | `data/metrics/follow-up-conversion-rate.yaml` |
| Close rate (high ticket) | 20-30% (bom), 30-40% (excelente) | Industry average | `data/metrics/close-rate-by-closer.yaml` |

## Atualização

- Benchmarks revisados trimestralmente durante `quarterly-intelligence-review`
- Novas fontes adicionadas ao `data/backlog/improvement-backlog.yaml` quando identificadas
- Comparação com métricas internas feita na `weekly-sales-quality-review`
