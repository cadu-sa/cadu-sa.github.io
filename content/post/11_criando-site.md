---
title: 'Criando um site com HUGO e GitHub Pages'
description: "Neste artigo, vou mostrar o processo de criação de um site usando o framework Hugo e como hospedar o site no GitHub com o GitHub Pages"

date: 2025-07-06T14:00:00-00:00

categories:
  - artigos
tags: [artigos, linkedin, hugo, github pages, golang]

cover: https://raw.githubusercontent.com/cadu-sa/arquivos-site/refs/heads/main/rabisc.png
---

# Criando um site com HUGO e GitHub Pages

<img src="https://raw.githubusercontent.com/cadu-sa/arquivos-site/refs/heads/main/meu-site.png"/>


## Introdução

Recentemente, criei esse site pessoal usando o framework [Hugo](http://gohugo.io/) (GoHugo) e hospedei no GitHub usando o [GitHub Pages](https://pages.github.com/). Neste artigo, vou mostrar como foi esse processo, desde a escolha do tema do site até a hospedagem no GitHub. Então, caso você esteja pensando em criar um site usando o Hugo, os passos apresentados aqui podem servir como base para a criação do seu site.


Link do meu site: https://cadu-sa.github.io/


### O que é Hugo? 

Basicamente, Hugo é um gerador de sites estáticos de código aberto, escrito na liguagem de programação Go (Golang), da Google. Com o Hugo, podemos definir a estrutura e a aparência do site usando templates e arquivos de configuração, gerando automaticamente páginas HTML estáticas extremamente rápidas, seguras e flexíveis. Além disso, podemos escrever as postagens em Markdown e o site criado tem uma integração fácil com o GitHub Pages.

### O que é GitHub Pages?

Basicamente, GitHub Pages é um serviço de hospedagem gratuita e segura de sites estáticos oferecido pelo GitHub. Ele permite publicar sites diretamente de um repositório GitHub, tornando-se uma solução popular para hospedar projetos pessoais, documentações, blogs e portfólios. Com o GitHub Pages, podemos fazer deploy automaticamente através de commits e teremos um site com domínio gratuíto do tipo `.github.io`.

## Passo a Passo da Criação

Primeiramente, precisamos fazer a instalação do Hugo no computador. 

### Instalando o Hugo

Para fazer a instalação do Hugo, primeiro acesse o link abaixo para baixar a versão mais recente do Hugo para Windows ou Linux: 

https://github.com/gohugoio/hugo/tags

Após acessar o link acima, vá na lista **Assets** e baixe o arquivo correspondente ao seu sistema operacional que tenha `hugo_extended` no nome. Por fim, execute o arquivo para a instalação ser feita.

> Como eu uso a distro Linux **Debian 12.11** como sistema operacional, fiz o download do arquivo `hugo_extended_0.147.9_linux-amd64.deb`. Após isso, abrir o terminal na pasta onde o arquivo foi salvo e executei o código abaixo:
> 
> ```bash
> sudo dpkg -i hugo_extended_0.147.9_linux-amd64.deb
> ```
> Para verificar se a instalação foi bem-sucedida, executei o códigio abaixo:
> 
> ```bash
> hugo version
> ```
> 
> Eu também poderia fazer a instalação do Hugo via terminal através do código abaixo:
> 
> ```bash
> sudo apt update
> sudo apt install hugo
> hugo version
> ```

Após a instalação do Hugo, vamos escolher um tema para o site. 

### Escolhendo o Tema do Site

No site do Hugo podemos encontrar vários temas que podemos usar no site. Segue o link dos temas do Hugo:

https://themes.gohugo.io/

**Observação:** nesse artigo, irei focar no tema escolhido para o meu site: [hugo-theme-reimu](https://themes.gohugo.io/themes/hugo-theme-reimu/)

<img src="https://themes.gohugo.io/themes/hugo-theme-reimu/screenshot_hu_408a192743931e1e.webp"/>

> Sobre o tema `hugo-theme-reimu`:
> 
> - É um tema criado por [D-Sketon](https://github.com/D-Sketon);
> - O tema é inspirado em Hakurei Reimu, uma personagem do Touhou Project;
> - Combina elementos de outros temas populares na China: [landscape](https://github.com/hexojs/hexo-theme-landscape), [Tangyuxian](https://github.com/tangyuxian/hexo-theme-tangyuxian) e [Shoka](https://github.com/amehime/hexo-theme-shoka);
> - Originalmente o tema foi criado para o framework [Hexo](https://hexo.io/pt-br/) e depois foi adaptado para Hugo;
> - O design é limpo e moderno, tem suporte multilíngue (implementação de i18n), é otimizado para performance, é responsivo e possui um guia de customização bem explicado.

Após escolher o tema, vamos baixar o tema no computador.

### Baixando o Tema

1. Acesse o tema que está hospedado no [GitHub](https://github.com/D-Sketon/hugo-theme-reimu/tree/main);
2. Clique em "Code";
3. Clique em "Download ZIP" para baixar o arquivo .zip;
4. Extraia o arquivo .zip.
5. Abra a pasta que foi extraida.

Ao abrir a pasta, veremos uma estrutura mais ou menos assim:

```bash
hugo-theme-reimu/
  ├── _example/
  ├── archetypes/
  ├── assets/
  ├── config/
  ├── data/
  ├── i18n/
  ├── images/
  ├── layouts/
  ├── static/
  ├── CHANGELOG.md
  ├── LICENSE
  ├── README.en.md
  ├── README.md
  ├── config.toml
  ├── go.mod
  ├── package.json
  └── theme.toml
```

Com o tema no computador, vamos iniciar o servidor Hugo.

### Iniciando o Servidor Hugo

Antes de começarmos a fazer a customização do site, vamos ver como o site está atualmente. Para fazer isso, primeiro abra o terminal na pasta do tema e execute o comando abaixo para iniciar o servidor local.

```bash
hugo server
```

O servidor será iniciado no link: `http://localhost:1313`

Agora vamos fazer a customização do site. Vamos começar deixando o site em Português, já que, por padrão do tema, o site está em Chinês.

### Traduzindo o site para Português

Acesse o arquivo `config.toml` na pasta principal e adicione o seguinte código:

```bash
languageCode = 'pt-BR'
defaultContentLanguage = 'pt-BR'
```

> **Observações:**
> - `languageCode = 'pt-BR'`: define o código do idioma principal como Português Brasileiro;
> - `defaultContentLanguage = 'pt-BR'`: define pt-BR como idioma padrão do conteúdo;

Isso não é suficiente para deixar o site totalmente em português, pois dentro da pasta `i18n/` não tem o arquivo `pt-BR.yml`, que é responsável pela tradução. Então vamos criar esse arquivo:
1. Acesse a pasta `i18n`;
2. Faça uma cópia do arquivo `en.yml` e nomeie a cópia de `pt-BR.yml`;
3. Ao abrir o arquivo `pt-BR.yml`, veremos algo parecido com:

```bash
categories: Categories
search: Search
tags: Tags
tagcloud: Tag Cloud
tweets: Tweets
prev: Prev
next: Next
comment: Comments
...
...
...
```

Nesse caso, precisamos colocar a tradução do lado direito dos dois pontos. Vai ficar mais ou menos assim:

```bash
categories: Categorias
search: Buscar
tags: Tags
tagcloud: Nuvem de Tags
tweets: Tweets
prev: Anterior
next: Próximo
comment: Comentários
...
...
...
```

> Observação: você pode fazer a tradução manualmente ou pode usar alguma LLM (por exemplo, ChatGPT) para auxiliar na tradução, basta copiar o conteúdo do arquivo `pt-BR.yml`, cola na LLM e escreve o seguinte prompt:
> 
> ```bash
> Estou criando um site usando o GoHugo. O conteúdo abaixo é do arquivo en.yml da pasta i18n, me ajude a criar o arquivo pt-BR.yml traduzindo o conteúdo abaixo para português brasileiro.
> 
> <cole aqui o conteúdo do arquivo pt-BR.yml>
> ```
> Após isso, é só conferir se as traduções estão corretas e depois cola no arquivo `pt-BR.yml`.

Dessa forma, a maior parte do site estará em português. Agora vamos traduzir alguns textos específicos do site.

1. Acesse o arquivo `params.yml` que está na pasta `config/_default/`;
2. No arquivo você vai adicionar `pt-BR: "texto traduzido"` em algumas partes do código:

```yml
preloader:
  enable: true
  text:
    pt-BR: "Carregando..."

footer:
  copyright:
    enable: true
    text:
      pt-BR: "© 2024 Seu Nome. Todos os direitos reservados."

clipboard:
  success:
    pt-BR: "Copiado com sucesso! 😊"
  fail:
    pt-BR: "Falha ao copiar 😔"

outdate:
  enable: true
  message:
    pt-BR: "Este artigo foi atualizado pela última vez em {time}. O conteúdo pode estar desatualizado."

sponsor:
  tip:
    pt-BR: "Me pague um café ☕"
```

Prontinho, agora o site estará em português.

### Customizações Básicas

Agora vamos fazer algumas customizações básicas no site.

#### Avatar, Banner, Favicon

Os recursos estáticos do tema (favicon, imagens de cabeçalho e avatar) estão localizados na pasta `static/`. Portanto, para alterar esses recursos no site, basta sobrescrever os arquivos da pasta com as imagens que você deseja, mantendo o mesmo nome. 

Esses recursos estáticos também estão presentes no arquivo `params.yml`. Por exemplo, em `params.yml`, podemos ver a linha responsável pelo avatar:

```yml
avatar: "avatar.webp"
```

Em relação a capa, a lógica de exibição da capa é a seguinte: se no Front Matter  do artigo contiver uma URL de capa em `cover`, tanto o cabeçalho do artigo quanto a miniatura da página inicial exibirão a imagem da URL.

```markdown
---
title: Título do post
cover: https://example.com
---
```

Se o Front Matter do artigo contiver `cover` definido como `false`, o artigo não exibirá uma imagem de cabeçalho, mas a página inicial ainda mostrará imagens aleatórias, que são as imagens definidas no arquivo `covers.yml` da pasta `data/`.

```markdown
---
title: Título do post
cover: false
---
```

Se o Front Matter do artigo contiver `cover` definido como `rgb(xxx,xxx,xxx)`, o cabeçalho do artigo será um gradiente dessa cor sólida, mas a página inicial ainda mostrará imagens aleatórias.

```markdown
---
title: Título do post
cover: rgb(255,117,117)
---
```

Se não tiver nenhuma imagem em `covers.yml`, será exibido a imagem do banner, que está em `static/images/banner.webp`.

#### Blocos de Código

Para garantir a exibição correta dos blocos de código nos posts, devemos incluir a seguinte configuração em `config.toml`:

```yml
[markup.highlight]
guessSyntax = true
noClasses = false
```

### Criação de Posts

Assim como explicado na `README.md` do [tema](https://github.com/D-Sketon/hugo-theme-reimu/tree/main), vamos mudar o nome da pasta `_examples` para `content`. Agora vamos ver o que tem nessa pasta:


```bash
content/
  ├── archives/
  │   └── _index.md
  ├── post/
  │   ├── _index.md
  │   └── hello.md
  ├── about.md
  └── friend.md
```

> Observações:
> - Em `archives/`, o arquivo `_index.md` é usado para exibir a página de arquivo, não pode ser omitido;
> - Em `post/`, o arquivo `_index.md` é usado para evitar a geração de `post/index.html`, não pode ser omitido;
> - O arquivo `about.md` é a página "sobre";
> - O arquivo `friend.md` é a página de links de amigos. Como não farei uso dessa arquivo, então irei remover-lo.

Os arquivos do posts devem ser criados na pasta `post/` e devem está no formato `.md` (Markdown). Segue a estrutura básica do arquivo `.md` do post:

```Markdown
---
title: "Título do Post"
description: "Descrição do post"

date: 2024-08-05T11:00:00-07:00

categories: [categoria1, categoria2]
tags: [tag1, tag2]

cover: https://example.com
---

escreva o conteúdo do post aqui
```

As customizações acima já são suficientes para ter um site funcional. Agora vamos hospedar o site no GitHub.

## Hospedando no GitHub

1. Abra o seu GitHub e crie um repertório público com o nome: `seu-usuario.github.io`. Por exemplo, `cadu-sa.github.io`;
2. Clone o repertório no seu computador:

```bash
git init
git remote add origin https://github.com/seu-usuario/seu-usuario.github.io.git
```

3. Copie todos os arquivos e pastas de `hugo-theme-reimu/` que você estava editando e cole dentro da pasta clonada `seu-usuario.github.io/`;
4. Acesse a pasta `seu-usuario.github.io/` e inicialize o servidor Hugo na pasta;
5. Abra o arquivo `config.toml` e inclua a seguinte configuração:

```yml
baseURL = "https://seu-usuario.github.io/"
```

6. Na pasta `seu-usuario.github.io/`, crie a pasta `.github`. Dentro dela, crie a pasta `workflows`. E dentro dessa última pasta, crie o arquivo `hugo.yml` e coloque a seguinte configuração em `hugo.yml`:

```yml
# Sample workflow for building and deploying a Hugo site to GitHub Pages
name: Deploy Hugo site to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ["main"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

# Default to bash
defaults:
  run:
    shell: bash

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    env:
      HUGO_VERSION: 0.128.0
    steps:
      - name: Install Hugo CLI
        run: |
          wget -O ${{ runner.temp }}/hugo.deb https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_linux-amd64.deb \
          && sudo dpkg -i ${{ runner.temp }}/hugo.deb
      - name: Install Dart Sass
        run: sudo snap install dart-sass
      - name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5
      - name: Install Node.js dependencies
        run: "[[ -f package-lock.json || -f npm-shrinkwrap.json ]] && npm ci || true"
      - name: Build with Hugo
        env:
          HUGO_CACHEDIR: ${{ runner.temp }}/hugo_cache
          HUGO_ENVIRONMENT: production
        run: |
          hugo \
            --minify \
            --baseURL "${{ steps.pages.outputs.base_url }}/"
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public

  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

7. Faça o commit:

```bash
git add .
git commit -m "commit inicial"
git push -u origin main
```

8. Abra o seu GitHub e acesse a página `Settings`;
9. No campo `Source`, selecione a opção `GitHub Actions`;
10. Vá na página `Actions` e aguarde o deploy finalizar;
11. Após o deploy finalizar, acesse seu site em `https://seu-usuario.github.io/`

## Conclusão

Ao longo deste artigo, exploramos o processo de criação de um site utilizando o tema `hugo-theme-reimu`. Os passos apresentados não apenas permitem construir um site funcional com este tema específico, mas também servem como base para trabalhar com qualquer outro [tema disponível no Hugo](https://themes.gohugo.io/).

Caso você escolha o tema `hugo-theme-reimu` como tema do seu site, considere ler a documentação para fazer mais customizações no site: https://github.com/D-Sketon/hugo-theme-reimu/blob/main/README.en.md.

Espero que tenham gostado desse artigo e até a próxima!