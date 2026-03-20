# Relatório de Certificação de Closer

> Relatório formal de certificação que determina se o closer está aprovado ou reprovado com base em critérios objetivos e evidências de múltiplas calls.

## Quando Usar
Ao final do período de certificação (onboarding, recertificação periódica, promoção de nível), para decidir formalmente se o closer está apto a operar de forma autônoma.

## Estrutura

### Seção 1 — Dados da Certificação
Informações administrativas.
**Formato**:
```
Closer: [nome completo]
Tipo de Certificação: [Inicial / Recertificação / Promoção de Nível]
Nível Pleiteado: [Júnior / Pleno / Sênior / Especialista]
Período de Avaliação: [DD/MM a DD/MM/AAAA]
Calls Avaliadas: [N] (mínimo exigido: [N])
Avaliador: [nome/agente]
Data do Relatório: [DD/MM/AAAA]
```

### Seção 2 — Resultado da Certificação
O veredicto.
**Formato**:
```
╔══════════════════════════════════════╗
║  RESULTADO: [APROVADO / REPROVADO]  ║
║  Score Final: [XX/100]              ║
║  Mínimo Exigido: [XX/100]          ║
╚══════════════════════════════════════╝

Condições (se aprovação condicional):
- [condição 1 — ex: "Recertificação do bloco de pricing em 30 dias"]
- [condição 2]
```

### Seção 3 — Scorecard de Certificação
Avaliação detalhada por bloco com mínimo exigido.
**Formato**:
```
| Bloco                    | Score | Mínimo | Status    | Evidência                           |
|--------------------------|-------|--------|-----------|-------------------------------------|
| Abertura e Rapport       | [X/10]| [6]    | [✓ / ✗]  | [resumo com call IDs]               |
| Qualificação Inicial     | [X/10]| [6]    | [✓ / ✗]  | [resumo com call IDs]               |
| Discovery Profunda       | [X/15]| [9]    | [✓ / ✗]  | [resumo com call IDs]               |
| Apresentação de Valor    | [X/10]| [6]    | [✓ / ✗]  | [resumo com call IDs]               |
| Prova Social/Autoridade  | [X/10]| [6]    | [✓ / ✗]  | [resumo com call IDs]               |
| Ancoragem de Preço       | [X/10]| [6]    | [✓ / ✗]  | [resumo com call IDs]               |
| Tratamento de Objeções   | [X/15]| [9]    | [✓ / ✗]  | [resumo com call IDs]               |
| Fechamento               | [X/10]| [6]    | [✓ / ✗]  | [resumo com call IDs]               |
| Next Step Lock           | [X/5] | [3]    | [✓ / ✗]  | [resumo com call IDs]               |
| Controle de Frame        | [X/5] | [3]    | [✓ / ✗]  | [resumo com call IDs]               |
| TOTAL                    | [XX]  | [70]   | [✓ / ✗]  |                                     |

Blocos Aprovados: [N/10]
Blocos Reprovados: [N/10]
Regra: Aprovação exige score total >= [70] E nenhum bloco abaixo do mínimo individual.
```

### Seção 4 — Evidências por Bloco
Detalhamento das calls que fundamentam cada nota.
**Formato**:
```
BLOCO: [Nome do Bloco]
Score: [X/Max]

Call [ID] — Score do Bloco: [X]
- Momento Positivo: "[trecho]" ([MM:SS])
- Momento Negativo: "[trecho]" ([MM:SS])

Call [ID] — Score do Bloco: [X]
- Momento Positivo: "[trecho]" ([MM:SS])
- Momento Negativo: "[trecho]" ([MM:SS])

Avaliação Consolidada: [parágrafo analítico sobre a competência do closer neste bloco]
```

### Seção 5 — Evolução durante o Período
Trajetória de desenvolvimento ao longo da certificação.
**Formato**:
```
| Call # | Data    | Score Total | Tendência | Observação                  |
|--------|---------|-------------|-----------|------------------------------|
| 1      | [DD/MM] | [XX]        | —         | [baseline]                   |
| 2      | [DD/MM] | [XX]        | [↑/↓]    | [o que mudou]                |
| ...    |         |             |           |                              |
| N      | [DD/MM] | [XX]        | [↑/↓]    | [call final de certificação] |

Velocidade de Aprendizado: [Rápida / Normal / Lenta]
Consistência: [Alta / Média / Baixa — desvio padrão dos scores]
```

### Seção 6 — Plano Pós-Certificação
Próximos passos independente do resultado.
**Formato**:
```
SE APROVADO:
- Áreas de desenvolvimento contínuo: [lista]
- Próxima recertificação: [DD/MM/AAAA]
- Metas para próximo nível: [critérios]

SE REPROVADO:
- Gaps críticos a fechar: [lista com prazo]
- Plano de recuperação: [ações específicas]
- Data de recertificação: [DD/MM/AAAA]
- Suporte oferecido: [coaching, mentoria, role-play]
```

## Exemplo
```
Closer: Rafael Mendes | Certificação Inicial — Nível Pleno
Período: 01/02 a 15/03/2026 | 12 calls avaliadas

╔══════════════════════════════╗
║  RESULTADO: APROVADO         ║
║  Score Final: 74/100         ║
║  Mínimo Exigido: 70/100     ║
╚══════════════════════════════╝

Condição: Recertificação do bloco de Ancoragem de Preço (5/10, mínimo 6) em 30 dias.

Blocos Aprovados: 9/10 | Reprovado: Ancoragem de Preço
Evolução: De 61 (call 1) para 78 (call 12) — aprendizado rápido
Consistência: Média (desvio 7.3) — precisa estabilizar

Pós-Certificação: Foco em pricing nas próximas 4 semanas. Recertificação parcial em 15/04/2026.
```

## Agente Responsável
`qa-agent` — Conduz o processo de certificação com base em auditorias do `audit-agent`.

## Checklists de Qualidade
- `qa-score-calibration-check.md` — Scores calibrados e consistentes para decisão de certificação.
- `qa-bias-detection-check.md` — Sem viés na avaliação.
- `qa-evidence-completeness-check.md` — Toda nota justificada com evidência.
- `coaching-progression-check.md` — Evolução documentada com métricas.
