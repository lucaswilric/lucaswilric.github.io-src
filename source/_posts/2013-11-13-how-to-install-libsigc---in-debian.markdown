---
layout: post
title: How to install libsigc++-2.0 from source in Debian
tags: [debian, linux, libsigc++]
date: 2013-11-13 19:07:47 +1000
---
Don't.

Install this package instead:

```shell
apt-get install libsigc++-2.0
```

If you want to compile something that relies on libsigc++ then you should also install this one:

```shell
apt-get install libsigc++-2.0-dev
```

I hope that helps.

