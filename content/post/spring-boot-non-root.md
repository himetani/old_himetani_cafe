+++
title = "非rootユーザでSpring Bootアプリをデーモンとして起動させる"
date = "2017-06-11T21:26:03+09:00"
tags = ['spring-boot']
+++

非rootユーザでSpring Bootアプリをデーモンを起動として起動させるためにやったことを書きました。

<!--more-->

# Spring Bootとは
- Springフレームワークをより手軽に使うことができるフレームワーク
- spring-boot-maven-pluginを使ってビルドすると、executable jarが作られる
- executable jarにはTomcatが組み込まれおり、jar直接実行することでWebアプリケーションを起動することができる

# executable Spring Boot
- 
