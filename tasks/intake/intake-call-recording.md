# Intake de Gravação de Call

> Receber gravação de call de vendas, registrar metadata completa e preparar para auditoria.

## Objetivo
Garantir que toda call que entra no sistema tenha metadata padronizada, rastreável e completa — permitindo que os agentes downstream trabalhem com contexto total.

## Trigger
- Nova gravação de call recebida (upload manual ou integração)
- Solicitação de auditoria por gestor comercial

## Agentes Envolvidos
| Agente | Papel |
|--------|-------|
| Transcript Analyst | Recebe a gravação, extrai/valida transcrição |
| Call Auditor | Valida completude da metadata antes de prosseguir |
| Sales Chief | Aprova intake em casos de prioridade ou exceção |

## Inputs
- Arquivo de gravação (áudio ou vídeo)
- Nome do closer
- Nome/identificação do lead
- Oferta apresentada na call
- Data e horário da call
- Resultado declarado (ganhou, perdeu, no-show, follow-up)
- Origem do lead (canal de tráfego, campanha)
- SDR responsável pelo agendamento (se aplicável)

## Processo
1. Receber gravação e verificar qualidade do áudio (audível, sem cortes, duração mínima)
2. Extrair ou receber transcrição bruta da call
3. Registrar metadata no `calls-registry.yaml`: closer, lead, oferta, data, resultado, origem, SDR
4. Atribuir ID único à call seguindo padrão `CALL-YYYY-MM-DD-NNN`
5. Classificar prioridade de auditoria (alta se close rate do closer < 30% ou call > 60min)
6. Criar brief de auditoria usando template `briefs/call-audit-brief`
7. Encaminhar para normalização de transcrição (`normalize-transcript`)

## Frameworks Aplicados
- Sales Call Stage Taxonomy (para pré-classificação de tipo de call)

## Checklists de Qualidade
- Áudio audível e completo (sem cortes que comprometam análise)
- Todos os campos de metadata preenchidos
- ID único atribuído sem duplicidade
- Brief de auditoria criado com contexto completo
- Call registrada no registry antes de prosseguir

## Output Esperado
- Entrada no `data/registries/calls-registry.yaml` com metadata completa
- Brief de auditoria preenchido em `data/briefs/`
- Transcrição bruta disponível em `data/transcripts/raw/`

## Registry Atualizado
- `data/registries/calls-registry.yaml`

## Critérios de Conclusão
- [ ] Gravação recebida e armazenada com ID único
- [ ] Metadata completa registrada (closer, lead, oferta, data, resultado, origem)
- [ ] Brief de auditoria criado
- [ ] Transcrição bruta extraída ou recebida
- [ ] Call encaminhada para normalização

---

## Contexto
Sem intake padronizado, calls entram no sistema com metadata incompleta, gerando retrabalho em todas as etapas downstream. Esta task existe para garantir que toda gravação tenha contexto completo e rastreável desde o primeiro momento.

## Especificação de I/O
- **Input**: Arquivo de gravação (áudio/vídeo) + nome do closer + lead + oferta + data + resultado + origem + SDR
- **Output**: Entrada em `data/registries/calls-registry.yaml` + brief em `templates/briefs/call-audit-brief` + transcrição bruta em `data/transcripts/raw/`

## Quality Gates Intermediários
- Após registro de metadata (step 3): checklist `transcript-normalization-quality` — todos os campos preenchidos, ID único atribuído, sem duplicidade
- Antes de output final: brief de auditoria criado com contexto completo, áudio validado como audível

## Escalation & Rework
- Se áudio < 80% audível ou duração < 5 minutos: escalar para `transcript-analyst` com flag `low_audio_confidence`
- Se quality gate falha: rework loop (max 2 ciclos), depois escalar para `sales-chief`

## Métricas de Sucesso
- `audit_cycle_time`: tempo entre recebimento da gravação e início da auditoria
- `cross_squad_delivery_rate`: % de calls com metadata completa na primeira tentativa

## Referências Cruzadas
- Workflow: `workflows/00-recording-to-transcript.md`, `workflows/06-full-funnel-call-audit.md`
- Agents: `agents/transcript-analyst.md`, `agents/call-auditor.md`, `agents/sales-chief.md`
- Templates: `templates/briefs/call-audit-brief.md`
- Registries atualizados: `data/registries/calls-registry.yaml`
