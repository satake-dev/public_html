# Technical Navigation Contract

## Purpose
Definir o contrato funcional e de conteúdo para o card técnico da home e para as subpáginas técnicas vinculadas.

## Navigation Surface

### Home Card Contract
- The home page MUST expose one technical card section.
- The card MUST list at least one subpage item.
- Each subpage item MUST provide:
  - Display label in PT-BR and EN
  - Navigable destination path
  - Publication status handling (published or unavailable)

### Required Initial Menu Item
- Item key: windows-wsl-stack
- PT-BR label: Ambiente de Desenvolvimento Windows + WSL
- EN label: Windows + WSL Development Environment
- Destination path: /technical/windows-wsl-stack

## Subpage Content Contract

### Required sections for /technical/windows-wsl-stack
1. Contexto histórico
- Narrativa de uso anterior com Linux em dual boot com Windows.

2. Evolução para WSL
- Explicacao de porque o WSL se tornou uma opcao madura para manter desenvolvimento Linux com interface principal no Windows.

3. Fluxo atual de trabalho
- Como o ambiente e organizado no dia a dia (editor, terminal, arquivos, execução local, depuracao).

4. Referências Linux práticas
- Citar comandos de uso recorrente e contexto de aplicação.
- Exemplos esperados: pwd, ls -la, grep, chmod, systemctl, journalctl.

5. Boas práticas e limites
- Quando usar Windows nativo, quando usar WSL e como evitar inconsistências de ambiente.

### Language Contract
- Every visible section title and description MUST have PT-BR and EN equivalents.
- Meaning parity is mandatory; literal translation is not required.

## Accessibility and Responsiveness Contract
- Links in the card MUST be keyboard reachable.
- Labels MUST remain legible on mobile and desktop.
- Command references MUST preserve readability without horizontal overflow breaking the layout.

## Error/Unavailable Contract
- If a destination subpage is unavailable, the item MUST present a clear unavailable state message.
- Unavailable state MUST NOT remove the card itself from the home page.
