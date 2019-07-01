在node安装目录下新建文件夹node_global和node_cache


npm config set prefix "D:\Program Files\nodejs\node_global"
npm config set cache "D:\Program Files\nodejs\node_cache"

npm install express -g
npm install hexo-cli -g
npm install hexo --save
npm install hexo-deployer-git -g
npm install --save hexo-deployer-git

### 配置node.js
NODE_PATH
D:\Program Files\nodejs\node_modules

### 配置hexo全局命令
PATH
D:\Program Files\nodejs\node_global\node_modules\hexo-cli\node_modules\.bin

### 初始化blog

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




## hexo安装主题
Anisina---放到themes目录下,修改_config.xml

===============================================================
七牛云作为图床,使用aifred快捷工具,自动上传图片,copy,windows下可研究wox,或者launchy


## 新加tags页面
hexo new page tags
sources/tags里面有个index.md的文件,修改types: tags
在主题配置文件中，在menu项下，要把tags页打开


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


## 问题处理

### npm install --save hexo-deployer-git报错(处理了3个多小时)
在npm安装路径上删除hexo-deployer-git目录,重新安装,解决