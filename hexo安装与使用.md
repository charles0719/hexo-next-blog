# hexo入门

## hexo的日常使用

- npm install 生成需要运行的node组件
- hexo s  启动服务器
- hexo g 生成文件(将md转换成html)，在public目录下
- hexo c 清空public目录下的所有文件
- hexo d 将本地文件部署到github上面去


## node配置
- 设置node 全局配置和缓存的地方
在node安装目录下新建文件夹node_global和node_cache
npm config set prefix "D:\Program Files\nodejs\node_global"
npm config set cache "D:\Program Files\nodejs\node_cache"

npm install express -g
npm install hexo-cli -g
npm install hexo --save
npm install hexo-deployer-git -g
npm install --save hexo-deployer-git

## 配置node.js
NODE_PATH
D:\Program Files\nodejs\node_modules

## 配置hexo全局命令
PATH
D:\Program Files\nodejs\node_global\node_modules\hexo-cli\node_modules\.bin

## 初始化blog

hexo init charles_blog
cd charles_blog
npm install
hexo g 生成静态网页 在public文件夹下
hexo s -p 9170  服务器启动


source/_posts/hello-world.md 就是首页

修改config.yml
url: https://charles0719.github.io

type:git
branch:master
repo:https://github.com/charles0719/charles0719.github.io.git



npm install hexo-deployer-git -g
设置_config.yml
https://[userName]:[password]@github.com/[username]/project.git




## hexo的使用

### hexo安装主题
Anisina---放到themes目录下,修改_config.xml

### 图床
七牛云作为图床,使用aifred快捷工具,自动上传图片,copy,windows下可研究wox,或者launchy
（只能使用一个月，以后是收费的，后来就不用了）

### 新加tags页面
hexo new page tags
sources/tags里面有个index.md的文件,修改types: tags
在主题配置文件中，在menu项下，要把tags页打开


### 设置中文
language行设置为zh-CN（中文）zh-EN(英文)
注意如果修改后不起作用，请来到theme/next/languages/目录下查看是否有zh-CN.yml


### 增加标签页和分类页
在主题配置文件menu设置
hexo n page tags
hexo n page categories在博客的source的目录下生成对应的文件夹
在tages目录下的index.md增加type:tags


### 主题样式
主题配置文件schema修改

### 设置头像
avatar
在主题的source/images里面放置图片
主题配置文件:
url: images/avatar.jpg(文件名)

### 社交账号
主题配置social

### 增加live2d

```shell
npm install --save hexo-helper-live2d

# 可选。具体参考https://github.com/xiazeyu/live2d-widget-models.git或百度
npm install --save live2d-widget-model-epsilon2_1
```


## 问题处理

### npm install --save hexo-deployer-git报错(处理了x个小时)
在npm安装路径上删除hexo-deployer-git目录,重新安装,解决



### velocity.min.js 等 not found

```
Failed to load resource: the server responded with a status of 404 ()
pace.min.js
velocity.min.js
font-awesome.min.css
```

`themes/next_v6/_config.xml`有配置项`vendors`
配置示例：`jquery: //cdnjs.cloudflare.com/ajax/libs/jquery/2.1.3/jquery.min.js`

以前没有配置，也能启动，现在莫名其妙报错，无语。。。

