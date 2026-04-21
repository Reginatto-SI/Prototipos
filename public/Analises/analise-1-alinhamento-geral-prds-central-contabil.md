# Análise 1 — Alinhamento Geral dos PRDs do Central Contábil

## Objetivo da revisão
Realizar uma revisão crítica e conservadora de todos os PRDs do diretório `Central Contabil/PRD`, eliminando inconsistências conceituais, estruturais e funcionais entre os documentos, com mudanças mínimas e sem alterar a intenção original do produto.

## PRDs analisados
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

## Inconsistências encontradas
1. Mistura de conceitos entre perfil do cliente e tributação em documentos-base.
2. Diferenças de nomenclatura entre “empresa” e “cliente” em trechos de configuração de obrigações.
3. Ambiguidade pontual entre papel de dashboard (triagem) e papel da execução detalhada.
4. Ambiguidade na ação de notificações para obrigação sem explicitar contexto operacional.
5. PRD-10 com conteúdo de rascunho (formatação de prompt/copiar-colar), duplicidade de campo e baixa consistência estrutural.
6. PRD-11 com conteúdo incorreto (duplicado de auditoria), sem cumprir o título proposto do documento.
7. Necessidade de reforço transversal de regra: status de execução (manual) vs indicador de prazo (automático).

## Correções aplicadas
- Separação explícita em PRD-00 entre:
  - tipo_pessoa (PF/PJ)
  - perfil (classificação operacional)
  - tributação (regime tributário)
- Ajuste em PRD-06 para geração automática considerar `tipo_pessoa`, `perfil` e `tributação` de forma combinada.
- Ajuste em PRD-05 para consolidar limite funcional:
  - dashboard como visão/triagem
  - obrigações como execução detalhada
- Ajuste em PRD-04 para direcionamento de notificação à obrigação em contexto operacional (lista/drawer), mantendo coerência com UX.
- Ajuste em PRD-07 para deixar explícita precedência de drawer quando o módulo definir esse padrão, sem quebrar padrão de modal.
- Ajuste em PRD-12 para padronizar nomenclatura “cliente” no lugar de “empresa” quando tratando entidade central.
- Ajuste em PRD-13 para explicitar na lista do drawer:
  - status de execução (manual)
  - indicador de prazo (automático)
- Reestruturação completa do PRD-10 para arquitetura conceitual consistente com PRDs funcionais, incluindo:
  - separação entre tipo de obrigação (configuração) e obrigação operacional (execução)
  - relações transversais de notificações/auditoria
  - regras de consistência intermodular
- Reescrita do PRD-11 para cumprir seu propósito real (padrão operacional e UX transversal), consolidando regras já existentes sem criar novos módulos.

## Decisões documentais consolidadas
- Cliente permanece como HUB oficial do sistema.
- Multi-tenant por `office_id` mantido em toda a base documental.
- Separação obrigatória entre:
  - configuração de obrigação
  - execução de obrigação
- Separação obrigatória entre:
  - status de execução (manual)
  - indicador de prazo (automático)
- Dashboard, calendário e notificações permanecem como camadas de visão/prioridade/atalho, com execução detalhada concentrada na lista operacional de obrigações.
- Auditoria permanece como trilha oficial de ações manuais e automáticas.

## Riscos evitados
- Implementação futura com filtros/automação incorretos por confusão entre perfil e tributação.
- Modelagem inconsistente entre configuração de obrigação e instância operacional.
- Ambiguidade de UX ao tratar dashboard e obrigações como centros simultâneos de execução detalhada.
- Divergência entre arquitetura conceitual e PRDs funcionais.
- Interpretação equivocada de status operacional versus situação de prazo.

## Dúvidas remanescentes
No momento, não há dúvidas bloqueantes para seguir para prototipação e detalhamento funcional.
