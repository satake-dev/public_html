# Implementation Plan: Navegacao Inicial nas Paginas Tecnicas

**Branch**: `feature/002-technical-home-navigation` | **Date**: 2026-08-16 | **Spec**: [spec.md](./spec.md)

**Input**: Feature specification from `specs/002-technical-home-navigation/spec.md`

## Summary

Adicionar, antes do conteudo principal de cada pagina tecnica, um link semantico
com icone de home e rotulo bilingue que direciona para `index.html`. A solucao
reutiliza o HTML, CSS e JavaScript locais de cada pagina tecnica, preserva a
preferencia de idioma existente e nao introduz dependencias nem alteracoes de
rotas.

## Technical Context

**Language/Version**: HTML5, CSS and vanilla JavaScript compatible with modern browsers

**Primary Dependencies**: None

**Storage**: Browser `localStorage` key `site-lang`, already used to retain language selection

**Testing**: Manual browser validation plus static HTML, CSS and JavaScript checks

**Target Platform**: Azure Static Web Apps; modern desktop and mobile browsers

**Project Type**: Static website

**Performance Goals**: The navigation control is available with the initial page content and adds no network request.

**Constraints**: Preserve the old-school visual identity; use `index.html` as the common destination; provide PT-BR and EN labels; maintain keyboard access and legibility at mobile and desktop widths; do not add packages or external icon assets.

**Scale/Scope**: Two current technical pages, `technical/windows-wsl-stack.html` and `technical/enterprise-architecture.html`, plus a repeatable markup and style pattern for future technical pages.

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-checked after Phase 1 design.*

| Principle | Plan response | Status |
|-----------|---------------|--------|
| Professional clarity | The control gives visitors a direct, predictable route back to the portfolio. | PASS |
| Old-school identity | The home symbol and local styling follow the existing 90s/2000 window aesthetic. | PASS |
| Architectural simplicity | The change only uses existing static HTML, CSS and vanilla JavaScript; no dependency, service or build step is added. | PASS |
| Responsive and accessible experience | The link is semantic, keyboard reachable, visibly focused, bilingual and checked at small and large widths. | PASS |
| Bilingual consistency | Visible and accessible labels are supplied in PT-BR and EN through the existing language behavior. | PASS |
| Privacy and external dependencies | No personal data, external request or icon asset is added. | PASS |
| Incremental evolution | Only the two published technical pages are changed; the pattern documents future adoption. | PASS |

**Post-design re-check**: PASS. The design artifacts keep the same static, dependency-free, bilingual and accessible approach.

## Project Structure

### Documentation (this feature)

```text
specs/002-technical-home-navigation/
├── plan.md              # This file (/speckit-plan command output)
├── research.md          # Phase 0 output (/speckit-plan command)
├── data-model.md        # Phase 1 output (/speckit-plan command)
├── quickstart.md        # Phase 1 output (/speckit-plan command)
├── contracts/           # Phase 1 output (/speckit-plan command)
└── tasks.md             # Phase 2 output (/speckit-tasks command - NOT created by /speckit-plan)
```

### Source Code (repository root)

```text
index.html                                      # Canonical home page and return destination
technical/
├── enterprise-architecture.html                # Add shared home navigation pattern
└── windows-wsl-stack.html                       # Add shared home navigation pattern
staticwebapp.config.json                         # Existing technical route mappings; no change expected
```

**Structure Decision**: Keep the existing single-file static page structure. Each technical page owns its markup, style and language copy, so the home navigation pattern is applied directly to both published pages. `index.html` remains the shared navigation destination and requires no functional change for this feature.
