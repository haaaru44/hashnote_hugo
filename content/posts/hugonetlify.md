+++
categories = ["Hugo","Netlify"]
date = "2020-08-08"
description = "HugoNetlify"
linktitle = "hugoinstall"
title = "HugoとNetlifyでハマる"
slug = "HugoNetlify"
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
![](https://lh3.googleusercontent.com/kzb4lmiOpI3rDKh9xi9bvJ_pzRQCS-U5td93U5QDBBoTKDVgh2KqoOogUlpcOjj7V9iRgA)

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
![](https://lh4.googleusercontent.com/Qk2fzmZBQIRKxtHKg1ZjE6LaSVfanXSiF-KKoGR2L_iCfTULI3KokNN9Qk96AssnNS-S5IDrrbKJSTYDb9o8uUpJrrBLycAEO5U5bkY-Nyx3OSIsgR6e=w1280)
