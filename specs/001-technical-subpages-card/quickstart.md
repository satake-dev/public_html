# Quickstart: Card de Subpáginas Técnicas

## Goal
Validar ponta a ponta o card técnico na home e a subpágina inicial sobre ambiente Windows + WSL.

## Prerequisites
- Repositório clonado localmente
- Navegador moderno em desktop e mobile (ou modo responsivo)
- Ambiente com servidor HTTP local simples

## Run Locally

1. Na raiz do projeto, subir servidor estatico local:

```bash
python3 -m http.server 8080
```

2. Abrir no navegador:
- http://localhost:8080/

## Validation Scenarios

### Scenario 1: Card técnico visivel na home
- Acessar home.
- Confirmar presença do card de subpáginas técnicas.
- Confirmar que a lista de itens esta visivel e legível.

Expected:
- Card presente e destacando navegação para conteúdo técnico.

### Scenario 2: Redirecionamento do primeiro item (Windows + WSL)
- Clicar no primeiro item do menu técnico.
- Verificar navegação para /technical/windows-wsl-stack.

Expected:
- Destino abre corretamente sem erro de rota.

### Scenario 3: Conteúdo técnico exigido na subpágina
- Validar seções obrigatorias:
  - contexto histórico de dual boot Linux/Windows
  - evolução para WSL
  - fluxo atual de trabalho
  - referências de comandos Linux
  - boas práticas e limites

Expected:
- Todas as seções existem e estao coerentes com o tema.

### Scenario 4: Referências Linux no estilo da página
- Confirmar presença de referências como pwd, ls -la, grep, chmod, systemctl, journalctl.
- Validar legibilidade dessas referências no layout old-school.

Expected:
- Comandos apresentados com boa leitura e sem quebrar o layout.

### Scenario 5: Consistencia bilingue
- Alternar idioma do site para PT-BR e EN.
- Validar card, item inicial e seções da subpágina.

Expected:
- Paridade semantica entre idiomas, sem campos faltantes.

### Scenario 6: Responsividade
- Verificar home e subpágina em largura mobile e desktop.

Expected:
- Itens clicáveis, textos legíveis e navegação funcional nas duas larguras.

## References
- Spec: specs/001-technical-subpages-card/spec.md
- Plan: specs/001-technical-subpages-card/plan.md
- Research: specs/001-technical-subpages-card/research.md
- Data model: specs/001-technical-subpages-card/data-model.md
- Contract: specs/001-technical-subpages-card/contracts/technical-navigation-contract.md

## Validation Log (2026-08-16)

- Static checks executed:
  - Technical pages exist at `technical/windows-wsl-stack.html` and `technical/enterprise-architecture.html`
  - Navigation routes mapped in `staticwebapp.config.json` for clean URLs under `/technical/*`
  - Home card now includes published and unavailable states with keyboard-accessible controls
  - Language preference sync uses `localStorage` key `site-lang` between home and technical pages

- Adjustments applied after validation:
  - Switched menu targets to clean routes (`/technical/windows-wsl-stack` and `/technical/enterprise-architecture`)
  - Added unavailable-state feedback message in the technical menu
  - Added route aliases from `/~thiago/technical/*` to clean `/technical/*` endpoints

- Pending manual browser verification before release:
  - Confirm all scenarios in desktop and mobile viewport
  - Confirm bilingual parity by toggling PT/EN on home and subpages
