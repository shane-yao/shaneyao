---
title: 威联通NAS(QNAS)的DDNS域名在国内部分地区解析失败以及解决办法
author: shane
date: 2024-06-16T08:30:39+00:00
aliases: /2024/06/16/威联通nasqnas的ddns域名在国内部分地区解析失败以及解/
categories:
  - HomeLab
---

大概在半年前，发现手机的Joplin无法同步QNAS中的笔记。一顿排查后居然是5G的网络用的DNS服务器202.96.128.166和202.96.128.86这两个解析*.myqnapcloud.com失败，全部返回127.0.0.1，详情看[这里][1]。

保障到中国电信，反馈该域名没有在白名单中，需要域名的拥有者申请。遂联络QNAP的HelpDesk，客服反馈很积极，但是由于这个只有部分地区有问题，而且他们也不清楚电信那边具体要做什么。他只能建议我用中国区的域名，问题是最近中国区的域名也不是很稳定，解析从myqnapcloud.cn切换到mycloudnas.com了。最后只能放弃。

直到今天看到cloudlink的app更新了，看了一眼CL，其中有一条:

<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
  <p>
    Added support for adding 3 DDNS alias names using mycloudnas.com.
  </p>
</blockquote>

是不是全球的也可以用mycloudnas.com这个域名了？加了一下别名，还真的生效了，而且电信也能正确解析了，而且let&#8217;s encrypt 的证书也支持两个别名，困扰半年的问题终于解决了。PS：反代也需要重新更新一下证书（重启就行）。

 [1]: https://v2ex.com/t/997330