---
author:
  name: 'Hugo'
date: 2020-08-08
linktitle: hugoinstall
title: 初心者向けhugoblogの作り方(mac)
type:
  - post
  - posts
weight: 10
tags: ['hugo', 'netlify', 'markdown', 'mac']
slug: install
series:
  - Hugo 101
aliases:
  - /blog/slug/
---

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

今回は「parsa-hugo」というシンプルなテーマを使用
![](https://friendly-galileo-52e802.netlify.app/images/img04.jpg)

ここで GitHub に New リポジトリを作成し init しておきます  
git clone でもインストールできますが Netlify にアップする際にハマるので git submodule を使います

```
git submodule add git@github.com:themefisher/parsa-hugo.git
```

を実行

```
% git submodule add git@github.com:themefisher/parsa-hugo.git                        (git)-[master]
Cloning into '/Users/haruharu/hugo/hugoblog/parsa-hugo'...
remote: Enumerating objects: 493, done.
remote: Total 493 (delta 0), reused 0 (delta 0), pack-reused 493
Receiving objects: 100% (493/493), 21.08 MiB | 5.83 MiB/s, done.
Resolving deltas: 100% (261/261), done.
```

これで「themes」ディレクトリ内にテーマをインストールできました

```
% tree -L 3                                                              (git)-[master]
.
├── README.md
├── archetypes
│   └── default.md
├── config.toml
├── content
│   └── about
│       └── _index.md
├── data
├── layouts
├── netlify.toml
├── resources
│   └── _gen
│       ├── assets
│       └── images
├── static
│   └── images
└── themes
    └── parsa-hugo
        ├── LICENSE
        ├── README.md
        ├── archetypes
        ├── assets
        ├── exampleSite
        ├── images
        ├── layouts
        ├── netlify.toml
        ├── static
        └── theme.toml
```

今回はテンプレートをそのまま使いたいのでインストールしたテーマ内の「examlreSite」の中身を全て「hugoblog」ディレクトリ直下にコピーします

![](https://friendly-galileo-52e802.netlify.app/images/img05.jpg)

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

![](https://friendly-galileo-52e802.netlify.app/images/img01.jpg)

> ### 記事の作成

```
$ hugo new posts/newpost.md
```

を実行

> ### 今回作成したサイトデモ

[demo](https://boring-colden-6acf01.netlify.app/)

[>#Hugo と Netlify でハマったこと](https://hashnote.biz/posts/2020/hugonetlify/)
