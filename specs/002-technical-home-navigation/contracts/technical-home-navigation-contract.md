# Technical Home Navigation Contract

## Purpose

Define the common navigation control that returns visitors from any technical page to the portfolio home page.

## Applicability

The contract applies to all published pages in `technical/`. Initial required pages:

- `technical/windows-wsl-stack.html`
- `technical/enterprise-architecture.html`

## Navigation Contract

- Each page MUST expose exactly one home navigation link before its first primary content heading.
- The link MUST use `../index.html` as its destination.
- The link MUST include a recognizable home icon or symbol and visible text that identifies the home-page destination.
- The link MUST use an anchor element so standard keyboard focus and activation work without custom navigation code.
- The link MUST have a visible focus state.
- The link MUST remain in normal document flow and fit without overlap at mobile and desktop widths.

## Language Contract

- The visible link label and accessible name MUST have PT-BR and EN equivalents.
- The active page language MUST select the matching link label and accessible name.
- The two language versions MUST communicate the same destination; literal translation is not required.

## Extension Contract

- Every new published page under `technical/` MUST implement this contract before being added to the home technical menu.
- `index.html` remains the canonical common destination; the home page does not need a reciprocal instance of this control.

## Verification Contract

- Opening a technical page directly MUST expose the link before the primary heading.
- Activating the link with mouse, touch, or keyboard MUST load `index.html` in one action.
- Switching page language MUST update the visible and accessible link text without affecting its destination.