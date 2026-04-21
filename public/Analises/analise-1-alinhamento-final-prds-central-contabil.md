# Análise 1 — Alinhamento final dos PRDs (Central Contábil)

## 1) PRDs revisados

Foram revisados os PRDs no diretório `Central Contabil/PRD`:

- PRD-00 — Visão Geral do Produto
- PRD-01 — Clientes (Módulo Principal / Hub do Sistema)
- PRD-02 — Obrigações (Módulo Operacional)
- PRD-03 — Usuários e Permissões
- PRD-04 — Notificações e Alertas
- PRD-05 — Dashboard Operacional
- PRD-06 — Automação Operacional
- PRD-07 — Padrões do Sistema
- PRD-08 — Busca Global
- PRD-09 — Auditoria e Histórico
- PRD-10 — Arquitetura Conceitual do Sistema
- PRD-11 — Padrão Operacional e UX do Sistema
- PRD-12 — Configuração de Obrigações (Motor de Recorrência)
- PRD-13 — Calendário Operacional

## 2) Inconsistências encontradas

1. Uso ambíguo do termo “responsável” em múltiplos módulos sem distinção entre dono do cliente e executor operacional.
2. Falta de explicitação transversal da hierarquia funcional completa: Escritório → Usuários → Carteira → Cliente → Obrigações/Tarefas.
3. Trechos de Dashboard e Calendário com comportamento de clique direto já esperado na prática, mas sem formalização clara como exceção oficial do padrão de menu “...”.
4. Automação com herança de responsável descrita de forma curta, sem reforço explícito da regra de não acoplamento pós-geração.
5. Auditoria e histórico ainda descrevendo “alteração de responsável” sem qualificar contexto (cliente x obrigação).

## 3) Ajustes aplicados

### 3.1 Separação conceitual obrigatória
- Padronização da distinção entre:
  - **Responsável da Carteira** (nível cliente)
  - **Responsável pela Execução** (nível obrigação/tarefa)
- Inclusão de comentários curtos de alinhamento nos pontos críticos para reduzir dupla interpretação por equipe e IA.

### 3.2 Hierarquia funcional padronizada
- Inclusão/ajuste da hierarquia funcional oficial no PRD-00 e reforço estrutural no PRD-10 (incluindo “Carteiras de Clientes” no diagrama conceitual).

### 3.3 Coerência por módulo
- **Clientes (PRD-01):** campos e colunas alterados para “Responsável da Carteira”; aba de obrigações distinguindo executor.
- **Obrigações (PRD-02):** padronização para “Responsável pela Execução”; ajuste de campo conceitual para `responsavel_execucao_id`.
- **Dashboard (PRD-05):** lista e filtros com “Responsável pela Execução”; reforço de papel de triagem.
- **Calendário (PRD-13):** conteúdo de detalhes e filtros com “Responsável pela Execução”; reforço do papel temporal.
- **Notificações (PRD-04):** destino operacional principal definido como executor da obrigação.
- **Automação (PRD-06 e PRD-12):** herança inicial via carteira documentada com clareza e sem confundir papéis.

### 3.4 Exceções oficiais de UX sem quebrar padrão global
- Formalização de que o menu “...” continua padrão geral.
- Documentação da exceção oficial em Dashboard e Calendário para clique direto abrir drawer/contexto quando reduzir cliques.

### 3.5 Auditoria sem ambiguidade
- Separação explícita de eventos:
  - alteração de Responsável da Carteira (cliente)
  - alteração de Responsável pela Execução (obrigação)

## 4) Dúvidas que deixaram de existir

- Se “responsável” no cliente e na obrigação eram o mesmo conceito.
- Se redistribuir obrigação deveria alterar dono da carteira do cliente.
- Se Dashboard/Calendário podiam usar clique direto sem violar padrão de UX.
- Se notificações operacionais deveriam priorizar o dono da carteira ou o executor.

## 5) Dúvidas residuais (se houver)

No escopo documental atual, não restaram ambiguidades conceituais críticas.

Observação opcional de governança futura: caso o produto deseje múltiplos níveis de ownership (ex.: co-responsável de carteira), isso deve virar regra explícita em novo ciclo de PRD, sem afetar este alinhamento.

## 6) Resumo final do alinhamento conceitual

A base funcional ficou alinhada para desenvolvimento com:

- separação clara entre carteira e execução;
- nomenclatura consistente entre módulos;
- hierarquia funcional explicitada transversalmente;
- papéis de Dashboard, Obrigações, Calendário e Cliente preservados;
- automação com herança inicial de carteira, sem acoplamento indevido pós-geração;
- exceções de UX formalizadas sem romper o padrão global.

Resultado: redução de risco de interpretação ambígua e maior previsibilidade para implementação.
