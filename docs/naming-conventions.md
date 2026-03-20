# Convenções de Nomenclatura

> Padrões oficiais para nomear arquivos, registries, IDs, tags e referências dentro do squad.

## Princípios Gerais

- Usar inglês para nomes de arquivos e IDs técnicos
- Usar português (BR) para conteúdo dentro dos arquivos
- Separar palavras com hífen (-) em nomes de arquivo
- Separar palavras com underscore (_) em IDs de registro
- Usar letras minúsculas sempre (exceto siglas como SPIN, NEPQ)
- Evitar caracteres especiais, acentos e espaços em nomes de arquivo

## Nomenclatura de Arquivos

### Documentação (docs/)
Padrão: `<assunto-principal>.md`
Exemplos: `getting-started.md`, `scoring-methodology.md`, `glossary.md`

### Resumos de Especialistas (authority/specialist-summaries/)
Padrão: `<sobrenome-especialista>-summary.md`
Exemplos: `hormozi-summary.md`, `miner-summary.md`, `belfort-summary.md`

### Cases (authority/case-studies/)
Padrão: `<contexto>-<tipo>-<descrição>.md`
Exemplos: `healthcare-closer-audit-case.md`, `closer-turnaround-30-days.md`

### Workshops (authority/workshop-kits/)
Padrão: `<tema-principal>-workshop.md`
Exemplos: `call-audit-workshop.md`, `objection-handling-workshop.md`

### Projetos (projects/)
Padrão de pasta: `<nome-do-projeto>/`
Padrão de arquivo: `<número-sequencial>-<atividade>.md`
Exemplos: `00-intake.md`, `01-transcript-cleaning.md`, `02-segmentation.md`

### Arquivo (archive/)
Padrão por subpasta:
- `iconic-calls/`: `<tipo-de-call>-example.md` ou `<nome>-audit-complete-analysis.md`
- `evolution/`: `evolution-<tema>.md`
- `failures-and-lessons/`: `calls-lost-by-<causa>.md`

## IDs de Registro

### ID de Call
Padrão: `CALL_<YYYYMMDD>_<closer-id>_<seq>`
Exemplo: `CALL_20260315_CL042_001`

### ID de Closer
Padrão: `CL<número-sequencial-3-dígitos>`
Exemplo: `CL042`, `CL001`, `CL128`

### ID de Auditoria
Padrão: `AUD_<YYYYMMDD>_<call-id>`
Exemplo: `AUD_20260316_CALL_20260315_CL042_001`

### ID de Coaching Sprint
Padrão: `COACH_<YYYYMMDD>_<closer-id>`
Exemplo: `COACH_20260301_CL042`

## Tags de Classificação

### Tags de Resultado
- `#won` — call que resultou em venda
- `#lost` — call que não resultou em venda
- `#no-show` — prospect não compareceu
- `#rescheduled` — call reagendada

### Tags de Framework
- `#spin` — SPIN Selling detectado
- `#nepq` — NEPQ detectado
- `#straight-line` — Straight Line detectado
- `#challenger` — Challenger Sale detectado
- `#closer-framework` — CLOSER de Hormozi detectado

### Tags de Qualidade
- `#gold-standard` — call de referência (score 90+)
- `#needs-coaching` — call que requer intervenção (score abaixo de 55)
- `#turnaround` — call que demonstrou virada significativa

### Tags de Contexto
- `#high-ticket` — ticket acima de R$ 10k
- `#premium` — ticket acima de R$ 50k
- `#b2b` — venda business-to-business
- `#b2c` — venda business-to-consumer
- `#first-call` — primeiro contato
- `#follow-up` — call de follow-up

## Versionamento

Documentos versionados seguem o padrão: `v<major>.<minor>`
Exemplo: `v1.0`, `v1.1`, `v2.0`
- Major: mudança estrutural significativa
- Minor: ajustes, correções, adições incrementais
