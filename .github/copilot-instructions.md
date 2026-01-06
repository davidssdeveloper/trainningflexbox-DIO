<!-- .github/copilot-instructions.md - instruções rápidas para agentes de IA -->

# Objetivo

Este repositório é um site estático (single-page) focado em um clone visual do site do Discord. As instruções abaixo ajudam agentes de IA a serem produtivos rapidamente aqui: onde editar, como pré-visualizar mudanças e quais convenções seguir.

## Visão geral do projeto
- Páginas: `index.html` (arquivo único).  
- Estilos: CSS está dividido em `assets/css/mobile.css` (mobile-first) e `assets/css/medium-and-large-window.css` (destinado a estilos para janelas médias/grandes — atualmente vazio).  
- Imagens: `assets/images/images-mobile/` contém os assets usados em `mobile.css` (ex.: `Header Background.svg`).  
- Fontes: carregadas via Google Fonts em `index.html` (`Luckiest Guy`, `Bangers`).

## Como trabalhar localmente (preview rápido)
- Visualização direta: abra `index.html` no navegador para mudanças rápidas.  
- Servidor estático (recomendado para rotas e CORS previsíveis): no terminal do projeto execute `python -m http.server 8000` e acesse `http://localhost:8000`. (Ou use a extensão Live Server do VS Code.)

## Convenções e padrões do projeto
- Mobile-first: aplique nova estilização em `assets/css/mobile.css`; coloque modificações para telas maiores em `assets/css/medium-and-large-window.css` usando media queries.  
- Unidade e layout: tipografia usa `rem` (ex.: `font-size: 3.5rem`), layout por `flexbox` e `gap`. Siga esse estilo quando adicionar novos componentes.  
- Assets e paths: imagens referenciadas por caminhos relativos no CSS (ex.: `background-image: url('../images/images-mobile/Header\ Background.svg')`). Recomenda-se usar nomes sem espaços (p.ex. `header-background.svg`) e atualizar o CSS ao renomear.  
- Semântica/idioma: `index.html` define `lang="en"` mas o conteúdo está em português; prefira `pt-BR` se for editar textos.

## Exemplos práticos (tarefas comuns)
- Adicionar estilos para desktop: editar/insertar media queries em `assets/css/medium-and-large-window.css` ou adicionar regras condicionais dentro de `mobile.css` (mobile-first).  
- Renomear imagem com espaços:
  - `git mv "assets/images/images-mobile/Header Background.svg" assets/images/images-mobile/header-background.svg`
  - Atualizar CSS: `background-image: url('../images/images-mobile/header-background.svg');`
- Inserir conteúdo em seções principais: o `index.html` possui quatro `<section>` vazias dentro do `<main>`; utilize essas seções para novos blocos seguindo as classes existentes (`.header-content`, `.buttons`).

## Observações práticas para PRs e commits
- Não há pipeline de build/test detectado — PRs pequenos e descritivos são apropriados. Exemplo de mensagem: `style: ajustar header e renomear imagem`.
- Valide visualmente no navegador (mobile + desktop) e confirme que fonts e imagens carregam corretamente.

## O que NÃO está aqui (limitações)
- Não há regras de lint, testes automatizados ou CI detectados no repositório — portanto os agentes não devem tentar conjurar passos de build inexistentes.

---
Se algo estiver impreciso ou se você quiser que eu adicione exemplos de PRs, conventions de commit (conventional commits) ou snippets de desenvolvimento (npm/python server tasks), diga o que prefere que eu detalhe. ✅
