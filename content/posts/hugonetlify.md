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
![](https://lh5.googleusercontent.com/tc7X6GsS-id_GSdc5bk6rmGkspu_00ZmnKo_QXzE6HEmvko0dt_8E5dVeRJ5jLkJuLMxZT5s6cRJTT6tsWdW0TwGrwmTAco0I3z3I4q7Xc6dFexILPM=w1280)

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
![](https://lh6.googleusercontent.com/BFzttJUuTQTX2fPHvp3d16ixShYT8fwTKGE-d_UBs4afvFtW5SpKJQBvyeifqbZ3WRiDoxt0mO9tZsZgZfEeNAVudIHQmeXVet48VOflBY3mkAM654AJ=w1280)
