---
title: 'Criando site com GoHugo e GitHub Pages'
description: "meu site"
#keywords: "meu,primeiro,artigo"

date: 2025-07-03T14:00:00-07:00
lastmod: 2025-07-03T14:00:00-07:00

math: false
mermaid: false

categories:
  - artigos
tags:
  - artigos
  - linkedin

cover: https://raw.githubusercontent.com/cadu-sa/arquivos-site/refs/heads/main/rabisc.png
---

<img src="https://raw.githubusercontent.com/cadu-sa/arquivos-site/refs/heads/main/meu-site.png"/>

# Introdução
Recentemente, criei um site pessoal usando o framework [Hugo](http://gohugo.io/) (GoHugo) e hospedei no [GitHub Pages](https://pages.github.com/). Neste artigo, vou mostrar como foi esse processo, desde a escolha do tema até a publicação.

Link do site: https://cadu-sa.github.io/

## O que é Hugo?

Basicamente, Hugo é um gerador de sites estáticos de código aberto, escrito em Go (Golang). Com o Hugo, podemos definir a estrutura e a aparência do site usando templates e arquivos de configuração, gerando automaticamente páginas HTML estáticas extremamente rápidas, seguras e flexíveis. Além disso, podemos escrever as postagens em Markdown e o site criado tem uma integração fácil com o GitHub Pages.

## O que é GitHub Pages?

Basicamente, GitHub Pages é um serviço de hospedagem gratuita e segura de sites estáticos oferecido pelo GitHub. Ele permite publicar sites diretamente de um repositório GitHub, tornando-se uma solução popular para hospedar projetos pessoais, documentações, blogs e portfólios. Com o GitHub Pages, podemos fazer deploy automaticamente através de commits e teremos um site com domínio gratuíto do tipo `github.io`.

# Passo a Passo da Criação

## Instalando o Hugo

Primeiramente, precisamos fazer a instalação do Hugo no computador. Como eu uso a distro Linux Debian 12.11 como sistema operacional, então fiz a instalação do Hugo através da execução direto do arquivo `.deb`, mas essa instalação também pode ser feita via terminal.


### Instalação via terminal

Execute o código abaixo para fazer a instalação do hugo:

```bash
sudo apt update
sudo apt install hugo
```

Para verificar se a instalação foi bem-sucedida:

```bash
hugo version
```

### Instalação através do arquivo .deb

> Segue o link da versão mais recente do Hugo para Windows, Linux ou macOS: 
>
> https://github.com/gohugoio/hugo/tags

Observação: escolha o arquivo que tenha `hugo_extended` no nome.

Após baixar o arquivo `.deb`, acesse o terminal na pasta de Downloads e execute o código abaixo:

```bash
sudo dpkg -i nome_do_arquivo.deb
```

Para verificar se a instalação foi bem-sucedida:

```bash
hugo version
```

## Escolha e Personalização do Tema

Após a instalação do Hugo, vamos escolher um tema para o site. No site do Hugo podemos encontrar vários temas que podemos usar no site.

> Segue o link dos temas do GoHugo: https://themes.gohugo.io/

### hugo-theme-reimu

Para o meu site, escolhi o tema `hugo-theme-reimu`. É um tema que foi criado por [D-Sketon](https://github.com/D-Sketon). O tema é inspirado em Hakurei Reimu (personagem do Touhou Project) e combina elementos de outros temas populares: landscape, Tangyuxian e Shoka. Além disso, originalmente o tema foi criado para o framework [Hexo](https://hexo.io/pt-br/) e depois foi adaptado para Hugo.


> Segue o link do hugo-theme-reimu: https://themes.gohugo.io/themes/hugo-theme-reimu/

<img src="https://themes.gohugo.io/themes/hugo-theme-reimu/screenshot_hu_408a192743931e1e.webp"/>

O design é limpo e moderno, tem suporte multilíngue (implementação de i18n - internacionalização), é otimizado para Performance, é responsivo e possui um guia de customização bem explicado.

### Configurando o tema

Agora vamos fazer o fork do tema no GitHub. Para fazer isso, acesse o link abaixo e depois clique em Fork

> Segue o link do hugo-theme-reimu: https://github.com/D-Sketon/hugo-theme-reimu/tree/main

Após isso, podemos usar o GitHub Desktop para abrir o repertório do fork no computador.

Ao abrir a pasta no computador, veremos uma estrutura mais ou menos assim:

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

Assim como explicado na `README.md` do [tema](https://github.com/D-Sketon/hugo-theme-reimu/tree/main), vamos mudar o nome da pasta `_examples` para `content`. Agora vamos ver o que tem nesta pasta:


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

Observações:
- Em `archives/`, o arquivo `_index.md` é usado para exibir a página de arquivo, não pode ser omitido;
- Em `post/`, o arquivo `_index.md` é usado para evitar a geração de post/index.html, não pode ser omitido. Além disso, é nessa pasta que criaremos os artigos do site;
- O arquivo `about.md` é a página "sobre";
- O arquivo `friend.md` é a página de links de amigos. Como não farei uso dessa arquivo, então irei remover-lo.

Antes de começarmos a fazer a customização do site, vamos ver como o site está atualmente. Para fazer isso, primeiro abra o terminal na pasta principal e  execute o comando abaixo para iniciar o servidor local.

```bash
hugo server
```

O servidor será iniciado e abrirá o site no link: `http://localhost:1313`

Agora vamos para a customização. Vamos começar deixando o site em Português.

### Traduzindo o site para Português

Acesse o arquivo `config.toml` na pasta principal e adicione a seguinte configuração:

```bash
languageCode = 'pt-BR'
defaultContentLanguage = 'pt-BR'

[languages]
[languages.pt-BR]
languageName = 'Português (Brasil)'
weight = 1
```

Observações:
- `languageCode = 'pt-BR'`: define o código do idioma principal como Português Brasileiro;
- `defaultContentLanguage = 'pt-BR'`: define `pt-BR` como idioma padrão do conteúdo;
- `[languages.pt-BR]`: seção específica para configurações do Português Brasileiro;
- `languageName = 'Português (Brasil)'`: nome amigável do idioma (aparece no seletor de idiomas, se houver);
- `weight = 1`: prioridade do idioma (útil quando há múltiplos idiomas)

Isso não é suficiente para deixar o site totalmente em português, pois dentro da pasta `i18n/` não tem o arquivo `pt-BR.yml`, que é responsável pela tradução. Então vamos criar esse arquivo:
1. Acesse a pasta `i18n/`;
2. Faça uma cópia do arquivo `en.yml` e renomeie de `pt-BR.yml`;
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

Faça a tradução dos termos da esquerda e escreva do lado direito, deixando assim:

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

Observação: você pode fazer isso manualmente ou pode usar alguma LLM (ChatGPT, por exemplo) para auxiliar na tradução, é só copiar todo conteúdo do arquivo, cola na LLM e escreve

```bash
Estou criando um site usando o GoHugo. O conteúdo abaixo é do arquivo en.yml da pasta i18n, me ajude a criar o arquivo pt-BR.yml traduzindo o conteúdo.

<conteúdo do arquivo pt-BR.yml>
```

Após isso, é só conferir as traduções dadas pela LLM e cola no arquivo `pt-BR.yml`. Dessa forma, a maior parte do site estará em português. Vamos traduzir agora alguns textos específicos.

1. Acesse o arquivo `params.yml` que está na pasta `config/_default/`;
2. No arquivo você vai adicionar `pt-BR:+ "texto traduzido"` em algumas partes:

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

### Outras alterações que podem ser feitas

Os recursos estáticos do tema (favicon, imagens de cabeçalho, avatar, etc.) estão localizados na pasta `static`, basta apenas sobrescrever os arquivos da pasta com os arquivos que você deseja no site. Esses recursos estáticos também estão presentes no código do arquivo `params.yml`. 

#### Avatar

Em `params.yml`, podemos ver a linha responsável pelo avatar:

```yml
avatar: "avatar.webp"
```

#### Capa

A lógica de exibição da capa é a seguinte: se o Front matter (`cover`) do artigo contiver uma URL de capa, tanto o cabeçalho do artigo quanto a miniatura da página inicial exibirão essa URL

```markdown
---
title: Olá Mundo
cover: https://example.com
---
```

Se o Front matter do artigo contiver cover definido como `false`, o artigo não exibirá uma imagem de cabeçalho, mas a página inicial ainda mostrará imagens aleatórias, que são as imagens definidas no arquivo `covers.yml` da pasta `data`.

```markdown
---
title: Olá Mundo
cover: false
---
```

Se o Front matter do artigo contiver cover definido como `rgb(xxx,xxx,xxx)`, o cabeçalho do artigo será um gradiente dessa cor sólida (a página inicial ainda mostrará imagens aleatórias)

```markdown
---
title: Olá Mundo
cover: rgb(255,117,117)
---
```

Se nenhum dos arquivos acima existir, ele exibirá a imagem do banner.

Observação: para imagens de capa aleatórias, consulte a estrutura de arquivos em `data/covers.yml` do tema:

```yml
- https://example.com/1.jpg
- https://example.com/2.jpg
```

#### Banner

O banner é salvo em `static/images/banner.webp`. Você pode modificar o caminho e o nome em `params.yml`

```yml
banner: "images/banner.webp"
```

#### Favicon

O favicon é salvo em `static/favicon.ico`. Você pode substituí-lo pelo seu próprio arquivo.


#### Blocos de Código

Para garantir a exibição correta dos blocos de código, certifique-se de ter a seguinte configuração em `config.toml`.

```yml
[markup.highlight]
guessSyntax = true
noClasses = false
```

Os blocos de código também fornecem funcionalidade de cópia de código. Clique no botão de copiar no canto superior direito do bloco de código para copiar o código.


#### Pesquisa no Site

Com base em Algolia, adicione a seguinte configuração ao seu `config.toml`:

```yml
[outputs]
home = ["Algolia", "HTML", "RSS"]

[outputFormats.Algolia]
baseName = "algolia"
isPlainText = true
mediaType = "application/json"
notAlternative = true
```

Isso gerará um arquivo `algolia.json` na pasta `public/`, que é usado para a pesquisa Algolia. Você pode então usar plugins como atomic-algolia para fazer o upload para o Algolia.

Além disso, em `params.yml`, defina `algolia_search.enable` como `true` e preencha as informações relevantes (Importante! Insira a Chave Somente de Pesquisa aqui, NÃO a Chave de Administrador!! Caso contrário, sua conta pode estar vulnerável a ataques)

Em `params.yml`, podemos ver a linha responsável pelo algolia:

```yml
algolia_search:
  enable: true
```


tornar o video no youtube responsivo
link da documentação Markdown

ver o que mais eu posso adicionar baseado nesse texto:
https://d-sketon.github.io/en/20230707/hexo-theme-reimu-guide/




explicar sobre fazer alteração na configuração do repertório, alterando o nome para github.io e também configurando o action.