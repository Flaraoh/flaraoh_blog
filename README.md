# Flaraoh — Portfólio de Game Design & Desenvolvimento

Site estático (HTML + CSS + JS puro, sem build). Abra `index.html` no navegador. Publicado na HostGator via Git do cPanel (veja `.cpanel.yml`).

O site tem duas trilhas: **Game Design** (acento ouro/marrom) e **Desenvolvimento** (acento verde-petróleo, `--c-track-dev`).

## Estrutura

```
index.html        Início: apresentação, as duas trilhas, projetos em destaque, diário e artigos recentes
games.html        Trilha Game Design: o que faço, projetos, habilidades, artigos e CTA (?assunto=games)
dev.html          Trilha Desenvolvimento: o que faço, projetos, habilidades, artigos e CTA (?assunto=dev)
projects.html     Portfólio completo (fora do menu): filtro por trilha, aceita ?trilha=games|dev
project-1.html    Case study: Pokémon Fan Battle (duas portas: #olhar-games e #olhar-dev)
project-2.html    Case study: o próprio site Flaraoh (trilha Desenvolvimento)
devlog.html       Diário: entradas de desenvolvimento ligadas a cada projeto (devlog-N.html)
articles.html     Artigos: filtro por categoria, aceita ?categoria=carreira|games|dev|bastidores
article-1.html    Modelo de artigo (duplique para article-2.html, ...)
about.html        Sobre: trajetória, competências atuais e direção profissional
contact.html      Contato: formulário com assunto + perfis profissionais
spotlight.html    Divulgações: jogos de outros desenvolvedores
css/style.css     Tokens, base, componentes (BEM-like), media queries mobile-first
js/main.js        Menu responsivo, filtros, ano do rodapé, validação/envio do formulário
assets/           Favicon e imagens de placeholder (SVG)
.cpanel.yml       Deploy no cPanel (HostGator): copia *.html, css, js e assets para public_html
```

## Personalização

- Procure por `EDITAR`, `PREENCHER` e `seu-usuario` nos HTML para trocar textos, links e e-mail.
- **Filtros:** cada card de projeto leva `data-trilha="games"`, `"dev"` ou `"games dev"`; cada artigo leva `data-categoria` com um ou mais valores separados por espaço.
- **Formulário:** crie um formulário em [Formspree](https://formspree.io) e troque `SEU_ID` em `contact.html`. Enquanto `SEU_ID` estiver lá, o envio roda em modo demonstração.
- **Imagens:** substitua os SVGs de `assets/img/` por capturas reais em WebP/AVIF (≈1600px de largura, < 200 KB) mantendo `width`/`height` e `loading="lazy"`.
- **Cores e fontes:** todas as variáveis ficam no `:root` de `css/style.css`.
- Cabeçalho e rodapé se repetem em cada página. Ao mudar o menu, atualize todos os HTML.

## Acessibilidade

- Texto principal `#333` sobre `#FDF9ED` (~12:1); botões `#FDF9ED` sobre `#8B4513` (~7:1). O ouro (`#C8A265`/`#B8860B`) é usado só em detalhes decorativos, nunca em texto.
- Skip link, foco visível, `aria-current` no menu, menu operável por teclado (Esc fecha), erros de formulário ligados aos campos via `aria-describedby`, e respeito a `prefers-reduced-motion`.
- Sem JS, o menu fica sempre visível e o formulário usa a validação nativa do navegador.
