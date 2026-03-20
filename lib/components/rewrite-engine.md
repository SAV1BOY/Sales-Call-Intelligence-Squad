# Engine de Reescrita

> Engine responsável por gerar reescritas de trechos da call onde o closer poderia ter se saído melhor, usando contexto e framework adequado.

## Função
Receber trechos problemáticos da transcrição e gerar versões reescritas que aplicam o framework correto, mantendo o contexto e a naturalidade da conversa.

## Inputs
- Trecho original da transcrição (fala do closer)
- Contexto anterior (últimas 3-5 falas antes do trecho)
- Etapa da call onde o trecho ocorreu
- Tipo de problema identificado (objeção mal tratada, pitch genérico, fechamento fraco, etc.)
- Framework recomendado para a reescrita
- Informações do lead (nicho, dor, linguagem usada)

## Lógica de Processamento
1. Analisar o trecho original e identificar o problema central:
   - Falta de framework (falou sem estrutura)
   - Framework errado (usou técnica inadequada para o contexto)
   - Framework incompleto (começou mas não terminou)
   - Tom inadequado (pressão, passividade, nervosismo)
2. Selecionar o framework mais adequado para o contexto:
   - Considerar etapa da call, tipo de objeção, perfil do lead
   - Priorizar frameworks que o closer já conhece
   - Se closer não conhece o framework, sugerir com explicação
3. Gerar reescrita aplicando o framework:
   - Manter o tom conversacional e natural
   - Usar linguagem compatível com o nível do lead
   - Incorporar informações do discovery (dor, números, palavras do lead)
   - Manter extensão similar ao trecho original (sem inflar)
4. Adicionar explicação da reescrita:
   - O que mudou e por quê
   - Qual framework foi aplicado
   - Resultado esperado da nova abordagem
5. Classificar nível de impacto da reescrita:
   - Ajuste fino (pequena melhoria de linguagem)
   - Correção de rota (mudança de abordagem significativa)
   - Reescrita total (trecho completamente refeito)

## Outputs
- Trecho original vs trecho reescrito (antes/depois)
- Framework aplicado na reescrita
- Explicação da mudança e justificativa
- Nível de impacto (ajuste fino, correção, reescrita total)
- Dica prática para o closer aplicar em futuras calls

## Integração
- Recebe dados da **objection-taxonomy-engine** (objeções para reescrever)
- Recebe dados da **framework-detection-engine** (frameworks adequados)
- Recebe dados da **evidence-tagging-engine** (trechos problemáticos)
- Alimenta os swipe files de **best-rewrites** (melhores reescritas geradas)
- Alimenta o coaching pack do closer (reescritas personalizadas)
