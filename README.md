<div align = center>
  <a href="https://cadu-sa.github.io/" target="_blank">Meu Site</a>
  <p></p>
</div>

<img src="https://raw.githubusercontent.com/cadu-sa/arquivos-site/refs/heads/main/meu-site.png"/>
<div align = center>
  <h1>hugo-theme-reimu</h1>
  <img alt="versão" src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FD-Sketon%2Fhugo-theme-reimu%2Fraw%2Fmain%2Fpackage.json&query=%24.version&label=version">
  <img alt="Licença GitHub" src="https://img.shields.io/github/license/D-Sketon/hugo-theme-reimu">
  <p align="center">
  <p align="center">
  💘 Hakurei Reimu 💘
  </p>

[hugo-theme-reimu](https://d-sketon.github.io/hugo-theme-reimu)
</div>

Um tema Hugo no estilo Hakurei Reimu. Migrado de [hexo-theme-reimu](https://github.com/D-Sketon/hexo-theme-reimu).

---

| framework                    | repositório                                                         | versão                                                                                                                                                                                     | 
| ---------------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | 
| [Hexo](https://hexo.io/)     | [hexo-theme-reimu](https://github.com/D-Sketon/hexo-theme-reimu)   | <img alt="versão" src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FD-Sketon%2Fhexo-theme-reimu%2Fraw%2Fmain%2Fpackage.json&query=%24.version&label=version">  | 
| [Astro](https://astro.build) | [astro-theme-reimu](https://github.com/D-Sketon/astro-theme-reimu) | <img alt="versão" src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FD-Sketon%2Fastro-theme-reimu%2Fraw%2Fmain%2Fpackage.json&query=%24.version&label=version"> | 
| [Hugo](https://gohugo.io)    | [hugo-theme-reimu](https://github.com/D-Sketon/hugo-theme-reimu)   | <img alt="versão" src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FD-Sketon%2Fhugo-theme-reimu%2Fraw%2Fmain%2Fpackage.json&query=%24.version&label=version">  |

## Funcionalidades

### Funções Básicas

- ✨ Funcionalidade completa de blog
- 🔄 Compatível com Hugo 0.124.0+
- 📱 Layout responsivo
- 🌙 Suporte a modo escuro
- 🅰️ Suporte a i18n

### Código e Matemática

- 🖥️ Destaque e cópia de código
- ➗ Suporte a fórmulas matemáticas KaTeX / MathJax3
- 📊 Suporte a fluxogramas Mermaid

### Pesquisa e Comentários

- 🔍 Integração com pesquisa Algolia
- 💬 Suporte a múltiplos sistemas de comentários:
  - Valine
  - Waline
  - Twikoo
  - Gitalk
  - Giscus

### Estatísticas e Análises

- 📊 Estatísticas de leitura de artigos (Valine / Waline)
- 👥 Estatísticas de visitantes (Busuanzi)

### Mídia e Recursos Interativos

- 🎵 Suporte a reprodutor de música:
  - Aplayer
  - Meting
- 🖼️ Carregamento lento para imagens
- ⚡ Animações de carregamento
- 🖱️ Efeitos de mouse:
  - Efeitos de animação
  - Estilo de cursor Reimu
- 👾 Integração Live2D / Live2D-widgets

### Navegação e Estrutura

- 📑 Sumário (TOC)
- 🔄 Suporte a PJAX
- 🔧 Implementação de ServiceWorker
- 📰 Feed RSS

### Design e Personalização

- 🎨 Suporte a ícones:
  - Iconfont
  - FontAwesome
- 🔗 Shortcodes personalizados para:
  - Links internos
  - Links externos
  - Links de amigos
  - Mapa de calor
- 🎨 Adaptação dinâmica da cor do tema
- ©️ Declaração de direitos autorais do artigo
- 🌐 Configuração de fonte CDN personalizada / fonte local
- 📜 Família de fontes personalizada
- 🎨 Funcionalidade de cartão de compartilhamento

## Instalação

> Para iniciantes, você pode usar diretamente [hugo-reimu-template](https://github.com/D-Sketon/hugo-reimu-template). Você só precisa clonar o repositório e modificar a configuração para obter um blog básico!

### Método 1: Módulo Hugo (Recomendado)

Adequado para usuários familiarizados com o ecossistema Go, suporta gerenciamento de versão e atualizações automáticas.

```bash
hugo new site quickstart
cd quickstart
hugo mod init github.com/<seu-nome-de-usuario-github>/quickstart  # Substitua <seu-nome-de-usuario-github> pelo seu nome de usuário real do GitHub
echo 'theme = ["github.com/D-Sketon/hugo-theme-reimu"]' >> hugo.toml
hugo server
```

### Método 2: Submódulo Git

Adequado para usuários que preferem o gerenciamento manual das versões do tema.

```bash
hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/D-Sketon/hugo-theme-reimu.git themes/reimu
echo 'theme = "reimu"' >> hugo.toml
hugo server
```

Escolha o método de instalação que melhor lhe convier, e você pode começar a usar o **Hugo Theme Reimu** imediatamente!

## Uso

<details>
<summary>Criar Configuração</summary>

### Criando Configuração

#### Configuração do Tema

Crie uma pasta `_default` sob a pasta `config` externa, então copie o `config/_default/params.yml` de dentro do tema para a pasta `_default`. Este arquivo serve como o arquivo de configuração do tema onde você pode modificar as configurações do tema.

#### Configuração de Dados

Copie todos os arquivos da pasta `config/data/` do tema para a pasta `data` externa. Os arquivos nesta pasta são usados para configurar dados dentro do tema:

- `covers.yml` é usado para configurar imagens de capa aleatórias
- `friends.yml` é usado para configurar links de amigos
- `vendor.yml` é usado para configurar fontes CDN para bibliotecas de terceiros

#### Configuração de Recursos Estáticos

Os recursos estáticos do tema (favicon, imagens de cabeçalho, etc.) estão localizados na pasta `static`. Você pode criar pastas correspondentes na pasta `static` externa e copiar os arquivos de dentro do tema para as pastas externas para sobrescrever os arquivos padrão do tema.

> Em resumo, não é recomendado modificar arquivos diretamente dentro do tema. Em vez disso, crie pastas correspondentes no diretório externo e copie os arquivos do tema para lá para sobrescrever os arquivos padrão. Essa abordagem facilita as atualizações do tema.

</details>
<details>

<summary>Estrutura Básica</summary>

### Estrutura Básica

Para garantir a exibição correta, crie as pastas `archives` e `post` em `content` consultando `_example` (o `_index.md` dentro não pode ser omitido, e observe que o `draft` de `post` deve ser definido como `true`)

#### archives

- `_index.md` é usado para exibir a página de arquivo, não pode ser omitido

#### post

Crie artigos neste diretório, observe que artigos com `draft` definido como `true` não serão exibidos na página inicial

- `_index.md` é usado para evitar a geração de `post/index.html`, não pode ser omitido

#### about\.md

Página sobre

#### friend\.md

Página de links de amigos

</details>

<details>
<summary>Avatar, Capa, Banner e Favicon</summary>

### Avatar, Capa, Banner e Favicon

#### Avatar

O avatar deve ser salvo em `static/avatar/avatar.webp`. Você pode modificar o nome do arquivo em `params.yml`

```yaml
avatar: "avatar.webp"
```

#### Capa

Para imagens de capa aleatórias, consulte a estrutura de arquivos em `data/covers.yml` do tema. Crie um arquivo `covers.yml` na pasta `data` externa com o seguinte formato:

```yaml
- https://example.com/1.jpg
- https://example.com/2.jpg
```

A lógica de exibição da capa é a seguinte:

- Se o Front matter do artigo contiver uma URL de capa, tanto o cabeçalho do artigo quanto a miniatura da página inicial exibirão essa URL

```yaml
---
title: Olá Mundo
cover: https://example.com
---
```

- Se o Front matter do artigo contiver `cover` definido como `false`, o artigo não exibirá uma imagem de cabeçalho (a página inicial ainda mostrará imagens aleatórias)

```yaml
---
title: Olá Mundo
cover: false
---
```

- Se o Front matter do artigo contiver `cover` definido como `rgb(xxx,xxx,xxx)`, o cabeçalho do artigo será um gradiente dessa cor sólida (a página inicial ainda mostrará imagens aleatórias)

```yaml
---
title: Olá Mundo
cover: rgb(255,117,117)
---
```

- Caso contrário, ele procurará `covers.yml` na pasta `data` e selecionará aleatoriamente uma imagem
- Se nenhum dos arquivos acima existir, ele exibirá a imagem do banner

#### Banner

O banner é salvo em `themes/hugo-theme-reimu/static/images/banner.webp`. Você pode modificar o caminho e o nome em `params.yml`

```yaml
banner: "images/banner.webp"
```

#### Favicon

O favicon é salvo em `themes/hugo-theme-reimu/static/favicon.ico`. Você pode substituí-lo pelo seu próprio arquivo.

</details>
<details>
<summary>Blocos de Código</summary>

### Blocos de Código

Para garantir a exibição correta dos blocos de código, certifique-se de ter a seguinte configuração em `hugo.toml`

```toml
[markup.highlight]
guessSyntax = true
noClasses = false
```

Os blocos de código também fornecem funcionalidade de cópia de código. Clique no botão de copiar no canto superior direito do bloco de código para copiar o código. Você pode configurar a funcionalidade de cópia em `params.yml`.  
`success` é o prompt exibido quando a cópia é bem-sucedida, `fail` é o prompt exibido quando a cópia falha. Além disso, você pode configurar avisos de direitos autorais - quando o texto copiado exceder `count` caracteres, o aviso de direitos autorais será adicionado após o conteúdo copiado.

```yaml
clipboard:
  success:
    en: Cópia bem-sucedida (*^▽^*)
  fail:
    en: Cópia falhou (ﾟ⊿ﾟ)ﾂ
  copyright:
    enable: false
    count: 50 # O número de caracteres quando o aviso de direitos autorais é exibido
    license_type: by-nc-sa # https://creativecommons.org/licenses
```

v0.2.0 adicionou configuração para controlar o estado de expansão padrão dos blocos de código. `expand` pode ser definido como `true`, `false` ou um número - o número indica que os blocos de código serão recolhidos por padrão quando o número de linhas exceder esse valor.

```yaml
code_block:
  expand: true # true | false | número
```

</details>
<details>
<summary>Comentários do Site</summary>

### Comentários do Site

> Os comentários do site podem ser controlados individualmente para cada artigo usando `comments` no Front matter.  
> Quando `comments` for `false`, os comentários não serão exibidos. Quando for `true` ou não especificado, a exibição será determinada pela configuração `params.yml`.

> Suporte para múltiplos sistemas de comentários simultaneamente após a versão 0.8.0+

Configuração global do sistema de comentários:

```yaml
comment:
  title: # Título da caixa de comentários
    en: Deixe um comentário
  default: waline # Sistema de comentários padrão usado quando múltiplos estão habilitados
```

Se estiver usando [Valine](https://valine.js.org/)  
Consulte a documentação oficial para completar a configuração do `LeanCloud`, então defina `valine.enable` como `true` no `params.yml` interno e preencha seu `appId` e `appKey`

```yaml
valine:
  enable: true
  appId: "seu appId"
  appKey: "seu appKey"
```

Se estiver usando [Waline](https://waline.js.org/)  
Consulte a [documentação oficial](https://waline.js.org/guide/get-started/) para completar a configuração do `LeanCloud`, então defina `waline.enable` como `true` no `params.yml` interno e preencha sua `serverURL`

```yaml
waline:
  enable: true
  serverURL: "sua url do servidor"
  locale: {} # https://waline.js.org/guide/features/i18n.html#%E8%87%AA%E5%AE%9A%E4%B9%89%E8%AF%AD%E8%A8%80
  emoji:
    - https://unpkg.com/@waline/emojis@1.2.0/weibo
    - https://unpkg.com/@waline/emojis@1.2.0/alus
    - https://unpkg.com/@waline/emojis@1.2.0/bilibili
    - https://unpkg.com/@waline/emojis@1.2.0/qq
    - https://unpkg.com/@waline/emojis@1.2.0/tieba
    - https://unpkg.com/@waline/emojis@1.2.0/tw-emoji
  meta:
    - nick
    - mail
    - link
  requiredMeta:
    - nick
    - mail
  wordLimit: 0
  pageSize: 10
  pageview: true
```

Se estiver usando [twikoo](https://twikoo.js.org)  
Consulte a [documentação oficial](https://twikoo.js.org/quick-start.html) para completar a implantação do Tencent Cloud ou Vercel, então defina `twikoo.enable` como `true` no `params.yml` interno e preencha seu `envId`

```yml
twikoo:
  enable: true
  envId: # Ambiente Tencent Cloud preencha envId; Ambiente Vercel preencha o endereço (https://xxx.vercel.app)
  region:
```

Se estiver usando [giscus](https://giscus.app/)  
Consulte a documentação para completar a configuração do repositório, então defina `giscus.enable` como `true` no `params.yml` interno e preencha os dados correspondentes

```yml
giscus:
  enable: true
  repo: "seu repositório"
  repoId: "seu repoId"
  category: "sua categoria"
  categoryId: "seu categoryId"
  mapping: mapping
  strict: 0
  reactionsEnabled: 1
  emitMetadata: 0
  inputPosition: bottom
```

Se estiver usando [gitalk](https://gitalk.github.io/)  
Consulte a [documentação oficial](https://github.com/gitalk/gitalk?tab=readme-ov-file#usage) para completar a configuração do repositório, então defina `gitalk.enable` como `true` no `params.yml` interno e preencha os dados correspondentes

```yml
gitalk:
  enable: true
  clientID: "seu ID de cliente de aplicativo"
  clientSecret: "seu segredo de cliente de aplicativo"
  repo: "seu repositório"
  owner: "proprietário do repositório"
  admin: "proprietário e colaboradores do repositório"
  md5: false # Se deve usar md5 para criptografar o caminho
```

</details>
<details>
<summary>Pesquisa no Site</summary>

Com base em [Algolia](https://www.algolia.com/), adicione a seguinte configuração ao seu `hugo.toml` externo:

```toml
[outputs]
home = ["Algolia", "HTML", "RSS"]

[outputFormats.Algolia]
baseName = "algolia"
isPlainText = true
mediaType = "application/json"
notAlternative = true
```

Isso gerará um arquivo `algolia.json` na pasta `public`, que é usado para a pesquisa Algolia. Você pode então usar plugins como `atomic-algolia` para fazer o upload para o Algolia.

Além disso, em `params.yml`, defina `algolia_search.enable` como `true` e preencha as informações relevantes (**Importante! Insira a Chave Somente de Pesquisa aqui, NÃO a Chave de Administrador!! Caso contrário, sua conta pode estar vulnerável a ataques**)

```yaml
algolia_search:
  enable: true
```

</details>
<details>

<summary>Fórmulas Matemáticas</summary>

### Fórmulas Matemáticas

Primeiro, adicione a seguinte configuração ao seu `hugo.toml` externo:

```toml
[markup.goldmark.extensions.passthrough]
enable = true
delimiters.block = [["\\[", "\\]"], ["$$", "$$"]]
delimiters.inline = [["\\(", "\\)"], ["$", "$"]]
```

Em seguida, adicione `math: true` ao Front matter de qualquer artigo onde você deseja usar fórmulas matemáticas:

```yaml
---
math: true
---
```

> Nota: Não habilite KaTeX e MathJax3 simultaneamente

#### KaTex

Se estiver usando [KaTeX](https://github.com/KaTeX/KaTeX), defina `math.katex.enable` como `true` em `params.yml`:

```yaml
math:
  katex:
    enable: true
```

#### MathJax3

Se estiver usando [MathJax3](https://www.mathjax.org/), defina `math.mathjax.enable` como `true` em `params.yml`. Você pode adicionar configurações em `options` (já que o Hugo converte automaticamente as chaves de objeto para minúsculas, as configurações precisam ser colocadas em um array para evitar o comportamento padrão):

```yaml
math:
  mathjax:
    enable: true
    options: [{}]
```

</details>
<details>
<summary>Mermaid</summary>

### Mermaid

Os fluxogramas são baseados em [Mermaid](https://mermaid.js.org/#/). Adicione `mermaid: true` ao Front matter dos artigos onde você deseja usar fluxogramas:

```yaml
---
mermaid: true
---
```

</details>
<details>
<summary>RSS</summary>

### RSS

Você pode configurar o RSS em `params.yml`.

```yaml
rss:
  limit: 10 # O número de artigos recentes a serem exibidos, escreva -1 para exibir todos
  showFullContent: false # exibir conteúdo completo ou descrição
  showCopyright: false # Se verdadeiro, adicione direitos autorais ao final do artigo.
```

</details>

<details>
<summary>Ícone</summary>

### Ícone

Os ícones padrão usam o iconfont fornecido por este projeto:

```yml
icon_font: 4552607_0khxww3tj3q9
```

Se você quiser continuar usando os ícones do FontAwesome, defina `icon_font` como `false`. Isso usará a configuração correspondente do FontAwesome em `vendor.yml`:




```yml
fontawesome:
  high_priority:
    - src: webcache|@fortawesome/fontawesome-free@6.5.1/css/regular.min.css
      integrity: sha384-k5640LgghgAohDLPwSqVWa96yQwWouT6wsAL+J1g0CFJVITNKYkIh1XpPLYKQe7Y
    - src: webcache|@fortawesome/fontawesome-free@6.5.1/css/solid.min.css
      integrity: sha384-8yO/A/BtltnG0hDxdwmmkza8UAleyDoAD1FhXiH6rsOQQsCho1P6WZP9TpBBH3YP
  low_priority:
    - src: webcache|@fortawesome/fontawesome-free@6.5.1/css/brands.min.css
      integrity: sha384-/BRyRRN0wxxRgh/DAXU621go9pdoMHl6LFPiX5Pp8PZYZlKBQCDXj9X9DHx6LOud
    - src: webcache|@fortawesome/fontawesome-free@6.5.1/css/v5-font-face.min.css
      integrity: sha384-/mBKnLlGtog8q2qQrgugURRDV+iHWHAPvM5KulYXT1C2ErKOKkBI0vbff8ZPq7rL
    - src: webcache|@fortawesome/fontawesome-free@6.5.1/css/v4-font-face.min.css
      integrity: sha384-d2Yn1/9Iw78r3oqwk5B+EcpRcmepXR5LyhmRF2a+WoSe9mpRGvVk0ZviFwDGDOTO
```

</details>

<details>
<summary>Recursos estendidos</summary>

### Recursos estendidos

#### Modo Escuro

A configuração padrão é `auto`, que alterna automaticamente com base nas configurações do sistema do usuário. Pode ser definido como `true` ou `false` para alterar o estado padrão.

```yaml
dark_mode:
  # true significa que o modo escuro está habilitado por padrão
  # false significa que o modo escuro está desabilitado por padrão
  # auto significa que o modo escuro é alternado automaticamente de acordo com as configurações do sistema
  enable: auto # true | false | auto
```

#### Barra de Progresso Pace

Habilitado por padrão

```yaml
pace:
  enable: true
```

#### Firework

Habilitado por padrão

```yaml
firework:
  enable: true
```

Para configuração detalhada, verifique [mouse-firework](https://github.com/D-Sketon/mouse-firework)

#### PJAX

Desabilitado por padrão

```yaml
pjax:
  enable: false
```

> PJAX é para usuários que precisam de recursos SPA como reprodutores de música. No entanto, ainda é experimental e pode causar problemas como **scripts não executando**, **scripts executando várias vezes** ou **problemas de renderização de página**. Por favor, considere cuidadosamente!

#### ServiceWorker

Desabilitado por padrão

```yaml
service_worker:
  enable: false
```

#### Live2D

Desabilitado por padrão

```yaml
live2d:
  enable: false
  position: left # left | right
```

#### Live2D Widgets

Desabilitado por padrão

```yaml
live2d_widgets:
  enable: false
  position: left # left | right
```

#### Cursor Reimu

Habilitado por padrão

```yml
reimu_cursor: true
```

#### Banner Responsivo

Desabilitado por padrão. Quando habilitado e fornecido com tamanhos de imagem e media queries correspondentes, pode melhorar o LCP móvel em certa medida

```yml
banner_srcset:
enable: false
srcset:
  - src: "images/banner-600w.webp"
    media: "(max-width: 479px)"
  - src: "images/banner-800w.webp"
    media: "(max-width: 799px)"
  - src: "images/banner.webp"
    media: "(min-width: 800px)"
```

#### Aviso de Direitos Autorais do Artigo

Desabilitado por padrão

```yml
article_copyright:
  enable: false # Mostrar cartão de direitos autorais?
  content:
    author: # true | false Mostrar autor no cartão de direitos autorais?
    link: # true | false Mostrar link no cartão de direitos autorais?
    title: # true | false Mostrar título no cartão de direitos autorais?
    date: # true | false Mostrar data de criação no cartão de direitos autorais?
    updated: # true | false Mostrar data de atualização no cartão de direitos autorais?
    license: # true | false Mostrar licença no cartão de direitos autorais?
    license_type: by-nc-sa # https://creativecommons.org/licenses
```

Além disso, pode ser controlado através do front-matter do artigo, que tem prioridade sobre a configuração global

```yaml
---
copyright: true # Mostrar cartão de direitos autorais?
---
```

#### Quicklink

Habilitado por padrão. Quando habilitado, ele pré-carrega links enquanto os usuários permanecem na página, melhorando a experiência do usuário

```yaml
quicklink:
  enable: true
  timeout: 3000 # Tempo limite para quicklink
  priority: true # Se deve priorizar o carregamento da página
  ignores: [] # Ignorar o link especificado, suporta apenas string
```

#### Aviso de Desatualização

Desabilitado por padrão

```yaml
outdate:
  enable: false
  daysAgo: 180 # Quantos dias um artigo é considerado desatualizado
  message:
    en: Este artigo foi atualizado pela última vez em {time}. Observe que o conteúdo pode não ser mais aplicável.
```

#### Patrocínio

Desabilitado por padrão

```yaml
sponsor:
  enable: false # Mostrar códigos QR de patrocínio?
  tip: # Dica de patrocínio
    en: Compre-me um café
  icon:
    url: "../images/taichi.png" # Caminho do ícone do patrocinador relativo a css/main.css
    rotate: true # Girar ícone?
    mask: true # Usar imagem como máscara (mostrar apenas o contorno da imagem PNG)?
  qr:
    - name: Alipay # Nome do código QR
      src: "sponsor/alipay.jpg" # Exemplo de caminho do código QR em static/sponsor/alipay.jpg
```

Também pode ser controlado através do front-matter do artigo, que tem prioridade sobre a configuração global

```yaml
---
sponsor: true # Mostrar códigos QR de patrocínio?
---
```

#### Reprodutor de Música (v0.4.0+)

> Recomendado habilitar o PJAX primeiro, caso contrário o reprodutor pode pausar automaticamente

Usa Aplayer + Meting (opcional), desabilitado por padrão

##### Aplayer Puro

Defina `player.aplayer.enable` como `true` e configure `player.aplayer.options` de acordo com [Aplayer Docs](https://aplayer.js.org/#/home?id=options)

```yaml
player:
  aplayer:
    enable: true
    options:
      audio: [] # lista de áudio
      fixed:
      autoplay:
      loop:
      order:
      preload:
      volume:
      mutex:
      listFolded:
      lrcType:
```

##### Aplayer + Meting

Defina `player.aplayer.enable` e `player.meting.enable` como `true`. Configure `player.meting.options` de acordo com [Meting Docs](https://github.com/metowolf/MetingJS?tab=readme-ov-file#option) e `player.aplayer.options` para configuração do Aplayer

```yaml
player:
  aplayer:
    enable: true
    options:
      audio: [] # esta opção será sobrescrita por meting
      fixed:
      autoplay:
      loop:
      order:
      preload:
      volume:
      mutex:
      listFolded:
      lrcType:
  meting:
    enable: true
    meting_api: # api personalizada
    options:
      id:
      server:
      type:
      auto:
```

#### Link / Cartão de Compartilhamento (v0.5.0+)

Desabilitado por padrão, atualmente suporta `facebook`, `twitter`, `linkedin`, `reddit`, `weibo`, `qq`, `weixin`.

```yaml
share:
  # - facebook
  # - twitter
  # - linkedin
  # - reddit
  # - weibo
  # - qq
  # - weixin
```

Para `weixin`, ele gera um cartão de compartilhamento com código QR que pode ser salvo localmente e compartilhado no WeChat Moments (Nota: quando a capa do artigo tem problemas de cross-origin, html-to-image não consegue gerar corretamente cartões com imagens!)

#### Cartões de Categoria da Página Inicial (v0.6.0+)

Desabilitado por padrão. Quando habilitado, ele mostra cartões de categoria na página inicial como uma alternativa às categorias de widget

```yml
home_categories:
  enable: false # Mostrar cartões de categoria da página inicial?
  content:
    - categories: # Nome da categoria (string)
      cover: # Capa do cartão, usa capa aleatória se não especificado
    - categories:
      cover:
```

</details>

<details>
<summary>Shortcodes de Cartão Integrados</summary>

### Shortcodes de Cartão Integrados

#### Cartão friendLink

```yaml
{{< friendsLink >}}
```

Sem parâmetros, lê diretamente do arquivo `data/friends.yml`

#### postLinkCard - Cartão de Link Interno

```yaml
{{<postLinkCard path="?" cover="?" escape="?" >}}
```

O primeiro parâmetro é o `path` do artigo; o segundo parâmetro (opcional) é a imagem de capa mostrada no cartão - se definido como `auto`, ele usará automaticamente o `banner` do blog; o terceiro parâmetro (opcional, `true | false`) indica se o título do artigo deve ser escapado

#### externalLinkCard - Cartão de Link Externo

```yaml
{{<externalLinkCard title="?" link="?" cover="?">}}
```

O primeiro parâmetro é o título do artigo; o segundo parâmetro é o link externo para o artigo; o terceiro parâmetro (opcional) é a imagem de capa mostrada no cartão - se definido como `auto`, ele usará automaticamente a capa padrão

#### Cartão de Mapa de Calor - Mapa de Calor do Artigo (Recurso Experimental em v0.8.0+)

```yaml
{{< heatMapCard levelStandard="?" >}}
```

O primeiro parâmetro é o padrão de nível para o mapa de calor (classificado com base na contagem de palavras dos artigos), com o valor padrão sendo `"1000,5000,10000"`.

</details>

<details>
<summary>Personalizar tema</summary>

#### Adaptação Dinâmica da Cor do Tema (Recurso Experimental em v0.8.0+)

Desabilitado por padrão. Quando habilitado, ele gera dinamicamente as cores do tema com base na cor dominante da imagem do banner do artigo, seguindo as diretrizes de design do Material You do Google.

```yml
material_theme:
  enable: false # true | false
```

> Nota: Quando este recurso está habilitado, o atributo `crossorigin="anonymous"` será adicionado ao elemento `img` do banner para buscar a cor dominante da imagem. Certifique-se de que seu servidor de imagem suporte acesso cross-origin ou use um proxy de imagem de terceiros.

#### Personalização Manual das Cores do Tema

hugo-theme-reimu suporta a personalização das cores do tema através de variáveis CSS. Você pode personalizar as cores do seu tema modificando as variáveis CSS sob a pseudo-classe `:root`.

~~O arquivo de variáveis está localizado em `assets/css/_variables.scss`. Você pode encontrar todas as variáveis CSS lá, mas você só precisa modificar as variáveis sob essas pseudo-classes~~

v0.9.0 adicionou a configuração `internal_theme` para personalizar as cores do tema. Você pode alterar as cores do tema modificando a configuração `internal_theme` em `params.yml`. As cores padrão do tema são as seguintes:

```yaml
internal_theme:
  light:
    --red-0: "#ff0000"
    --red-1: "#ff5252"
    --red-2: "#ff7c7c"
    --red-3: "#ffafaf"
    --red-4: "#ffd0d0"
    --red-5: "#ffecec"
    --red-5-5: "#fff3f3"
    --red-6: "#fff7f7"
    --color-red-6-shadow: "rgba(255, 78, 78, 0.6)"
    --color-red-3-shadow: "rgba(255, 78, 78, 0.3)"

    --highlight-nav: "#e6e6e6"
    --highlight-scrollbar: "#d6d6d6"
    --highlight-background: "#f7f7f7"
    --highlight-current-line: "#dadada"
    --highlight-selection: "#e9e9e9"
    --highlight-foreground: "#4d4d4d"
    --highlight-comment: "#7d7d7d"
    --highlight-red: "#c8362b"
    --highlight-orange: "#b66014"
    --highlight-yellow: "#cb911d"
    --highlight-green: "#2ea52e"
    --highlight-aqua: "#479d9d"
    --highlight-blue: "#1973b8"
    --highlight-purple: "#7135ac"
  dark:
    --red-4: "rgba(255, 208, 208, 0.5)"
    --red-5: "rgba(255,228,228,0.15)"
    --red-5-5: "rgba(255,236,236,0.05)"
    --red-6: "rgba(255, 243, 243, 0.2)"

    --highlight-nav: "#2e353f"
    --highlight-scrollbar: "#454d59"
    --highlight-background: "#22272e"
    --highlight-current-line: "#393939"
    --highlight-selection: "#515151"
    --highlight-foreground: "#cccccc"
    --highlight-comment: "#999999"
    --highlight-red: "#f47067"
    --highlight-orange: "#f69d50"
    --highlight-yellow: "#ffcc66"
    --highlight-green: "#99cc99"
    --highlight-aqua: "#66cccc"
    --highlight-blue: "#54b6ff"
    --highlight-purple: "#dcbdfb"
```

#### Personalizar fonte do tema

Você pode definir fontes do Google através da seguinte configuração:

```yaml
# https://fonts.google.com/
font:
  enable: true # Habilitar Google Fonts
  article:
    - Mulish
    - Noto Serif SC
  code:
    # - Ubuntu Mono
    # - Source Code Pro
    # - JetBrains Mono
```

v0.2.0 adicionou a configuração `local_font` para definir fontes locais, que tem prioridade menor que as fontes do Google:

```yaml
local_font:
  article:
    - "-apple-system"
    - PingFang SC
    - Microsoft YaHei
    - sans-serif
  code:
    - Menlo
    - Monaco
    - Consolas
    - monospace
```

v0.9.0 adicionou a configuração `custom_font` para definir fontes personalizadas, que tem a maior prioridade:

```yaml
custom_font:
  enable: true
  article:
    - css: https://fontsapi.zeoseven.com/292/main/result.css # css da fonte
      name: LXGW WenKai # css da fonte
  code:
```

#### Personalizando Ícones

##### Ícones de Cabeçalho / Barra Lateral

A estrutura de configuração `menu` mudou na v0.1.0, permitindo que os usuários personalizem os ícones. Quando o ícone está vazio, ele usa o ícone Taichi por padrão. Você pode preencher um número hexadecimal para personalizar o ícone, suportando FontAwesome e icon font.

v0.10.2 o ícone suporta caminho de imagem, como `/avatar/avatar.webp`.

```yaml
menu:
  - name: home
    url: /
    icon: # Ícone Taichi padrão quando vazio
  - name: archives
    url: /archives
    icon: f0c1 # Você pode preencher um número hexadecimal para personalizar o ícone
  - name: about
    url: /about
    icon:
  - name: friend
    url: /friend
    icon:
```

##### Ícones de Rodapé / Voltar ao Topo / Patrocinador

v0.1.0 adicionou a configuração `icon` para `footer`, `top` e `sponsor` para personalizar os ícones.

- `url` é o caminho do ícone relativo a `css/main.css`, então você precisa subir um nível para encontrar a pasta de imagens.
- `rotate` determina se o ícone deve girar, o padrão é `true`.
- `mask` determina se a imagem deve ser usada como máscara (mostrando apenas o contorno da imagem PNG), o padrão é `true`.

```yaml
footer:
  icon:
    url: "../images/taichi.png" # Caminho relativo a css/main.css
    rotate: true
    mask: true

top:
  icon:
    url: "../images/taichi.png"
    rotate: true
    mask: true

sponsor:
  icon:
    url: "../images/taichi.png"
    rotate: true
    mask: true
```

##### Ícone de Carregamento

v0.1.0 adicionou a configuração `icon` para `preloader` para personalizar o ícone de carregamento. Quando o ícone está vazio, ele usa SVG inline por padrão (garantindo a velocidade de carregamento da primeira tela). Você pode inserir um link para personalizar o ícone de carregamento.

Não é recomendado usar ícones grandes para evitar afetar a velocidade de carregamento.

```yaml
preloader:
  enable: true
  text:
    en: Loading...
    pt-BR: Carregando...
  icon: # Padrão usa SVG inline quando vazio, você pode inserir um link como 
  rotate: true
```

##### Ícone de Âncora

v0.1.0 adicionou a configuração `anchor_icon` para personalizar os ícones de âncora. O padrão usa o ícone `#`. Você pode preencher um número hexadecimal para personalizar o ícone, suportando FontAwesome e icon font.

```yaml
anchor_icon: # Padrão usa o ícone # quando vazio
```

v0.11.0 `anchor_icon` suporta a passagem de `false` para ocultar o ícone de âncora

##### Ícone do Cursor (v0.5.0+)

v0.5.0 adicionou a configuração `reimu_cursor.cursor` para personalizar o ícone do cursor. Você pode preencher um caminho relativo a `css/main.css` para personalizar o ícone do cursor.

```yaml
reimu_cursor:
  enable: true
  cursor:
    default: ../images/cursor/reimu-cursor-default.png
    pointer: ../images/cursor/reimu-cursor-pointer.png
```

</details>

