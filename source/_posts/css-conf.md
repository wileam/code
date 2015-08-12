title: CSS CONF小记
date: 2015-01-21 22:05:40
category:
tags:
- conference
- css
- frontend
---

1月10号去北京参加了[CSS CONF](http://css.w3ctech.com/)中国首届CSS开发者大会，总体感觉还不错。了解了更多关于css未来可能的发展方向，现在的新技术，以及应用情况，不足之处可能是时间安排过于紧张，有些消化不了，以及后期由于时间紧张导致的没有互动和交流环节。

W3ctech已更新slides资料，见：http://www.w3ctech.com/topic/733

下面就挨个讲每个分享我记得的要点、感受及资料分享吧。

<!-- more -->

Bert Bos - The future of CSS
====
> Slides: http://www.w3.org/Talks/2015/0110-CSS-Beijing/

Bert Bos是CSS的联合创始人，也是重量级人物。这次主要就是介绍了W3C标准的工作流程，以及CSS未来的发展方向。

题外话：现场邀请了高博老师来翻译，之前w3ctech有个投票说是否需要翻译，80%＋是需要，但是其实现场说的很简单根本不需要翻译嘛（逃

### W3C的文稿状态：
WD: working draft草案
CR: Candidate Recommendation
PR: Proposed Recommendation
REC: Recommendation

这四种是从WD-CR-PR-REC的顺序，所以看到一个标准先看它目前所处的状态，一般越靠后越稳定。REC就是最终定稿了。

### level NOT version
扩展：level 3包括level2全部内容。
not change, only extent.
add new feature, not change existing one.

1994-1996: 1 spec.
1998: 1 spec.
1999+: 60 modules, each have independent level.

1999年之后一个重要的变化就是把整体的一个标准拆分成60个模块，每一个模块都有自己的level，也就是不存在CSS3、CSS4，只有某个处在CSS level 3的模块，或者是CSS level 1的模块。

### where does the w3c wg get ideas
- company: w3c members
- join other group.
- **join the w3c email group <www-style@w3.org>**
- conferences, personal communication i.e. w3c agenda

参与W3C的方式：1和2都需要公司层面的参与，3是所有人都可以加入邮件组，也是bert比较推荐的方式。另外中文也有一个邮件组，叫 W3C HTML5 中文興趣小組 <public-html-ig-zh@w3.org>，有兴趣的同学也欢迎加入。

### development areas
- 语音识别
- 电子书格式标准化 Pager
- GUI layout ( include user interaction)
- Graphics

### 总结
- CSS虽然已经18年了但仍然在活跃的开发中，是很有活力的语言
- 未来关注ebooks & paper books领域CSS标准的发展
- 打印排版的解决方式，尤其是非西方字体的排版，Bert也是呼吁中文开发者们需要加快行动，进行中文排版的优化。


winter 重识CSS
=========

计子winter老师用geek的方式去学习css，他觉得学习一个语言有三步：学习语法、学习表达式、如何去用。他期待看到的是一个css的语法的列表，表达式的列表，但现状是这些都是零散的散落在w3c的文档里。于是他拉取了css所有syntax和semantic的Json串……方便有一个整体的认识还有做二次开发。
（问了一下寒老师json地址，他说回头会放到github上。到时候再更新。

点头猪 移动时代CSS对用户体验的影响
======
> Slides: keynote http://pan.baidu.com/s/1mgA6Unu
PDF: http://pan.baidu.com/s/1dDo035n
PDF带注释：http://pan.baidu.com/s/1sjO9Olf

CSS女神前携程现平安付的点头猪分享了她的一些思考，台风很赞，有内容有深度思考也有恰到好处的幽默，强烈推荐。等视频出来也不要错过。

- 关于交互的很多细节和思考。
- 设计师工程师的职责划分。
	设计师和工程师不同的角色，以及开发者个人的知识结构的影响。理想状态大概是豆瓣的克军老师提到的“产品工程师”。
- CSS动画性能：招财猫的动画。



灭灭 豆瓣阅读在 WebFont 上的探索和实践
=========
> Slides: https://speakerdeck.com/houkanshan/web-fonts-at-douban-read （需翻墙）

灭灭是豆瓣阅读的前端，关注已久但是一直没见过。据说我在帝都的时候去open party那场他也在，只是当时我不知道。这回也算是终于见面了。

这场有蛮多干货，对web字体排版有兴趣的强烈推荐去看slides。但是讲的非常非常快，有点跟不上节奏。事后沟通得知是安排时间太紧张了，只有15分钟。很多对于文字处理的细节，非常细致到近乎处女座。下面只是简单记的几个问题，重点还是去看slides，制作也很精致。

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

见[caniuse](http://caniuse.com/#feat=flexbox)
兼容性还并不好，安卓4.4+, IE11 目前还无法广泛使用。

### flexbox原理

- flexbox宽度的计算：
flex-grow: 没有充满的时候充满宽度
flex-shrink: 超过宽度的时候缩小宽度
flex-basis:没有flex-grow和flex-shrink时的宽度

default:
flex: 1 0 auto;



hax（贺师俊） myth of css frameworks
=======
> Slides: http://johnhax.net/2015/myth-of-css-frameworks/

Hax的主题是对CSS框架的迷(pi)思(pan)，关于各种CSS的组织方式(OOCSS/SMACSS/ACSS/BEM)的思(pi)考(pan)。

这个问题其实我之前有蛮多思考，CSS本身不难，但涉及到命名、规范、可维护性，就变的复杂起来。Hax看了很多很多相关文章，其中不少我也看过。Hax用了很久来说BEM，OOCSS这些方案的缺陷，和css的初衷背离，得出的结论是semantic（语义化） css是没有意义的，只有semantic html。而这些实践事实上都是在解决一个block/widget/ui components层面的问题，这个问题有很多的方案，hax更认同的是html层面的，比如html5的一些自定义标签，role="xx"乃至未来的web components。而这个问题在实际中更加复杂，会受到项目历史的代码规范、工期等等的影响，BEM等方案并不能提高可维护性反而可能更差。

贺老的最终观点就是：
There's no such thing as semantic CSS. There's only semantic HTML and its visible form.

我觉得web components自然是很好的，可是目前我们还很不成熟，没办法投入生产，甚至h5的自定义标签使用也需要hack的引入一段js来兼容旧版浏览器。那么对于一个block/widget/ui components，总需要一种方式去解决，虽然bem很丑，但是它也是一种实践中比较有效的解决方案。避免了多层嵌套，实现了复用。至于过长的书写，也都有比较成熟的工具比如html中emmet+bem, css中scss/less+bem都可以大大的简化书写复杂度，实现了一个比较清晰的组件和较好的可维护性，同时并没有增加工作量。

所以我觉得在新项目中，之前没有代码规范的情况下，还是可以使用这些方式去组织css和html的，只要项目成员达成一致。我觉得可能任何方案都会有问题，重要的是总是要有一种相对统一的规范来解决问题。

（如有错误欢迎指出，求hax大神轻喷


一丝 CSS工作流
=====
> Slides: http://yisibl.github.io/share/css-workflow.html

因为之前一丝姐姐来我们部门分享过类似的内容，这里就主要是复习一下+听段子了。武大头传奇、百家讲坛什么的，简直23333……讲了CSS后处理器的一些原理，虽然我至今也没完全明白postcss和css-preprocessor比如scss/less的区别，我理解的css grace大概就是紧跟W3C标准，如果标准没有实现，那么css grace会给一个hack的实现。虽然在生产中还不打算使用，但是回头打算在demo或个人项目里尝试一下。

另外还提到了阿里妈妈那边对中文字体的处理 [Type.css](http://thx.github.io/cube/doc/type/)，也是针对中文做了一些优化。


尤雨溪 CSS与界面动效
==========
> Slides: http://feppt.qiniudn.com/浅谈CSS与web界面动效开发模式.pdf

前Google Creative Lab成员，Vue.js作者，尤小右。之前也来我厂做了vuejs的分享，这次的主题是关于界面动效的。有几点印象比较深的。

- 命令式 vs 声明式
命令式：如jQuery
声明式：状态和动画分离，易于维护。如Angular/Vue

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
web components标准的翻译：http://w3c-html-ig-zh.github.io/webcomponents/

勾股上场的时候离整场大会结束只剩20分钟了，于是噼里啪啦飞速的过了一遍还跳过了好多，见现场视频，之后又补录了一个视频把现场略过的章节细讲了一下。讲的很清楚，对web components有兴趣的严重推荐看视频。毕竟这是web可能的未来。

### web components
- 组件化
- 自定义标签
- 隐藏内部结构 shadow-dom


吴小倩 CSS动画性能
==========
> Slides: http://www.w3.org/2015/Talks/0109-CSSConf-xq/

之前都只是在邮件组里或者w3c的skype会议里听到小倩声音（很好听），这次见到真人，也是一个很美的小姑娘。她上场的时候只剩5分钟了几乎没什么时间，于是快速的过了一些CSS动画的demo，对比他们的速度和性能，主要是说做CSS动画的时候要避免repaint和reflow，这两个是比较耗性能的。

另外小倩还介绍了动画控制相关的新的API，[RequestAnimationFrame](http://www.w3.org/TR/animation-timing/) & [will-change](http://dev.w3.org/csswg/css-will-change/)。
