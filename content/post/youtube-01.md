---
title: 'Criando uma base de dados artificial (ChatGPT + Google Colab)'
description: "Inicialmente, a intenção do vídeo era que a própria IA gerasse uma base de dados, mas não deu muito certo, então tive que contornar essa situação pedindo para que o ChatGPT gerasse um script em Python."
#keywords: "meu,primeiro,artigo"

date: 2025-05-21T11:00:00-07:00
lastmod: 2025-05-21T11:00:00-07:00

math: false
mermaid: false

categories:
  - vídeos
tags:
  - vídeos
  - youtube

cover: https://raw.githubusercontent.com/cadu-sa/arquivos-site/refs/heads/main/record.png
---

# Criando uma base de dados artificial (ChatGPT + Google Colab)

<a href="https://www.youtube.com/watch?v=uTt1TX5ebiU" target="_blank" >Clique aqui para acessar o vídeo no YouTube</a>

<div class="video-container"> 
  <iframe 
    src="https://www.youtube.com/embed/uTt1TX5ebiU?si=gjYmeyjvhLT3iBfP" 
    title="YouTube video player" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
    referrerpolicy="strict-origin-when-cross-origin" 
    allowfullscreen>
  </iframe>
</div>


Inicialmente, a intenção do vídeo era que a própria IA (ChatGPT) gerasse uma base de dados, mas não deu muito certo, então tive que contornar essa situação pedindo para que o ChatGPT gerasse um script em Python.

Segue abaixo a parte escrita desse projeto.

## Introdução

Vamos criar uma base de dados artificial usando inteligência artificial, mas, antes disso, precisamos definir como será a base de dados.

### Base de Dados

O primeiro passo envolve a conceitualização da lanchonete fictícia, a definição das informações essenciais que serão incluídas na base de dados e a imposição de alguns critérios sobre os dados.


> **Contexto dos Dados:**
> 
> Vamos considerar que os dados são de uma lanchonete fictícia que atende apenas por delivery. E os dados são os registros de informações dos pedidos que foram realizados na lanchonete. Para esse contexto, não importa se o pedido foi feito por Whatsapp, Instagram ou aplicativo de delivery. 

Com esse contexto em mente, vamos usar uma IA para definir as informações que estarão presente na base de dados. 

Apesar de termos várias opções de IA para usar (ChatGPT, Claude, Gemini, Grok, etc), para esse projeto vamos usar o ChatGPT por ser o mais conhecido.

Segue o prompt usado:

```txt
Pretendo criar uma base de dados artificial de uma lanchonete que atende apenas por Delivery. 
Quais dados essa base de dados precisa ter?
```

O ChatGPT nos deu algumas sugestões de informações que poderemos adicionar na base de dados, vamos selecionar as opções que forem relevantes para a nossa base de dados. 

> **Informações que estarão na base de dados:**
> 
> - Código do pedido (identificador único)
> - Nome do cliente
> - Telefone
> - Endereço de entrega
> - Bairro
> - Data do pedido
> - Status do pedido (Entregue e Cancelado)
> - Forma de pagamento (Dinheiro, Pix, Crédito e Débito)
> - Valor do pedido
> - Tempo de entrega (em minutos)
> - Avaliação

Antes de pedir para a IA gerar a base de dados, vamos considerar alguns critérios sobre os dados.

> **Critérios Estabelecidos na Base de Dados:**
> 
> - A base de dados terá 50 pedidos
> - Os pedidos corresponderão ao mês de Maio de 2025
> - Alguns clientes fizeram mais de um pedido
> - Nem todos os clientes avaliaram

### Processo de Criação

Agora vamos escrever um prompt para o ChatGPT criar a base de dados. 

Segue o prompt usado:

```txt
Gere a base de dados seguindo os critérios:
- A base de dados terá 50 pedidos
- Os pedidos corresponderão ao mês de Maio de 2025
- Alguns clientes fizeram mais de um pedido
- Nem todos os clientes avaliaram

A base de dados deve ter as seguintes colunas:
- Código do pedido (identificador único)
- Nome do cliente
- Telefone
- Endereço de entrega
- Bairro
- Data do pedido
- Status do pedido (Entregue e Cancelado)
- Forma de pagamento (Dinheiro, Pix, Crédito e Débito)
- Valor do pedido
- Tempo de entrega (em minutos)
- Avaliação
```

Infelizmente, o ChatGPT não conseguiu gerar a base de dados tabular diretamente no formato desejado, mas ele deu como sugestão de usar a linguagem de programação Python para criar um script que gerasse essa base de dados. Então vamos mudar a nossa estratégia: vamos pedir para que o ChatGPT gere um script Python para realizar essa tarefa.

Segue o prompt usado:

```txt
Crie um código em Python para ser usado no Google Colab que gera essa base de dados
```

O ChatGPT retornou o script em Python. O script utiliza as bibliotecas `pandas`, para manipulação de dados e DataFrames, `random`, para gerar números aleatórios, e `Faker`, para gerar dados aleatórios realistas, como nomes, endereços, etc.

> Ao analisar o script, podemos ver que:
>
> - foi definido que terão 50 pedidos na base de dados, e 20 clientes (que garantirá as repetições);
> - tem duas listas de opções, uma para formas de pagamento e a outra para status do pedido;
> - usa o `Faker` para gerar nomes, telefones, endereços, bairros de forma aleatória;
> - usa o `random` para auxiliar na geração aleatória das datas, status, valores, tempos de entrega e avaliações;
> - faz estruturação dos dados em um `DataFrame` do `Pandas`.
> - salva o arquivo final no formato ".csv".

Com o código em mãos, vamos rodar ele no Google Colab, uma plataforma online que facilita a execução de notebooks Python sem necessidade de instalação local.

## Resultado Final

O script conseguiu gerar uma planilha no formato ".csv". Ao abrir a planilha no Google Planilhas, conseguimos ver que tem todas as informações que solicitamos.


## Conclusão

O processo demonstrou com sucesso a criação de uma base de dados artificial para uma lanchonete fictícia.

Apesar do ChatGPT não conseguir gerar a base de dados diretamente, conseguimos contornar isso pedindo para que ele gerasse um script na linguagem Python. Após gerar o script, fizemos uso do Google Colab para executar o script Python sem configurações locais.

A base de dados resultante está organizada e contém as informações definidas. Agora podemos fazer algumas análises em cima desses dados, mas isso fica para a próxima.