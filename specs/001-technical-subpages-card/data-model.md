# Data Model: Card de Subpáginas Técnicas

## Entity: TechnicalCard
- Description: Componente da home que destaca a entrada para conteúdos técnicos.
- Fields:
  - id (string, required): identificador estavel do card
  - title_pt (string, required): título em português
  - title_en (string, required): título em inglês
  - summary_pt (string, optional): resumo curto em português
  - summary_en (string, optional): resumo curto em inglês
  - is_visible (boolean, required): controla exibição do card
- Validation Rules:
  - title_pt e title_en não podem ser vazios
  - id deve ser unico no contexto da página

## Entity: TechnicalSubpageItem
- Description: Item navegavel dentro do card, apontando para uma subpágina técnica.
- Fields:
  - id (string, required): identificador estavel do item
  - card_id (string, required): referência ao TechnicalCard
  - title_pt (string, required): título em português
  - title_en (string, required): título em inglês
  - href (string, required): destino da subpágina
  - order (integer, required): ordem de exibição
  - publication_status (enum, required): draft | published | unavailable
  - topic_type (enum, required): experience | tooling | architecture | documentation
- Validation Rules:
  - href deve apontar para rota técnica valida do site
  - order deve ser inteiro positivo sem duplicidade dentro do mesmo card
  - publication_status = published exige href funcional
  - title_pt e title_en obrigatorios para consistência bilingue

## Entity: TechnicalSubpage
- Description: Página de detalhe com informações técnicas adicionais.
- Fields:
  - slug (string, required): identificador da rota
  - title_pt (string, required): título da página em português
  - title_en (string, required): título da página em inglês
  - intro_pt (string, required): introducao em português
  - intro_en (string, required): introducao em inglês
  - sections (list, required): lista de seções técnicas da página
  - last_updated (date, required): data de atualização
  - status (enum, required): draft | published
- Validation Rules:
  - slug deve ser unico por subpágina
  - sections deve conter ao menos 3 seções
  - para a página de Windows + WSL, seções obrigatorias:
    - contexto histórico (dual boot Linux/Windows)
    - fluxo atual com WSL
    - comandos Linux de referência e quando usar

## Entity: TechnicalSection
- Description: Bloco interno de conteúdo dentro de uma subpágina técnica.
- Fields:
  - id (string, required)
  - subpage_slug (string, required)
  - heading_pt (string, required)
  - heading_en (string, required)
  - body_pt (string, required)
  - body_en (string, required)
  - emphasis_type (enum, optional): note | command | warning | timeline
- Validation Rules:
  - body_pt e body_en não podem ser vazios
  - emphasis_type = command exige pelo menos um comando Linux citado

## Relationships
- TechnicalCard 1 -> N TechnicalSubpageItem
- TechnicalSubpageItem N -> 1 TechnicalSubpage
- TechnicalSubpage 1 -> N TechnicalSection

## State Transitions
- TechnicalSubpage.status:
  - draft -> published (quando conteúdo bilingue e validações de navegação forem atendidas)
  - published -> draft (se houver necessidade de revisao semantica)
- TechnicalSubpageItem.publication_status:
  - draft -> published (subpágina pronta)
  - published -> unavailable (destino temporariamente indisponivel)
  - unavailable -> published (destino restabelecido)
