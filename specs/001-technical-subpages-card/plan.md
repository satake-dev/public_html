# Implementation Plan: Card de Subpáginas Técnicas

**Branch**: `001-technical-subpages-card` | **Date**: 2026-08-16 | **Spec**: `/specs/001-technical-subpages-card/spec.md`

**Input**: Feature specification from `/specs/001-technical-subpages-card/spec.md`

## Summary

Adicionar na página inicial um card técnico com lista de subpáginas que direciona para conteúdos aprofundados sobre experiências e ferramentas. O primeiro item do menu sera uma subpágina dedicada ao ambiente de desenvolvimento com Windows + WSL, explicando a evolução de um período longo com Linux em dual boot para um fluxo moderno com desenvolvimento Linux e interface principal no Windows, mantendo identidade old-school e incluindo referências visuais e textuais a comandos Linux.

## Technical Context

**Language/Version**: HTML5, CSS3 e JavaScript (ES compativel com navegadores modernos)

**Primary Dependencies**: Sem novas dependencias de framework; ativos estaticos do proprio projeto

**Storage**: Arquivos estaticos no repositório

**Testing**: Validacao manual funcional e visual em desktop e mobile; verificacao de links, navegação e consistência bilingue

**Target Platform**: Navegadores modernos em desktop e mobile, com publicação via Azure Static Web Apps

**Project Type**: Website estatico pessoal/profissional

**Performance Goals**: Conteúdo principal da home perceptível em até 2 segundos em conexão comum; navegação entre home e subpáginas sem atrasos perceptíveis ao usuário

**Constraints**: Preservar identidade visual old-school, manter simplicidade arquitetural (sem backend), garantir acessibilidade básica e responsividade

**Scale/Scope**: 1 card técnico na home, 1 item inicial detalhado (Windows + WSL), estrutura preparada para expansão incremental de novas subpáginas técnicas

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

- Princípio I (clareza profissional): PASS. O card organiza narrativas técnicas com foco em experiência real e contexto.
- Princípio II (old-school com atuação moderna): PASS. A proposta combina estilo nostálgico com conteúdo técnico atual (WSL, fluxo moderno).
- Princípio III (simplicidade arquitetural): PASS. Solucao permanece estatica com HTML/CSS/JS vanilla.
- Princípio IV (responsividade e acessibilidade): PASS. Planejamento inclui navegação legível e clicável em desktop/mobile.
- Princípio V (consistência bilingue): PASS. Escopo contempla card, menu e subpágina em PT-BR e EN.
- Princípio VI (privacidade/dependencias): PASS. Sem coleta de dados nem nova dependencia externa obrigatoria.
- Princípio VII (evolução incremental): PASS. Entrega inicial pequena, reversível e expansível por novos itens.

Recheck pos-design: PASS mantido após definicao de artefatos de dados, contratos e quickstart.

## Project Structure

### Documentation (this feature)

```text
specs/001-technical-subpages-card/
├── plan.md
├── research.md
├── data-model.md
├── quickstart.md
├── contracts/
│   └── technical-navigation-contract.md
└── tasks.md
```

### Source Code (repository root)

```text
index.html
README.md
staticwebapp.config.json

# Planned additions for this feature
technical/
├── windows-wsl-stack.html
└── enterprise-architecture.html

assets/
└── (optional static images/icons used by technical pages)
```

**Structure Decision**: Estrutura de site estatico com páginas técnicas em um diretório dedicado, mantendo a home como hub de navegação e preservando publicação simples no mesmo fluxo atual.

## Complexity Tracking

Sem violacoes de constituicao que exijam justificativa adicional.
