---
author:
  name: "hash"
title: Dockerインストール(Linux)
linktitle: Dockerインストール(Linux)
date: 2020-08-04T16:19:46+09:00
type:
  - post
  - posts
draft: true
toc: false
weight: 10
images:
slug = "linux docker mint"
series:
  - Hugo 101
tags:
  - untagged
---

# Linux に Docker インストール

```
Get https://registry-1.docker.io/v2/: dial tcp: lookup registry-1.docker.io on 10.0.238.70:53: no such host
```

このエラーが出た際に今回の手順で再インストールして解決。

### 環境

> Linux Mint 20 Ulyana

### Docker のインストール

```
apt install docker.io docker-compose
sudo gpasswd -a $USER docker
service docker restart
```

一度ログアウトすれば docker, docker-compose コマンドが使えるようになる。
