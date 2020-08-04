+++
categories = ["Hugo","Linux"]
date = "2020-08-03"
description = "HugoMacOs"
linktitle = ""
title = "hugoインストール(mac)"
slug = ["linux","docker","mint"]
tags = [
  "linux",
  "docker",
  "mint",
  "hugo",
  ]
type = "post"
+++

### 準備するもの

> [brew](https://brew.sh/index_ja)

### インストール

```
$ brew install hugo
```

### サイトを作る

適当なディレクトリで

```
$ hugo new site my_blog
$ cd my_blog
```

### テーマのインストール

> テーマは公式から
> [HUGO](https://themes.gohugo.io/)

### ローカルでテスト

```
$ hugo server -D
```

### 記事の作成

```
$ hugo new posts/markdown.md
```
