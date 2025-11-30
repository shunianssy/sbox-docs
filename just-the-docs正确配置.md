---
title: just-the-docs正确配置
layout: about
---

# just-the-docs正确配置

## just-the-docs-template在配置的时候经常出现各种问题，这里我总结了一下问题出现的地点

_config.yml
```yml
title: Sbox Docs # 这里要写你的标题
description: Sbox Docs # 这里是你的简介
remote_theme: just-the-docs/just-the-docs #注意一下原文写的是theme: just-the-docs，但实际上应该写成remote_theme: just-the-docs/just-the-docs，否则即使成功部署也会工作流报错

url: https://shunianssy.github.io/sbox-docs #这里是仓库名，记得更改用户名和仓库，记住一定要有仓库
aux_links:
  Template Repository: https://github.com/shunianssy/sbox-docs #这里是仓库地址
```

## 如果你不改"remote_theme: just-the-docs/just-the-docs"，就会出现以下报错：

```Github
build
 Logging at level: debug Configuration file: /github/workspace/./_config.yml Theme: just-the-docs github-pages 232 | Error: The just-the-docs theme could not be found.
```