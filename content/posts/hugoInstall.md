---
author:
  name: 'hash'
date: 2020-08-03
linktitle: hugoブログインストール
type:
  - post
  - posts
title: hugoブログインストール(mac)
weight: 10
series:
  - Hugo 101
---

## 準備するもの

brew
https://brew.sh/index_ja

##　インストール

```
$ brew install hugo
```

## サイトを作る

適当なディレクトリで

```
$ hugo new site my_blog
$ cd my_blog
```

## テーマのインストール

テーマは公式から
https://themes.gohugo.io/
かなり豊富にありますね。。

## ローカルでテスト

```
$ hugo server -D
```
