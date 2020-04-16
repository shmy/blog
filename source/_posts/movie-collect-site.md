---
title: 分享几个电影采集网站的接口和使用方式
date: 2020-04-16 16:53:44
categories: ["backend", "summaries"]
tags: ["nginx"]
---

## 注解

+ HTTPS （能够返回支持https的资源）
+ M3U8 （返回的视频格式为M3U8）
+ XML（接口通讯格式为XML）

## 最大资源网

> 接口地址：http://www.zdziyuan.com/inc/s_api_m3u8.php

特点：

- [x] HTTPS
- [x] M3U8
- [x] XML

## OK资源网

> 接口地址：https://api.iokzy.com/inc/ldg_feifei.php

特点：

- [x] HTTPS
- [x] M3U8
- [x] XML

## 永久资源网

> 接口地址：http://cj.yongjiuzyw.com/inc/ldg_feifei.php

特点：

- [x] HTTPS
- [x] M3U8
- [x] XML

## 最快资源

> 接口地址：http://cj.zuikzy.com/inc/ldg_feifei.php

特点：

- [ ] HTTPS
- [x] M3U8
- [x] XML

## 卧龙影视资源

> 接口地址：http://copyplus.cn/inc/s_api_ff_m3u8.php

特点：

- [x] HTTPS
- [x] M3U8
- [x] XML

## 135资源网

> 接口地址：http://cj.135zy.co/inc/ldg_feifei.php

特点：

- [ ] HTTPS
- [x] M3U8
- [x] XML

## 33uu 资源网

> 接口地址：http://cj.156zy.me/inc/ldg_feifei.php

特点：

- [ ] HTTPS
- [x] M3U8
- [x] XML

## 高清资源网

> 接口地址：http://cj.gaoqingzyw.com/inc/ldg_feifei.php

特点：

- [ ] HTTPS
- [x] M3U8
- [x] XML

## 使用方式

> 这些接口直接返回xml格式的数据，所以浏览器直接打开可能显示不正确，以下两种方式便于我们获得接口的响应

1. 我们可以在浏览器的network里直接获取`response`

![XM7BCde91vUasrW](https://i.loli.net/2020/04/16/XM7BCde91vUasrW.png)

2. 我们打开终端

```bash
$ curl https://api.iokzy.com/inc/ldg_feifei.php -o list.xml
```

> 然后可以复制里面的内容
>
> 
>
> 接下来，我们找个XML美化的在线工具（例如：https://tool.oschina.net/codeformat/xml），美化结果如下：

```xml
<?xml version="1.0" encoding="utf-8"?>

<rss version="5.1">
  <list page="1" pagecount="1237" pagesize="40" recordcount="49474">
    <video>
      <last>2020-04-16 16:10:54</last>
      <id>75609</id>
      <tid>3</tid>
      <name><![CDATA[娱乐新闻报道]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200415期]]></note>
    </video>
    <video>
      <last>2020-04-16 16:09:45</last>
      <id>83828</id>
      <tid>10</tid>
      <name><![CDATA[红色编织]]></name>
      <type>剧情片</type>
      <dt>m3u8</dt>
      <note><![CDATA[HD1280高清中字版]]></note>
    </video>
    <video>
      <last>2020-04-16 16:07:48</last>
      <id>83826</id>
      <tid>10</tid>
      <name><![CDATA[破神录]]></name>
      <type>剧情片</type>
      <dt>m3u8</dt>
      <note><![CDATA[HD1280高清国语中字版]]></note>
    </video>
    <video>
      <last>2020-04-16 16:06:29</last>
      <id>83827</id>
      <tid>6</tid>
      <name><![CDATA[英勇废柴]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD1280高清中字版]]></note>
    </video>
    <video>
      <last>2020-04-16 15:33:28</last>
      <id>82769</id>
      <tid>3</tid>
      <name><![CDATA[跟我走吧朋友]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200416期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:33:15</last>
      <id>82561</id>
      <tid>15</tid>
      <name><![CDATA[塔科马消防队第二季]]></name>
      <type>欧美剧</type>
      <dt>m3u8</dt>
      <note><![CDATA[更新至03集]]></note>
    </video>
    <video>
      <last>2020-04-16 15:32:39</last>
      <id>71616</id>
      <tid>3</tid>
      <name><![CDATA[十三邀第四季]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[更新到13集]]></note>
    </video>
    <video>
      <last>2020-04-16 15:12:15</last>
      <id>76054</id>
      <tid>3</tid>
      <name><![CDATA[全民星攻略[2020]]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200415期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:11:46</last>
      <id>82278</id>
      <tid>3</tid>
      <name><![CDATA[这事有影呒]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200415期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:10:41</last>
      <id>83667</id>
      <tid>3</tid>
      <name><![CDATA[脱口秀大会云海选]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200416期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:10:23</last>
      <id>74858</id>
      <tid>4</tid>
      <name><![CDATA[玻璃之唇]]></name>
      <type>动漫片</type>
      <dt>m3u8</dt>
      <note><![CDATA[13集全]]></note>
    </video>
    <video>
      <last>2020-04-16 15:09:45</last>
      <id>77096</id>
      <tid>3</tid>
      <name><![CDATA[医师好辣[2020]]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200415期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:09:28</last>
      <id>83332</id>
      <tid>20</tid>
      <name><![CDATA[什么都不做的出租先生]]></name>
      <type>日本剧</type>
      <dt>m3u8</dt>
      <note><![CDATA[更新到02集]]></note>
    </video>
    <video>
      <last>2020-04-16 15:09:12</last>
      <id>76520</id>
      <tid>3</tid>
      <name><![CDATA[请问今晚住谁家[2020]]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200415期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:08:47</last>
      <id>81143</id>
      <tid>3</tid>
      <name><![CDATA[刘在街头[2020]]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200415期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:08:06</last>
      <id>76136</id>
      <tid>3</tid>
      <name><![CDATA[妈妈好神[2020]]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200415期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:07:20</last>
      <id>76014</id>
      <tid>3</tid>
      <name><![CDATA[非常完美[2020]]]></name>
      <type>综艺片</type>
      <dt>m3u8</dt>
      <note><![CDATA[20200416期]]></note>
    </video>
    <video>
      <last>2020-04-16 15:02:44</last>
      <id>79103</id>
      <tid>15</tid>
      <name><![CDATA[终生第一季]]></name>
      <type>欧美剧</type>
      <dt>m3u8</dt>
      <note><![CDATA[更新到09集]]></note>
    </video>
    <video>
      <last>2020-04-16 14:59:48</last>
      <id>80526</id>
      <tid>13</tid>
      <name><![CDATA[谈判官粤语]]></name>
      <type>香港剧</type>
      <dt>m3u8</dt>
      <note><![CDATA[更新到33集]]></note>
    </video>
    <video>
      <last>2020-04-16 14:59:13</last>
      <id>75566</id>
      <tid>13</tid>
      <name><![CDATA[爱回家之开心速递国语]]></name>
      <type>香港剧</type>
      <dt>m3u8</dt>
      <note><![CDATA[更新到847集]]></note>
    </video>
    <video>
      <last>2020-04-16 14:58:31</last>
      <id>83387</id>
      <tid>13</tid>
      <name><![CDATA[载得有情人粤语]]></name>
      <type>香港剧</type>
      <dt>m3u8</dt>
      <note><![CDATA[更新到05集]]></note>
    </video>
    <video>
      <last>2020-04-16 14:22:59</last>
      <id>83825</id>
      <tid>6</tid>
      <name><![CDATA[废柴赌神]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[HD国语中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:21:18</last>
      <id>83824</id>
      <tid>6</tid>
      <name><![CDATA[非我吉日]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD1280高清德语中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:19:37</last>
      <id>83823</id>
      <tid>6</tid>
      <name><![CDATA[独角兽商店]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:17:50</last>
      <id>83822</id>
      <tid>6</tid>
      <name><![CDATA[都市浪人]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:16:13</last>
      <id>83821</id>
      <tid>11</tid>
      <name><![CDATA[德国往事]]></name>
      <type>战争片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:13:45</last>
      <id>83820</id>
      <tid>6</tid>
      <name><![CDATA[打拳架]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:11:56</last>
      <id>83819</id>
      <tid>6</tid>
      <name><![CDATA[丑陋的真相]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:10:14</last>
      <id>83818</id>
      <tid>6</tid>
      <name><![CDATA[超级神丁病]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD国语中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:08:25</last>
      <id>83817</id>
      <tid>10</tid>
      <name><![CDATA[不可抗力]]></name>
      <type>剧情片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD1280高清中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:07:34</last>
      <id>83816</id>
      <tid>15</tid>
      <name><![CDATA[最后一人第二季]]></name>
      <type>欧美剧</type>
      <dt>m3u8</dt>
      <note><![CDATA[18集全]]></note>
    </video>
    <video>
      <last>2020-04-16 14:04:50</last>
      <id>83815</id>
      <tid>6</tid>
      <name><![CDATA[保姆2015]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:02:19</last>
      <id>83814</id>
      <tid>6</tid>
      <name><![CDATA[绑架丁丁当]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD粤语中字]]></note>
    </video>
    <video>
      <last>2020-04-16 14:00:34</last>
      <id>83813</id>
      <tid>6</tid>
      <name><![CDATA[肮脏的周末]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD中字]]></note>
    </video>
    <video>
      <last>2020-04-16 13:58:17</last>
      <id>83812</id>
      <tid>6</tid>
      <name><![CDATA[101岁老人跷家去]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[HD中字]]></note>
    </video>
    <video>
      <last>2020-04-16 13:56:12</last>
      <id>83811</id>
      <tid>6</tid>
      <name><![CDATA[失眠男女]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD超清中字]]></note>
    </video>
    <video>
      <last>2020-04-16 13:54:28</last>
      <id>83810</id>
      <tid>6</tid>
      <name><![CDATA[顺风车]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD超清中字]]></note>
    </video>
    <video>
      <last>2020-04-16 13:52:39</last>
      <id>83809</id>
      <tid>6</tid>
      <name><![CDATA[一路有戏]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD超清中字]]></note>
    </video>
    <video>
      <last>2020-04-16 13:50:39</last>
      <id>83808</id>
      <tid>6</tid>
      <name><![CDATA[男人制造]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD超清中字]]></note>
    </video>
    <video>
      <last>2020-04-16 13:48:40</last>
      <id>83807</id>
      <tid>6</tid>
      <name><![CDATA[大内密探王二狗]]></name>
      <type>喜剧片</type>
      <dt>m3u8</dt>
      <note><![CDATA[BD超清中字]]></note>
    </video>
  </list>
  <class>
    <ty id="1">电影片</ty>
    <ty id="2">连续剧</ty>
    <ty id="3">综艺片</ty>
    <ty id="4">动漫片</ty>
    <ty id="5">动作片</ty>
    <ty id="6">喜剧片</ty>
    <ty id="7">爱情片</ty>
    <ty id="8">科幻片</ty>
    <ty id="9">恐怖片</ty>
    <ty id="10">剧情片</ty>
    <ty id="11">战争片</ty>
    <ty id="12">国产剧</ty>
    <ty id="13">香港剧</ty>
    <ty id="14">韩国剧</ty>
    <ty id="15">欧美剧</ty>
    <ty id="16">福利片</ty>
    <ty id="17">伦理片</ty>
    <ty id="18">音乐片</ty>
    <ty id="19">台湾剧</ty>
    <ty id="20">日本剧</ty>
    <ty id="21">海外剧</ty>
    <ty id="22">记录片</ty>
  </class>
</rss>

```



> 我们主要关注这个接口的`ty`标签，如`<ty id="6">喜剧片</ty>`， 其中`id`值为该分类的`ID`

> 然后我们给接口加上参数 https://api.iokzy.com/inc/ldg_feifei.php?ac=videolist&t=6&pg=1
>
> 其参数如下：

+ `ac`: `videolist`表示请求服务器直接返回视频详情，如播放地址，描述等
+ `t`: 表示分类ID，如果使用ID返回空内容，可能是ID错误或者这个ID是一个父ID,需要找他下面的分类的ID
+ `pg`: 请求第几页

> 返回如下：

```xml
<?xml version="1.0" encoding="utf-8"?>

<rss version="5.1">
  <list page="1" pagecount="87" pagesize="40" recordcount="3464">
    <video>
      <last>2018-03-14 10:41:44</last>
      <id>35</id>
      <tid>6</tid>
      <name><![CDATA[呆呆计划]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2018-03-14/201803141520964460.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语|粤语中字版]]></note>
      <actor><![CDATA[陈小春,邓家佳,汪东城,李凡秀,吴启华,张小觉,徐鸥仪,朴文熙,郭云飞,卢晋杰,单宝中,何军,朱丹青]]></actor>
      <director><![CDATA[森岛]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语中字版$https://haoa.haozuida.com/20180314/q6d1OR8u/index.m3u8$zuidam3u8#BD1280高清粤语中字版$https://haoa.haozuida.com/20180314/hiUvnwuT/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[郁郁不得志的赌场洗码仔梅大志（陈小春 饰）因妻子安静（邓家佳 饰）和萍水相逢的蜜月夫妇郝东东（汪东城 饰）与菓菓（张小觉 饰）而欠下了巨额赌债，又因为安静的姐姐安宁（徐鸥仪 饰）和她的学生仔仔，不慎卷入了一块价值连城的宝物龙凤镜的生死争夺中。与此同时，香港黑道富商白楚雄（吴启华 饰）、黑老大十三幺、济州岛韩国黑帮、好...<span class="intro-more hide">简介：郁郁不得志的赌场洗码仔梅大志（陈小春 饰）因妻子安静（邓家佳 饰）和萍水相逢的蜜月夫妇郝东东（汪东城 饰）与菓菓（张小觉 饰）而欠下了巨额赌债，又因为安静的姐姐安宁（徐鸥仪 饰）和她的学生仔仔，不慎卷入了一块价值连城的宝物龙凤镜的生死争夺中。与此同时，香港黑道富商白楚雄（吴启华 饰）、黑老大十三幺、济州岛韩国黑帮、好赌欠债的业余杀手车基范（李凡秀 饰）也纷纷加入到了命运的漩涡之中，众人开始了一场围绕龙凤镜的夺宝大战。深陷其中的众人将如何破局而出……]]></des>
    </video>
    <video>
      <last>2019-03-18 13:46:16</last>
      <id>44</id>
      <tid>6</tid>
      <name><![CDATA[分手专家]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2018-03-10/201803101520693133.png</pic>
      <lang/>
      <area>美国</area>
      <year>2004</year>
      <state>0</state>
      <note><![CDATA[BD高清中字]]></note>
      <actor><![CDATA[Amanda Crew,Ali Liebert]]></actor>
      <director><![CDATA[ Steve Woo]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清中字$https://hair.jingpin88.com/20171026/tPzoaskn/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[昆西·华生（杰米·福克斯 饰）是个不入流的小作家，最近却似乎倒了霉运，在与未婚妻海伦（碧安卡·劳森 饰）的订婚派对上，一个没留神就被未婚妻随便当做垃圾甩掉了。遭受这样的打击要比失恋痛苦十倍。接着莫名奇妙又被老板菲利普（彼特·麦尼科 饰）炒了鱿鱼，昆西简直无法再振作起来。郁闷和伤心下昆西把自己灌得烂醉，他只好拿起了自己的...<span class="intro-more hide">简介：昆西·华生（杰米·福克斯 饰）是个不入流的小作家，最近却似乎倒了霉运，在与未婚妻海伦（碧安卡·劳森 饰）的订婚派对上，一个没留神就被未婚妻随便当做垃圾甩掉了。遭受这样的打击要比失恋痛苦十倍。接着莫名奇妙又被老板菲利普（彼特·麦尼科 饰）炒了鱿鱼，昆西简直无法再振作起来。郁闷和伤心下昆西把自己灌得烂醉，他只好拿起了自己的笔，灵感突发竟写出了一本《分手手册》。这本书教那些被女友折磨的男人，怎样在被女友抛弃之前，先在15分钟甚至更短的时间内把女友甩掉。书刚刚出版就引起了轰动，成为了畅销书，被许多男人疯狂抢购，昆西也在一时之间成为了名人。</span>]]></des>
    </video>
    <video>
      <last>2017-09-05 21:03:10</last>
      <id>260</id>
      <tid>6</tid>
      <name><![CDATA[九条命]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892732930.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[BD1280高清中英双字版]]></note>
      <actor><![CDATA[凯文·史派西/珍妮弗·加纳/罗比·阿梅尔/]]></actor>
      <director><![CDATA[巴里·索南菲尔德]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中英双字版$https://leshi.cdn-zuyida.com/20170905/WQcjhDmJ/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[商业精英的汤姆·布兰德（凯文·史派西 饰）是彻头彻尾的工作狂，却时常忽视家庭与亲情。女儿生日这一天，因公迟到的他匆忙赶去宠物店，为女儿买了一只她喜欢的宠物猫，却被宠物店老板用魔法将他的躯体困在一只宠物猫体内。被困于宠物猫的汤姆大声呼救，然而这对于听不懂猫语的人类只是“喵喵”的叫声。这时沃肯出现在它的笼前，说自己是“猫...<span class="intro-more hide">简介：商业精英的汤姆·布兰德（凯文·史派西 饰）是彻头彻尾的工作狂，却时常忽视家庭与亲情。女儿生日这一天，因公迟到的他匆忙赶去宠物店，为女儿买了一只她喜欢的宠物猫，却被宠物店老板用魔法将他的躯体困在一只宠物猫体内。被困于宠物猫的汤姆大声呼救，然而这对于听不懂猫语的人类只是“喵喵”的叫声。这时沃肯出现在它的笼前，说自己是“猫语者”，但沃肯此次并非来救他，只是让他思考自己被变成猫的原因。绝望的汤姆惊呼“我讨厌猫”，却得知猫的生命很短暂，很有可能一辈子被困在这里，而回归原型的条件则是要做回一个称职的老公和父亲。随后便发生了一系列令人啼笑皆非的故事。]]></des>
    </video>
    <video>
      <last>2018-04-28 16:27:14</last>
      <id>285</id>
      <tid>6</tid>
      <name><![CDATA[特鲁曼]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892731560.jpg</pic>
      <lang/>
      <area>西班牙</area>
      <year>2015</year>
      <state>0</state>
      <note><![CDATA[BD1280高清中字版]]></note>
      <actor><![CDATA[里卡杜·达林/贾维尔·卡马拉/多洛莉丝·房兹/]]></actor>
      <director><![CDATA[塞斯科·盖]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中字版$https://haoa.haozuida.com/20180428/QoODRLLf/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[胡利安（里卡杜·达林 饰）身患绝症，只剩下一个月的生命，于是他做出了放弃化疗的决定。胡利安是个剧场演员，因为身体原因遭到了炒鱿鱼。和妻子在加拿大生活的托马斯（贾维尔·卡马拉 饰）是胡利安的挚友，听到这些消息后他回到了已经离开几十年的家乡，希望能够打消胡利安放弃治疗的念头，然而最终改变想法的人是托马斯。托马斯决定在最...<span class="intro-more hide">简介：胡利安（里卡杜·达林 饰）身患绝症，只剩下一个月的生命，于是他做出了放弃化疗的决定。胡利安是个剧场演员，因为身体原因遭到了炒鱿鱼。和妻子在加拿大生活的托马斯（贾维尔·卡马拉 饰）是胡利安的挚友，听到这些消息后他回到了已经离开几十年的家乡，希望能够打消胡利安放弃治疗的念头，然而最终改变想法的人是托马斯。托马斯决定在最后的日子里一直陪在胡利安身边，直到他生命的最后一刻。影片片名“特鲁曼”是胡利安养的斗牛犬的名字。]]></des>
    </video>
    <video>
      <last>2018-02-17 08:17:36</last>
      <id>1443</id>
      <tid>6</tid>
      <name><![CDATA[捉妖记]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892660159.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2015</year>
      <state>0</state>
      <note><![CDATA[HD1280高清国语中字版]]></note>
      <actor><![CDATA[白百何,井柏然,姜武,金燕玲,钟汉良,曾志伟,吴君如,汤唯,姚晨,闫妮,保剑锋,王栎鑫,郭晓东,李菁菁,田雨橙,张悦轩]]></actor>
      <director><![CDATA[许诚毅]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[HD1280高清国语中字版$https://haoa.haozuida.com/20180217/SU9mj1YW/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[不知何年，妖界大乱。新妖王对前代势力痛下杀手，更誓要对前妖后腹中的孩子斩尽杀绝。妖后一行躲避追杀来到地处大山深处的永宁村，偏巧遇到捉妖天师霍小岚（白百何 饰）和罗刚（姜武 饰）。一番混乱过后，妖后自知气数将尽，遂将妖蛋放入永宁村保长宋天荫（井柏然 饰）的腹中保存。是夜，小岚所属的天师堂掌门人葛千户（钟汉良 饰）率领手下血洗永宁村，天荫不得已随小岚逃亡。时机成熟，萝卜妖怪胡巴降生人间。在接下来的旅途中，小岚和天荫对彼此的了解不断加深，而胡巴也终于成为他们中间最不可割舍的重要存在。&nbsp;<br />　　战争仍在继续，人和妖的界限日渐模糊……]]></des>
    </video>
    <video>
      <last>2017-12-10 15:53:50</last>
      <id>1630</id>
      <tid>6</tid>
      <name><![CDATA[天生一对]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892660846.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>1998</year>
      <state>0</state>
      <note><![CDATA[BD1024高清中英双字版]]></note>
      <actor><![CDATA[琳赛·洛翰,丹尼斯·奎德,娜塔莎·理查德森,伊莲·亨德里克斯,丽萨·安·沃尔特,西蒙·坤茨,罗尼·斯蒂芬斯,玛姬·惠勒]]></actor>
      <director><![CDATA[南希·迈耶斯]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1024高清中英双字版$https://yiyi.55zuiday.com/20171209/F4glJhnv/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[安妮（琳赛·洛翰 Lindsay Lohan 饰）和荷莉（琳赛·露安 Lindsay Lohan 饰）两个小女孩在夏令营中相识。她们相貌惊人地相似，却非常合不来。十分偶然的，她们知道了对方原来是自己的孪生姐妹。&nbsp;<br />　　她们开始互相打听对方的生活，讨论自己的父母：他们在一个豪华的航海轮船上相遇，在旅途中就结了婚，然而最后却以感情破裂收场。因为这场离异，双胞胎姐妹一个被爸爸（丹尼斯·奎德 Dennis Quaid 饰）带到加州，生活在一个美丽的葡萄园；一个则被当婚纱设计师的妈妈（娜塔莎·理查德森 Natasha Richardson 饰）带到伦敦。两人因此从未谋面，甚至不知道彼此的存在。&nbsp;<br />　　得知了这个真相，两个调皮的小鬼开始谋划她们的计策：她们决定调换身份，到对方的家庭去生活。一切都进展顺利，直到父亲要再婚，姐妹俩对后母（伊莲·亨德里克斯 Elaine Hendrix 饰）的一场疯狂狙击大战开始了……&nbsp;<br />　　本片翻拍自1961年版美国电影《爸爸爱妈妈》。年仅11岁的琳赛·洛翰凭借在片中一人分饰两角的表演，荣获1999年美国“艺术新秀奖”最佳年轻女演员奖。]]></des>
    </video>
    <video>
      <last>2017-06-07 00:21:39</last>
      <id>1797</id>
      <tid>6</tid>
      <name><![CDATA[霹雳大喇叭]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892661402.jpg</pic>
      <lang/>
      <area>香港</area>
      <year>1986</year>
      <state>0</state>
      <note><![CDATA[正片]]></note>
      <actor><![CDATA[洪金宝/张学友/姜大卫/]]></actor>
      <director><![CDATA[刘观伟]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD$https://leshi.cdn-zuyida.com/20170606/pg7NNeQK/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[陈文俊（洪金宝 饰）和张定其（张学友 饰）只是警队中的无名小卒，却在机缘巧合之下被指派到神探（姜大卫 饰）手下助其侦破“千面人”之案。没想到，一场意外中神探不幸丧生，可是，心愿未了的他显然不愿就此归去，而是化为冤魂，缠上了陈文俊和张定其两人，要他们破案为自己报仇。 神探威胁陈文俊，若不帮他报仇，就要破坏他和女友乔娜（王祖贤 饰）之间的姻缘。经不住神探的死缠烂打和卑鄙威胁，个性胆小怕事的陈文俊只能答应下来。就这样，陈文俊和张定其开始了对案件的追查，在神探的暗中帮助下，他们最终将罪犯捉拿归案，陈文俊和乔娜亦有情人终成眷属。,陈文俊（洪金宝 饰）和张定其（张学友 饰）只是警队中的无名小卒，却在机缘巧合之下被指派到神探（姜大卫 饰）手下助其侦破“千面人”之案。没想到，一场意外中神探不幸丧生，可是，心愿未了的他显然不愿就此归去，而是化为冤魂，缠上了陈文俊和张定其两人，要...]]></des>
    </video>
    <video>
      <last>2018-04-29 19:44:15</last>
      <id>1971</id>
      <tid>6</tid>
      <name><![CDATA[刑警兄弟]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892661985.jpg</pic>
      <lang/>
      <area>香港</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语|粤语版]]></note>
      <actor><![CDATA[黄宗泽/金刚/徐子珊/]]></actor>
      <director><![CDATA[戚家基]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语版$https://leshi.cdn-zuyida.com/20180429/24372_6354d655/index.m3u8$zuidam3u8#BD1280高清粤语版$https://leshi.cdn-zuyida.com/20180429/24371_b99c533f/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[陈建飞（黄宗泽 饰）和仲尼（金刚 饰）是两个来自单亲家庭的年轻警员，同处一个警局，常常火星撞地球互相看不顺眼。在公被上司编排成一组互相监视，在私因彼此父母突然相恋结婚，也要住在同一屋檐下，为争宠争功，一家人闹出许多令人捧腹的笑话。陈建飞在一次调查兄弟刘晶（陈小春 饰）意外死亡的过程中，发现前任贝茜（方皓玟 饰）的老...<span class="intro-more hide">简介：陈建飞（黄宗泽 饰）和仲尼（金刚 饰）是两个来自单亲家庭的年轻警员，同处一个警局，常常火星撞地球互相看不顺眼。在公被上司编排成一组互相监视，在私因彼此父母突然相恋结婚，也要住在同一屋檐下，为争宠争功，一家人闹出许多令人捧腹的笑话。陈建飞在一次调查兄弟刘晶（陈小春 饰）意外死亡的过程中，发现前任贝茜（方皓玟 饰）的老板孔祥兴（林家栋 饰），可能是幕后黑手，并且涉及一桩大案。正当调查渐渐明朗之时，陈建飞却遭人追杀，牵连家人受伤。正义的仲尼为了救这个“哥哥”，放下成见，联手对付孔祥兴。一场正义与邪恶的斗争，翻天覆地，而这一斗，也让两兄弟的感情越来越深。]]></des>
    </video>
    <video>
      <last>2017-07-02 00:13:01</last>
      <id>2198</id>
      <tid>6</tid>
      <name><![CDATA[护士也疯狂]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892662754.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[HD1280高清国语中字版]]></note>
      <actor><![CDATA[张蓝艺/李雨阳/孙心娅/]]></actor>
      <director><![CDATA[姚雨鑫]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[HD1280高清国语中字版$https://leshi.cdn-zuyida.com/20170701/kTXiyW3w/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[影片《护士也疯狂》讲述护士李玲儿（张蓝艺 饰）阴差阳错与第二天要面试的整形医科主任文森（李雨阳 饰）意外的发生了关系，当二人在整形医院碰见时就注定了今后的不解之缘。与此同时，同在整形医科的李玲儿闺蜜也在为自己的爱情痛苦，作为其他人口中破坏别人家庭的“小三”，当看到自己爱人的妻子为挽留丈夫，不顾一切的想要改变自己的时...<span class="intro-more hide">简介：影片《护士也疯狂》讲述护士李玲儿（张蓝艺 饰）阴差阳错与第二天要面试的整形医科主任文森（李雨阳 饰）意外的发生了关系，当二人在整形医院碰见时就注定了今后的不解之缘。与此同时，同在整形医科的李玲儿闺蜜也在为自己的爱情痛苦，作为其他人口中破坏别人家庭的“小三”，当看到自己爱人的妻子为挽留丈夫，不顾一切的想要改变自己的时候，才知道真正的幸福不应如此，却在伤心时刻留意到幸福就在身边。外表看似冷漠的护士“男哥”心心念念的牵挂着身为老顾客的明星康东（李一鸣 饰），虽彼此误会过，却也因此明白了对方的心意，幸福的走在了一起。]]></des>
    </video>
    <video>
      <last>2018-04-29 19:48:33</last>
      <id>2667</id>
      <tid>6</tid>
      <name><![CDATA[我的个神啊]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148926642917.jpg</pic>
      <lang/>
      <area>印度</area>
      <year>2014</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语|原声版]]></note>
      <actor><![CDATA[阿米尔·汗/安努舒卡·莎玛/桑杰·达特/]]></actor>
      <director><![CDATA[拉吉库马尔·希拉尼]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中字版$https://leshi.cdn-zuyida.com/20180429/24373_c5faf6ba/index.m3u8$zuidam3u8#BD1280高清国语中字版$https://leshi.cdn-zuyida.com/20180429/24374_714cdb3a/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[<span style="color: rgb(17, 17, 17); font-family: Helvetica, Arial, sans-serif; line-height: 19.44px;">　　贾古（安努舒卡·莎玛 Anushka Sharma 饰）意外邂逅了名为萨弗拉兹（苏翔特·辛·拉哈普特 Sushant Singh Rajput 饰）的男子，趣味相投的两人很快走到了一起。然而，萨弗拉兹是巴基斯坦人，他的国籍和信仰令这段恋情遭到了贾古家人的极力反对。不仅如此，贾古父亲信仰的教主塔帕斯维（沙鲁巴·舒克拉 Saurabh Shukla 饰）更是预言萨弗拉兹注定要欺骗和抛弃贾古。为了证明预言的荒谬，贾古决定同萨弗拉兹闪婚，然而，婚礼当天，贾古等到的却是一封分手信。&nbsp;<br style="color: rgb(17, 17, 17); font-family: Helvetica, Arial, sans-serif; line-height: 19.44px;" /><span style="color: rgb(17, 17, 17); font-family: Helvetica, Arial, sans-serif; line-height: 19.44px;">　　心碎的贾古回到了家乡，成为了一名记者。一次偶然中，贾古遇见了名为PK（阿米尔·汗 Aamir Khan 饰）的男子，让贾古感到惊讶的是，PK竟然声称自己是一名外星人，因为宇宙飞船的钥匙被人抢走，所以流落至地球。刚开始，贾古以为PK在胡言乱语，不过，之后发生的种种令贾古开始相信PK所言，贾古甚至决定帮助PK寻找返回他的星球的方法。<br />]]></des>
    </video>
    <video>
      <last>2019-03-23 13:58:38</last>
      <id>3307</id>
      <tid>6</tid>
      <name><![CDATA[精武雄风]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2018-03-12/201803121520838116.png</pic>
      <lang/>
      <area>大陆</area>
      <year>2015</year>
      <state>0</state>
      <note><![CDATA[BD高清]]></note>
      <actor><![CDATA[龙武,广帅,竹子,凡凡]]></actor>
      <director><![CDATA[广帅]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清$https://hair.jingpin88.com/20171027/pm8g6ths/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[《精武雄风》是一部糅合了动作、喜剧、爱情、兄弟情、黑色幽默等多重元素的影片，影片展现了几个怀揣英雄梦想的屌丝在追梦的旅途历经磨难……这个时代是需要英雄的时代，但怀揣英雄梦的人又往往生活的很屌丝，虽然是屌丝，但在他们自己的圈子里却扮演着各自的英雄，所谓英雄不问出处……影片中也关注了很多社会问题，虽然是一笔带过，但是让大家感受到每一个细节的背后都有很多人在默默的‘绞尽脑汁’地为之付出着，很多桥段也是导演本人经历过的，也算是一种自我嘲讽，生活就是这麽无奈，但我们要坚持我们的梦“不忘初心、方得始终”。很多人看完电影可能说导演要表达的东西太多，其实不多，生活那么复杂，一部电影表达的只是冰山一角，我是想让大家能从影片中看到尽量多一点的有意义的信息；形式上可能也与以往的电影有所区别，这是我最想解释的一点，每个导演的创作立足点不同，创作形式各异，如果作品千篇一律也就失去了我创作的初衷，《精武雄风》注定是一部个性的电影，因为有一群个性的创作者为之不惜一切的付出着，感谢他们，他们个个都是英雄……影片表达了什么其实并不重要，重要的是你在观影的过程中感受到了什么！邀请了中国第一大力士龙武、国际武术冠军田雕侠、国际武术冠军竹子、还有众多武术界的资深人士，武戏部分几乎都是真打，演员的脸被打肿，手指踢断、肋骨骨折等等时有发生，每一位创作者为之付出的太多太多……影片武戏劲爆写实，是一部拳拳到肉的电影；影片喜剧笑点颇多，是一部开发快乐的电影；影片情节感人至深，是一部表达人性的电影；影片兄弟其利断金，是一部不忘初心的电影；影片大胆自我嘲讽，是一部黑色幽默的电影。]]></des>
    </video>
    <video>
      <last>2017-09-02 03:42:26</last>
      <id>3406</id>
      <tid>6</tid>
      <name><![CDATA[好鬼两个半]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148926659715.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[HD1280高清国语中字版]]></note>
      <actor><![CDATA[闫佩伦/杨杏]]></actor>
      <director><![CDATA[侯国涛]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[HD1280高清国语中字版$https://leshi.cdn-zuyida.com/20170901/w0vXmELf/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[冒牌“养鬼人”关耳（闫佩伦 饰）带着小僵尸钱米一路招摇撞骗，可谁知时运不济撞死了“养鬼师”美女白依（杨杏 饰），七日内必须带她去还魂。沿途他们俘获了来自英国的吸血鬼德古拉，庆幸之余却发现白依的肉身被拍电影的凶悍傀儡偷走。好不容易消灭了凶悍傀儡，却惹来了法力超强的邪恶“养鬼天师”，他正觊觎着白依那万里挑一的肉身，想要利用...<span class="intro-more hide">简介：冒牌“养鬼人”关耳（闫佩伦 饰）带着小僵尸钱米一路招摇撞骗，可谁知时运不济撞死了“养鬼师”美女白依（杨杏 饰），七日内必须带她去还魂。沿途他们俘获了来自英国的吸血鬼德古拉，庆幸之余却发现白依的肉身被拍电影的凶悍傀儡偷走。好不容易消灭了凶悍傀儡，却惹来了法力超强的邪恶“养鬼天师”，他正觊觎着白依那万里挑一的肉身，想要利用白依肉身炼成超强鬼魁。为了救回白依，就要打败天师，而要打败天师，关耳必须成为真正的“养鬼大师”。]]></des>
    </video>
    <video>
      <last>2019-03-24 09:47:05</last>
      <id>3768</id>
      <tid>6</tid>
      <name><![CDATA[我是大明星]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148926667116.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2015</year>
      <state>0</state>
      <note><![CDATA[ BD高清]]></note>
      <actor><![CDATA[刘波,腾飞,马瑞曼,谭皓]]></actor>
      <director><![CDATA[张艺飞]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清$https://hair.jingpin88.com/20171028/4AMcIfbg/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[江永建是电视台的一名保安，平时酷爱唱歌，每天看着进进出出一心想当明星的选秀歌手们，江永建也动了当明星的梦，时不时借用工作的便利跟电视台的工作人员套近乎，同时不忘天天跑到演播室门口偷看别人比赛取经。李光辉（高天 饰）是江永建的老乡，在电视台的家属小区当保安，江永建跟李光辉同时住在电视台家属楼的地下室，李光辉是一个老实巴交的人，最大的梦想就是当一回英雄，以后好跟未来的老婆显摆一下，所以没事晚上时不时在小区溜达，希望碰到一个小偷强盗之类的人，好脱离自己只是一个普通保安的名头。朱丽是电视台最漂亮的当家花旦，也是“我是大明星”当红选秀节目的女主持人，每天面对的不是一大堆溜须拍马的选手就是一大堆拿鲜花围着她的追求者，朱丽最大的梦想就是有一天能回归自然，做一天普通人，出门没有那么多人围着，不用天天装着笑脸迎合自己讨厌的赞助商。江永建除了每天巡逻外，还找借口跟朱丽套近乎，希望朱丽能帮自己参加选秀这个忙，让自己也能当明星，好脱离只是小保安的名头。]]></des>
    </video>
    <video>
      <last>2017-10-18 17:42:54</last>
      <id>3942</id>
      <tid>6</tid>
      <name><![CDATA[西游降魔篇]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148926670519.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2013</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语|粤语中字版]]></note>
      <actor><![CDATA[文章,舒淇,黄渤,罗志祥,李尚正,陈炳强,赵志凌,周秀娜,杨迪,释彦能,冯勉恒,谢晶晶,何文辉,唐艺昕,卢正雨,张煜雯,葛行于,张超理,程思寒]]></actor>
      <director><![CDATA[周星驰,郭子健]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语中字版$https://leshi.cdn-zuyida.com/20171018/yKlMfjjR/index.m3u8$zuidam3u8#BD1280高清粤语中字版$https://leshi.cdn-zuyida.com/20171018/9YjMU35d/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[大唐年间妖魔横行，一小渔村因为饱受鱼妖之害请来道士（冯勉恒 饰）除妖，年轻驱魔人陈玄奘（文章 饰）前来帮忙却被误认为骗子，幸亏职业赏金驱魔人段小姐（舒淇 饰）帮助玄奘制服了鱼妖真身（李尚正 饰）。二人又在高家庄为制服猪妖猪刚鬣（陈炳强 饰） 而再次相遇，这次除妖没有成功 ，但是段小姐却对玄奘二见钟情。玄奘求助师父，得知除妖的办法是去找被压在五指山下的孙悟空（黄渤 饰）帮忙，于是他准备前往五指山，途中又遇到段小姐和手下五煞，段小姐连蒙带哄想与玄奘在一起却屡次遭拒，在四妹（周秀娜 饰）调教下想变得更有女人味却适得其反。二人决裂后玄奘独自上路，与此同时降魔师（释延能 饰）、天残脚（张超理 饰）、空虚公子（罗志祥 饰）也一同前往除妖。经过千辛万苦玄奘终于找到孙悟空，段小姐又再次出现并交给玄奘一件重要的东西，猪妖终于被降服，但是更大的危机又出现在了玄奘面前，原来孙悟空与传闻中不一样，玄奘的除魔之路能否继续？&nbsp;<br />　　本片是周星驰多年之后的力作，演员阵容延续了以往，除了主演外，还请了诸如卢正雨、杨迪等网络红人加盟。]]></des>
    </video>
    <video>
      <last>2018-03-15 00:05:32</last>
      <id>4199</id>
      <tid>6</tid>
      <name><![CDATA[男二本色]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148926675810.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2015</year>
      <state>0</state>
      <note><![CDATA[BD高清]]></note>
      <actor><![CDATA[刘刚/邓炀/奚望/]]></actor>
      <director><![CDATA[陈之月]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清$https://hair.jingpin88.com/20171029/kTN0sAge/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[电影《男二本色》讲述了一群“傻傻的可爱的”男人遭遇的一系列啼笑皆非的“囧事”，不但昭示了“天公疼憨人，傻人有傻福” 这个简单朴实的道理，还在接地气的诙谐幽默中透着生活的辛酸与家庭温情，让人笑出声、流下泪，可谓是一部充满讽刺和戏剧性的黑色幽默电影，大有当年《疯狂的石头》的风范，显示出一定的黑马潜力。剧中的男主人公名叫“大...<span class="intro-more hide">简介：电影《男二本色》讲述了一群“傻傻的可爱的”男人遭遇的一系列啼笑皆非的“囧事”，不但昭示了“天公疼憨人，傻人有傻福” 这个简单朴实的道理，还在接地气的诙谐幽默中透着生活的辛酸与家庭温情，让人笑出声、流下泪，可谓是一部充满讽刺和戏剧性的黑色幽默电影，大有当年《疯狂的石头》的风范，显示出一定的黑马潜力。剧中的男主人公名叫“大楞”，性格也是人们口中的“愣头青”形象。大楞在剧中做起事来横冲直撞，为帮朋友甚至是陌生人都可以两肋插刀，所以经常因为做出一些违法的出格行为而受到惩罚。而且，只要是大楞认准的事情，任何人都无法劝其改变。在大楞心中，生活看起来就是非黑即白，他认为对的事情就是对的，错的事情就一定要尝试用自己的力量去改变。影片中最经典的桥段之一，就是当摔倒的老太太在路边无人管时，大楞不惜在路上用板砖抢了一辆汽车后将老太太送到医院。当然，因为抢车最后大楞没有逃脱被警察带进看守所的命运。]]></des>
    </video>
    <video>
      <last>2019-03-24 13:25:04</last>
      <id>4352</id>
      <tid>6</tid>
      <name><![CDATA[小鬼当家2]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148926678911.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>1992</year>
      <state>0</state>
      <note><![CDATA[BD高清]]></note>
      <actor><![CDATA[麦考利·卡尔金,乔·佩西,丹尼尔·斯特恩,凯瑟琳·欧哈拉]]></actor>
      <director><![CDATA[克里斯·哥伦布]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清$https://hair.jingpin88.com/20171028/JrTeNonA/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[又一年圣诞节来临，上集因被遗忘在家而没有去成圣诞旅游的凯文（麦考利·卡尔金 Macaulay Culkin 饰）今年和家人准备到佛罗里达去享受他们的圣诞假期。粗心的爸爸妈妈这次当然不会再忘记带上凯文，但他们丢三落四的性格没有改变。眼看飞机准备起飞了，一家子才急冲冲的赶到机场。这次凯文没被忘在家里，却在登记时被忘在了机场，阴差阳错的登上了飞往纽约的航班！第一次来到这个完全陌生的大城市，聪明捣蛋的凯文也不禁暗暗害怕。更糟糕的是，他竟然遇上了上一集在他家里被他修理得很惨的那两个笨贼。两人刚刚越狱出来，碰上了凯文，这次自然要一雪前耻。于是，凯文的战场从上一集的家里搬到了纽约的中央公园酒店和玩具反斗城！]]></des>
    </video>
    <video>
      <last>2017-07-16 11:34:54</last>
      <id>6406</id>
      <tid>6</tid>
      <name><![CDATA[新乌龙女校2]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148926726813.jpg</pic>
      <lang/>
      <area>英国</area>
      <year>2009</year>
      <state>0</state>
      <note><![CDATA[BD1280高清中英双字版]]></note>
      <actor><![CDATA[鲁伯特·艾弗雷特/妲露拉·莱莉/科林·费斯/]]></actor>
      <director><![CDATA[奥利弗·帕克]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中英双字版$https://leshi.cdn-zuyida.com/20170715/hBhrHDU5/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[　　翻拍50年代经典伊灵喜剧的《新乌龙女校》（St. Trinian's）系列第二部，上一集的转校生Annabelle Fritton 已晋升为新的大姐大（head girl）。根据上世纪50年代的《乌龙女校》，改编的《新乌龙女校》在2007年取得了巨大成功。如今续集《新 乌龙女校2》已经登陆英国的银幕，新片中又讲述了怎样的离奇故事呢？影片中女学生们发现，校长竟然是一位著名海盗的后代，于是她们开始了探秘之旅，共同寻找埋藏的海盗宝藏。有着模特身材的80后英国美女，塔姆欣·伊格顿扮演了片中的女主角，“乌龙女校”女学生组织的领军人物切尔西。塔姆欣表示，相比第一部《新乌龙女校》，这部续集将故事的重心更多放在了女学生身上，《新乌龙女校2》已经于18号在英国上映。这一集主要讲述女校学生们发现校长是一位著名海盗的后代，从而出发寻找埋藏的黄金的故事。]]></des>
    </video>
    <video>
      <last>2017-12-09 19:22:22</last>
      <id>6485</id>
      <tid>6</tid>
      <name><![CDATA[帕丁顿熊]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148926729416.jpg</pic>
      <lang/>
      <area>英国</area>
      <year>2014</year>
      <state>0</state>
      <note><![CDATA[BD1280高清原声|国语中英双字版]]></note>
      <actor><![CDATA[本·威士肖/休·博内威利/莎莉·霍金斯/]]></actor>
      <director><![CDATA[保罗·金]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语中英双字版$https://yiyi.55zuiday.com/20171209/v1TuGZps/index.m3u8$zuidam3u8#BD1280高清中英双字版$https://yiyi.55zuiday.com/20171209/lPthRVJs/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[<span style="color: rgb(17, 17, 17); font-family: Helvetica, Arial, sans-serif; font-size: 13px; line-height: 21.06px;">　　在神秘的秘鲁，生活着一种十分稀有的果酱熊，他们拥有非常高的智商和语言能力。当年果酱熊夫妇帕斯图佐和露西曾与来自伦敦的探险家结下深厚的友谊，并且学到了压制果酱的技巧。时至今日，一场灾难摧毁了果酱熊安宁快乐的生活，露西阿姨将淘气的侄子送上开往伦敦的邮轮，嘱咐他在那个友好的国度展开新的生活。万里漂泊而来的小熊懵懵懂懂来到帕丁顿火车站，可是当代人的冷漠却让他倍感失落。幸运的是小熊遇到了布朗一家，并且得到了一个好听的名字——帕丁顿（本·卫肖 Ben Whishaw 配音）。善良的女主人玛丽（莎莉·霍金斯 Sally Hawkins 饰）殷切要帮助帕丁顿找到可以栖身的地方，而男主人亨利（休·博内威利 Hugh Bonneville 饰）则时刻想把这个突如其来的麻烦赶走。&nbsp;<br style="color: rgb(17, 17, 17); font-family: Helvetica, Arial, sans-serif; font-size: 13px; line-height: 21.06px;" /><span style="color: rgb(17, 17, 17); font-family: Helvetica, Arial, sans-serif; font-size: 13px; line-height: 21.06px;">　　在此过程中，搞怪不断的帕丁顿和布朗一家关系逐渐融洽，而自然历史博物馆的标本师米莉森特（妮可·基德曼 Nicole Kidman 饰）则怀着邪恶的目的悄然向帕丁顿接近……<br />]]></des>
    </video>
    <video>
      <last>2017-11-28 13:36:30</last>
      <id>6805</id>
      <tid>6</tid>
      <name><![CDATA[大话西游之月光宝盒]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-07-02/201707021498960468.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>1995</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语|粤语中字版]]></note>
      <actor><![CDATA[ 周星驰 / 吴孟达 / 罗家英 / 蓝洁瑛 / 莫文蔚]]></actor>
      <director><![CDATA[刘镇伟　孙悟空（周星驰）护送唐三藏（罗家英）去西天取经路上，与牛魔王合谋欲杀害唐三藏，并偷走了月光宝盒，此举使观音萌生将其铲除心思，经唐三藏请求，孙悟空被判五百年后重新投胎做人赎其罪孽。  　　五百年后孙悟空化身强盗头头至尊宝。当遇见预谋吃唐僧肉的妖怪姐妹蜘蛛精春三十娘（蓝洁瑛）和白骨精白晶晶（莫文蔚）时，因为五百年前孙悟空曾与白晶晶有过一段恋情，至尊宝与她一见钟情，但因菩提老祖将二人妖怪身份相告，至尊宝仍带领众强盗开始与二妖展开周旋，过程中，白晶晶为救至尊宝打伤春三十娘，自己也中毒受伤，为了救白晶晶，至]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语版$https://yiyi.55zuiday.com/20171127/v6Y4tNdF/index.m3u8$zuidam3u8#BD1280高清粤语版$https://yiyi.55zuiday.com/20171127/w25R7EIb/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[　孙悟空（周星驰）护送唐三藏（罗家英）去西天取经路上，与牛魔王合谋欲杀害唐三藏，并偷走了月光宝盒，此举使观音萌生将其铲除心思，经唐三藏请求，孙悟空被判五百年后重新投胎做人赎其罪孽。 　　五百年后孙悟空化身强盗头头至尊宝。当遇见预谋吃唐僧肉的妖怪姐妹蜘蛛精春三十娘（蓝洁瑛）和白骨精白晶晶（莫文蔚）时，因为五百年前孙悟空曾与白晶晶有过一段恋情，至尊宝与她一见钟情，但因菩提老祖将二人妖怪身份相告，至尊宝仍带领众强盗开始与二妖展开周旋，过程中，白晶晶为救至尊宝打伤春三十娘，自己也中毒受伤，为了救白晶晶，至尊宝去找春三十娘，遭白晶晶误会，绝望自杀，至尊宝开始用月光宝盒以期使时光倒流。]]></des>
    </video>
    <video>
      <last>2017-09-17 20:21:09</last>
      <id>8788</id>
      <tid>6</tid>
      <name><![CDATA[大小笑探]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892684261.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语中字版]]></note>
      <actor><![CDATA[贾旭明,张康]]></actor>
      <director><![CDATA[赵晨曦]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语中字版$https://leshi.cdn-zuyida.com/20170917/IqtftEeQ/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[保安贾东南与张西北在一个夜晚抓住了被警方通缉的摩托飞贼。在向小区业主归还失物时却闯入赌局，形成对峙，最终导致一名女性死亡。两人承担责任被公司开除。失业后两人分道扬镳，为各自理想奋斗。贾东南当上了侦探，张西北下海经商，成为了一个土豪。五年后，贾东南的侦探社生意凋零，张西北则面临破产。而这时，张西北新交往的网红女友小敏遭到绑架，急切的张西北找到贾东南寻求帮助。一场惊心动魄悬念丛生笑果频出的破案之旅即可展开。]]></des>
    </video>
    <video>
      <last>2017-06-21 12:17:09</last>
      <id>9746</id>
      <tid>6</tid>
      <name><![CDATA[来自月亮的我]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148927172719.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2017</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语中字版]]></note>
      <actor><![CDATA[夏嘉伟/夏嘉伟/洪剑涛/徐敬轩/颜丹/]]></actor>
      <director><![CDATA[夏嘉伟]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语中字版$https://leshi.cdn-zuyida.com/20170620/Q1lJApox/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[月老的半吊子徒弟刘二八（夏嘉伟 饰）得罪师尊，被罚下凡，需要撮合三对有情人才能回天庭，而刘二八的法力非常不靠谱，闹出无数笑话，最终却意外过三关。]]></des>
    </video>
    <video>
      <last>2018-04-29 20:16:10</last>
      <id>9754</id>
      <tid>6</tid>
      <name><![CDATA[欢乐喜剧人]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892717358.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2017</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语版]]></note>
      <actor><![CDATA[黎继强/郭德纲/岳云鹏/罗温·艾金森/孙越/艾伦/张小斐/张泰维/潘斌龙/]]></actor>
      <director><![CDATA[黎继强]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语版$https://leshi.cdn-zuyida.com/20180429/24398_ca263c6c/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[　《欢乐喜剧人》新春版录制之前期，岳岳、伦伦等人因工作压力而泄气。郭老师请他们到澳门散心。狂欢之后，众人发现老郭人间蒸发！寻找老郭时，团队成员接连消失！结果岳岳和伦伦把神秘人掀岀来救回队友。]]></des>
    </video>
    <video>
      <last>2017-07-18 19:25:21</last>
      <id>9937</id>
      <tid>6</tid>
      <name><![CDATA[仙球大战]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892718551.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2017</year>
      <state>0</state>
      <note><![CDATA[HD1280高清国语中字版]]></note>
      <actor><![CDATA[刘镇伟,何炅,钟欣潼,蔡卓妍,马丽,林子聪,邓丽欣,杜海涛,吴昕]]></actor>
      <director><![CDATA[刘镇伟]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[HD1280高清国语中字版$https://leshi.cdn-zuyida.com/20170718/44Uq9E4P/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[《仙球大战》集结了快乐家族、Twins及开心麻花等一众“爆笑天团”，豪华笑星阵容强强联手讲述了一个以蹴鞠为主题的爆笑故事。影片中，朝廷内忧外患，为保国之安定，无奈召集中原各大门派掌门联手，与异族超能蹴鞠队展开了一场以割裂国土为条件的蹴鞠大战。在乱世中各大门派掌门流离失所，为贫穷所累，在适应市井生活的过程摩擦不断，笑点频出。]]></des>
    </video>
    <video>
      <last>2018-04-30 00:01:18</last>
      <id>10062</id>
      <tid>6</tid>
      <name><![CDATA[大宋绯闻录]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148927193512.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2017</year>
      <state>0</state>
      <note><![CDATA[HD1024高清国语版]]></note>
      <actor><![CDATA[范向南/刘羽琦/沈驰/梅年佳/]]></actor>
      <director><![CDATA[范向南]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[HD1024高清国语版$https://leshi.cdn-zuyida.com/20180429/24436_5b61f477/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[<span style="color: rgb(17, 17, 17); font-family: Helvetica, Arial, sans-serif; line-height: 19.44px;">　　《大宋绯闻录》讲述了现代女强人“潘潇潇”因为一场电梯事故意外穿越到大宋水浒世界，化身“潘金莲”，遇到与现代男友张赫长相相似的武松回家探亲，误认为是张赫穿越而来撞坏脑子失去记忆，为帮助男友恢复记忆并顺利回到现代，潘潇潇依靠现代人的智慧，与西门庆、王婆、武大郎等水浒中的经典人物斗智周旋，从而引发的一系列啼笑皆非的故事。<br />]]></des>
    </video>
    <video>
      <last>2017-08-11 07:57:57</last>
      <id>10186</id>
      <tid>6</tid>
      <name><![CDATA[绝世高手]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-07-10/201707101499689750.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2017</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语中字版]]></note>
      <actor><![CDATA[卢正雨,郭采洁,范伟,蔡国庆,陈冲,仓田保昭,孔连顺,黄龄,杨迪]]></actor>
      <director><![CDATA[卢正雨]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语中字版$https://kuku.zuida-youku.com/20170810/UZiYAI2K/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[　　一个先天没有知觉，挨揍不疼却冒充高手的小混混（卢正雨 饰），一个人称女张飞的暴力少女（郭采洁 饰），一个醉心于织毛衣的过气大师（范伟 饰），一个只会做黑暗料理的美食大亨（蔡国庆 饰），一个可以用汤操纵情绪的当代孟婆（陈冲 饰），一个身患强迫症的日本武士（仓田保昭 饰），为了一本失传的秘笈，引发了一场绝世高手的爆笑对决。]]></des>
    </video>
    <video>
      <last>2017-07-02 00:14:45</last>
      <id>10194</id>
      <tid>6</tid>
      <name><![CDATA[老师也疯狂]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148927202411.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2017</year>
      <state>0</state>
      <note><![CDATA[HD1280高清国语中字版]]></note>
      <actor><![CDATA[赵宏丽/韩立/贡米/方青卓/苑琼丹/]]></actor>
      <director><![CDATA[赵宏丽]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[HD1280高清国语中字版$https://leshi.cdn-zuyida.com/20170701/Hig1C6k4/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[光正实验学校“六一”实验班，是一个终日充斥着自私、鬼马、娇气、难缠、集结了全校超级不良学生的问题班级。为了整顿这个宛如毒瘤一般的班级，校方请来了有过海外教学背景的热血教师肖子恩来担任“六一”实验班的班主任。不服管教的问题学生们轮番给新来的班主任肖子恩下马威，企图吓跑这个毫不起眼的新老师。肖子恩却始终不以为然，一心想要积极拉近与大家的关系，并用自己独特的教育方法激发、引导、打动这群问题学生，他不按常理的教育方式亦引起了其他老师和学生家长的不满，每天都有意想不到的麻烦出现，陷入窘境的肖子恩却始终选择相信自己的学生们，并努力将他们领向正途，达成学年总成绩第一的目标。]]></des>
    </video>
    <video>
      <last>2018-04-29 23:38:31</last>
      <id>10203</id>
      <tid>6</tid>
      <name><![CDATA[我的女神女汉子]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892720321.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语版]]></note>
      <actor><![CDATA[林琛/徐笑文/赵淼/朱赤丹/刘惠/袁冬冬/?邵汉军/]]></actor>
      <director><![CDATA[林琛]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语版$https://leshi.cdn-zuyida.com/20180429/24425_5fc8d211/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[离家出走的外地妹，在一天内所有的倒霉事都发生在她身上，被盗，失业，男友出轨，被老板索赔100万人民币。小白领背负着的100万债务行走上海滩，又在无家可贵归时遭遇熟盗抢劫。更是巧遇色老板潜规则，幸好男闺蜜肝胆相照,不料却在最狼狈时撞见了初恋，无颜面对,从而产生了一系列悲喜交加趣味横生的故事。]]></des>
    </video>
    <video>
      <last>2017-09-08 16:15:43</last>
      <id>10263</id>
      <tid>6</tid>
      <name><![CDATA[流行歌星：永不停歇]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892720664.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[BD1280高清中字版]]></note>
      <actor><![CDATA[安迪·萨姆伯格,乔玛·塔科内]]></actor>
      <director><![CDATA[阿吉瓦·沙弗尔]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中字版$https://leshi.cdn-zuyida.com/20170908/qyqkZNEx/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[成名于《周六夜现场》（Saturday Night Live）节目中的三人说唱组合“孤岛”（The Lonely Island）即将开拍自己的电影，这部影片由贾德·阿帕罗（Judd Apatow）参与制片，环球公司负责发行。&nbsp;<br />　　“孤岛”组合由《周六夜现场》演员安迪·萨姆博格（Andy Samberg）、阿吉瓦·沙弗尔（Akiva Schaffer）、乔玛·塔昆（Jorma Taccone）三人组成，以搞笑见长，他们出过三张录音室专辑，代表作有“D*ck in a Box”等。&nbsp;<br />　　据悉这部《孤岛组合》的电影将由组合成员阿吉瓦·沙弗尔、乔玛·塔昆联合执导，讲述的是发生在“音乐世界里的事儿”。]]></des>
    </video>
    <video>
      <last>2019-03-23 14:39:55</last>
      <id>10429</id>
      <tid>6</tid>
      <name><![CDATA[奔跑吧！兄弟]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148927212318.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2015</year>
      <state>0</state>
      <note><![CDATA[高清]]></note>
      <actor><![CDATA[/胡笳/杨颖/王宝强/李晨/陈赫/郑恺/王祖蓝/谢依霖/熊黛林/郭京飞/伊一/金钟国/]]></actor>
      <director><![CDATA[岑俊义]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清$https://hair.jingpin88.com/20171028/ep1hEAJ7/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[有这样一个传说，很久很久以前，雨林在孔雀公主的庇护下，生活着虎人和鹿人两个部落，直到某天黑虎挑起战争。惨烈的搏杀过后，虎人落败，黑虎死亡，但他的仇恨却穿越时空来到了21世纪。新年伊始，脱胎自韩国《Running Man》的大型综艺竞技娱乐节目、并由浙江卫视节目中心和韩国SBS电视台联合制作的《奔跑吧兄弟》创下了超高收视率，此番节目组》向忙着各自事业的团员们发出召集令，熊黛林、王宝强、杨颖、谢依霖、李晨、郑恺、王祖蓝在导游伊一的带领下集结三亚。但是这是一次极为凶险的旅程，跑男团的背叛者隐藏其中，相机而动，时刻准备将所有人的快乐摧毁无形……]]></des>
    </video>
    <video>
      <last>2018-03-13 00:20:13</last>
      <id>10748</id>
      <tid>6</tid>
      <name><![CDATA[泰迪熊]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148927232614.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>2012</year>
      <state>0</state>
      <note><![CDATA[BD1280高清中英双字版]]></note>
      <actor><![CDATA[塞思·麦克法兰,马克·沃尔伯格,米拉·库尼斯,吉奥瓦尼·瑞比西,瑞恩·雷诺兹,诺拉·琼斯,乔尔·麦克哈尔]]></actor>
      <director><![CDATA[塞思·麦克法兰]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中英双字版$https://leshi.cdn-zuyida.com/20171013/xwoAY8oX/index.m3u8$zuidam3u8#BD高清$https://hair.jingpin88.com/20171027/ax6UQyJ1/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[该片是导演塞思·麦克法兰首次进军大银幕，自编自导的作品，片中的泰迪熊也是由他本人配音。&nbsp;<br />　　孤僻的约翰儿时许了一个愿，希望他的玩具泰迪熊可以活过来，成为他真正的朋友。奇迹发生了，泰迪（塞思·麦克法兰 Seth MacFarlane 配音）有了生命，并和约翰一起生活了二十多年。如今老大不小的约翰（马克·沃尔伯格 Mark Wahlberg 饰）无所事事，整天和泰迪一起抽烟喝酒吸大麻，过着醉生梦死的生活。直到他遇上美丽的劳丽（米拉·库妮丝 Mila Kunis 饰），决心要改变自己。可是，泰迪却并不喜欢约翰的新女友劳丽，总是处处给劳丽找麻烦，甚至破坏约翰和劳丽的感情。面对陪伴多年的老友，和刚刚俘获的女友，约翰要如何处理两者之间的关系？他是不是能找到一个平衡点呢？&nbsp;]]></des>
    </video>
    <video>
      <last>2017-06-09 15:59:39</last>
      <id>10873</id>
      <tid>6</tid>
      <name><![CDATA[幸福额度]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892723996.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2011</year>
      <state>0</state>
      <note><![CDATA[HD1280高清国语版]]></note>
      <actor><![CDATA[/林志玲/陈坤/廖凡/]]></actor>
      <director><![CDATA[陈正道]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[HD1280高清国语版$https://kuku.zuida-youku.com/20170609/E7VbQA4V/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[孪生姐妹李晓红（林志玲 饰）与莫晓青（林志玲 饰）因父母离异而分开，两人的人生也变得迥然不同。任广告公关的李晓红做了多年上司的情人，终于不堪忍受等待而心生厌倦。莫晓青相恋四年的男友姜成（廖凡 饰）最近被朋友欺骗，导致二人的房产岌岌可危，晓青一怒之下考虑分手。晓红在酒店结 识了拥有“无限卡”的富二代张全（陈坤 饰），一番激情过后布下情网。失业的晓青寻找工作巧遇晓红，在后者安排下参加party，得以认识了家族公司的实力青年沈涛（杨佑宁 饰）。晓青办了多张信用卡奋力一搏，试图博得沈涛青睐，而晓红如愿得到了张全的求婚……性格不同的姐妹二人，能否得到各自的幸福？]]></des>
    </video>
    <video>
      <last>2019-03-24 13:25:19</last>
      <id>10949</id>
      <tid>6</tid>
      <name><![CDATA[小鬼当家3]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892724306.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>1997</year>
      <state>0</state>
      <note><![CDATA[BD高清]]></note>
      <actor><![CDATA[亚历克斯·D·林兹,奥莱克·克鲁帕,莱亚·吉斯特德,林尼·冯·多伦]]></actor>
      <director><![CDATA[拉加·高斯内尔]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清$https://hair.jingpin88.com/20171028/ipdE6KXm/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[美国国防部的一块电脑芯片不见了，里面存着高级的机密。国际犯罪分子也将其价格炒到了天文数字。为了能完成交易，犯罪分子将其藏匿在一台玩具遥控车里面，并顺利通过了机场的安检。不过，途中却阴差阳错的被一位老太太调包，最终这台藏着高级机密芯片的遥控车被送到了8岁男孩儿阿历克斯（亚历克斯·D·林兹 Alex D. Linz 饰）的手中。为了取回芯片，受过专业训练的犯罪分子潜入了阿历克斯所住的小区。一天晚上，阿历克斯因为长水痘而被独自留在了家里，这给犯罪分子极大的机会。不过……阿历克斯却不是他们想象中的8岁男孩儿，他有着让人意想不到的“武器”，最终用智慧打败了犯罪分子。由于之前两部的小主角麦考利克金在第三部开拍时已经长大，所以第三部启用了新的小主角亚历克斯·D·林兹。]]></des>
    </video>
    <video>
      <last>2018-03-14 00:42:14</last>
      <id>11074</id>
      <tid>6</tid>
      <name><![CDATA[和莎莫的500天]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148927253317.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>2009</year>
      <state>0</state>
      <note><![CDATA[BD高清]]></note>
      <actor><![CDATA[约瑟夫·高登-莱维特,佐伊·丹斯切尔,吉奥弗瑞·阿伦德,科洛·莫瑞兹]]></actor>
      <director><![CDATA[马克·韦布]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清$https://hair.jingpin88.com/20171028/tTJTJozI/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[来自新泽西的汤姆（Joseph Gordon-Levitt约瑟夫•高登-莱维特 饰）是一个沉溺于英伦哀歌与《毕业生》情境的年轻人。他供职于一家贺卡公司，任务是撰写富有创意的祝辞。某次会议上，汤姆的老板把新助理介绍给大家，她是来自密歇根的魅力女孩莎莫（Zooey Deschanel 佐伊•丹斯切尔 饰）。莎莫自幼父母离异，因此对于感情的态度与众不同。汤姆和莎莫没有一见钟情，但却在一次酒吧K歌后彼此示好，成了非典型的恋人。而且这段办公室恋情迅速升温，爱火烧得谁都无法预料。最后，在一个餐馆里，莎莫对汤姆说了绝情的分手。深陷情网的汤姆，经受不住失恋的打击，郁郁寡欢，周围的伙伴们希望帮他走出阴影，然而，这并不是故事的全部，本片以汤姆的视角把时间重新组接，让观众在对比中体味500天恋爱的弦外之音……]]></des>
    </video>
    <video>
      <last>2019-03-20 12:31:35</last>
      <id>11268</id>
      <tid>6</tid>
      <name><![CDATA[跷家大作战]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892727492.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>2004</year>
      <state>0</state>
      <note><![CDATA[BD1280超清中字]]></note>
      <actor><![CDATA[蒂姆·艾伦,杰米·李·柯蒂斯,丹·艾克罗伊德]]></actor>
      <director><![CDATA[乔·罗斯]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清中字$https://hair.jingpin88.com/20171026/eYPg2Gky/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[影片改编自当今美国著名小说家约翰·格里沙姆(John Grisham)的畅销作品《逃离圣诞》(Skipping Christmas)。故事描写一对美国夫妇，路德·克拉克(蒂姆o艾伦饰)与诺拉(杰米·李·柯蒂斯饰)在圣诞节前夕作出了一个“惊人”的决定--今年不过圣诞节。他们打算在圣诞期间去加勒比海旅游。这样一来，不但能痛痛快快地享受久违的二人世界，同时还能节省一年一度“无聊透顶”的节日开支。 然而，此举立刻招致亲朋好友甚至邻居们的非议。一个小小的改变竟然引来如此巨大的社会反响完全出乎路德和诺拉的预料。他们不得不面对来自各方面的压力，其间自然发生了许多不可思议的笑料。就在克拉克夫妇迷惑之际，他们的宝贝女儿布莱尔(茱丽·贡泽罗饰)突然告知父母她将回家过圣诞节……一心一意向往逃离圣诞的路德和诺拉不得不再次面对“郁闷的”节日。]]></des>
    </video>
    <video>
      <last>2019-03-19 13:17:53</last>
      <id>11323</id>
      <tid>6</tid>
      <name><![CDATA[挂线情未了]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2018-03-10/201803101520693554.png</pic>
      <lang/>
      <area>美国</area>
      <year>2000</year>
      <state>0</state>
      <note><![CDATA[BD高清中字]]></note>
      <actor><![CDATA[黛安·基顿,梅格·瑞恩,沃尔特·马修,丽莎·库卓]]></actor>
      <director><![CDATA[黛安·基顿]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD高清中字$https://hair.jingpin88.com/20171026/9l9wcwkc/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[年老的劳（沃特尔•马修 饰）有三个女儿，可是他很少与女儿们见面，平常女儿们都只是打电话询问老父亲的情况。身为妇女杂志主编的大女儿乔姬娅（黛安•基顿 饰）每天的工作都非常繁忙，身居要职的她每天都在努力工作；二女儿艾薇（梅格•瑞恩 饰）美丽动人，但也同样与父亲缺少沟通；至于三女儿则是个演员，虽然不是大红大紫，但她仍享受自己的工作。父亲从来都很少照顾女儿们，也很少关心她们的生活，无形中也成为了女儿与父亲之间的隔阂。父亲有自己孤独的晚年生活，女儿们也有各自要忙碌的工作与生活。可是当有一天，三姐妹接到老父亲病倒的消息，都纷纷赶到了父亲的身边……]]></des>
    </video>
    <video>
      <last>2018-03-01 16:14:32</last>
      <id>11548</id>
      <tid>6</tid>
      <name><![CDATA[小萝莉的猴神大叔]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2018-03-01/201803011519866616.jpg</pic>
      <lang/>
      <area>印度</area>
      <year>2015</year>
      <state>0</state>
      <note><![CDATA[BD1280高清中英双字版]]></note>
      <actor><![CDATA[萨尔曼·汗,哈莎莉·马洛特拉,卡琳娜·卡普尔,纳瓦祖丁·席迪圭,欧姆·普瑞,梅·维贾]]></actor>
      <director><![CDATA[卡比尔·汗]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中英双字版$https://haoa.haozuida.com/20180301/tLc9Lr9D/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[　　电影讲述了一个拥有虔诚宗教信仰的单纯印度男人帮助巴基斯坦哑女与父母重聚的故事。印度教教徒帕万（萨尔曼·汗 饰）在一次机缘巧合下结识了与母亲走失并有语言障碍的穆斯林小女孩沙希达（哈尔莎莉·马尔霍特 饰）。在得知沙希达是巴基斯坦人后，帕万决定帮助她回家，可在回巴基斯坦途中却四处碰壁，遭遇领事馆冲突、被旅游局欺骗之后，帕万立志将不惜一切代价尽其所能带沙希达回到自己的家乡与家人团聚。]]></des>
    </video>
    <video>
      <last>2017-10-13 19:06:40</last>
      <id>11641</id>
      <tid>6</tid>
      <name><![CDATA[泰迪熊2]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148927300814.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>2015</year>
      <state>0</state>
      <note><![CDATA[BD1280高清中英双字版]]></note>
      <actor><![CDATA[塞思·麦克法兰,马克·沃尔伯格,阿曼达·塞弗里德,杰西卡·巴斯,连姆·尼森,摩根·弗里曼,帕特里克·斯图尔特,杰·雷诺,吉米·坎摩尔,鲍比·莫尼汉]]></actor>
      <director><![CDATA[塞思·麦克法兰]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中英双字版$https://leshi.cdn-zuyida.com/20171013/Vmri1NFm/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[为了巩固两人的婚姻，泰迪（塞思·麦克法兰 Seth MacFarlane 配音）和泰米琳（杰西卡·巴斯 Jessica Barth 饰）产生了要一个孩子的念头，在尝试了各种方法无果后，两人决定领养。然而，此时泰迪却发现政府并没有将他当做一个真正的“人”，而仅仅只是一份“财产”，因此，他不仅无法领养孩子，还丧失了身为一个“人”的所有公民权利——信用卡报废，工作泡汤，就连他和泰米琳的婚姻也成了一纸空文。 　　愤怒的泰迪和好友约翰（马克·沃尔伯格 Mark Wahlberg 饰）商量之后，两人决定起诉，他们找到了新手律师萨曼莎（阿曼达·塞弗里德 Amanda Seyfried 饰）三人共同为争取“熊权”而展开了战斗。]]></des>
    </video>
    <video>
      <last>2017-09-04 00:36:29</last>
      <id>13667</id>
      <tid>6</tid>
      <name><![CDATA[大话西游3]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-09-03/201709031504450330.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语|粤语中字版]]></note>
      <actor><![CDATA[韩庚/唐嫣/吴京/莫文蔚/何炅/钟欣潼/韩庚/唐嫣/吴京/莫文蔚/何炅/钟欣潼/]]></actor>
      <director><![CDATA[刘镇伟]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语中字版$https://leshi.cdn-zuyida.com/20170903/xTNcXY8B/index.m3u8$zuidam3u8#BD1280高清粤语中字版$https://leshi.cdn-zuyida.com/20170903/xNmcTNQK/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[《大话西游3》是由刘镇伟导演，韩庚、唐嫣、吴京、莫文蔚、何炅、钟欣潼主演的电影。影片剧情简介：在《大话西游之大圣娶亲》中死在牛魔王叉下的紫霞仙子（唐嫣 饰），将会通过月光宝盒预先看到这一下场，为了避免惨剧发生，她选择回到从前不让至尊宝（韩庚 饰）爱上自己。而至尊宝又再次重逢一直在等待他的白晶..。]]></des>
    </video>
    <video>
      <last>2017-06-07 15:42:11</last>
      <id>13910</id>
      <tid>6</tid>
      <name><![CDATA[醒醒吧之跟风者]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/14892755573.jpg</pic>
      <lang/>
      <area>大陆</area>
      <year>2017</year>
      <state>0</state>
      <note><![CDATA[BD1280高清国语中字版]]></note>
      <actor><![CDATA[姜寒/肖旭/衣云鹤/]]></actor>
      <director><![CDATA[周星星]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清国语中字版$https://leshi.cdn-zuyida.com/20170607/QWv7jxwV/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[这个世界上总会有一群愚昧无知的人，也会有利用这群人混口饭的投机者，《名编》里的郑义就是典型的投机者，他会根据自身的优势及外部条件，抓住一切机会从那些盲从者手中骗取金钱利益，而《小师妹》中的小师妹则是典型的愚昧之人，她没有自己的判断力，他人的三言两语就能将她忽悠过去，盲从的同时也损失了金钱和时间，《有故事的人》里的三兄弟介于两者之间，他们既是愚昧之人，又想要骗取他们自认为愚昧之人的钱财，不想弄巧成拙，不仅赔了钱财，还伤了自己。<span class="intro-more hide">]]></des>
    </video>
    <video>
      <last>2017-09-18 14:04:20</last>
      <id>17035</id>
      <tid>6</tid>
      <name><![CDATA[成长边缘]]></name>
      <type>喜剧片</type>
      <pic>https://tu.tianzuida.com/pic/upload/vod/2017-03-12/148927748012.jpg</pic>
      <lang/>
      <area>美国</area>
      <year>2016</year>
      <state>0</state>
      <note><![CDATA[BD1280高清中英双字版]]></note>
      <actor><![CDATA[海莉·斯坦菲尔德/海利·路·理查森/布莱克·詹纳/凯拉·塞吉维克]]></actor>
      <director><![CDATA[凯莉·弗莱蒙·克雷格]]></director>
      <dl>
        <dd flag="m3u8"><![CDATA[BD1280高清中英双字版$https://leshi.cdn-zuyida.com/20170917/Sd8uhqhN/index.m3u8$zuidam3u8]]></dd>
      </dl>
      <des><![CDATA[　　娜丁（海莉·斯坦菲尔德 Hailee Steinfeld 饰）从小就是一个性格古怪孤僻不合群的姑娘，因此常常受到同学的欺负。克里斯塔（海莉·路·理查森 Haley Lu Richardson 饰）好像一道光，照亮娜丁的生活，她们从相识起便形影不离，互相分享快乐和秘密，时光荏苒，两个女孩长大走进了高中校园，她们之间的感情从未改变。 　　娜丁的哥哥达里安（布莱克·詹纳 Blake Jenner 饰）英俊帅气阳光开朗，他的存在衬得愤世嫉俗少年老成的娜丁显得更加不合时宜，但娜丁不在意，因为她拥有克里斯塔的友谊。然而某一日，娜丁震惊的发现克里斯塔和达里安竟然躺到了一张床上，与此同时，娜丁爱上了名为尼克（亚历山大·卡尔弗特 Alexander Calvert 饰）的男生，可她根本无法打入他所在的圈子。]]></des>
    </video>
  </list>
</rss>


```



> 该页的返回的元信息可以在头部找到

```xml
<list page="1" pagecount="87" pagesize="40" recordcount="3464">
```



> 然后解析该页的视频列表
>
> 我们可以通过`video`标签下的`dl.dd`标签 提取需要的播放链接。
