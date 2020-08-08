+++
categories = ["Hugo","Netlify"]
date = "2020-08-03"
description = "HugoNetlify"
linktitle = "hugoinstall"
title = "HugoとNetlifyでハマる"
slug = "HugoNetlify"
images = ""
tags = [
  "linux",
  "netlify",
  "mint",
  "hugo",
  ]
type = "post"
+++

> ### デプロイでハマったところのメモ

- テーマが反映されない
- CSS が反映されない

> #### テーマが反映されない
>
> themes 下にテーマをインストールする際、、

```
git clone git@github.com:themefisher/parsa-hugo.git
```

これでも local では大丈夫ですが Netlify デプロイの際にハマる

```
git submodule add git@github.com:themefisher/parsa-hugo.git
```

で解決

> #### CSS が反映されない
>
> config.toml の baseURL をデフォルトでは

```
# default config
baseURL = "https://examplesite.org"
languageCode = "ja"
title = "Parsa Hugo | Personal Blog Template"
theme = "parsa-hugo"
summaryLength = "10"
paginate = 6

```
