springboot集成jsp搭建文化旅游地图
=
如需源码请联系[程序帮](http://ll032.cn/HZ6vHa)：QQ1022287044


开发环境
-----
1. jdk 8
2. intellij idea
3. maven 3.6

所用技术
-----
1. springboot
2. jsp

项目介绍
----
北京旅游地图，快捷导航！

项目适用人群
---- 
正在做毕设的学生，或者需要项目实战练习的Java学习者

程序访问
```
http://localhost:8090/index
```

准备工作
-----
1. pom.xml加入jsp模板引擎支持：
```diff
<dependency>
    <groupId>org.apache.tomcat.embed</groupId>
    <artifactId>tomcat-embed-jasper</artifactId>
    <scope>provided</scope>
</dependency>
```
2. springboot配置jsp
```diff
spring.mvc.view.prefix=/
spring.mvc.view.suffix=.jsp
```
运行效果
----
![首页](/image/页面.png)

技术实现
----
1.整体布局
``` diff
<frameset rows="10%,90%">
    <frame src="search">
    <frameset cols="10%,90%" id="frame1">
        <frame src="menu">
        <frameset rows="60%,40%" id="frame2">
            <frame src="https://www.amap.com/search" id="mainHtml" name="showframe">
            <frameset cols="50%,50%" id="frame3">
                <frame src="https://www.baidu.com" id="mfwFrame" name="mfwFrame">
                <frame src="https://weixin.sogou.com/weixin" id="sgwxFrame" name="sgwxFrame">
            </frameset>
        </frameset>
    </frameset>
</frameset>
```
 
- 左侧菜单代码实现
```diff
<div class="container" style="padding-left: 80px;padding-top: 50px">
    <div class="row">
        <div class="span6">
            <ul class="nav nav-list">
                <li class="nav-header"><span class="glyphicon glyphicon glyphicon-map-marker"></span>&nbsp;总览</li>
                <li class="active "><a href="https://www.amap.com/search?query=%E5%8C%97%E4%BA%AC%E5%B8%82&city=110101&geoobj=106.165942%7C29.343435%7C107.154712%7C29.801484&zoom=11" target="showframe">默认地图</a></li>
                <li><a href="https://www.amap.com/search?query=%E5%8C%97%E4%BA%AC%E6%99%AF%E7%82%B9&city=110000&geoobj=116.022898%7C39.709792%7C117.011668%7C40.113754&zoom=11" target="showframe">热门景点</a></li>
                <li class="nav-header"><span class="glyphicon glyphicon-globe"></span>&nbsp;攻略</li>
                <li><a href="https://you.ctrip.com/place/beijing1.html#ctm_ref=www_hp_bs_lst" target="_blank">携程</a></li>
                <li><a href="https://dujia.qunar.com/pdqk/list_%E8%B5%A3%E5%B7%9E_%E5%8C%97%E4%BA%AC%E6%99%AF%E7%82%B9_all?ti=3&tf=pc_big_search&tm=l01_all_search_origin" target="_blank">去哪儿</a></li>
                <li><a href="https://www.xiaohongshu.com/explore" target="_blank">小红书</a></li>
                <li class="nav-header"><span class="glyphicon glyphicon-user"></span> &nbsp;友情链接</li>
                <li><a href="http://whlyj.beijing.gov.cn/" target="_blank">北京文化局</a></li>
            </ul>
        </div>
    </div>
</div>
```
项目总结
----
1. frame 目前已经不太友好，可用其他技术实现页面分割
2. 其他有更好的简洁操作，希望留言交流
3. 原地址认准[程序帮](http://ll032.cn/HZ6vHa)：

