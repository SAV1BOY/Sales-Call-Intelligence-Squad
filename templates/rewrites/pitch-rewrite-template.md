# Template de Reescrita de Pitch

> Reescrita de pitch de apresentação conectando diretamente à fala e dor do lead revelada na discovery.

## Quando Usar
Quando o closer fez uma apresentação genérica que não amarrou à dor específica do lead, ou quando o pitch não ressoou e o lead perdeu interesse.

## Estrutura

### Seção 1 — Contexto da Apresentação
Dados do momento.
**Formato**:
```
Call ID: [ID]
Closer: [nome]
Trecho da Apresentação: [MM:SS a MM:SS]
Duração do Pitch: [MM:SS]
Fase: [após discovery — adequado / sem discovery — prematuro]
Engajamento do Lead: [Alto / Médio / Baixo — sinais observados]
```

### Seção 2 — Dor Revelada na Discovery
O que o lead disse que deveria ter guiado o pitch.
**Formato**:
```
DOR PRINCIPAL:
Fala do Lead: "[trecho exato onde revelou a dor]" ([MM:SS])
Palavras-Chave: [termos específicos que o lead usou]
Emoção Detectada: [frustração / medo / desejo / urgência]
Impacto Quantificado: [se o lead mencionou números — R$, tempo, % de perda]

DOR SECUNDÁRIA:
Fala do Lead: "[trecho]" ([MM:SS])
```

### Seção 3 — Pitch Original (ANTES)
O que o closer disse.
**Formato**:
```
PITCH ORIGINAL:
"[transcrição do pitch do closer — trecho completo relevante]"

DIAGNÓSTICO:
- Conectou à dor do lead: [Sim / Não / Parcialmente]
- Usou palavras do lead: [Sim / Não]
- Focou em features vs. benefícios: [features / benefícios / misto]
- Tom: [entusiasmado / robótico / inseguro / consultivo]
- Reação do Lead: "[o que o lead disse/fez durante o pitch]" ([MM:SS])
- O que Faltou: [o que deveria ter sido incluído]
```

### Seção 4 — Pitch Reescrito (DEPOIS)
A versão que amarra à fala do lead.
**Formato**:
```
TÉCNICA: [Ponte Dor→Solução / Storytelling Espelhado / Antes→Depois→Ponte]

PITCH REESCRITO:

"[Abertura conectando diretamente à fala do lead]
Closer: 'Carla, você mencionou que [usar palavras exatas do lead]. E isso tá custando [impacto que ela mencionou].

O que a gente faz é exatamente resolver [dor nas palavras dela]. Na prática, funciona assim: [explicação do mecanismo em linguagem simples].

Por exemplo, a [cliente similar] estava na mesma situação — [descrever situação espelhada]. Em [prazo], ela conseguiu [resultado específico e quantificado].

O que isso significa pra você é que [benefício traduzido para a realidade da Carla], em vez de continuar [consequência da inação que ela mesma descreveu].'
"

ESTRUTURA DO REWRITE:
1. Espelho: Repetir as palavras exatas do lead
2. Ponte: Conectar a dor ao mecanismo da solução
3. Prova: Case similar com resultado quantificado
4. Projeção: Traduzir o resultado para a realidade do lead
5. Contraste: Comparar com a alternativa de não agir
```

### Seção 5 — Justificativa
Por que o rewrite é mais eficaz.
**Formato**:
```
POR QUE FUNCIONA:
1. [Usa as palavras do lead — gera identificação imediata]
2. [Conecta feature a benefício que resolve a dor específica]
3. [Case similar cria "se funcionou pra ela, funciona pra mim"]
4. [Contraste com inação gera urgência natural]

ERROS DO ORIGINAL:
1. [Erro 1 — ex: "pitch genérico que serviria para qualquer lead"]
2. [Erro 2 — ex: "listou features sem conectar a benefícios"]
```

## Exemplo
```
CALL-2026-0342 | Rafael | Pitch: 14:30 a 22:00

DOR DO LEAD (10:45): "Eu gasto tipo 3 horas por dia tentando gerar lead e não converte nada"
Palavras-chave: "gasto 3 horas", "não converte nada"

ANTES: "Então, a nossa mentoria tem 8 módulos, acesso vitalício, grupo de mastermind, suporte individual..."
Diagnóstico: Listou features, zero conexão com a dor. Lead ficou em silêncio.

DEPOIS: "Carla, você falou uma coisa que me chamou atenção — 3 horas por dia tentando gerar lead e sem conversão. São 60 horas por mês que você tá investindo sem retorno. O que a gente faz é eliminar esse desperdício. Em vez de você tentar sozinha, a gente implementa um sistema que já trouxe resultado pra mais de 200 empresas como a sua. A Marina, da TechStar — situação idêntica à sua — em 45 dias parou de prospectar manualmente e passou a receber 15 leads qualificados por semana. Pra você, isso significa sair dessas 3 horas diárias e usar esse tempo pra fechar, não pra prospectar."
```

## Agente Responsável
`coaching-agent` — Cria rewrites de pitch como parte do coaching.

## Checklists de Qualidade
- `coaching-specificity-check.md` — Rewrite usa dados reais da call.
- `coaching-actionability-check.md` — Closer consegue replicar a estrutura.
