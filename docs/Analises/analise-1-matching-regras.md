# Análise 1 — Matching (chave NFe + IE)

## Inconsistências encontradas
- Regra de fallback de matching sem IE estava implícita e distribuída entre PRDs.
- PRD 05 citava matching por chave+IE, mas sem regra formal para ERP sem IE.
- PRD 02 dizia IE opcional, mas sem explicitar impacto no matching.
- PRD 03 não deixava explícito que a UI não calcula status.

## Ajustes aplicados
- PRD 07: criada seção oficial **Regra Oficial de Matching (V1)** com regra única e determinística.
- PRD 05: seção de matching atualizada com referência explícita ao PRD 07 e regra operacional textual.
- PRD 02: reforço de que IE ausente no ERP não bloqueia importação nem matching.
- PRD 01: observação de que matching não é validação fiscal e ERP só confirma existência.
- PRD 03: reforço de que UI não depende de IE e apenas exibe status do motor.

## Regras finais consolidadas
1. ERP com IE preenchida: matching por `chave_nfe + inscricao_estadual`.
2. ERP sem IE preenchida: matching apenas por `chave_nfe`.
3. Múltiplos registros ERP com mesma chave: apenas confirmação de existência (`encontrada_no_erp = true`).
4. Não exigir correspondência 1:1 entre SEFAZ e ERP.
5. ERP não cria nota; apenas confirma existência de nota da SEFAZ.
6. Proibido heurística/similaridade/validação por nome ou CNPJ para matching.

## Possíveis riscos remanescentes
- Maior chance de falso positivo quando ERP vier sem IE e existir reutilização indevida de chave em arquivos de baixa qualidade.
- Dependência da qualidade da `chave_nfe` no ERP para manter precisão operacional.
- Necessidade futura de métricas de qualidade de input (sem mudar a regra V1).
