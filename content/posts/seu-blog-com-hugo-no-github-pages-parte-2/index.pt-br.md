---
title: "Série: Seu Blog com Hugo no GitHub Pages (Parte 2)"
date: 2024-05-22T22:14:01-0300
draft: false
summary: "Como criar e hospedar seu blog usando hugo no github pages"
tags: ["GitHub Pages", "Hugo", "Blog"]
---
E aí, beleza? :grin:

No [primeiro post dessa série](/posts/seu-blog-com-hugo-no-github-pages-parte-1), eu te mostrei um pouco sobre como você pode criar o seu Blog usando o [Hugo](https://gohugo.io/).

Agora, vamos hospedar ele gratuitamente no [GitHub](https://github.com), através do [GitHub Pages](https://pages.github.com). Lembra que a gente fez um clone do seu repositório lá do GitHub? Pois então, depois que você fez todos as alterações necessárias e já fez seu primeiro post, vamos commitar tudo:
```
git add .
git commit -m 'Enviando tudo pro github'
git push
```

## Tá, fiz o que pediu, mas não vejo meu blog...
Calma, hahaha, você precisa pedir para o Hugo fazer o build dos seus arquivos e gerar, de fato, o html necessário para que seu blog apareça bonitão!

Digite:
```
hugo
```

Simples, né? esse comando vai analisar todo os arquivos markdown, e gerar todo o html do seu blog no diretório `public`.

Agora commite os novos arquivos e acesse: `https://<seu-usuario>.github.io/`

## Pronto!

Viu como é fácil? O GitHub Pages ainda permite que você utilize o seu próprio domínio para acessar o seu blog! Dá uma olhadinha na [documentação oficial](https://docs.github.com/pt/pages), com certeza lá vai ter muito mais opções além das que eu mostrei aqui!

Com isso, finalizamos a série! Obrigado pela sua leitura, se tiver qualquer dúvida, me chama ali nas redes sociais que eu tento te ajudar melhor!

Até!
