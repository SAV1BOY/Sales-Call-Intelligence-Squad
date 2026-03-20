# 00 — Recording to Transcript

> Transformar a gravação bruta de uma sales call em transcrição limpa, normalizada e segmentada por speakers com timestamps.

## Objetivo

Receber o arquivo de áudio/vídeo da call e produzir uma transcrição textual de alta fidelidade, com identificação de speakers, timestamps precisos e marcação de trechos inaudíveis, pronta para análise downstream.

## Quando Executar

- Imediatamente após o encerramento de qualquer sales call gravada.
- Quando uma gravação histórica for submetida para auditoria retroativa.
- Quando houver reprocessamento solicitado por falha na transcrição anterior.

## Agentes Envolvidos

| Agente | Papel neste workflow |
|--------|---------------------|
| transcript-analyst | Responsável principal pela transcrição, limpeza e normalização do áudio em texto estruturado |

## Frameworks Utilizados

- transcript-normalization-standard
- speaker-diarization-protocol

## Checklists Obrigatórios

- transcript-normalization-quality
- audio-intake-checklist

## Etapas

### Etapa 1 — Intake do Áudio
**Responsável**: transcript-analyst
**Input**: Arquivo de áudio/vídeo da call (MP3, MP4, WAV, ou link de plataforma como Zoom/Google Meet)
**Ação**:
1. Verificar integridade do arquivo (duração, formato, tamanho).
2. Confirmar que o áudio possui qualidade mínima para transcrição (SNR aceitável).
3. Registrar metadados: data da call, closer envolvido, lead ID, produto/oferta discutida.
4. Se o áudio estiver corrompido ou inaudível em mais de 20%, rejeitar e solicitar regravação ou fonte alternativa.
**Output**: Arquivo de áudio validado + ficha de metadados preenchida.
**Quality Gate**: audio-intake-checklist (formato OK, duração > 5min, SNR aceitável, metadados completos).

### Etapa 2 — Transcrição Bruta (Raw Transcript)
**Responsável**: transcript-analyst
**Input**: Arquivo de áudio validado
**Ação**:
1. Submeter o áudio ao engine de transcrição (Whisper, AssemblyAI, ou equivalente).
2. Gerar transcrição bruta com timestamps a cada utterance.
3. Aplicar diarização de speakers para separar closer vs. lead (e eventuais terceiros).
4. Marcar trechos com confiança abaixo de 85% como `[inaudível]` ou `[verificar]`.
5. Preservar interjeições, hesitações e sobreposições relevantes.
**Output**: Transcrição bruta com timestamps e speakers identificados como Speaker_1, Speaker_2.
**Quality Gate**: Cobertura mínima de 95% do áudio transcrito; trechos inaudíveis < 5%.

### Etapa 3 — Identificação e Nomeação de Speakers
**Responsável**: transcript-analyst
**Input**: Transcrição bruta + metadados da call
**Ação**:
1. Cruzar metadados (nome do closer, nome do lead) com os speakers identificados.
2. Analisar contexto conversacional para confirmar quem é quem (quem faz perguntas de diagnóstico = closer; quem responde sobre sua situação = lead).
3. Substituir Speaker_1/Speaker_2 por nomes reais ou roles (Closer: João, Lead: Maria).
4. Em caso de mais de 2 participantes, identificar cada um (ex: Manager, Cônjuge, Sócio).
**Output**: Transcrição com speakers nomeados corretamente.
**Quality Gate**: 100% dos speakers identificados; nenhum trecho atribuído ao speaker errado.

### Etapa 4 — Normalização e Limpeza
**Responsável**: transcript-analyst
**Input**: Transcrição com speakers nomeados
**Ação**:
1. Corrigir erros óbvios de transcrição (nomes próprios, termos técnicos do produto, valores monetários).
2. Padronizar formato de timestamps (HH:MM:SS).
3. Remover artefatos de áudio transcritos erroneamente (ruídos interpretados como palavras).
4. Manter linguagem coloquial original — não "corrigir" a fala do lead ou do closer.
5. Inserir marcadores de pausa significativa `[pausa 3s]` quando relevante.
6. Padronizar formatação de valores: R$ X.XXX,XX.
**Output**: Transcrição limpa e normalizada.
**Quality Gate**: transcript-normalization-quality (formato padronizado, nomes corretos, valores legíveis, sem artefatos).

### Etapa 5 — Segmentação por Blocos Temporais
**Responsável**: transcript-analyst
**Input**: Transcrição limpa
**Ação**:
1. Dividir a transcrição em blocos de ~1 minuto para facilitar referência.
2. Marcar início e fim de cada bloco com timestamp.
3. Adicionar header descritivo para cada bloco (ex: "Bloco 03:00-04:00 — Closer pergunta sobre situação atual").
4. Gerar índice navegável no topo do documento.
**Output**: Transcrição segmentada com índice de blocos.
**Quality Gate**: Todos os blocos possuem header descritivo; índice reflete conteúdo real.

### Etapa 6 — Exportação e Registro
**Responsável**: transcript-analyst
**Input**: Transcrição final segmentada
**Ação**:
1. Exportar em formato Markdown padronizado.
2. Nomear arquivo: `YYYY-MM-DD_closer-name_lead-name_transcript.md`.
3. Registrar no registry de transcrições com status "pronta para análise".
4. Notificar pipeline de que a transcrição está disponível para o próximo workflow.
**Output**: Arquivo de transcrição final publicado + registro atualizado.
**Quality Gate**: Arquivo salvo no diretório correto, registry atualizado, próximo workflow notificado.

## Templates de Output

- transcript-output-template (formato padrão de transcrição segmentada)

## Registries Atualizados

- transcript-registry (nova entrada com metadados e status)
- call-log-registry (atualização do status da call para "transcrita")

## Critérios de Conclusão

- [ ] Áudio validado e metadados registrados
- [ ] Transcrição com cobertura >= 95% do áudio
- [ ] Speakers corretamente identificados e nomeados
- [ ] Formatação normalizada conforme transcript-normalization-quality
- [ ] Segmentação por blocos com índice navegável
- [ ] Arquivo exportado e registry atualizado

## Próximo Workflow

→ 01-transcript-cleaning-and-segmentation.md (limpeza avançada e segmentação por fase da call)

---

## Quality Gates por Step

| Transição | Gate | Critério Pass | Rework Path |
|-----------|------|--------------|-------------|
| Etapa 1 → Etapa 2 | audio-intake-checklist | Formato OK, duração > 5min, SNR aceitável, metadados completos | Voltar a Etapa 1 (solicitar regravação ou fonte alternativa) |
| Etapa 2 → Etapa 3 | Cobertura mínima de transcrição | >= 95% do áudio transcrito; trechos inaudíveis < 5% | Voltar a Etapa 2 (reprocessar com engine alternativo ou ajustar parâmetros) |
| Etapa 3 → Etapa 4 | Identificação completa de speakers | 100% dos speakers identificados e nenhum trecho atribuído incorretamente | Voltar a Etapa 3 (revisar diarização e cruzar metadados) |
| Etapa 4 → Etapa 5 | transcript-normalization-quality | Formato padronizado, nomes corretos, valores legíveis, sem artefatos de áudio | Voltar a Etapa 4 (corrigir termos, formatos e artefatos remanescentes) |
| Etapa 5 → Etapa 6 | Segmentação completa com índice | Todos os blocos possuem header descritivo; índice reflete conteúdo real | Voltar a Etapa 5 (ajustar headers e regenerar índice) |
| Etapa 6 → Conclusão | Exportação e registro validados | Arquivo salvo no diretório correto, registry atualizado, próximo workflow notificado | Voltar a Etapa 6 (corrigir nome do arquivo ou atualizar registry) |

## Decision Points
- Após Etapa 1: se áudio íntegro e SNR aceitável → prosseguir para Etapa 2; se áudio corrompido ou inaudível > 20% → rejeitar e solicitar regravação ou fonte alternativa
- Após Etapa 2: se cobertura >= 95% e trechos inaudíveis < 5% → prosseguir para Etapa 3; se cobertura < 95% → reprocessar com engine alternativo ou aplicar filtragem de ruído antes de nova tentativa
- Após Etapa 3: se todos os speakers identificados com confiança → prosseguir para Etapa 4; se há ambiguidade na identificação (ex: 3+ participantes sem metadados claros) → escalar para confirmação manual com gestor da call

## Escalation Triggers
- Se áudio possui qualidade degradada mas não atinge o limiar de rejeição (inaudível entre 10-20%) → pausar workflow, escalar para sales-chief para decisão sobre prosseguir com scope reduzido ou aguardar fonte alternativa
- Se a transcrição bruta apresenta divergências significativas entre engines diferentes → escalar para transcript-analyst sênior para arbitragem
- Se metadados estão incompletos e não é possível identificar closer ou lead → escalar para sales-chief para preenchimento antes de prosseguir
