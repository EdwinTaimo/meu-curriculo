Site pessoal de currículo (portfólio), desenvolvido em **HTML5 + CSS3 puro**,
sem frameworks de CSS e sem JavaScript, como Trabalho Prático I da disciplina
de Programação de Design Web.

## Autor

**Edwin Jerry Joaquim Taimo Gema**
Curso de Licenciatura em Informática — 2º Ano
Universidade Licungo

## Como visualizar o site

Não é preciso instalar nada. Basta abrir o ficheiro `index.html` num
navegador 

Também podes acessar o site  com o **GitHub Pages**:

[edwintaimo.github.io/meu-curriculo](https://edwintaimo.github.io/meu-curriculo/)

Páginas do site

| Página            | Ficheiro           | Conteúdo                                                                                          |
| ------------------ | ------------------ | -------------------------------------------------------------------------------------------------- |
| Início            | `index.html`     | Apresentação pessoal, frase de efeito, destaques rápidos, vídeo e áudio de apresentação     |
| Sobre / Currículo | `about.html`     | Formação académica, experiência (AIESEC), tabela de competências técnicas, citação pessoal |
| Portfólio         | `portfolio.html` | Projetos/iniciativas em cartões, organizados com CSS Grid                                         |
| Hobbies            | `hobbies.html`   | Amigos, eventos automóveis, boxe e futebol, organizados com Flexbox                               |
| Contacto           | `contact.html`   | Formulário completo com validação nativa em HTML5                                               |

## Estrutura de pastas

```
meu-curriculo/
├── index.html
├── about.html
├── portfolio.html
├── hobbies.html
├── contact.html
├── css/
│   ├── estilo.css       → estilos partilhados (variáveis, header, footer, componentes)
│   └── responsivo.css   → media queries (mobile-first)
├── assets/
│   ├── img/              → fotografias e retrato
│   ├── video/             → vídeo de demonstração + capa (poster)
│   ├── audio/              → áudio de demonstração
│   └── ficheiros/           → CV em PDF ou outros anexos
└── README.md
```




- **`<header>` / `<nav>` / `<main>` / `<section>` / `<article>` / `<aside>` / `<footer>`** — estrutura semântica da página, em vez de tudo feito só com `<div>`. Ajuda leitores de ecrã e motores de busca a perceber a função de cada bloco.



- **`<figure>` / `<figcaption>`** — usados sempre que uma imagem tem legenda (ex.: foto do evento AIESEC).



- **`<video controls poster="...">` com `<source type="video/mp4">`** — vídeo nativo, sem plugins nem JavaScript; o `poster` mostra uma imagem antes do vídeo começar a carregar.



- **`<audio controls>` com `<source type="audio/mpeg">`** — áudio nativo do HTML5.



- **`<table>` com `<thead>`/`<tbody>` e `colspan`** — organiza a tabela de competências técnicas; o `colspan="3"` faz o cabeçalho "Nível" ocupar as três colunas de proficiência.
- **`<fieldset>` / `<legend>`** — agrupa campos relacionados no formulário de contacto (ex.: "Dados pessoais").
- **`<label for="...">`** — associa cada rótulo ao respetivo campo através do `id`, essencial para acessibilidade (clicar no texto ativa o campo).
- **Atributos de validação nativa** — `required`, `minlength`, `pattern`, `min`, `max`, `type="email"`, `accept` — validam o formulário sem uma linha de JavaScript.

### CSS3

- **Variáveis CSS (`:root { --cor-primaria: ... }`)** — cores, fontes e espaçamentos centralizados num só sítio.
- **Seletores avançados** — descendente (`.projeto__corpo h3`), filho direto (`.menu-principal > li`), irmão adjacente (`.campo label + input`) e de atributo (`input[type="email"]`).
- **Pseudo-classes** — `:hover`, `:focus`, `:first-child`, `:last-child`, `:nth-child()` (ex.: linhas "zebra" na tabela, pontos do mock-up do navegador, cor da barra de cada cartão de projeto).
- **Pseudo-elementos** — `::before` e `::after` (sublinhado animado do menu, aspas decorativas da citação, faixa de destaque no topo dos cartões).
- **Flexbox** — usado de forma intencional na página `hobbies.html` (`flex-wrap`, `justify-content`, `align-items`) e também no menu do cabeçalho e no rodapé.
- **CSS Grid** — usado na grelha principal da página `portfolio.html`, com `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))`.
- **`position: sticky`** — o cabeçalho acompanha o scroll; a diferença entre `static`, `relative`, `absolute`, `fixed` e `sticky` está explicada em comentário no `estilo.css`.



- **Media queries mobile-first** — estilos base pensados para telemóvel em `estilo.css`; `responsivo.css` usa `min-width` para ampliar o layout em ecrãs maiores (3 breakpoints: 640px, 768px, 1024px).



- **Unidades relativas** — `rem` (espaçamentos e tipografia, escaláveis com as definições do navegador), `%`/`fr` (larguras e colunas do Grid), `vw` (dentro de `clamp()` para títulos fluidos) e `ch` (largura máxima confortável de leitura dos parágrafos), sempre combinadas com `px` onde faz sentido (ex.: bordas finas, ícones).



- Os nomes das classes CSS estão em português (ex.: `.cabecalho`, `.rodape`, `.grelha-portfolio`) para me ser mais fácil de ler e explicar o código.



- Optei por **não usar `:target`** para o menu ativo porque, tendo páginas HTML separadas (e não uma *single page*), a classe `.activo` aplicada manualmente em cada link é mais simples de perceber e de manter neste nível de aprendizagem.
- O cartão "Site de Currículo Pessoal", no Portfólio, usa um pequeno "mock-up" de janela de navegador feito só com `<div>`s e CSS (sem imagem), para representar este próprio projeto.
