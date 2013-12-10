# Light-JimLiu

Hexo主题Light的修改版

**DEMO** @ [Jim Liu's Blog](http://blog.jimliu.net)

## 增加功能：

* 多说评论框——在`_config.yml`的`duoshuo`填写多说标识，或修改`_partial/duoshuo.ejs`
* 多说最新评论模块——`duoshuo_recent_comments`
* ABOUT ME模块——修改`_config.yml`中的about_me段落，或修改`_widget/about_me.ejs`
* Links模块——修改`_config.yml`中的`links`段落
* 百度统计——在`_partial/baidu_stats.ejs`中放入你的百度统计代码

## 默认去掉：

* twitter
* addthis

## 其他：

* 按中文习惯调整了一些字体
* 调整了引用块和代码块的样式细节
* 调整了文章中粗体字的颜色

# Light

Default theme for [Hexo].

## Install

Execute the following command and modify `theme` in `_config.yml` to `light`.

```
git clone git://github.com/tommy351/hexo-theme-light.git themes/light
```

## Update

Execute the following command to update Light.

```
cd themes/light
git pull
```

## Config

Default config:

``` yaml
menu:
  Home: /
  Archives: /archives

widgets:
- search
- category
- tag
- twitter

excerpt_link: Read More

twitter:
  username:
  show_replies: false
  tweet_count: 5

addthis:
  enable: true
  pubid:
  facebook: true
  twitter: true
  google: true
  pinterest: true

fancybox: true

google_analytics:
rss:
```

- **menu** - Main navigation menu
- **widget** - Widgets displaying in sidebar
- **excerpt_link** - "Read More" link text at the bottom of excerpted articles
- **twitter** - Twitter widget config
  - **username** - Twitter username
  - **show_replies** - Enable displaying replies
  - **tweet_count** - Tweets display in widget
- **addthis** - Share buttons at the buttom of articles (Powered by [AddThis])
  - **enable** - Enable share buttons
  - **pubid** - Profile ID of [AddThis]
  - **facebook** - Enable Facebook button
  - **twitter** - Enable Twitter button
  - **google** - Enable Google+ button
  - **pinterest** - Enable Pinterest button
- **fancybox** - Enable [Fancybox]
- **google_analytics** - Google Analytics ID
- **rss** - RSS subscription link (change if using Feedburner)

## Features

### Gallery Post

![](http://i.minus.com/ibp6Hbytwgof9y.jpg)

```
---
layout: photo
title: Gallery Post
photos:
- http://i.minus.com/ibobbTlfxZgITW.jpg
- http://i.minus.com/iedpg90Y0exFS.jpg
---
```

### Link Post

![](http://i.minus.com/i7hBbGqh14EWo.png)

```
---
layout: link
title: Link Post
link: http://www.google.com/
---
```

### Tweet Widget

![](http://i.minus.com/iMC8EyF9y0Y3y.PNG)

### Fancybox

![](http://i.minus.com/iHv7h7rZNqHvo.PNG)

[Hexo]: http://zespia.tw/hexo/
[AddThis]: https://www.addthis.com
[Fancybox]: http://fancyapps.com/fancybox/