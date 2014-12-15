title: 升级hexo的一些坑
date: 2014-08-24 01:46:13
category:
tags:
---

好久不用博客，转眼升级的时候已经各种报错了。原来hexo已经到了2.8.2版本，并且各种各种不兼容啊。

<!-- more -->


## 报错一 `HexoError`：

```sh
[error] { name: 'HexoError',
reason: 'incomplete explicit mapping pair; a key node is missed',
mark:
{ name: null,
buffer: 'categories: Kategorien\nsearch: Suche\ntags: Tags\ntagcloud: Tag-C
loud\ntweets: Tweets\nprev: Vorherige Seite\nnext: Nächste Seite\ncomment: Komm
entare\narchive_a: Archiv\narchive_b: Archiv: %s\npage: Seite %d\nrecent_posts:
Neueste Artikel\n\u0000',
position: 180,
line: 9,
column: 17 },
message: 'Process failed: languages/de.yml',
domain:
{ domain: null,
_events: { error: [Function] },
_maxListeners: 10,
members: [ [Object] ] },
domainThrown: true,
stack: undefined }
```

原因：
YAML格式规则改变，有空格的项都需要加上双引号。

`tag cloud` --> `"tag cloud"`

解决方法：
将主题language下的有空格的项都需要加上双引号。

如果用的默认主题light，可以直接拉取最新主题，覆盖language文件夹即可。

```sh
$ git clone https://github.com/tommy351/hexo-theme-light themes/light
```

## 更新plugins

安装升级后必须的plugins:

```sh
$ (sudo) npm install hexo-renderer-ejs --save
$ (sudo) npm install hexo-renderer-marked --save
$ (sudo) npm install hexo-renderer-stylus --save
```

完成后的package.json类似这样：

```json
{
  "name": "hexo",
  "version": "2.8.2",
  "private": true,
  "dependencies": {
    "hexo-generator-feed": "^0.2.0",
    "hexo-generator-sitemap": "0.0.6",
    "hexo-renderer-ejs": "^0.1.0",
    "hexo-renderer-marked": "^0.1.0",
    "hexo-renderer-stylus": "^0.1.0"
  }
}
```

这样之后应该就大功告成了。若有其他报错，可去hexo的[github页面](https://github.com/hexojs/hexo)找一下issue或者提新的issue。作者大多都会解答。

以上。Happy blogging. :)


----
本文源码：https://github.com/wileam/code/blob/master/source/_posts/update-hexo.md