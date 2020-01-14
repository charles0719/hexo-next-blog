---
title: Hexo的next主题的使用
tags:
  -博客
  -next
  -hexo
categories: blog
  -hexo
  -next
	
	
---
# hexo的日常使用
## 新建文章
hexo new post xxx 

## 发布到github
hexo d

## 启动本地服务器
hexo s

## 清理本地文件
hexo clean

## 生成本地文件
hexo g

# 博客配置注意点
```
# permalink: :year/:month/:day/:title/ :title.html
permalink: :title.html
```
配置permalink: :year/:month/:day/:title/ :title.html
点击文章的链接显示是 /2018/12/3/文章名.html

permalink: :title.html
点击文章的链接编程2018/12/3/文章名.html
点击文章的链接显示是 /文章名.html

如果title后面没有.html,会变成一个下载链接.


<!--more-->
# 主题配置
## 设置中文
language行设置为zh-CN（中文）zh-EN(英文)
注意如果修改后不起作用，请来到theme/next/languages/目录下查看是否有zh-CN.yml


## 增加标签页和分类页
在主题配置文件menu设置
hexo n page tags
hexo n page categories在博客的source的目录下生成对应的文件夹
在tages目录下的index.md增加type:tags


## 主题样式
主题配置文件schema修改

## 设置头像
avatar
在主题的source/images里面放置图片
主题配置文件:
url: images/avatar.jpg(文件名)

## 社交账号
主题配置social


## 打赏
修改主题配置里面的_config.xml,如下配置的图片需要保存到 主题/source/images目录下
```
reward:
  enable: true
  comment: 感谢观看,感谢打赏
  wechatpay: /images/wechatpay.jpg
  alipay: /images/alipay.jpg
  bitcoin: /images/bitcoin.png
```
设置鼠标悬浮在二维码上文字不转
修改`next/source/css/_common/components/post/post-reward.styl`，注释`wechat:hove`r和`alipay:hover`.我的主题配置的是`#QR > div:hover p `注释掉即可


## 订阅公众号
```
wechat_subscriber:
  enabled: true
  qcode: http://pj55chpdo.bkt.clouddn.com/18-12-3/64267586.jpg
  description: 欢迎您扫一扫上面的微信公众号，订阅我的博客！
```
要求图片放置在uploads里面,不知道放在绝对目录是啥.索性用极简图片的地址

## 设置头像旋转
修改themes\next_v6\source\css\_common\components\sidebar的sidebar-author.styl
```
.site-author-image {
	border-radius: 50%;
	transition:2s all		
}
.site-author-image:hover{
	transform:rotate(360deg)
}
```

## 阅读全文
```
auto_excerpt:
  enable: true
  length: 150
```
除了这样,还可以增加
```
<!--more-->
```
该注释以上的内容会显示出来


## 动态背景
首先要下载对应的js
[dynamic_background](https://github.com/theme-next/theme-next-three)
设置canvas_sphere为true

## fork github
参考链接
[github_corner](http://tholman.com/github-corners/)

[github_ribbons](https://blog.github.com/2008-12-19-github-ribbons/)

```
	<a href="https://github.com/charles0719" class="github-corner" aria-label="View source on GitHub"><svg width="80" height="80" viewBox="0 0 250 250" style="fill:#70B7FD; color:#fff; position: absolute; top: 0; border: 0; right: 0;" aria-hidden="true"><path d="M0,0 L115,115 L130,115 L142,142 L250,250 L250,0 Z"></path><path d="M128.3,109.0 C113.8,99.7 119.0,89.6 119.0,89.6 C122.0,82.7 120.5,78.6 120.5,78.6 C119.2,72.0 123.4,76.3 123.4,76.3 C127.3,80.9 125.5,87.3 125.5,87.3 C122.9,97.6 130.6,101.9 134.4,103.2" fill="currentColor" style="transform-origin: 130px 106px;" class="octo-arm"></path><path d="M115.0,115.0 C114.9,115.1 118.7,116.5 119.8,115.4 L133.7,101.6 C136.9,99.2 139.9,98.4 142.2,98.6 C133.8,88.0 127.5,74.4 143.8,58.0 C148.5,53.4 154.0,51.2 159.7,51.0 C160.3,49.4 163.2,43.6 171.4,40.1 C171.4,40.1 176.1,42.5 178.8,56.2 C183.1,58.6 187.2,61.8 190.9,65.4 C194.5,69.0 197.7,73.2 200.1,77.6 C213.8,80.2 216.3,84.9 216.3,84.9 C212.7,93.1 206.9,96.0 205.4,96.6 C205.1,102.4 203.0,107.8 198.3,112.5 C181.9,128.9 168.3,122.5 157.7,114.1 C157.9,116.9 156.7,120.9 152.7,124.9 L141.0,136.5 C139.8,137.7 141.6,141.9 141.8,141.8 Z" fill="currentColor" class="octo-body"></path></svg></a><style>.github-corner:hover .octo-arm{animation:octocat-wave 560ms ease-in-out}@keyframes octocat-wave{0%,100%{transform:rotate(0)}20%,60%{transform:rotate(-25deg)}40%,80%{transform:rotate(10deg)}}@media (max-width:500px){.github-corner:hover .octo-arm{animation:none}.github-corner .octo-arm{animation:octocat-wave 560ms ease-in-out}}</style>
```
找到headband的div,在下面加上代码块,修改github的地址即可

## 修改文章链接样式

在`themes\next_v6\source\css\_common\components\post`路径下修改post.styl文件,增加如下文件
```
.post-body p a{
	coloe: #345;
	border-bottom: none;
	&:hover{
		color: red;
	}
```

## 修改文章底部带#的标签
在`/themes/next_v6/layout/_macro/post.swig`中找到post-footer

[图标库](http://fontawesome.dashgame.com/)

在`# {{ tag.name }} `修改为`<i class="fa fa-tag"></i>`

## 评论系统
```
valine:
  enable: true # When enable is set to be true, leancloud_visitors is recommended to be closed for the re-initialization problem within different leancloud adk version.
  appid: XXXXXXXXXXXX
  appkey: XXXXXXXXXXX
  notify: false # mail notifier , https://github.com/xCss/Valine/wiki
  verify: false # Verification code
  placeholder: Just go go
  avatar: mm # gravatar style
  guest_info: nick,mail,link # custom comment header
  pageSize: 10 # pagination size
  visitor: false # leancloud-counter-security is not supported for now. When visitor is set to be true, appid and appkey are recommended to be the same as leancloud_visitors' for counter compatibility. Article reading statistic https://valine.js.org/visitor.html

```
最好appid后面不加注释.(在原有的基础上加的,发现route请求报错,用URI解码解析,发现有错)
评论管理在应用的存储里面,对应Comment的表
应用appid和appkey获取是在应用的设置里面

安全中心配置
```
http://127.0.0.1:4000
https://charles0719.github.io/
```

## 来必力评论
注册来必力,安装
```
<!-- 来必力City版安装代码 -->
<div id="lv-container" data-id="city" data-uid="XXXXXXXX">
<script type="text/javascript">
   (function(d, s) {
       var j, e = d.getElementsByTagName(s)[0];

       if (typeof LivereTower === 'function') { return; }

       j = d.createElement(s);
       j.src = 'https://cdn-city.livere.com/js/embed.dist.js';
       j.async = true;

       e.parentNode.insertBefore(j, e);
   })(document, 'script');
</script>
<noscript>为正常使用来必力评论功能请激活JavaScript</noscript>
</div>
<!-- City版安装代码已完成 -->

```
在主题配置配置
```
livere_uid: xxxx
```
关闭其他服务即可使用

## gitment使用
[github_注册](https://github.com/settings/applications/new)

新建一个repo仓库charlesCommentRepo,与app同名
```
gitment:
  enable: true
  mint: true # RECOMMEND, A mint on Gitment, to support count, language and proxy_gateway
  count: true # Show comments count in post meta area
  lazy: false # Comments lazy loading with a button
  cleanly: false # Hide 'Powered by ...' on footer, and more
  language: # Force language, or auto switch by theme
  github_user: charles0719
  github_repo: charlesCommentRepo
  client_id: xxxxxx
  client_secret: xxxxxx
  proxy_gateway: # Address of api proxy, See: https://github.com/aimingoo/intersect
  redirect_protocol: # Protocol of redirect_uri with force_redirect_protocol when mint enabled


```

## 搜索添加之local search
[参考链接](http://theme-next.iissnan.com/third-party-services.html#search-system)
安装 hexo-generator-searchdb，在站点的根目录下执行以下命令：(安装一直报错,浪费太多时间)
```
$ npm install hexo-generator-searchdb --save
```
编辑 站点配置文件，新增以下内容到任意位置：
```
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```
编辑 主题配置文件，启用本地搜索功能：
```
# Local search
local_search:
  enable: true
```
## 增加卜算子的统计功能
[卜算子](http://theme-next.iissnan.com/third-party-services.html#analytics-busuanzi)
修改配置`busuanzi_count`配置


## 增加分享功能
修改如下配置
```
baidushare:
  type: button
  baidushare: true
```
`jiathis: true`本人的主题中不包含jiathis配置,自己添加,`hexo g`重新生成也不生效

## 增加加载效果
首先要先按照[pace链接](https://github.com/theme-next/theme-next-pace)去操作,然后在主题配置如下:
```
pace: true
pace_theme: pace-theme-center-atom

```
## 增加点击爆炸效果
首先在themes/next/source/js/src里面建一个叫fireworks.js的文件.

打开`themes/next/layout/_layout.swig`,在`</body>`上面写下如下代码：
```
{% if theme.fireworks %}
   <canvas class="fireworks" style="position: fixed;left: 0;top: 0;z-index: 1; pointer-events: none;" ></canvas> 
   <script type="text/javascript" src="//cdn.bootcss.com/animejs/2.2.0/anime.min.js"></script> 
   <script type="text/javascript" src="/js/src/fireworks.js"></script>
{% endif %}
```
打开主题配置文件，在里面最后写下：
```
# Fireworks
fireworks: true
```
## 点击出现桃心效果
浏览器输入：`[](http://7u2ss1.com1.z0.glb.clouddn.com/love.js)`

拷贝所有代码，在`/themes/next/source/js/src`里面新建love.js，然后在`\themes\next\layout\_layout.swig`文件末尾添加以下代码：
```
<!-- 页面点击小红心 --> 
<script type="text/javascript" src="/js/src/love.js"></script>
```
##隐藏强力驱动
打开	`themes/next/layout/_partials/footer.swig`,使用””隐藏之间的代码即可，或者直接删除
```
<!--
{% if theme.footer.powered.enable %}
  <div class="powered-by">{#
  #}{{ __('footer.powered', next_url('https://hexo.io', 'Hexo', {class: 'theme-link'})) }}{#
  #}{% if theme.footer.powered.version %} v{{ hexo_env('version') }}{% endif %}{#
 #}</div>
{% endif %}

{% if theme.footer.powered.enable and theme.footer.theme.enable %}
  <span class="post-meta-divider">|</span>
{% endif %}

{% if theme.footer.theme.enable %}
  <div class="theme-info">{#
  #}{{ __('footer.theme') }} – {{ next_url('https://theme-next.org', 'NexT.' + theme.scheme, {class: 'theme-link'}) }}{#
  #}{% if theme.footer.theme.version %} v{{ version }}{% endif %}{#
#}</div>
{% endif %}
-->

```
## 统计字数和时长
安装hexo-symbols-count-time,而不是hexo-wordcount
修改博客配置文件，添加以下代码
```
symbols_count_time:
symbols: true
time: true
total_symbols: true
total_time: true
```
修改主题配置文件，搜索symbols_count_time，快速定位，修改成以下代码
```
  symbols_count_time:
  separated_meta: true
  item_text_post: true
  item_text_total: false
  awl: 4
  wpm: 275
```

本人的_config.xml没有找到hexo-wordcount的配置,最后只显示了一个全局的统计字数

## 以后的研究方向
 - topx 的实现
 - 站点地图的实现
 - 动画人物的实现




# next 爬坑记录

## hexo d 失败
删除博客目录下的.deploygit目录,重新执行命令

## npm install xxx --save报错(这是重点)

file not found
4048
4058

百度搜索:`npm install 报错4058 或4048`
最后的解决方案:
删除博客的node_modules,然后`npm install`,再执行安装.
本人安装localsearch和rss均报错,搞了大概有5个小时了,实在不易,网上查也没有找到合适的结果.


将no such file or directory,access中指明的文件路径中的node_modules删除：
rm -r node_modules或者直接在在项目文件夹中删除

然后再重新npm install 安装
