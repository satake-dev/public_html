---

description: "Task list for technical-page home navigation implementation"
---

# Tasks: Navegacao Inicial nas Paginas Tecnicas

**Input**: Design documents from `specs/002-technical-home-navigation/`

**Prerequisites**: [plan.md](./plan.md), [spec.md](./spec.md), [research.md](./research.md), [data-model.md](./data-model.md), and [technical-home-navigation-contract.md](./contracts/technical-home-navigation-contract.md)

**Tests**: Automated tests were not requested. Validation is performed manually using [quickstart.md](./quickstart.md) and static checks.

**Organization**: Tasks are grouped by user story so the P1 return path can be delivered and validated before bilingual refinements.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel because the task changes a different file.
- **[Story]**: User story mapped to the task.
- Every task includes its exact target file path.

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Confirm existing page-local conventions that the shared pattern will reuse.

- [X] T001 Review the existing language-state and direct-home-link conventions in `technical/windows-wsl-stack.html`, `technical/enterprise-architecture.html`, and `specs/002-technical-home-navigation/contracts/technical-home-navigation-contract.md` before editing.

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Establish the common visual foundation required by both user stories.

**CRITICAL**: Complete this phase before applying the home navigation markup or localized copy.

- [X] T002 [P] Add the home-navigation layout, contrast-preserving link treatment, visited state, and visible keyboard-focus styling in `technical/windows-wsl-stack.html`.
- [X] T003 [P] Add the same home-navigation layout, contrast-preserving link treatment, visited state, and visible keyboard-focus styling in `technical/enterprise-architecture.html`.

**Checkpoint**: Both technical pages have a responsive, dependency-free style foundation for the home navigation control.

---

## Phase 3: User Story 1 - Retornar a Pagina Inicial (Priority: P1) MVP

**Goal**: Give visitors a single, top-of-page home link that reaches `index.html` without relying on browser history.

**Independent Test**: Open each technical page directly, find the home control before the primary heading, activate it with pointer and keyboard, and verify that `index.html` opens in one action.

### Implementation for User Story 1

- [X] T004 [P] [US1] Add one semantic home-icon anchor before the primary heading, point it to `../index.html`, and remove the duplicate footer return link in `technical/windows-wsl-stack.html`.
- [X] T005 [P] [US1] Add one semantic home-icon anchor before the primary heading, point it to `../index.html`, and remove the duplicate footer return link in `technical/enterprise-architecture.html`.
- [X] T006 [US1] Validate direct access, one-activation navigation, single-link presence, and keyboard activation for both pages using scenarios 1 and 2 in `specs/002-technical-home-navigation/quickstart.md`.

**Checkpoint**: The MVP return journey works independently on every published technical page.

---

## Phase 4: User Story 2 - Compreender o Destino do Retorno (Priority: P2)

**Goal**: Make the home control clear and equivalent in PT-BR and EN, including its accessible name.

**Independent Test**: On each technical page, switch between PT-BR and EN and confirm that the home control's visible label and accessible name change together while its destination remains `../index.html`.

### Implementation for User Story 2

- [X] T007 [P] [US2] Add PT-BR and EN home-label and accessible-name values to the existing language copy and update the language application flow in `technical/windows-wsl-stack.html`.
- [X] T008 [P] [US2] Add PT-BR and EN home-label and accessible-name values to the existing language copy and update the language application flow in `technical/enterprise-architecture.html`.
- [X] T009 [US2] Validate bilingual visible labels, accessible names, persisted language selection, and unchanged home destination using scenario 3 in `specs/002-technical-home-navigation/quickstart.md`.

**Checkpoint**: Both languages clearly communicate the same home-page destination on every published technical page.

---

## Phase 5: Polish and Cross-Cutting Concerns

**Purpose**: Verify the shared contract across pages and screen sizes before release.

- [X] T010 Verify that each published page satisfies the single-control, placement, destination, and focus requirements in `technical/windows-wsl-stack.html`, `technical/enterprise-architecture.html`, and `specs/002-technical-home-navigation/contracts/technical-home-navigation-contract.md`.
- [X] T011 Run the 320 px and desktop responsive checks from scenario 4 in `specs/002-technical-home-navigation/quickstart.md` against `technical/windows-wsl-stack.html` and `technical/enterprise-architecture.html`.

---

## Dependencies and Execution Order

### Phase Dependencies

- **Phase 1**: Has no dependencies.
- **Phase 2**: Depends on T001 and blocks both user stories.
- **User Story 1 (Phase 3)**: Depends on T002 and T003.
- **User Story 2 (Phase 4)**: Depends on T004 and T005 because it localizes the home controls introduced by the MVP.
- **Polish (Phase 5)**: Depends on T006 and T009.

### User Story Dependencies

- **US1 (P1)**: Delivers the independently usable return path and is the MVP.
- **US2 (P2)**: Extends US1 with bilingual visible and accessible text; it does not change the destination or navigation behavior.

### Parallel Opportunities

- T002 and T003 can run in parallel because they change separate technical pages.
- T004 and T005 can run in parallel after the corresponding foundational tasks complete.
- T007 and T008 can run in parallel after the corresponding US1 tasks complete.

## Parallel Examples

### Foundational styling

```text
Task: "Add home-navigation styling in technical/windows-wsl-stack.html"
Task: "Add home-navigation styling in technical/enterprise-architecture.html"
```

### User Story 1 markup

```text
Task: "Add the semantic home control in technical/windows-wsl-stack.html"
Task: "Add the semantic home control in technical/enterprise-architecture.html"
```

### User Story 2 localization

```text
Task: "Localize home-control copy in technical/windows-wsl-stack.html"
Task: "Localize home-control copy in technical/enterprise-architecture.html"
```

## Implementation Strategy

### MVP First

1. Complete T001 through T005.
2. Run T006 to validate the direct, keyboard-accessible return journey.
3. The MVP is ready once every published technical page returns to `index.html` in one activation.

### Incremental Delivery

1. Add the localized labels and accessible names with T007 and T008.
2. Validate language behavior with T009.
3. Complete responsive and contract verification with T010 and T011.