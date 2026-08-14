<!--
Sync Impact Report
- Version change: 1.0.0 -> 1.1.0
- Modified principles: all principles translated and aligned with the latest project definition
- Added principles: II. Identidade old-school com atuação moderna; VII. Evolução incremental
- Added sections: Restrições técnicas; Processo de qualidade
- Removed sections: none
- Follow-up TODOs: none
-->

# public_html Constitution

## Princípios fundamentais

### Princípio I — Clareza de posicionamento profissional

Todo conteúdo deve reforçar uma imagem profissional coerente com Principal
Software Architect, liderança técnica, arquitetura de software, IoT e cloud
platforms. O conteúdo deve priorizar impacto, contexto e resultados, evitando
uma simples lista de tecnologias.

### Princípio II — Identidade old-school com atuação moderna

O site deve preservar uma identidade visual inspirada nos anos 90 e 2000,
remetendo à cultura dos primeiros sites pessoais, ao estilo Windows 95 e à
estética old-school da web. Essa escolha visual é parte essencial da identidade
do projeto e deve ser mantida de forma consistente.

Ao mesmo tempo, o conteúdo deve demonstrar atuação profissional em arquiteturas
modernas, incluindo cloud-native, sistemas distribuídos, escalabilidade,
observabilidade, IoT, plataformas digitais e liderança técnica. A estética
nostálgica representa a história e a personalidade do site, não uma limitação
tecnológica.

### Princípio III — Simplicidade arquitetural

O projeto deve permanecer um site estático simples, utilizando HTML, CSS e
JavaScript vanilla sempre que possível. Novas dependências, frameworks ou
camadas de abstração só podem ser adicionados quando resolverem uma necessidade
concreta e documentada.

### Princípio IV — Experiência responsiva e acessível

Toda alteração visual deve funcionar em desktop e dispositivos móveis. O
conteúdo deve possuir hierarquia clara, contraste adequado, textos alternativos
para imagens, navegação compreensível e suporte razoável a teclado.

### Princípio V — Consistência bilíngue

Alterações de conteúdo visível devem ser implementadas em português brasileiro
e inglês. A troca de idioma não pode produzir textos ausentes, traduções
inconsistentes ou elementos visualmente quebrados.

### Princípio VI — Privacidade e dependências externas

O site não deve coletar dados pessoais sem necessidade explícita. Links,
imagens, favicons, contadores e outros recursos externos devem ser avaliados
quanto à disponibilidade, privacidade e impacto no carregamento da página.

### Princípio VII — Evolução incremental

Cada alteração deve ser pequena, reversível e alinhada ao objetivo do site. Não
devem ser criadas funcionalidades especulativas, sistemas de backend ou
complexidade de produto sem uma necessidade real.

## Restrições técnicas

- O site deve continuar publicável como Azure Static Web App.
- HTML, CSS e JavaScript devem permanecer compatíveis com navegadores modernos.
- O arquivo estático deve continuar sendo a principal unidade da aplicação,
	salvo justificativa explícita para uma nova estrutura.
- A estética visual dos anos 90/2000 deve ser preservada, exceto quando uma
	mudança de identidade for intencionalmente especificada.
- A estética old-school não deve impedir melhorias de acessibilidade,
	responsividade, desempenho ou clareza profissional.
- Recursos externos devem possuir fallback ou degradação aceitável quando
	possível.

## Processo de qualidade

- Mudanças relevantes devem começar com `/speckit.specify`.
- Ambiguidades devem ser resolvidas com `/speckit.clarify`.
- Decisões técnicas devem ser registradas com `/speckit.plan`.
- Antes da implementação, requisitos e tarefas devem ser revisados.
- Toda alteração deve ser validada no navegador em desktop e mobile.
- Alterações de i18n devem ser verificadas nos dois idiomas.
- Links externos, imagens e badges modificados devem ser testados.
- O HTML, CSS e JavaScript devem ser verificados antes da publicação.

## Governança

A constitution é a referência para decisões recorrentes do projeto. Mudanças
nas regras exigem justificativa registrada, revisão do proprietário do projeto
e atualização da versão. Alterações de conteúdo, layout ou funcionalidade não
devem modificar a constitution, a menos que introduzam uma nova regra
permanente.

Alterações nesta constitution devem preservar o Sync Impact Report no início do
documento. A versão segue intenção semântica: MAJOR para mudanças incompatíveis
de governança, MINOR para novos princípios ou ampliações relevantes e PATCH
para correções que não alterem as regras.

**Versão**: 1.1.0 | **Data de ratificação**: 2026-08-14 | **Última alteração**: 2026-08-14
