---
author:
  name: 'Hugo'
date: 2020-08-08
linktitle: hugoinstall
title: HugoとNetlifyでハマる
type:
  - post
  - posts
weight: 10
tags: ['hugo', 'netlify', 'markdown']
series:
  - Hugo 101
aliases:
  - /blog/mdtitle/
---

> ### デプロイでハマったところのメモ

- テーマが反映されない
- CSS が反映されない

> #### テーマが反映されない

themes 下にテーマをインストールする際、、

```
git clone git@github.com:themefisher/parsa-hugo.git
```

これでも local では大丈夫ですが Netlify デプロイの際にハマる

```
git submodule add git@github.com:themefisher/parsa-hugo.git
```

で解決

> #### CSS が反映されない

config.toml

```
# default config
baseURL = "https://examplesite.org"
languageCode = "ja"
title = "Parsa Hugo | Personal Blog Template"
theme = "parsa-hugo"
summaryLength = "10"
paginate = 6

```

local では大丈夫ですが
Netlify デプロイでは「baseURL」をデフォルトではこのように CSS が反映されていない
![](https://friendly-galileo-52e802.netlify.app/images/img02.jpg)

```
# default config
baseURL = "https://boring-colden-6acf01.netlify.app"
languageCode = "ja"
title = "Parsa Hugo | Personal Blog Template"
theme = "parsa-hugo"
summaryLength = "10"
paginate = 6
```

公開用の URL に変更して解決
![](https://friendly-galileo-52e802.netlify.app/images/img03.jpg)
