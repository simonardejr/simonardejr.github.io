---
title: "Série: Seu Blog com Hugo no GitHub Pages (Parte 1)"
date: 2024-05-22T20:49:01-0300
draft: false
summary: "Como criar e hospedar seu blog usando hugo no github pages"
tags: ["GitHub Pages", "Hugo", "Blog"]
---
E aí, beleza? :grin:

Existem várias maneiras (e ferramentas) para você criar o seu blog. Nesse primeiro post vou te mostrar como você pode usar o [Hugo](https://gohugo.io/) para criar o seu e, na segunda parte, como hospedá-lo gratuitamente no [GitHub](https://github.com/), como fiz com este aqui.

## Tá, mas o que é o Hugo?
Ele é um gerador de páginas estáticas open-source escrito em Go, é bem fexível, possui algumas centenas de temas prontos para uso e está entre os mais populares do tipo.

## Beleza, vamos começar!
Primeiro, você precisa de uma conta no GitHub, se ainda não tem a sua, vai lá criar, eu te espero!

Pronto? Criou sua conta? Então agora crie um novo repositório com o nome `<seu_usuario>.github.io` (lembre de trocar para o seu usuário).

{{< alert >}}
**Importante!** os comandos que você vai ver a seguir foram executados no Debian e devem servir na maioria das distros baseadas nele.
{{< /alert >}}

## Faça o clone do seu repositório
Escolha um diretório na sua máquina e digite:
```bash
git clone git@github.com:seu_usuario/seu_usuario.github.io.git
```
e depois:
```bash
cd seu_usuario.github.io
```

## Instale o Hugo
Digite no seu terminal o seguinte comando:
```bash
sudo apt install hugo
```
Caso o gerenciador de pacotes da sua distro não seja o apt, na [documentação oficial](https://gohugo.io/installation/) existem outros métodos de instalação, dá uma olhada lá :wink:

Verifique se foi instalado corretamente com `hugo version`.
{{< alert >}}
Para seguir o restante desse tutorial, Você precisa ter pelo menos a versão v0.112.0.
{{</ alert >}}

## Criando seu blog
Agora vamos usar o Hugo para criar, de fato, a estrutura do seu blog, digte os comandos abaixo dentro do diretório que acabou de clonar no primeiro passo e fique tranquilo, vou te explicar o que cada um vai fazer logo mais:
```bash
hugo new site . --force
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```
Deixa eu te explicar os comandos.

1) **hugo new site . --force**: esse comando vai criar todas os diretórios e arquivos de configurações necessários. O *--force* é importante porque você você tá criando em um diretório que não tá vazio, e ele, como o próprio nome já diz, vai forçar a criação mesmo assim.
2) **git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke**: aqui você tá adicionando o tema do seu blog no submodules do git e fazendo o clone para o diretório `themes/ananke`. O Hugo tem algumas centenas de temas prontos, dá uma olhada na [galeria](https://themes.gohugo.io/).
3) **echo "theme = 'ananke' >> hugo.toml"**: esse comando diz pro Hugo qual que é o tema que você vai usar.
4) **hugo server**: aqui vamos iniciar o servidor de testes do Hugo. Você deve ver a mensagem `Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)`. Abra essa url no seu navegador. Você deve ver algo semelhante à imagem a abaixo.

{{< figure src="images/hugo_first_screen.png" title="Hugo Homepage" >}}

Pronto! A primeira parte acabou! Agora vamos escrever o seu primeiro post! 

Aperte `Ctrl + C` para parar o servidor e siga em frente.

## Criando o seu primeiro post
Para criar seu primeiro post é muito fácil, olha só:
```bash
hugo new content posts/my-first-post.md
```
Esse comando vai criar o arquivo `my-first-post.md` dentro de `contents/posts`. o Hugo usa markdown para formatar o texto,  abre ele para dar uma olhada, você deve ter algo parecido com isso:
```md
+++
title = 'My First Post'
date = 2024-05-22T22:57:42-03:00
draft = true
+++
```
Esses são os metadados do seu post, é o que o Hugo vai usar para saber o que é cada coisa no seu post. Muda aquele `draft = true` para `draft = false` e roda o servidor de novo, você deve ver seu post como na imagem abaixo.

{{< figure src="images/hugo_second_screen.png" title="First Post" >}}

Viu como o Hugo facilita muito? :wink:

Agora escreve seu primeiro post logo após o segundo `+++` e salva o arquivo.
```md
+++
title = 'My First Post'
date = 2024-05-22T22:57:42-03:00
draft = false
+++
## Olá Mundo!

Esse é o meu primeiro post usando [Hugo](https://gohugo.io)!

Olha que incrível!
```

## Configurando o seu blog
Agora vamos mudar algumas coisas. Abra o arquivo `hugo.toml`
e altere a seu critério:
```
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'Meu Blog Incrível!'
theme = 'ananke'

[params]
  author = "Seu Nome"
  description = "Pensamentos e Devaneios"

[[params.ananke_socials]]
  name = "twitter"
  url = "https://twitter.com/GoHugoIO"
```
Salve e roda o servidor novamente, você deve ver todas as alterações que fez até agora. Algumas dessas opções variam de acordo com o tema que você estiver utilizando.

## Finalizando
Nesse post você viu como usar o Hugo para criar rapidamente o seu blog/site, mas isso é só a pontinha do iceberg, o Hugo oferece muito mais coisas do que eu mostrei aqui, dá uma olhada na [documentação oficial](https://gohugo.io/documentation/), com certeza você vai achar alguma opção que eu não mostrei aqui e, se precisar de ajuda com alguma coisa, me chama nas redes sociais que eu tento te ajudar melhor :wink:

Até a parte 2 desse tutorial!


<small>Imagem no background por [Bram Naus](https://unsplash.com/@bramnaus?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) no [Unsplash](https://unsplash.com/photos/silver-macbook-beside-space-gray-iphone-6-and-clear-drinking-glass-on-brown-wooden-top-n8Qb1ZAkK88?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)</small>

