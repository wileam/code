title: hexo搭建静态博客以及优化
date: 2013-12-14 12:56:49
tags:
- hexo
- blog
categories: other
---

首先，*这不是一篇详尽的完整的教程*，只是记录大致的hexo建站流程以及自己折腾的过程。因为网上关于hexo的教程已经太多，一搜一大把。但是我还是推荐英文尚可的直接阅读hexo作者的**[文档](http://zespia.tw/hexo/docs/)**，因为很多教程也只是一知半解，还是看作者文档来的比较彻底。另外，hexo源代码开源，实在不行还可以去hexo的[github](https://github.com/tommy351/hexo)去提[issue](https://github.com/tommy351/hexo/issues)。

折腾的成果就是你现在看到的这个博客，所以这里本身就是一个demo。^_^

*p.s. hexo作者据说是台湾的一名在校学生…… T_T 努力吧少年…… *

建站流程
-----

### 1. 安装node.js以及git
<!-- more -->

### 2. 安装hexo

    $ npm install -g hexo

### 3. 部署github pages

#### 3.1 github建立repo
以下二选一。

- 建立一个 username.github.com 的repo，username为你的github用户名，每个用户只能有一个这样的repo，则直接发布到master分支即可。
- 建立一个项目repo，发布的branch是gh-pages.

自定义域名

如果你用自定义域名的话，github pages需要你建立一个名称为CNAME的文件，里面放入你的域名地址。如我的[CNAME文件](https://github.com/wileam/code/blob/gh-pages/CNAME).

因为每次deploy的时候hexo都会重新生成文件，所以直接加在github是不好使的，**这个文件需要放在 hexo folder/source文件夹根目录下。**

#### 3.2 hexo配置deploy信息：

修改在blog根目录下的_config.yml，添加repo地址：

    deploy:
      type: github
      repository: https://github.com/[username]/[reponame].git

References:
[1] [github pages help](https://help.github.com/categories/20/articles)
[2] [hexo Deployment Docs](http://zespia.tw/hexo/docs/deployment.html)
[3] 想用BAE的可以看这篇：[在BAE上使用hexo搭建博客](http://jimliu.net/2013/11/20/use-hexo-on-bae/)

### 4. hexo基本操作

- 新建博客

      $ hexo init <folder>

在该目录下就建立了你的hexo blog.

- 新建文章

      $ hexo init <title>

会在source/_post新建一个名为 title.md 的文章，用喜欢的编辑器打开就可以用markdown语法写文章了。

- server

      $ hexo server

就可以在 localhost:4000/ 查看你的博客。

- generate & deploy

      $ hexo generate
      $ hexo deploy

或者（以下这俩效果是完全一样的）

    $ hexo generate --deploy
    $ hexo deploy --generate


折腾
----

### 插件 plugins

- rss生成 hexo-generator-feed
- sitemap hexo-generator-sitemap

添加插件的基本操作是：

    $ npm install <plugin-name> --save
    $ npm update

然后修改blog根目录下的_config.yml，添加：

    plugins:
    - plugin-name

插件部分详见：https://github.com/tommy351/hexo/wiki/Plugins

### 组件 widgets

- 关于 about me [1]
- 日历 calendar [2]
- 返回页面顶部 Scrolltop [2]
- 微博秀 weibo show [3]

### 其他调整

- 去掉addthis和Disqus
- 添加多说 [1]
- 添加百度统计 [1] 和Google Analytics
原先一直用GA然后现在两个都用是打算对比一下。。
- 自动附上博客文章源码的github地址
- **添加social icons**
- 样式微调
- 字体微调 [1]

优化调整参考了：
[1] [jim-liu的优化版light theme](https://github.com/LiuJi-Jim/hexo-theme-light)
[2] [净土howiefh](https://github.com/howiefh/howiefh.github.io/)
[3] [微博开放平台](http://app.weibo.com/tool/weiboshow)

其他
-----
### 源代码管理

由于我用的github pages所以发布是会发布到gh-pages分支，而我用这个博客repo的master分支管理整个博客的源代码。这样就可以轻松的实现不同电脑的同步了。
本博客的源代码：https://github.com/wileam/code/

### 发布显示更多

在你觉得适合的位置插入

    <!-- more -->

就会将之前的部分生成摘要。点击”阅读全文“才会看到全文。

### YAML
hexo文章的头部文件是用[YAML](http://en.wikipedia.org/wiki/YAML)来写的，比如文章要同时标记多个tags，就需要用

    tags: [tag1, tag2]

或者

    tags:
    - tag1
    - tag2

这样的语法来写，详见YAML的[wikipedia](http://en.wikipedia.org/wiki/YAML).

### ejs和stylus

hexo是用的ejs和stylus。同样如果习惯用LESS之类也可以装相应的plugins.

ejs是embedded javascript，从js文件中抽取出html结构，使代码结构清晰简洁易读。(其实我还不太明白所以没怎么改ejs……)
文档存备用：https://code.google.com/p/embeddedjavascript/w/list

stylus是和less/sass类似的一个css processor，比原生的css更简洁一些。
同样文档存备用：http://learnboost.github.io/stylus/

### markdown

参见[markdown syntax](http://daringfireball.net/projects/markdown/syntax)，或者我之前的博客，[markdown语法](http://code.wileam.com/markdown-syntax/)

### 疑似bug

如果更新了css文件，那么需要把public的css文件删除，然后

    $ hexo deploy --generate

这样才会重新生成新的文件。我试了好几次都是这样，不知道是不是bug……

----
本文源码：https://github.com/wileam/code/blob/master/source/_posts/build-a-hexo-blog-and-optimize.md