---
title: "SpringBootConfig"
date: 2019-08-14T20:17:52+08:00
tags: ["java"]
---
#springboot启动读取外部配置文件

有时候项目打包成一个jar 或者war ,通过java -jar 命令运行springboot 项目，因为springboot 项目有自己的application.properties 配置文件，但是我们打完包之后，它也会打到包里边，倒是也能打开压缩包修改properties 文件，但是也是较为麻烦。
  现在有如下需求，比如客户需要在很多个服务器部署一套项目，但是它们的数据库连接不一样，我们不能针对于这么多服务器，多次打包，很恶心，当然可以打完包，复制一堆，分别修改压缩包里边的配置文件。


---
springboot 有读取外部配置文件的方法，如下优先级：
第一种是在jar包的同一目录下建一个config文件夹，然后把配置文件放到这个文件夹下。
第二种是直接把配置文件放到jar包的同级目录。
第三种在classpath下建一个config文件夹，然后把配置文件放进去。
第四种是在classpath下直接放配置文件。

如果内配置文件里有外配置文件没有的配置，那两者互补。比如外配置文件没有配置数据库，内配置文件里配置了数据库，那内配置文件的配置会被使用。
如果内配置文件里和外配置文件里都有相同的配置，比如两者都配置了数据库，但是两个连接的不同，那外配置文件会覆盖内配置文件里的配置。
