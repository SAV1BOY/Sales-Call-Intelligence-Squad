# Fase 0 — Intake

> Recebimento da call, validação de metadados e registro no sistema para início do pipeline de auditoria.

## Objetivo
Garantir que a call entra no pipeline com todas as informações necessárias para uma auditoria completa e contextualizada.

## Inputs
- Transcrição bruta da call (texto ou arquivo de áudio com transcrição)
- Nome do closer e ID no registry
- Data e horário da call
- Resultado da call (ganhou, perdeu, reagendou, no-show)
- Ticket do produto/serviço oferecido
- Origem do lead (campanha, canal, fonte)
- Contexto adicional: tipo de call (primeiro contato, follow-up), nicho do prospect

## Atividades
1. Validar que a transcrição está legível e completa (início ao fim da call)
2. Verificar que todos os metadados obrigatórios foram fornecidos
3. Gerar ID único da call seguindo padrão: CALL_YYYYMMDD_CLXXX_SEQ
4. Gerar ID da auditoria: AUD_YYYYMMDD_CALL-ID
5. Registrar a call no registry com status "em auditoria"
6. Classificar prioridade: alta (call perdida + ticket alto), média (call perdida + ticket médio), baixa (call ganha)
7. Verificar se o closer tem auditorias anteriores no registry para contexto histórico

## Agentes Responsáveis
- Intake Agent (responsável principal)
- Registry Manager (suporte para verificação de histórico)

## Output
- Call registrada com ID único e todos os metadados preenchidos
- Status "em auditoria" no registry
- Prioridade classificada
- Contexto histórico do closer disponível (se existir)

## Critérios de Conclusão
- [ ] Transcrição validada como legível e completa
- [ ] Todos os 7 metadados obrigatórios preenchidos
- [ ] ID da call e da auditoria gerados corretamente
- [ ] Call registrada no registry
- [ ] Prioridade definida

## Próxima Fase
→ Fase 1 — Limpeza de Transcrição
