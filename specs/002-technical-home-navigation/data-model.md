# Data Model: Navegacao Inicial nas Paginas Tecnicas

## Overview

This feature has no persisted or server-side data. The model describes the UI state owned by each static technical page.

## Home Navigation Control

| Field | Description | Validation rule |
|-------|-------------|-----------------|
| `destination` | Common return destination. | Must resolve from every `technical/` page to `../index.html`. |
| `icon` | Visual home indicator. | Must not be the only way the destination is communicated. |
| `visibleLabel.pt` | Portuguese Brazilian text shown with the icon. | Must clearly state that the link returns to the home page. |
| `visibleLabel.en` | English text shown with the icon. | Must convey the same destination as the Portuguese label. |
| `accessibleName.pt` | Portuguese Brazilian accessible name. | Must identify the home-page destination. |
| `accessibleName.en` | English accessible name. | Must identify the home-page destination. |
| `focusStyle` | Visible focus treatment. | Must remain visible against the navigation background. |

## Relationships

- Each published technical page owns exactly one Home Navigation Control.
- The control is rendered before the page's primary technical content.
- The selected page language selects the corresponding visible label and accessible name.
- `index.html` is the single destination for every instance of the control.

## State Transitions

| Current state | Event | Result |
|---------------|-------|--------|
| Page loaded in PT-BR | Visitor switches to EN | The control updates to the English label and accessible name. |
| Page loaded in EN | Visitor switches to PT-BR | The control updates to the Portuguese label and accessible name. |
| Control focused | Visitor presses Enter or activates by pointer | Browser navigates to `index.html`. |