# Research: Navegacao Inicial nas Paginas Tecnicas

## Decision 1: Use a semantic home link with a local home symbol

**Decision**: Add a standard anchor link at the start of the main content area of each technical page. The link uses a home symbol as the visual icon, a visible localized label, and an accessible localized name.

**Rationale**: An anchor is the correct native control for navigation, is keyboard reachable without custom handling, and can use the existing inline styles. A character-based home symbol retains the old-school visual language without adding a package, asset request, or framework.

**Alternatives considered**:

- External icon library: rejected because it adds a dependency for one control.
- Image or SVG asset: rejected because an asset request is unnecessary and can fail independently of the page.
- Button with scripted navigation: rejected because it is less semantic than a link and adds unnecessary behavior.

## Decision 2: Make index.html the shared return destination

**Decision**: Every technical page links to `../index.html` from within the `technical/` directory.

**Rationale**: The destination is explicit, works when a technical page is opened directly, and matches the existing static page structure and user request.

**Alternatives considered**:

- Browser history navigation: rejected because a direct visit may not have a prior portfolio page in history.
- Linking to a technical catalog route: rejected because the requested common destination is the existing home page.

## Decision 3: Reuse the existing language state

**Decision**: Update the link's visible label and accessible name through each page's existing PT-BR/EN language-copy mechanism, including the persisted `site-lang` preference.

**Rationale**: This preserves language parity and avoids a second source of language state.

**Alternatives considered**:

- A fixed single-language label: rejected because it violates the bilingual content requirement.
- Separate language handling for the home link: rejected because it can drift from the current page language.

## Decision 4: Keep responsive behavior in normal document flow

**Decision**: Place the control before the first primary heading in the existing content container, using a compact inline or flex layout with a visible focus state.

**Rationale**: Normal flow retains a predictable tab order and avoids overlap at narrow widths without introducing fixed positioning.

**Alternatives considered**:

- Fixed corner control: rejected because it can overlap page content on small screens.
- Combining the link with the language switch: rejected because the controls serve separate navigation purposes and would obscure hierarchy.