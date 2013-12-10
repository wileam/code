title: markdown-exercise
date: 2013-12-11 01:12:44
tags: [markdown, syntax]
---
Markdown学习练习笔记/兼文档

## 标题 HEADERS

### 一级标题 H1
    # 一级标题 H1
    
    一级标题第二种写法 H1
    ===========
    
### 二级标题 H2
    ## 二级标题 H2
    
    二级标题第二种写法 H2
    
    ### H3

### 引用 Blockquotes
    > Smile, breathe and go slowly.

## 列表 LIST

### 无序列表 Unordered lists
	- 第一点
	- 第二点

### 有序列表 Ordered lists

    3. 第一点
    2. 第二点

*有趣的是这里前面的数字不重要，无论写什么数字都会生成从1开始递增的有序列表。比如我上面这个例子。会生成。*

3. 第一点
2. 第二点
    

*to be continued*

reference: [markdown syntax](http://daringfireball.net/projects/markdown/syntax)
点此查看：[文章源码](https://raw.github.com/wileam/code/master/source/_posts/markdown-exercise.md)

**题外话**
hexo支持markdown语法，而hexo本身是要求用[YAML](http://en.wikipedia.org/wiki/YAML)来写的，比如文章要同时标记多个tags，就需要用

    tags: [tag1, tag2]

这样的语法来写，倒是和JSON有点儿像。 :)