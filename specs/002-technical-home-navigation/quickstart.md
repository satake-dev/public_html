# Quickstart: Navegacao Inicial nas Paginas Tecnicas

## Goal

Validate that every published technical page exposes an accessible, bilingual home-icon link before its primary content and that the link reaches `index.html` in one activation.

## Prerequisites

- Repository checked out locally
- Modern browser with desktop and responsive mobile views
- Python 3 for a simple local static server

## Run Locally

1. From the repository root, start a static server:

```bash
python3 -m http.server 8080
```

2. Open these direct technical-page URLs:

- `http://localhost:8080/technical/windows-wsl-stack.html`
- `http://localhost:8080/technical/enterprise-architecture.html`

## Validation Scenarios

### Scenario 1: Placement and destination

1. Open each technical page directly.
2. Confirm that the home-icon link appears before the first primary content heading.
3. Activate it by pointer or touch.

**Expected**: The browser opens `http://localhost:8080/index.html` in one action.

### Scenario 2: Keyboard access

1. Reload each technical page.
2. Press Tab until the home link is focused.
3. Confirm the focus treatment is visible.
4. Press Enter.

**Expected**: The home link is reachable, visibly focused, and opens the home page.

### Scenario 3: Bilingual parity

1. Open each technical page in PT-BR and note the home-link text and accessible name.
2. Switch to EN using the existing language control.
3. Verify the visible and accessible home-link text changes to the equivalent English meaning.
4. Activate the link in both languages.

**Expected**: Both language versions clearly identify the home destination and resolve to the same `index.html` page.

### Scenario 4: Responsive layout

1. Test each technical page at 320 px and at a desktop width of at least 1280 px.
2. Check the home control, language switch, title, and first paragraph.

**Expected**: The home link stays visible and usable, no elements overlap, and the focus outline remains visible.

## References

- Specification: [spec.md](./spec.md)
- Plan: [plan.md](./plan.md)
- UI model: [data-model.md](./data-model.md)
- Navigation contract: [technical-home-navigation-contract.md](./contracts/technical-home-navigation-contract.md)