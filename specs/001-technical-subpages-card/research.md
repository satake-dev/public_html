# Research: Card de Subpáginas Técnicas

## Decision 1: Estrategia de navegação para subpáginas técnicas
- Decision: Usar um card técnico na home como hub com lista explicita de subpáginas e rotas estaticas dedicadas por assunto.
- Rationale: Mantem simplicidade arquitetural, facilita descoberta de conteúdo e reduz friccao para acessar experiências e ferramentas.
- Alternatives considered:
  - Conteúdo técnico todo na home: rejeitado por reduzir escaneabilidade e aumentar densidade visual.
  - Menu técnico global sem card: rejeitado por perder destaque contextual da seção profissional.

## Decision 2: Primeiro item do menu (Windows + WSL)
- Decision: O primeiro item redireciona para uma página dedicada ao ambiente de desenvolvimento Windows + WSL, com narrativa técnica da transição de Linux em dual boot para WSL.
- Rationale: Atende diretamente o pedido da feature e comunica maturidade de percurso técnico com contexto histórico e prático.
- Alternatives considered:
  - Página curta apenas com lista de ferramentas: rejeitado por não contextualizar decisoes e trade-offs.
  - Artigo focado somente em instalacao: rejeitado por ser utilitario demais para um portfolio técnico.

## Decision 3: Estrutura de conteúdo da subpágina Windows + WSL
- Decision: Estruturar a página com seções de contexto, evolução histórica, fluxo atual, comandos Linux de referência e orientações de uso.
- Rationale: Equilibra storytelling técnico com utilidade pratica e reforca identidade de arquitetura/engenharia.
- Alternatives considered:
  - Texto continuo sem seções: rejeitado por prejudicar leitura e navegação.
  - Conteúdo somente em bullets: rejeitado por reduzir profundidade explicativa.

## Decision 4: Referências Linux e estilo visual
- Decision: Incluir referências explícitas a comandos Linux (ex.: pwd, ls -la, grep, chmod, systemctl, journalctl) em blocos de destaque, preservando visual old-school consistente com o site.
- Rationale: Mantem autenticidade técnica e atende ao requisito de detalhamento com identidade visual do projeto.
- Alternatives considered:
  - Omitir comandos Linux: rejeitado por perder valor prático e identidade técnica.
  - Exagerar em terminal art em toda página: rejeitado por possivel impacto em legibilidade e acessibilidade.

## Decision 5: Consistencia bilingue
- Decision: Garantir equivalencia semantica entre PT-BR e EN para card, item de menu e conteúdo principal da subpágina.
- Rationale: Atende principio de governança do projeto e amplia alcance profissional.
- Alternatives considered:
  - Publicar inicialmente em um idioma: rejeitado por conflito com constituicao vigente.

## Decision 6: Contrato de navegação e conteúdo
- Decision: Definir um contrato documental de navegação para o card e para as subpáginas técnicas, incluindo obrigatoriedade de seções minimas por página.
- Rationale: Evita regressao de qualidade em futuras adições de itens e facilita validação no ciclo de implementacao.
- Alternatives considered:
  - Validacao informal sem contrato: rejeitado por aumentar risco de inconsistências entre páginas.
