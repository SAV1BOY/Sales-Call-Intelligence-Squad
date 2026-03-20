# Fase 1 — Detecção de Frameworks nas Calls Ganhas

> Mapear todos os frameworks utilizados nas calls ganhas para identificar quais técnicas correlacionam com sucesso.

## Objetivo
Criar um mapa completo de frameworks usados em calls ganhas, incluindo frequência, combinações e qualidade de aplicação.

## Inputs
- 25-30 calls ganhas selecionadas (output da Fase 0)
- Biblioteca de frameworks do squad

## Atividades
1. Executar detecção de frameworks completa para cada call
2. Registrar cada framework detectado com: etapa, classificação (correto/parcial/incorreto), evidência
3. Calcular frequência de cada framework: em quantas calls ganhas ele aparece?
4. Identificar combinações de frameworks recorrentes (ex: NEPQ + Value Equation + Assumptive Close)
5. Mapear a sequência temporal dos frameworks mais comuns (ex: Frame Setting → SPIN → Value Stack → Isolation → Assumptive)
6. Comparar com dados de calls perdidas (se disponíveis): quais frameworks aparecem mais em ganhas que em perdidas?
7. Identificar frameworks "diferenciadores": que aparecem quase exclusivamente em calls ganhas

## Agentes Responsáveis
- Framework Detector (responsável principal)
- Technique Classifier (classificação de aplicação)
- Win/Loss Correlator (comparação com calls perdidas)

## Output
- Mapa de frameworks por call com classificação
- Ranking de frameworks por frequência em calls ganhas
- Top 5 combinações de frameworks mais eficazes
- Lista de frameworks diferenciadores

## Critérios de Conclusão
- [ ] Todas as calls analisadas com detecção de frameworks
- [ ] Frequências calculadas
- [ ] Combinações identificadas
- [ ] Diferenciadores mapeados

## Próxima Fase
→ Fase 2 — Extração de Padrões

