title: CSS CONF小记
date: 2015-01-21 22:05:40
category:
tags:
- conference
- css
- frontend
---

1月10号去北京参加了[CSS CONF](http://css.w3ctech.com/)中国首届CSS开发者大会，总体感觉还不错。了解了更多关于css未来可能的发展方向，现在的新技术，以及应用情况，不足之处可能是时间安排过于紧张，有些消化不了，以及后期由于时间紧张导致的没有互动和交流环节。

下面就挨个讲每个分享我记得的要点、感受及资料分享吧。

Bert Bos - The future of CSS
====
> Slides: http://www.w3.org/Talks/2015/0110-CSS-Beijing/

Bert Bos是CSS的联合创始人，也是重量级人物。这次主要就是介绍了W3C标准的工作流程，以及CSS未来的发展方向。

题外话：现场邀请了高博老师来翻译，之前w3ctech有个投票说是否需要翻译，80%＋是需要，但是其实现场说的很简单根本不需要翻译嘛（逃

以下是一些要点

### W3C的文稿状态：
WD: working draft草案
CR: Candidate Recommendation
PR: Proposed Recommendation
REC: Recommendation

### level NOT version
扩展：level 3包括level2全部内容，
not change, only extent.
add new feature, not change existing one.

1994-1996: 1 spec.
1998: 1 spec.
1999+: 60 modules, each have independent level.

### where does the w3c wg get ideas
- company: w3c members
- join other group.
- **join the w3c email group <www-style@w3.org>**
- conferences, personal communication i.e. w3c agenda

注：中文也有一个邮件组，是W3C HTML5 中文興趣小組 <public-html-ig-zh@w3.org>，有兴趣的欢迎加入。

### development areas
- 语音识别
- 电子书格式标准化 Pager
- GUI layout ( include user interaction)
- Graphics

### summary
- css is still active developed
- ebooks & paper books
	- partly replacing xsl: 处理电子书
- printing solutions
	- non-western typography:
		- Japanese layout: paved the way/
		- Indic layout in preparation
		- hangul layout ditto
		- Chinese layout: force about to start



winter（@寒泉） 重识CSS
=========
> Slides: 暂无

计子winter老师用geek的方式去学习css，于是拉取了css所有syntax和semantic的Json串……虽然winter老师后来没有给地址，但是我去github找到了这个gist：[CSS3标准和属性对应数据](https://gist.github.com/wintercn/5918272)……不知是不是最新版。

### Agenda
- learn syntax
- learn semantic
- learn to use



点头猪 移动时代CSS对用户体验的影响
======
> Slides: keynote http://pan.baidu.com/s/1mgA6Unu
PDF: http://pan.baidu.com/s/1dDo035n
PDF带注释：http://pan.baidu.com/s/1sjO9Olf

- 关于交互的很多细节和思考。
- 设计师工程师的职责划分。
	克军老师提到的产品工程师
- 动画性能



灭灭 豆瓣阅读在 WebFont 上的探索和实践
=========
> Slides: https://speakerdeck.com/houkanshan/web-fonts-at-douban-read （需翻墙）

很多干货，对字体排版有兴趣的强烈推荐去看slides。但是讲的非常非常快，有点跟不上节奏。事后沟通得知是安排时间太紧张了，只有15分钟。很多对于文字处理的细节，非常细致到近乎处女座。下面只是简单记的几个问题，重点还是去看slides，制作也很精致。

### Itatic Type
中文斜体的处理：楷体。

中英文混排时对italic type的处理，期望的效果：中文楷体，正体。英文斜体。

### bitmap
unicode-range: 强制对中文使用中文引号。

### Kerning
OpenType中也用到了kerning，来调整字符间距。

### 标点挤压
制作了一套标点挤压的字体Mojikumi。

解决方案：
**自己做字体，选取异常的字符做成字体，并且放在声明的最前面。**

### 坑
line-height
不同字体的base-line位置，ascend height和descend height不同。slides里面有各个系统的这些数据汇总表。

### hint
webfont替换本地字体 闪动

webfont无法加载，影响整个页面加载。如google font。
解决：检测加载，超时不加载，采用本地字体。

中文排版优化：[漢字標準格式](http://css.hanzi.co/)



Jaychsu Flexbox更优雅的布局
=====
> Slides: https://gitcafe.com/jaychsu/flex

### 功能

垂直居中的实现：

1 固定宽高的容器
parent:
```css
position:relative
```
child:
```css
position:absolute;
left:50%;
top:50%;
margin-left:-width/2;
margin-top:-height/2;
```

2
parent:
```css
text-align: center;
```

child:
```css
display:inline-block;
vertical-align:middle;
```

3 flexbox
```css
display:flexbox;
justify-content:center; //水平居中
align-items:center; //垂直居中
```

### 兼容性

### flexbox原理

－ flexbox宽度的计算：
flex-grow: 没有充满的时候充满宽度
flex-shrink: 超过宽度的时候缩小宽度
flex-basis:没有flex-grow和flex-shrink时的宽度

default:
flex: 1 0 auto;



hax（贺师俊） myth of css frameworks
=======
> Slides: http://johnhax.net/2015/myth-of-css-frameworks/

这个问题其实我之前有蛮多思考，CSS本身不难，但涉及到命名、规范、可维护性，就变的复杂起来。Hax看了很多很多相关文章，其中不少我也看过。Hax用了很久来说BEM，OOCSS这些方案的缺陷，和css的初衷背离，得出的结论是semantic（语义化） css是没有意义的，只有semantic html。而这些实践事实上都是在解决一个block/widget/ui components层面的问题，这个问题有很多的方案，hax更认同的是html层面的，比如html5的一些自定义标签，role="xx"乃至未来的web components。而这个问题在实际中更加复杂，会受到项目历史的代码规范、工期等等的影响，BEM等方案并不能提高可维护性反而可能更差。

贺老的最终观点就是：
There's no such thing as semantic CSS. There's only semantic HTML and its visible form.

我觉得web components自然是很好的，可是目前我们还很不成熟，没办法投入生产，甚至h5的自定义标签使用也需要hack的引入一段js来兼容旧版浏览器。那么对于一个block/widget/ui components，总需要一种方式去解决，虽然bem很丑，但是它也是一种实践中比较有效的解决方案。避免了多层嵌套，实现了复用。至于过长的书写，也都有比较成熟的工具比如html中emmet+bem, css中scss/less+bem都可以大大的简化书写复杂度，实现了一个比较清晰的组件和较好的可维护性，同时并没有增加工作量。

所以我觉得在新项目中，之前没有代码规范的情况下，还是可以使用这些方式去组织css和html的，只要项目成员达成一致。我觉得可能任何方案都会有问题，重要的是总是要有一种相对统一的规范来解决问题。

（如有错误欢迎指出，求hax大神轻喷


一丝 CSS工作流
=====
> Slides: 暂无

CSS Reset
CSS后处理器－写面向未来的CSS
中文字体的处理 [Type.css](http://thx.github.io/cube/doc/type/)


尤雨溪 CSS与界面动效
==========
> Slides: 暂无



- 命令式 vs 声明式
命令式：jquery
声明式：状态和动画分离，易于维护。ng/vue

- JS vs CSS 动画
JS：逐帧渲染
CSS: 避免触发reflow，repaint

- 动画 可能的未来：
- http://famo.us/
- [web-animations at polymer](https://www.polymer-project.org/platform/web-animations.html)


勾三股四（@勾股） web components
============
> **Slides**: http://jiongks.name/slides/css-scoping/ (勾股：由于本人比较骚包急于秀一下新技术，所以需要支持webcomponents的浏览器才可以正常打开，比如Chrome 36+)
**Video**: 现场 http://www.tudou.com/programs/view/8bvwGHaL6T4/
补充：http://www.tudou.com/programs/view/dz4aXjDFnLw/

勾股上场的时候离整场大会结束只剩20分钟了，于是噼里啪啦飞速的过了一遍还跳过了好多，见现场视频，之后又补录了一个视频把现场略过的章节细讲了一下。讲的很清楚，对web components有兴趣的严重推荐看视频。毕竟这是web可能的未来。

### web components
- 组件化
- 自定义标签
- 隐藏内部结构 shadow-dom


小倩 CSS动画性能
==========
> Slides: 暂无

之前都只是在邮件组里或者w3c的skype会议里听到小倩声音（很好听），这次见到真人，也是一个很美的小姑娘。她上场的时候只剩5分钟了几乎没什么时间，于是快速的过了一些CSS动画的demo，对比他们的速度和性能，主要是说做CSS动画的时候要避免repaint和reflow，这两个是比较耗性能的。