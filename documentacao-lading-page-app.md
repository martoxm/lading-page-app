# Documentação de Estudo — Lading Page App (Zingen)

> **Repositório:** [https://github.com/martoxm/lading-page-app](https://github.com/martoxm/lading-page-app)  
> **Tecnologias:** HTML5 · CSS3 (Flexbox · Grid · CSS Nesting · Custom Properties)  
> **Objetivo do projeto:** Construir uma landing page completa para um app de karaokê, praticando estruturação semântica, sistema de design com variáveis CSS, componentes reutilizáveis e responsividade.

---

## Índice

1. [Estrutura Final do Projeto](#estrutura-final-do-projeto)
2. [Histórico de Commits](#histórico-de-commits)
   - [Commit 1 — Initial commit](#commit-1--initial-commit)
   - [Commit 2 — Definindo variáveis CSS](#commit-2--definindo-variáveis-css)
   - [Commit 3 — Add classes utilitárias](#commit-3--add-classes-utilitárias)
   - [Commit 4 — Estilizando os botões](#commit-4--estilizando-os-botões)
   - [Commit 5 — Componente de menu e social links](#commit-5--componente-de-menu-e-social-links)
   - [Commit 6 — Criando o header](#commit-6--criando-o-header)
   - [Commit 7 — Hero section](#commit-7--hero-section)
   - [Commit 8 — About section](#commit-8--about-section)
   - [Commit 9 — Features section](#commit-9--features-section)
   - [Commit 10 — Pricing section](#commit-10--pricing-section)
   - [Commit 11 — Download section](#commit-11--download-section)
   - [Commit 12 — Footer](#commit-12--footer)
   - [Commit 13 — Ajuste de bug na área featured](#commit-13--ajuste-de-bug-na-área-featured)
   - [Commit 14 — Remove scroll horizontal](#commit-14--remove-scroll-horizontal)
   - [Commits 15–16 — README](#commits-15–16--readme)
3. [Conceitos Aplicados](#conceitos-aplicados)
4. [Arquitetura dos arquivos CSS](#arquitetura-dos-arquivos-css)
5. [Resumo prático para estudo](#resumo-prático-para-estudo)

---

## Estrutura Final do Projeto

```text
lading-page-app/
├── .gitignore
├── README.MD
├── index.html
├── assets/
│   ├── logo.svg
│   ├── music-bars.svg
│   ├── smartphones.png
│   ├── bg-hero-desktop.svg
│   ├── illustration.svg
│   ├── button-apple.svg
│   ├── button-play-store.svg
│   ├── preview.png
│   ├── Tela 1.png
│   ├── Tela 2.png
│   ├── Tela 3.png
│   ├── rapaz-ouvindo-musica-com-fones-de-ouvido-e-cantando-no-aplicativo-de-karaoke-removebg 1.png
│   └── icons/
│       ├── MagicWand.svg
│       ├── GameController.svg
│       ├── MicrophoneStage.svg
│       ├── UsersThree.svg
│       ├── MusicNotes.svg
│       ├── Check.svg
│       ├── tiktok.svg / tiktok-hover.svg
│       ├── instagram.svg / instagram-hover.svg
│       ├── twitter.svg / twitter-hover.svg
│       └── discord.svg / discord-hover.svg
└── style/
    ├── index.css
    ├── global.css
    ├── utility.css
    ├── buttons.css
    ├── social.css
    ├── header.css
    ├── hero.css
    ├── sections.css
    ├── about.css
    ├── cards.css
    ├── features.css
    ├── pricing.css
    ├── download.css
    └── footer.css
```

---

## Histórico de Commits

### Commit 1 — Initial commit

**SHA:** `0525735c`  
**Data:** 08/06/2026 — 18:06

#### O que foi feito

Criação inicial do projeto com a estrutura base de HTML, pasta `assets/`, arquivos de imagens e primeiros estilos em `style/`.

#### Estrutura do `index.html`

```html
<!doctype html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Zingen - Karaokê</title>
    <link rel="stylesheet" href="style/index.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Alice&family=Archivo:ital,wght@0,100..900;1,100..900&family=Inter:ital,opsz@0,14..32;1,14..32&family=Poppins:wght@400;700&display=swap"
      rel="stylesheet"
    />
  </head>
```

#### Conceito: base HTML e fontes

O projeto já nasce com `lang="pt-br"`, `meta viewport` e integração com Google Fonts. Isso garante acessibilidade, responsividade e tipografia pronta desde o começo.

---

### Commit 2 — Definindo variáveis CSS

**SHA:** `ba455afb`  
**Data:** 08/06/2026 — 18:35

#### O que foi feito

Criação do `style/global.css` com reset, variáveis globais, tipografia base e regras gerais para o documento.

#### Código — `style/global.css`

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

* {
  margin: 0;
  padding: 0;
  font: inherit;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

:root {
  --bg-color: #09090b;
  --surface-color: #18181b;
  --stroke-color: #27272a;
  --text-color-primary: #f4f4f5;
  --text-color-secondary: #a1a1aa;
  --brand-color-primary: #f7b733;
  --brand-color-secundary: #fc4a1a;

  --ff-sans: "Inter", system-ui, sans-serif;
  --fw-base: 400;
  --fw-md: 500;
  --fw-bold: 800;

  --fs-sm: 0.875rem;
  --fs-base: 1rem;
  --fs-lg: 1.25rem;
  --fs-xl: 1.5rem;
  --fs-2xl: 2.75rem;

  --py-base: 1rem;
  --py-lg: 1.5rem;
  --py-xl: 3rem;

  --px-lg: 1.5rem;
}
```

#### Conceito: custom properties

As variáveis concentram cores, tamanhos e espaçamentos em um só lugar. Isso facilita manutenção e deixa o projeto com cara de design system.

#### Responsividade no `:root`

No breakpoint desktop, os tamanhos são reajustados:

```css
@media (width >= 80em) {
  :root {
    --fs-lg: 2rem;
    --fs-xl: 3rem;
    --fs-2xl: 4rem;
    --py-base: 1.5rem;
    --py-lg: 2.5rem;
    --py-xl: 5rem;
    --px-lg: 2rem;
  }
}
```

Isso é ótimo porque o layout inteiro se adapta apenas alterando tokens globais.

---

### Commit 3 — Add classes utilitárias

**SHA:** `4fa6620e`  
**Data:** 08/06/2026 — 19:12

#### O que foi feito

Criação de `style/utility.css` com classes reutilizáveis para espaçamento, layout e visibilidade.

#### Código — `style/utility.css`

```css
.py-base { padding-block: var(--py-base); }
.py-lg { padding-block: var(--py-lg); }
.py-xl { padding-block: var(--py-xl); }
.px-lg { padding-inline: var(--px-lg); }

.container {
  --max-width: 375px;
  width: min(var(--max-width), 100% - var(--px-lg) * 2);
  margin-inline: auto;
}

.desktop-only { display: none; }
.even-columns { display: grid; gap: 1rem; }
.flex { display: flex; }
.items-center { align-items: center; }
.gap-1 { gap: 1rem; }
.gap-1\.5 { gap: 1.5rem; }
.grid { display: grid; }

@media (width >= 80em) {
  .container { --max-width: 80rem; }
  .desktop-only { display: initial; }
  .even-columns {
    grid-auto-flow: column;
    grid-auto-columns: 1fr;
  }
}
```

#### Conceito: utility-first

O arquivo segue um estilo utility-first: classes pequenas e focadas, reaproveitadas no HTML. Isso acelera a montagem da interface e reduz duplicação de CSS.

#### Conceito: `width: min(...)`

A `.container` usa `width: min(var(--max-width), 100% - var(--px-lg) * 2)`. Isso impede que o conteúdo ultrapasse a largura máxima e também respeita o padding lateral em telas menores.

---

### Commit 4 — Estilizando os botões

**SHA:** `a4c232c7`  
**Data:** 08/06/2026 — 20:10

#### O que foi feito

Criação de `style/buttons.css`, definindo o componente `.btn` e suas variações `btn-sm`, `btn-md` e `btn-lg`.

#### Código — `style/buttons.css`

```css
.btn {
  --btn-bg-color: var(--text-color-primary);
  --btn-color: var(--bg-color);
  border: 0;
  background-color: transparent;
  display: flex;
  align-items: center;
  justify-content: center;
  width: fit-content;
  border-radius: 0.5rem;
  font: var(--fw-md) var(--fs-base)/1.5rem var(--ff-sans);
  cursor: pointer;
  background: var(--btn-bg-color);
  color: var(--btn-color);
}
```

#### Conceito: botão como componente

A classe `.btn` é um componente base. Depois, as variações ajustam apenas tamanho e padding, mantendo consistência visual em toda a página.

#### Técnica: botão com `aria-label`

No HTML, alguns botões não têm texto visível, então usam `aria-label`. O CSS aproveita isso com `::before` e `::after` para renderizar um efeito visual sem perder acessibilidade.

---

### Commit 5 — Componente de menu e social links

**SHA:** `c7bae8d9`  
**Data:** 08/06/2026 — 20:39

#### O que foi feito

Criação dos links sociais e do menu principal no header usando ícones SVG e classes utilitárias.

#### Conceito: `social.css`

```css
a.social {
  --bg-img: "";
  background-image: var(--bg-img);
  width: 1.5rem;
  height: 1.5rem;
  display: block;
}
```

Cada rede social troca o `background-image` pelo atributo `aria-label`.

#### Conceito: uso de `aria-label`

```css
&[aria-label="tiktok"] { --bg-img: url(../assets/icons/tiktok.svg); }
```

Isso permite reutilizar um único componente `.social` para vários ícones, sem classes diferentes para cada rede.

---

### Commit 6 — Criando o header

**SHA:** `dcaa585b`  
**Data:** 09/06/2026 — 19:24

#### O que foi feito

Estrutura do cabeçalho com logo, links de navegação e botão principal “Baixar Agora”.

#### HTML do header

```html
<header>
  <div class="container py-base">
    <nav class="flex items-center gap-1.5">
      <a href="#">
        <img src="./assets/logo.svg" alt="Logo Zingen" />
      </a>

      <a href="#about" class="desktop-only">Conheça o app</a>
      <a href="#features" class="desktop-only">Funcionalidades</a>
      <a href="#pricing" class="desktop-only">Planos e preços</a>

      <a href="#download" class="btn btn-sm">Baixar Agora</a>
    </nav>
  </div>
</header>
```

#### Conceito: navegação responsiva

Os links principais ficam escondidos no mobile com `.desktop-only` e aparecem no desktop. Isso simplifica a interface em telas pequenas sem perder conteúdo no desktop.

---

### Commit 7 — Hero section

**SHA:** `e113295b`  
**Data:** 09/06/2026 — 19:44

#### O que foi feito

Criação da seção hero com ilustração, título, subtítulo e dois botões de ação.

#### HTML do hero

```html
<section id="hero">
  <div class="container py-xl">
    <img src="./assets/music-bars.svg" alt="Music bars" />
    <h1>Quem canta seus males espanta</h1>
    <p>Cantar nunca foi tão fácil</p>

    <div class="buttons flex items-center gap-1">
      <a href="#pricing" aria-label="Ver planos" class="btn btn-md"></a>
      <a href="#download" class="btn btn-md">Baixar agora </a>
    </div>
  </div>
</section>
```

#### CSS do hero

```css
#hero {
  text-align: center;
  & img[src*="music"] { width: 12.875rem; }
  & h1 { margin-top: 1rem; }
  & p {
    font: var(--fw-md) var(--fs-lg)/1.4 var(--ff-sans);
    color: var(--text-color-secondary);
    margin-top: 0.5rem;
  }
  & .buttons {
    justify-content: center;
    margin-top: 2rem;
  }
}
```

#### Conceito: seletor por atributo

`img[src*="music"]` seleciona a imagem cujo `src` contém a palavra “music”. É útil quando você quer estilizar um grupo específico sem adicionar classes extras.

---

### Commit 8 — About section

**SHA:** `2279839d`  
**Data:** 09/06/2026 — 20:12

#### O que foi feito

Estrutura da seção “Conheça o app”, explicando o produto e seu diferencial de inteligência artificial.

#### HTML resumido

```html
<section id="about">
  <div class="container even-columns py-xl items-center">
    <div>
      <header>
        <strong>Conheça o app</strong>
        <h2>O aplicativo perfeito para aprender a cantar</h2>
      </header>
      <p>...</p>
    </div>
    <div>
      <img class="desktop-only" src="assets/smartphones.png" alt="" />
    </div>
  </div>
</section>
```

#### CSS do about

```css
#about {
  background-color: var(--surface-color);
  & .even-columns { gap: 2rem; }
}
```

#### Conceito: duas colunas no desktop

A classe `.even-columns` permite que conteúdo textual e imagem fiquem lado a lado no desktop, mas continuem empilhados no mobile.

---

### Commit 9 — Features section

**SHA:** `c71ab699`  
**Data:** 09/06/2026 — 20:57

#### O que foi feito

Montagem da seção de funcionalidades com 5 cards, alguns com imagem flutuando no canto e outros com layout assimétrico.

#### CSS mais importante

```css
#features {
  & .cards {
    grid-template-columns: 17.5rem 1fr 1fr 17.5rem;
    grid-template-rows: 25rem 25rem;
    gap: 2rem;
  }

  & .card {
    position: relative;
    overflow: hidden;

    & img.desktop-only {
      position: absolute;
      max-width: 15rem;
      filter: drop-shadow(1rem 1rem 4rem rgb(0 0 0 / 0.34));
    }
  }
}
```

#### Conceito: Grid complexo com cards

Essa seção usa CSS Grid para montar um layout visual mais elaborado, com cards ocupando colunas diferentes. É um ótimo exemplo de quando Grid é melhor que Flexbox.

---

### Commit 10 — Pricing section

**SHA:** `9f95361e`  
**Data:** 10/06/2026 — 00:00

#### O que foi feito

Criação da seção de planos com três cards: Básico, Premium e Família.

#### Estrutura do Premium

```html
<div class="premium">
  <div class="card py-lg px-lg">
    <span>1 mês grátis</span>
    <h3>Premium</h3>
    <p>Ideal para quem já cansou de passar vergonha no Karaokê</p>
    <zin-pricing>R$ 24,90 <small>/mês</small></zin-pricing>
    <a href="#download" class="btn btn-md">Experimente de graça</a>
    <div class="separator"></div>
    <ul role="list" class="grid gap-1">...</ul>
  </div>
</div>
```

#### Conceito: cartão em destaque

O plano Premium recebe borda e badge de destaque, indicando que é a opção central da página. O destaque foi criado com `::before` e gradiente no wrapper `.premium`.

#### Conceito: componente customizado `zin-pricing`

O projeto usa uma tag personalizada `zin-pricing` para exibir o preço. Embora não seja uma tag HTML padrão, funciona como elemento inline/block estilizado via CSS.

---

### Commit 11 — Download section

**SHA:** `2fe23b1e`  
**Data:** 10/06/2026 — 00:18

#### O que foi feito

Criação da seção de download com texto persuasivo, botões da App Store e Play Store, e imagem do app/ilustração do personagem.

#### CSS da seção

```css
#download {
  .card {
    padding: 3rem 1.5rem 15rem;
    position: relative;

    & > img {
      width: 14.5rem;
      position: absolute;
      bottom: 0;
      right: -3.5rem;
    }
  }

  .buttons {
    flex-wrap: wrap;
    margin-top: 2rem;
  }
}
```

#### Conceito: imagem absoluta no card

A imagem é posicionada com `position: absolute` para “sair” do fluxo normal e parecer encaixada ao lado do conteúdo. Isso ajuda a criar composição visual mais rica sem quebrar a estrutura do HTML.

---

### Commit 12 — Footer

**SHA:** `6d0e052b`  
**Data:** 10/06/2026 — 01:11

#### O que foi feito

Criação do rodapé com links organizados em colunas e ícones sociais no final.

#### CSS do footer

```css
footer {
  color: var(--text-color-secondary);
  font-weight: var(--fw-md);

  & .bottom {
    flex-wrap: wrap;

    & > div {
      margin-right: auto;
    }

    & span {
      font-size: 0.875rem;
    }
  }
}
```

#### Conceito: separação de conteúdo e navegação

O footer divide o conteúdo em duas áreas: links institucionais no topo e redes sociais/copyright no rodapé interno. Isso melhora a leitura e a hierarquia da página.

---

### Commit 13 — Ajuste de bug na área featured

**SHA:** `9dceb020`  
**Data:** 10/06/2026 — 01:20

#### O que foi feito

Correção de problema de layout na área principal, provavelmente ligado à seção de destaque ou proporções dos cards.

#### Lição prática

Esse commit mostra a importância de testar o layout em diferentes larguras. Em landing pages com muitas seções, pequenos ajustes de `grid`, `flex`, `overflow` e imagens absolutas são comuns.

---

### Commit 14 — Remove scroll horizontal

**SHA:** `28a9c505`  
**Data:** 10/06/2026 — 01:24

#### O que foi feito

Correção final para eliminar rolagem horizontal indesejada.

#### Solução aplicada no projeto

No `global.css`:

```css
html {
  overflow-x: hidden;
}

body {
  overflow-x: hidden;
}
```

#### Conceito: scroll horizontal

Esse bug aparece quando algum elemento extrapola a largura da viewport. Pode acontecer por imagens grandes, elementos posicionados absolutamente ou larguras fixas em telas menores.

---

### Commits 15–16 — README

**SHA:** `9dfa0213`, `c0111390`  
**Data:** 10/06/2026 — 21:35 e 21:39

#### O que foi feito

Criação e atualização do `README` com descrição do projeto, preview e informações para estudo.

#### Conceito: documentação como parte do projeto

Um bom README não é só “enfeite”. Ele ajuda a explicar a proposta do projeto, mostra o que foi aprendido e facilita revisitar o código depois.

---

## Conceitos Aplicados

### Custom Properties

O projeto usa variáveis para tudo: cores, fontes, pesos e espaçamentos. Isso torna o CSS escalável e fácil de alterar.

### Utility-first

Arquivos como `utility.css` criam classes pequenas e reutilizáveis, acelerando a montagem de páginas inteiras.

### CSS Nesting

O código usa aninhamento para deixar os blocos mais organizados:

```css
#hero {
  & h1 { ... }
  & .buttons { ... }
}
```

### Grid e Flexbox

- Flexbox foi usado para alinhamento interno de componentes.
- Grid foi usado para seções mais complexas, como `features` e `even-columns`.

### Responsividade

O projeto adota o breakpoint de `80em` para alternar entre mobile e desktop. Isso define desde classes utilitárias até seções inteiras.

---

## Arquitetura dos arquivos CSS

```css
@import url(global.css);
@import url(utility.css);
@import url(buttons.css);
@import url(social.css);
@import url(header.css);
@import url(hero.css);
@import url(sections.css);
@import url(about.css);
@import url(cards.css);
@import url(features.css) (width >= 80rem);
@import url(pricing.css);
@import url(download.css);
@import url(footer.css);
```

#### Responsabilidade de cada arquivo

| Arquivo | Função |
|---|---|
| `global.css` | Base, reset, tokens e estilos globais |
| `utility.css` | Classes utilitárias reutilizáveis |
| `buttons.css` | Componentização dos botões |
| `social.css` | Ícones sociais com hover |
| `header.css` | Estrutura do cabeçalho |
| `hero.css` | Seção principal da página |
| `sections.css` | Regras genéricas para títulos e textos de seção |
| `about.css` | Fundo e espaçamento da seção about |
| `cards.css` | Base visual dos cards |
| `features.css` | Layout complexo de funcionalidades |
| `pricing.css` | Planos e preços |
| `download.css` | Bloco final com CTA de download |
| `footer.css` | Rodapé e navegação final |

---

## Resumo prático para estudo

Se você quiser reaplicar esse projeto em outro estudo, a sequência mental é esta:

1. Defina os **tokens globais** no `:root`.
2. Crie classes utilitárias para **padding, grid e flex**.
3. Monte o **header** com navegação responsiva.
4. Estruture o **hero** com CTA e imagem de destaque.
5. Divida o resto em **seções semânticas** (`about`, `features`, `pricing`, `download`).
6. Reutilize `.card`, `.btn`, `.container` e `desktop-only` para consistência.
7. Finalize com o **footer** e revise bugs de overflow.

> **Lição principal:** este projeto é um ótimo exercício de componentização em HTML/CSS. Ele mostra como organizar uma landing page de forma limpa, escalável e fácil de manter.

---

*Documentação gerada com base no repositório [https://github.com/martoxm/lading-page-app](https://github.com/martoxm/lading-page-app).*