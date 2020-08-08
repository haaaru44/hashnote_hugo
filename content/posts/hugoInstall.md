+++
categories = ["Hugo","Linux"]
date = "2020-08-03"
description = "HugoMacOs"
linktitle = "hugoinstall"
title = "hugoインストール(mac)"
slug = "HugoInstall"
tags = [
  "linux",
  "docker",
  "mint",
  "hugo",
  ]
type = "post"
+++

> ### 準備するもの

ローカルでの立ち上げはこの 2 つ

- [brew](https://brew.sh/index_ja)
- [vscode](https://code.visualstudio.com/download)

さらに公開するには

- [GitHub アカウント](https://github.co.jp/)
- [Netlify アカウント](https://www.netlify.com/)
  > ### Hugo のインストール

```
$ brew install hugo
```

> ### Hugo のスタートアップサイトを作る

適当なディレクトリで
`hugo new site hugoblog`
を実行する

```
% hugo new site hugoblog
Congratulations! Your new Hugo site is created in /Users/haruharu/hugo/hugoblog.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```

これでスタートアップサイトの完成
「hugoblog」ディレクトリに移動してテーマをインストールしていきます

```
$ cd hugoblog
```

```
% tree
.
├── archetypes
│   └── default.md
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes
```

この時点でディレクトリの中身はこのようになっています

> ### テーマのインストール

テーマは公式から
[HUGO](https://themes.gohugo.io/)

今回は「aether」というシンプルなテーマを使用
![](https://lh3.googleusercontent.com/FMFhRnADI6ZPloe8QrM45Z77JcxVBZgCvShICujCwrcU_ARAjH6AcMQrWFdnJHrCCctZg9-lEeXQ2-Ogg8-uMTzMvPUUNeCIttFImbMHwq-tO0vUOUc=w1280)

テーマのページのインストール方法を参考に

```
git clone https://github.com/josephhutch/aether.git themes/aether
```

を実行

```
% git clone https://github.com/josephhutch/aether.git themes/aether
Cloning into 'themes/aether'...
remote: Enumerating objects: 81, done.
remote: Counting objects: 100% (81/81), done.
remote: Compressing objects: 100% (55/55), done.
remote: Total 1463 (delta 41), reused 54 (delta 21), pack-reused 1382
Receiving objects: 100% (1463/1463), 8.19 MiB | 1.31 MiB/s, done.
Resolving deltas: 100% (656/656), done.
```

これで「themes」ディレクトリ内にテーマをインストールできました

```
% tree -L 3
.
├── archetypes
│   └── default.md
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes
    └── aether
        ├── LICENSE.md
        ├── README.md
        ├── archetypes
        ├── assets
        ├── exampleSite
        ├── images
        ├── layouts
        ├── static
        └── theme.toml
```

インストールしたテーマ内の「examlreSite」の中身を全て「hugoblog」ディレクトリ直下にコピーします

![](https://lh5.googleusercontent.com/IC-SB9-r25nqxRm_LAyA3Eel7yKLA0sGTdsBM8jGKzcKUvwsDowIfo5oWDIuG3W7yZ11HDRc_SbeupGa_eLXgvggH2Iqn8wJ_IJ4H0EUfSiC1fIdDg=w1280)

「config.toml」を一部削除

```
baseurl = "http://example.org"
title = "Hugo Themes - aether"
author = "Joe Hutchinson"
canonifyurls = true
paginate = 3
theme = "aether"
themesDir = "themes/aether" #←ここを削除
```

> ### ローカルでテスト

```
$ hugo server -D
```

```
% hugo server -D

                   | EN
-------------------+-----
  Pages            | 35
  Paginator pages  |  7
  Non-page files   |  6
  Static files     | 73
  Processed images | 26
  Aliases          | 14
  Sitemaps         |  1
  Cleaned          |  0

Built in 545 ms
Watching for changes in /Users/haruharu/hugo/hugoblog/{archetypes,assets,content,data,layouts,static,themes}
Watching for config changes in /Users/haruharu/hugo/hugoblog/config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

これで localhost:1313 で無事立ち上がりました

![](https://lh3.googleusercontent.com/gx9iMFsnUYakwDhufUM3Fn5gBVZoLitb5m2bbuBDD0S5kGBNDJc6PUZNemPAHxn-9GnwP0au9NVSlnUexoLYX2V_kC1GvwVXDHZySDM99yB_skw6RXg=w1280)

> ### 記事の作成

```
$ hugo new posts/newpost.md
```

を実行
