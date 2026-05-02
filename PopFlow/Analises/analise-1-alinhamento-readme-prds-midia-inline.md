# Análise 1 — Alinhamento README e PRDs sobre mídia inline

## Diagnóstico das inconsistências encontradas
- O README orientava como comportamento principal “Clique → exibe mídia no painel lateral”, conflitando com a decisão atual de produto.
- O PRD 12 ainda trazia “Painel lateral dinâmico (RECOMENDADO)” e referência explícita a painel lateral para imagem/áudio.
- O PRD 12 já tinha uma extensão para documentos inline, mas a visão/escopo principal no topo ainda estava centrada em imagem, áudio e vídeo.
- O PRD 2 não conflita diretamente, mas não reforçava explicitamente a regra de mídia contextual sem compressão lateral.
- O PRD 1 mencionava anexos, porém sem explicitar referências inline e sem reforçar ausência de drawer lateral fixo.

## Arquivos analisados
- `README.txt`
- `PRD/PRD 1 — SISTEMA DE POPs (VERSÃO 1.0).txt`
- `PRD/PRD 2 — Execução de Processos com Tracking de Usuário.txt`
- `PRD/PRD 3 — Sistema de Revisão e Aprovação de POPs.txt`
- `PRD/PRD 4 — Permissões e Multi-Empresa (Multi-Tenant).txt`
- `PRD/PRD 5 — Analytics Operacional.txt`
- `PRD/PRD 6 — Templates de POP (Modelos Reutilizáveis).txt`
- `PRD/PRD 7 — Sistema de Busca Inteligente (Base de Conhecimento).txt`
- `PRD/PRD 8 — Notificações e Alertas Operacionais.txt`
- `PRD/PRD 9 — Sistema de Comentários e Colaboração.txt`
- `PRD/PRD 10 — Versionamento Avançado de POPs.txt`
- `PRD/PRD 11 — Sistema de Visibilidade e Compartilhamento de POPs.txt`
- `PRD/PRD 12 — Sistema de Mídia Inline Multimodal (Texto + Imagem + Áudio + Vídeo).txt`

## Arquivos alterados
- `README.txt`
- `PRD/PRD 1 — SISTEMA DE POPs (VERSÃO 1.0).txt`
- `PRD/PRD 2 — Execução de Processos com Tracking de Usuário.txt`
- `PRD/PRD 12 — Sistema de Mídia Inline Multimodal (Texto + Imagem + Áudio + Vídeo).txt`

## Resumo das alterações feitas
- README atualizado para remover recomendação de painel lateral fixo e definir abertura contextual por tipo (imagem/vídeo/documento em modal; áudio em mini-player flutuante).
- PRD 12 alinhado para:
  - incluir documento/PDF no escopo principal;
  - substituir a recomendação de painel lateral por visualização contextual sem drawer;
  - detalhar comportamento por tipo incluindo documento/PDF;
  - ajustar estrutura de dados para contemplar tipo documento.
- PRD 2 recebeu observação curta no bloco de princípios de UX/UI reforçando foco da execução sem compressão lateral por drawer fixo.
- PRD 1 recebeu ajuste de linguagem para explicitar referências inline de mídia/anexos e reforço de mídia contextual sem drawer lateral fixo.

## Pontos que já estavam corretos
- O PRD 12 já possuía seção de extensão com documentos inline e formatos de arquivo.
- O PRD 2 já enfatizava interface limpa, redução de distrações e foco na etapa atual.
- O PRD 1 já mantinha foco em execução e interface limpa.

## Pontos que ainda dependem de decisão futura
- Critério objetivo de quando documentos devem abrir em modal vs nova aba (regra técnica por tamanho/formato/navegador).
- Definição de persistência e posicionamento final do mini-player de áudio em diferentes tamanhos de tela.

## Confirmação final
README e PRDs relevantes ficaram alinhados com a regra oficial de produto: mídia inline contextual, sem drawer lateral fixo como comportamento padrão, preservando foco da execução.
