title: 一些前端面试题
date: 2014-02-15 17:22:01
tags:
- frontend
- interview
- career
category: frontend

---

前一阵时间找工作，面试了一些公司，这里也总结一下遇到的前端技术相关的问题，做个记录，也看看自己缺那块，以后要往什么方向继续努力。以下面试题都不指明公司名称了。

## Html/CSS方面

<!-- more -->

- ** IE有几种渲染模式？ **

答：标准模式(Standards mode)和兼容模式(Quirks mode)。

详见：https://developer.mozilla.org/en-US/docs/Quirks_Mode_and_Standards_Mode

- ** 遇到过IE 6/7 下元素消失的情况吗？ **

所有IE低版本兼容相关问题都被我忽略了，真心没怎么处理过。硬伤。 TT

后来查了些资料，大概是IE6/7下绝对定位元素的bug。

详见：http://www.positioniseverything.net/explorer/ienondisappearcontentbugPIE/index.htm

- ** CSS怎么实现相对定位？ **

答：父元素<code>position:relative</code> 子元素 <code>position:absolute</code>

- ** <code>inline-block</code>和<code>Float</code>的对比，优缺点，如何选择。 **

答：<code>inline-block</code>需要处理空白问题，<code>float</code>需要清除浮动。

参考链接：

[1] [CSS display: inline-Block: Why It Rocks, And Why It Sucks](http://robertnyman.com/2010/02/24/css-display-inline-block-why-it-rocks-and-why-it-sucks/)

[2] [About inline-blocks](http://webdesigner-webdeveloper.com/weblog/about-inline-blocks/)

[3] [What is inline-block](http://www.impressivewebs.com/inline-block/)

[4] [CSS Float Theory: Things You Should Know](http://coding.smashingmagazine.com/2007/05/01/css-float-theory-things-you-should-know/)

- ** 清除浮动的方式，优缺点。 **

见：

[1] http://www.quirksmode.org/css/clearing.html

[2] http://www.positioniseverything.net/easyclearing.html

- ** 对响应式设计的理解。 **

- ** 用CSS实现三角形。 **

见：[CSS Triangle](http://css-tricks.com/snippets/css/css-triangle/)

##　JS/jQuery方面：

- ** <code>document.ready</code>和<code>window.onload</code>有什么区别？ **

答得不好，查了下资料，是酱紫：document.ready 是DOM加载完毕，onload是所有页面元素加载完毕。onload比ready晚一些。

见：http://stackoverflow.com/questions/3698200/window-onload-vs-document-ready

- ** 了解哪些前端的MVC，怎么理解前端MVC？ **

- ** 用jQuery如何选择一个元素的兄弟节点？ **

- ** 关于Ajax回调函数的。 **

- ** 写一个slides的效果。 **

## 综合/其他：

- ** 有哪些熟悉的前端html/css框架？ **

- ** 如果让你从头开始搭建一个类似Bootstrap的框架，你会怎么实现？ **

- ** Git里删除一个远程分支的命令是？ **

答：这个问题好坑爹，我回答是<code>git branch -d origin branch-name</code>，回头一查应该是<code>git push origin :branch-name</code>

- ** 平时关注哪些站点，从什么渠道获得资讯？ **

- ** 最近读过的一篇印象最深的文章 **

- ** 对代码风格的理解。 **


说些题外话，其实面试是一个双向选择，从面试题也可以看出一个公司的风格，侧重点。这样就可以考虑一下和你自己想要的方向是否一致，环境氛围是否契合。在一个舒服的契合的环境里工作，至少对我还是非常重要的。


----
本文源码：https://github.com/wileam/code/blob/master/source/_posts/front-end-interview.md