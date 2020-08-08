---
author:
  name: 'Hugo'
date: 2020-08-04
linktitle: LinuxMintDocker
title: LinuxにDockerをインストール
type:
  - post
  - posts
weight: 10
tags: ['hugo', 'docker', 'mint', 'linux']
slug: linuxdocker
series:
  - Hugo 101
aliases:
  - /blog/slug/
---

```
Get https://registry-1.docker.io/v2/: dial tcp: lookup registry-1.docker.io on 10.0.238.70:53: no such host
```

このエラーが出た際に今回の手順で再インストールして解決。

### 環境

> Linux Mint 20 Ulyana

### Docker のインストール

```
$ apt install docker.io docker-compose
$ sudo gpasswd -a $USER docker
$ service docker restart
```

一度ログアウトすれば docker, docker-compose コマンドが使えるようになる。
