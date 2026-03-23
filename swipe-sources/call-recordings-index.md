# Índice de Gravações de Referência

> Índice de calls gravadas que servem como referência para o squad. Não contém os arquivos de áudio — apenas metadata para localização e contexto.

## Estrutura do Índice

Cada gravação de referência é catalogada com:
- **ID**: Identificador único (REC-YYYY-MM-NNN)
- **Tipo**: discovery | follow_up | closing | rescue | upsell
- **Resultado**: won | lost
- **Score**: Pontuação no scorecard de 100 pontos
- **Destaques**: Momentos-chave para estudo
- **Usado em**: Quais swipe files, treinamentos ou análises utilizam esta gravação

## Gravações Icônicas

| ID | Descrição | Tipo | Score | Referência |
|----|-----------|------|-------|-----------|
| REC-REF-001 | Elane — Auditoria completa exemplar | closing | 92 | `archive/iconic-calls/elane-audit-complete-analysis.md` |
| REC-REF-002 | Discovery perfeita — SPIN completo | discovery | 95 | `archive/iconic-calls/perfect-discovery-example.md` |
| REC-REF-003 | Objection handling exemplar — looping + isolation | closing | 88 | `archive/iconic-calls/perfect-objection-handling.md` |
| REC-REF-004 | Price reveal perfeito — ancoragem + value stack | closing | 90 | `archive/iconic-calls/perfect-price-reveal.md` |
| REC-REF-005 | Close exemplar — assumptive + next step | closing | 93 | `archive/iconic-calls/perfect-close-example.md` |
| REC-REF-006 | Turnaround — deal quase perdido recuperado | rescue | 85 | `archive/iconic-calls/turnaround-call-example.md` |

## Gravações de Estudo de Falha

| ID | Descrição | Tipo | Score | Referência |
|----|-----------|------|-------|-----------|
| REC-FAIL-001 | Perda por discovery rasa | discovery | 42 | `archive/failures-and-lessons/calls-lost-by-weak-discovery.md` |
| REC-FAIL-002 | Perda por price reveal mal feito | closing | 38 | `archive/failures-and-lessons/calls-lost-by-price-reveal.md` |
| REC-FAIL-003 | Perda por falta de frame | closing | 35 | `archive/failures-and-lessons/calls-lost-by-no-frame.md` |
| REC-FAIL-004 | Perda por pressão excessiva | closing | 30 | `archive/failures-and-lessons/calls-lost-by-pressure.md` |
| REC-FAIL-005 | Perda por fechamento fraco | closing | 45 | `archive/failures-and-lessons/calls-lost-by-weak-close.md` |

## Atualização

- Novas gravações adicionadas pelo `win-loss-miner` durante `extract-win-patterns` e `extract-loss-patterns`
- Gravações icônicas curadas pelo `sales-chief` durante `monthly-closer-certification`
- Registro em `data/registries/calls-registry.yaml`
