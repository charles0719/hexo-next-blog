��node��װĿ¼���½��ļ���node_global��node_cache


npm config set prefix "D:\Program Files\nodejs\node_global"
npm config set cache "D:\Program Files\nodejs\node_cache"

npm install express -g
npm install hexo-cli -g
npm install hexo --save
npm install hexo-deployer-git -g
npm install --save hexo-deployer-git

### ����node.js
NODE_PATH
D:\Program Files\nodejs\node_modules

### ����hexoȫ������
PATH
D:\Program Files\nodejs\node_global\node_modules\hexo-cli\node_modules\.bin

### ��ʼ��blog

hexo init charles_blog
cd charles_blog
npm install
hexo g ���ɾ�̬��ҳ ��public�ļ�����
hexo s -p 9170  ����������


source/_posts/hello-world.md ������ҳ

�޸�config.yml
url: https://charles0719.github.io

type:git
branch:master
repo:https://github.com/charles0719/charles0719.github.io.git



npm install hexo-deployer-git -g
����_config.yml
https://[userName]:[password]@github.com/[username]/project.git




## hexo��װ����
Anisina---�ŵ�themesĿ¼��,�޸�_config.xml

===============================================================
��ţ����Ϊͼ��,ʹ��aifred��ݹ���,�Զ��ϴ�ͼƬ,copy,windows�¿��о�wox,����launchy


## �¼�tagsҳ��
hexo new page tags
sources/tags�����и�index.md���ļ�,�޸�types: tags
�����������ļ��У���menu���£�Ҫ��tagsҳ��


## ��������
language������Ϊzh-CN�����ģ�zh-EN(Ӣ��)
ע������޸ĺ������ã�������theme/next/languages/Ŀ¼�²鿴�Ƿ���zh-CN.yml


## ���ӱ�ǩҳ�ͷ���ҳ
�����������ļ�menu����
hexo n page tags
hexo n page categories�ڲ��͵�source��Ŀ¼�����ɶ�Ӧ���ļ���
��tagesĿ¼�µ�index.md����type:tags


## ������ʽ
���������ļ�schema�޸�

## ����ͷ��
avatar
�������source/images�������ͼƬ
���������ļ�:
url: images/avatar.jpg(�ļ���)

## �罻�˺�
��������social


## ���⴦��

### npm install --save hexo-deployer-git����(������3����Сʱ)
��npm��װ·����ɾ��hexo-deployer-gitĿ¼,���°�װ,���