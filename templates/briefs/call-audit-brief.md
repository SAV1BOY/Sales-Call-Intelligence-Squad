# Brief de Auditoria de Call

> Documento de entrada que consolida todos os dados necessários para iniciar uma auditoria de call de vendas.

## Quando Usar
Antes de iniciar qualquer auditoria de call. Este brief é o ponto de partida obrigatório que garante que o auditor tem todos os dados necessários antes de ouvir a gravação.

## Estrutura

### Seção 1 — Identificação da Call
Dados básicos para localizar e contextualizar a call.
**Formato**:
```
Call ID: [ID único da call]
Data/Hora: [DD/MM/AAAA HH:MM]
Duração: [MM:SS]
Link da Gravação: [URL]
Link da Transcrição: [URL ou "não disponível"]
```

### Seção 2 — Dados do Closer
Informações sobre quem conduziu a call.
**Formato**:
```
Nome do Closer: [nome completo]
Tempo de Empresa: [X meses/anos]
Score Médio Atual: [XX/100]
Última Auditoria: [DD/MM/AAAA — Score: XX]
Áreas de Foco Atual: [lista das prioridades de coaching vigentes]
```

### Seção 3 — Dados do Lead
Informações sobre o prospect que participou da call.
**Formato**:
```
Nome do Lead: [nome]
Empresa/Segmento: [empresa — segmento de mercado]
Cargo/Papel: [cargo — decisor/influenciador/usuário]
Origem do Lead: [fonte de tráfego — campanha específica]
Nível de Consciência Estimado: [inconsciente/problema/solução/produto/mais consciente]
Temperatura: [frio/morno/quente]
Interações Anteriores: [SDR call, email, evento — ou "primeiro contato"]
```

### Seção 4 — Dados da Oferta
O que foi apresentado ao lead.
**Formato**:
```
Produto/Serviço: [nome da oferta]
Ticket: [R$ XX.XXX]
Condições: [à vista, parcelado, bônus ativos]
Promoção Vigente: [sim/não — detalhes]
Materiais de Apoio Usados: [proposta, deck, demo — ou "nenhum"]
```

### Seção 5 — Resultado da Call
O desfecho e próximos passos.
**Formato**:
```
Resultado: [Vendeu / Não vendeu / Follow-up agendado / No-show parcial]
Se vendeu: [valor fechado, condição, data de fechamento]
Se não vendeu: [motivo declarado pelo lead]
Próximo Passo: [descrição do que foi combinado]
Data do Próximo Passo: [DD/MM/AAAA ou "não definido"]
```

### Seção 6 — Contexto Adicional
Informações relevantes que podem influenciar a análise.
**Formato**:
```
Observações do Closer: [notas livres do closer sobre a call]
Observações do Gestor: [pedidos específicos de análise, se houver]
Foco Especial da Auditoria: [análise geral / foco em discovery / foco em pricing / etc.]
```

## Exemplo
```
Call ID: CALL-2026-0342
Data/Hora: 18/03/2026 14:30
Duração: 47:22
Link da Gravação: https://plataforma.com/calls/0342
Link da Transcrição: https://plataforma.com/transcripts/0342

Nome do Closer: Rafael Mendes
Tempo de Empresa: 8 meses
Score Médio Atual: 72/100
Última Auditoria: 11/03/2026 — Score: 69
Áreas de Foco Atual: Discovery profunda, Ancoragem de preço

Nome do Lead: Carla Souza
Empresa/Segmento: TechFlow — SaaS B2B
Cargo/Papel: CEO — Decisora
Origem do Lead: Meta Ads — Campanha "Escala Q1"
Nível de Consciência Estimado: Consciente da solução
Temperatura: Morno
Interações Anteriores: SDR call em 15/03

Produto/Serviço: Mentoria Premium
Ticket: R$ 12.000
Condições: 12x R$ 1.000 ou R$ 10.800 à vista
Promoção Vigente: Não

Resultado: Não vendeu
Motivo: "Preciso pensar"
Próximo Passo: Follow-up em 20/03
Foco Especial da Auditoria: Análise geral com atenção a pricing
```

## Agente Responsável
`orchestrator-agent` — Compila o brief antes de acionar a auditoria.

## Checklists de Qualidade
- Nenhum checklist específico — este é o documento de entrada.
- Completude dos campos é validada pelo orchestrator antes de prosseguir.
