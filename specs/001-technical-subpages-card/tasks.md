---

description: "Task list for implementing technical subpages card and navigation"
---

# Tasks: Card de Subpáginas Técnicas

**Input**: Design documents from `/specs/001-technical-subpages-card/`

**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: Tests automatizados não foram explicitamente solicitados na especificacao; este plano usa validação manual guiada por quickstart.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Preparar estrutura base de arquivos e pontos de extensão para subpáginas técnicas.

- [X] T001 Criar diretório e arquivos base `technical/windows-wsl-stack.html` e `technical/enterprise-architecture.html`
- [X] T002 Revisar e documentar regra de rotas estaticas para subpáginas em `staticwebapp.config.json`
- [X] T003 [P] Inserir comentário de âncora técnica para integração do card na home em `index.html`

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Infraestrutura de navegação e exibição que bloqueia todas as histórias de usuário.

**⚠️ CRITICAL**: Nenhum trabalho de historia de usuário deve começar antes de concluir esta fase.

- [X] T004 Implementar estrutura base do card técnico (container, título e area da lista) em `index.html`
- [X] T005 [P] Implementar estrutura de dados dos itens técnicos (id, labels PT/EN, href, status, ordem) em `index.html`
- [X] T006 Implementar renderizacao dos itens do card com suporte a estado `unavailable` em `index.html`
- [X] T007 [P] Implementar navegação por teclado e foco visivel para itens do card em `index.html`
- [X] T008 Criar estrutura HTML base reutilizavel das subpáginas técnicas em `technical/windows-wsl-stack.html` e `technical/enterprise-architecture.html`
- [X] T009 Definir metadados bilingues iniciais (título/descrição/lang) nas duas subpáginas em `technical/windows-wsl-stack.html` e `technical/enterprise-architecture.html`

**Checkpoint**: Base de navegação e layout pronta; histórias de usuário podem ser executadas.

---

## Phase 3: User Story 1 - Acesso Rapido a Conteúdo Técnico (Priority: P1) 🎯 MVP

**Goal**: Exibir card técnico na home com lista navegavel e redirecionamento funcional.

**Independent Test**: Na home, localizar card técnico e abrir pelo menos uma subpágina com no máximo 2 cliques.

### Implementation for User Story 1

- [X] T010 [P] [US1] Adicionar textos de apresentação do card técnico em PT-BR e EN em `index.html`
- [X] T011 [P] [US1] Registrar primeiro item do menu técnico para `technical/windows-wsl-stack.html` em `index.html`
- [X] T012 [US1] Implementar redirecionamento de clique e teclado para o primeiro item em `index.html`
- [X] T013 [US1] Ajustar layout responsivo do card técnico para desktop e mobile em `index.html`
- [X] T014 [US1] Garantir comportamento correto quando houver apenas um item publicado na lista em `index.html`

**Checkpoint**: US1 funcional e demonstravel como MVP.

---

## Phase 4: User Story 2 - Conhecer Experiencias e Ferramentas (Priority: P2)

**Goal**: Entregar subpáginas com conteúdo técnico aprofundado e contexto prático.

**Independent Test**: Abrir duas subpáginas a partir do card e confirmar contexto técnico, experiências e ferramentas em cada uma.

### Implementation for User Story 2

- [X] T015 [P] [US2] Escrever conteúdo PT-BR da página de ambiente Windows + WSL (contexto dual boot, evolução para WSL, fluxo atual) em `technical/windows-wsl-stack.html`
- [X] T016 [P] [US2] Escrever conteúdo EN equivalente da página Windows + WSL em `technical/windows-wsl-stack.html`
- [X] T017 [US2] Incluir seções de referências de comandos Linux (`pwd`, `ls -la`, `grep`, `chmod`, `systemctl`, `journalctl`) com explicação de uso em `technical/windows-wsl-stack.html`
- [X] T018 [P] [US2] Criar conteúdo técnico inicial da página de arquitetura enterprise de referência em `technical/enterprise-architecture.html`
- [X] T019 [US2] Adicionar segundo item do menu técnico apontando para `technical/enterprise-architecture.html` em `index.html`
- [X] T020 [US2] Implementar mensagem de indisponibilidade para item sem página publicada em `index.html`

**Checkpoint**: US2 funcional com duas páginas técnicas acessíveis e conteúdo especializado.

---

## Phase 5: User Story 3 - Navegação Consistente em PT-BR e EN (Priority: P3)

**Goal**: Garantir paridade de significado e experiência entre idiomas no card e subpáginas.

**Independent Test**: Alternar idioma e validar card, itens e conteúdo técnico sem texto ausente ou inconsistente.

### Implementation for User Story 3

- [X] T021 [P] [US3] Aplicar labels PT-BR e EN em todos os textos visiveis do card e lista em `index.html`
- [X] T022 [P] [US3] Aplicar headings e descrições bilingues equivalentes nas seções da página WSL em `technical/windows-wsl-stack.html`
- [X] T023 [US3] Sincronizar mecanismo de alternancia de idioma entre home e subpáginas em `index.html`, `technical/windows-wsl-stack.html` e `technical/enterprise-architecture.html`
- [X] T024 [US3] Ajustar atributos de acessibilidade por idioma (`lang`, `aria-label`, textos de navegação) em `index.html` e `technical/windows-wsl-stack.html`

**Checkpoint**: US3 concluida com consistência bilingue e acessibilidade básica.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Consolidar qualidade final e validação de entrega.

- [X] T025 [P] Atualizar documentação de navegação técnica e páginas criadas em `README.md`
- [X] T026 [P] Revisar comportamento de deep-link e fallback de rotas técnicas em `staticwebapp.config.json`
- [X] T027 Executar cenarios de validação do quickstart e registrar ajustes necessários em `specs/001-technical-subpages-card/quickstart.md`
- [X] T028 Realizar refinamentos finais de responsividade e legibilidade old-school em `index.html`, `technical/windows-wsl-stack.html` e `technical/enterprise-architecture.html`

---

## Dependencies & Execution Order

### Phase Dependencies

- **Phase 1 (Setup)**: sem dependencias.
- **Phase 2 (Foundational)**: depende da conclusão da Phase 1 e bloqueia todas as histórias.
- **Phase 3 (US1)**: depende da conclusão da Phase 2.
- **Phase 4 (US2)**: depende da conclusão da Phase 2; pode iniciar após US1 se houver acoplamento de UI pendente.
- **Phase 5 (US3)**: depende da conclusão funcional de US1 e US2 para validar paridade completa.
- **Phase 6 (Polish)**: depende das histórias priorizadas concluídas.

### User Story Dependencies

- **US1 (P1)**: independente após fase foundational; define o MVP.
- **US2 (P2)**: usa a navegação criada em US1 e adiciona profundidade de conteúdo.
- **US3 (P3)**: consolida consistência entre idiomas sobre card e conteúdos das histórias anteriores.

### Parallel Opportunities

- Setup: T003 pode rodar em paralelo com T001-T002.
- Foundational: T005 e T007 podem executar em paralelo com T004/T006 quando não houver conflito de bloco.
- US1: T010 e T011 podem rodar em paralelo antes de T012.
- US2: T015, T016 e T018 podem rodar em paralelo (arquivos diferentes).
- US3: T021 e T022 podem rodar em paralelo (home vs subpágina).
- Polish: T025 e T026 podem rodar em paralelo.

---

## Parallel Example: User Story 2

```bash
# Conteúdo paralelo em arquivos diferentes
Task: "T015 [US2] Conteúdo PT-BR em technical/windows-wsl-stack.html"
Task: "T016 [US2] Conteúdo EN em technical/windows-wsl-stack.html"
Task: "T018 [US2] Conteúdo inicial em technical/enterprise-architecture.html"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Concluir Phase 1 e Phase 2.
2. Implementar apenas Phase 3 (US1).
3. Validar navegação home -> primeira subpágina.
4. Publicar incremento MVP.

### Incremental Delivery

1. Entregar US1 (navegação essencial).
2. Adicionar US2 (conteúdo técnico aprofundado).
3. Finalizar com US3 (consistência bilingue e acessibilidade).
4. Encerrar com polish e validação final.

### Suggested MVP Scope

- **MVP recomendado**: Phase 1 + Phase 2 + Phase 3 (US1).
- Entrega minima de valor: card técnico funcional com redirecionamento para a página `technical/windows-wsl-stack.html`.

---

## Notes

- Todos os itens seguem formato de checklist executavel com ID sequencial, marcadores [P]/[US#] quando aplicavel e caminho de arquivo explicito.
- Validacao funcional detalhada esta centralizada em `specs/001-technical-subpages-card/quickstart.md`.
