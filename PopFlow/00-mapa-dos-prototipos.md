# Mapa de Protótipos Visuais — PopFlow

## Objetivo

Este documento organiza os protótipos visuais do PopFlow e relaciona cada tela/módulo aos PRDs correspondentes, para orientar implementações futuras com clareza de escopo entre referência visual e regras funcionais.

## Regra de uso dos protótipos

- Protótipos são referência visual e de UX.
- PRDs são a fonte de verdade funcional.
- Protótipos não devem criar regras funcionais novas.
- Elementos visuais, botões, campos ou comportamentos presentes no HTML só devem ser considerados funcionais se também estiverem previstos no PRD correspondente.
- Em caso de conflito, seguir o PRD.

> **Em caso de conflito entre protótipo visual e PRD, o PRD prevalece. O protótipo deve orientar apenas aparência, organização visual, hierarquia de informação e experiência de navegação, sem criar regras funcionais novas.**

## Ordem sugerida de desenvolvimento

| Ordem | Protótipo visual | Tela/Módulo | PRDs relacionados | Como usar o protótipo |
|---|---|---|---|---|
| 00 | `00-design-system-popflow.md` | Design system | Todos | Referência visual geral de cores, tipografia, espaçamento, cards, botões e linguagem visual. |
| 01 | `01-dashboard-popflow.html` | Dashboard | PRD 5, PRD 8 | Referência visual para indicadores, alertas, cards de resumo e visão operacional inicial. |
| 02 | `02-listagem-de-pops-popflow.html` | Listagem de POPs | PRD 1, PRD 7, PRD 11 | Referência visual para biblioteca/listagem de POPs, filtros, cards e ações. |
| 03 | `03-detalhe-do-pop-popflow.html` | Detalhe do POP | PRD 1, PRD 10, PRD 11, PRD 12 | Referência visual para página de leitura, metadados, ações e estrutura das etapas. |
| 04 | `04-criar-pop-popflow.html` | Criar/Editar POP | PRD 1, PRD 6, PRD 12 | Referência visual para fluxo de cadastro, edição, abas, campos e organização do formulário. |
| 05 | `05-execucao-guiada-midia-contextual-popflow.html` | Execução guiada | PRD 2, PRD 9, PRD 12 | Referência visual prioritária para execução guiada, checklist e mídia contextual inline. |
| 06 | `06-revisoes-popflow.html` | Revisões | PRD 3, PRD 9, PRD 10 | Referência visual para fila de revisão, aprovação, solicitação de ajustes e análise de POPs. |
| 07 | `07-historico-de-versoes-popflow.html` | Histórico de versões | PRD 10 | Referência visual para linha do tempo, versões, auditoria e visualização de alterações. |
| 08 | `08-biblioteca-de-templates-popflow.html` | Templates | PRD 6 | Referência visual para biblioteca de modelos reutilizáveis e uso de templates. |
| 09 | `09-comentarios-e-colaboracao-popflow.html` | Comentários e colaboração | PRD 9 | Referência visual para comentários, threads, resolução de discussões e colaboração por etapa. |
| 10 | `10-analytics-popflow.html` | Analytics | PRD 5 | Referência visual para dashboards, gráficos, métricas e filtros analíticos. |
| 11 | `11-notificacoes-popflow.html` | Notificações | PRD 8 | Referência visual para central de notificações, alertas, prioridades e ações rápidas. |
| 12 | `12-usuarios-e-permissoes-popflow.html` | Usuários e permissões | PRD 4 | Referência visual para administração de usuários, papéis, permissões e status. |

## Como usar em prompts futuros

Ao solicitar implementação futura ao Codex ou Lovable, use este padrão:

> Use o PRD correspondente como fonte de verdade funcional. Use o protótipo HTML correspondente apenas como referência visual e de UX. Em caso de conflito, siga o PRD.

## Observações importantes

- O protótipo pode conter textos, botões, campos ou interações fictícias.
- O protótipo não substitui PRD.
- O protótipo não deve ser usado para inferir regra de negócio.
- O protótipo serve para reduzir retrabalho visual e manter consistência entre telas.
- A ordem dos arquivos indica sequência sugerida de desenvolvimento, não obrigação técnica absoluta.
