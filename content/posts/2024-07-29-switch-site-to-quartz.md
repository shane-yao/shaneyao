---
title: 从Jekyll切换到Quartz、Hugo作为静态网站生成器
date: 2024-07-29
aliases:
---
## 为什么要用Jekyll
Github集成，本地可以不用配置环境。Jekyll最早进入中文博客圈就是因为github默认使用Jekyll生成静态页面。
可以直接通过push 内容让github生成，本地不需要ruby环境。

## 为什么要迁移？
1. Ruby是原罪。
2. Jekyll基本比较少更新。
3. Jekyll的模板引擎Liquid稀烂。
4. Jekyll的主题TexT定制性也是受限。
5. GithubAction可以更加灵活支持其他SSG。
6. 无法本地预览可能会导致更多的Push。最终还是需要本地安装Ruby和Gems包。

## 为什么是Quartz和Hugo
1. Quartz和Hugo都是SSG，都能很方便的被GH Action支持
2. Quartz偏向知识片段、文章的共享（EverGreenNotes）。有点像Wiki，强调知识之间的连接。
3. Hugo更偏向传统的博客。虽然Quartz也可以用于博客内容分享，但毕竟博客内容比较散乱，跟Quartz的定位不一致，最终决定还是分离。
4. 目前来看Quartz可以和Hugo共享一个知识仓库，分开渲染。所以目前采取了这样一个组合。

## 更进一步
目前Quartz的域名在[这里](https://notes.shaneyao.com)，Hugo的域名在[这里](https://blog.shaneyao.com)。内容上是独立的，怎样将两者的内容整合呢。目前的想法是用Astro开发一个Dashboard之类的页面，部署在https://shaneyao.com。顺便把[国内Wordpress](https://yaozhixiang.com)内容也整合进来。这样的解法似乎还可以接受。