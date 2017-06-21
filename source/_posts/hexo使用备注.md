---
title: hexo使用备注
date: 2017-06-11 17:50:20
description: hexo常用的命令行在这里备注
tags: 
- hexo
---



``` bash

$ cd ee07b577.github.io
$ hexo server [-port 3000 --static --log] // 启动本地服务
$ hexo generate --watch
$ hexo new test   //在source/_posts/ 中添加test.md文件
                  //网站配置相关修改_config.yml
$ hexo deploy  //刷新localhost:4000查看无误后部署

```



### 每次部署的步骤，可按以下三步来进行。

``` bash

hexo clean
hexo generate
hexo deploy

```

其他常用命令


``` bash
$ hexo render <file1> [file2] ...
$ hexo clean
$ hexo new"postName" #新建文章
$ hexo new page"pageName" #新建页面
$ hexo generate #生成静态页面至public目录
$ hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
$ hexo deploy #将.deploy目录部署到GitHub
$ hexo help # 查看帮助
$ hexo version #查看Hexo的版本

```

更多信息: [官网](https://hexo.io/)
