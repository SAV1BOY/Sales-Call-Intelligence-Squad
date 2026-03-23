# Scorecard de Certificação

> Define os requisitos mínimos por bloco para certificação de closers em cada nível, servindo como régua oficial de aprovação.

## Quando Usar
Como referência durante processos de certificação. Este documento define os critérios — o relatório de certificação aplica estes critérios.

## Estrutura

### Seção 1 — Visão Geral do Sistema de Certificação
Regras gerais do processo.
**Formato**:
```
REGRAS DE CERTIFICAÇÃO:
1. Score total deve atingir o mínimo do nível pleiteado
2. NENHUM bloco pode estar abaixo do mínimo individual do nível
3. Avaliação baseada em mínimo de [N] calls auditadas
4. Calls devem ser de períodos diferentes (não apenas 1 semana)
5. Aprovação condicional: máximo 1 bloco abaixo do mínimo (margem de 1 ponto)
6. Recertificação: a cada [N] meses
```

### Seção 2 — Requisitos por Nível
Tabela de mínimos por bloco e por nível.
**Formato**:
```
| Bloco                    | Peso | Júnior (Min) | Pleno (Min) | Sênior (Min) | Expert (Min) |
|--------------------------|------|--------------|-------------|--------------|--------------|
| Abertura e Rapport       | 10   | 5            | 6           | 8            | 9            |
| Qualificação Inicial     | 10   | 5            | 6           | 7            | 8            |
| Discovery Profunda       | 15   | 7            | 9           | 12           | 13           |
| Apresentação de Valor    | 10   | 5            | 6           | 8            | 9            |
| Prova Social/Autoridade  | 10   | 4            | 6           | 7            | 8            |
| Ancoragem de Preço       | 10   | 4            | 6           | 8            | 9            |
| Tratamento de Objeções   | 15   | 6            | 9           | 11           | 13           |
| Fechamento               | 10   | 4            | 6           | 8            | 9            |
| Next Step Lock           | 5    | 2            | 3           | 4            | 5            |
| Controle de Frame        | 5    | 2            | 3           | 4            | 5            |
| TOTAL MÍNIMO             | 100  | 55           | 70          | 82           | 90           |
| Calls Mínimas Avaliadas  | —    | 5            | 8           | 10           | 12           |
```

### Seção 3 — Descrição dos Níveis
O que cada nível significa operacionalmente.
**Formato**:
```
JÚNIOR (55+ pontos):
- Descrição: Closer em fase de aprendizado, capaz de conduzir calls com supervisão
- Permissões: Calls com leads mornos, ticket até [R$ X], acompanhamento semanal
- Expectativa: Evoluir para Pleno em até [N] meses
- Recertificação: A cada 2 meses

PLENO (70+ pontos):
- Descrição: Closer autônomo que executa o processo de vendas com competência
- Permissões: Todos os leads, todos os tickets, autonomia total
- Expectativa: Manter nível e buscar Sênior
- Recertificação: A cada 4 meses

SÊNIOR (82+ pontos):
- Descrição: Closer de alta performance que serve de referência para o time
- Permissões: Leads estratégicos, mentoria de júniors, input em processo
- Expectativa: Contribuir para elevação do nível do time
- Recertificação: A cada 6 meses

EXPERT (90+ pontos):
- Descrição: Closer excepcional com domínio total das metodologias
- Permissões: Treinamento de novos closers, design de processo, input estratégico
- Expectativa: Referência absoluta de qualidade
- Recertificação: Anual
```

### Seção 4 — Critérios Detalhados por Bloco
O que é avaliado em cada faixa de score.
**Formato**:
```
BLOCO: [Nome do Bloco] (0-[Peso Máximo])

Faixa 0-30% do máximo (Insuficiente):
- [descrição do que o closer faz/não faz nesta faixa]

Faixa 31-50% do máximo (Básico):
- [descrição]

Faixa 51-70% do máximo (Competente):
- [descrição]

Faixa 71-90% do máximo (Avançado):
- [descrição]

Faixa 91-100% do máximo (Excepcional):
- [descrição]
```

### Seção 5 — Processo de Certificação
Passo a passo do processo.
**Formato**:
```
ETAPA 1: Seleção de Calls
- [como as calls são selecionadas para avaliação]

ETAPA 2: Auditoria
- [como as calls são auditadas — padrão, calibração]

ETAPA 3: Cálculo de Scores
- [como a média é calculada — simples, ponderada, descarte de outliers]

ETAPA 4: Aplicação dos Critérios
- [como os mínimos são verificados — total e por bloco]

ETAPA 5: Decisão
- [quem decide — agente, gestor, comitê]

ETAPA 6: Comunicação
- [como o resultado é comunicado ao closer]

ETAPA 7: Plano Pós-Certificação
- [o que acontece depois — desenvolvimento, recertificação]
```

## Exemplo
```
Closer: Rafael Mendes — Pleiteando Pleno (mínimo: 70)

| Bloco             | Score | Mínimo Pleno | Status |
|-------------------|-------|--------------|--------|
| Rapport           | 8.8   | 6            | ✓      |
| Qualificação      | 7.1   | 6            | ✓      |
| Discovery         | 6.1   | 9            | ✗      |
| Apresentação      | 7.4   | 6            | ✓      |
| Prova Social      | 8.2   | 6            | ✓      |
| Pricing           | 4.9   | 6            | ✗      |
| Objeções          | 9.5   | 9            | ✓      |
| Fechamento        | 7.0   | 6            | ✓      |
| Next Step         | 3.2   | 3            | ✓      |
| Frame             | 3.5   | 3            | ✓      |
| TOTAL             | 65.7  | 70           | ✗      |

RESULTADO: REPROVADO — Score total abaixo do mínimo (65.7 < 70) + 2 blocos abaixo do mínimo individual (Discovery, Pricing)
```

## Agente Responsável
`qa-agent` — Mantém os critérios atualizados. `coaching-agent` — Prepara closers para certificação.

## Checklists de Qualidade
- `qa-score-calibration-check.md` — Critérios calibrados e consistentes.

## Preenchido Por

- **Task(s)**: certify-closer
- **Agente(s) responsável(is)**: closer-trainer, qa-guardian, sales-chief
- **Workflow(s)**: Certificação de Closer (quarterly)
- **Frequência**: quarterly
- **Registro**: data/registries/closers-registry
