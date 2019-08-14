---
title: "Hugo 常用命令"
date: 2019-08-14T17:54:53+08:00
<!--draft: true-->
---

1.新建markdown

在项目目录中执行 hugo new XX.md 命令，会在 content 目录中创建这个 XX.md 文件。

```
hugo new about.md
```

2.启动 hugo 自带的服务器

在项目根目录下，通过 hugo server 命令可以使用 hugo 内置服务器调试预览博客。--theme 选项可以指定主题，--watch 选项可以在修改文件后自动刷新浏览器，--buildDrafts 包括标记为草稿（draft）的内容。

```
hugo server --theme=hugo-bootstrap --buildDrafts --watch

hugo server
```

3.发布

在使用hugo server -D预览网站无误后可正式发布网站到域名供大家浏览。将要发布的文章内draft改为false后执行命令
```
hugo
hugo --theme=yelee --baseUrl="http://luohengL.github.io/"
```
可看到根目录下多出/public文件夹出来，该文件夹的内容即Hugo生成的整个静态网站。最终我们需要把这些静态网站的文件部署到一个地方.

4.参数

 --bind="127.0.0.1"    服务监听IP地址；

  -p, --port=1313       服务监听端口；

  -w, --watch[=true]      监听站点目录，发现文件变更自动编译；

  -D, --buildDrafts     包括被标记为draft的文章；

  -E, --buildExpired    包括已过期的文章；

  -F, --buildFuture     包括将在未来发布的文章；

  -b, --baseURL="www.datals.com"  服务监听域名；

  --log[=false]:           开启日志；

  --logFile="/var/log/hugo.log":          log输出路径；

  -t, --theme=""          指定主题；

  -v, --verbose[=false]: 输出详细信息


