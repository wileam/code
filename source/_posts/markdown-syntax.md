title: markdown语法
date: 2013-12-11 01:12:44
tags:
- markdown
- syntax
- translate
categories: other

---
Markdown学习练习笔记/兼文档

哲学 philosophy
---------

咳咳。简单说就是“易读”，“易写”。

> Markdown is intended to be as easy-to-read and easy-to-write as is feasible.

<!-- more -->

## 标题 HEADERS

### 一级标题 H1

    # 这是一个一级标题 header1

    这还是一个一级标题 header1
    ===========

### 二级标题 H2

    ## 这是一个二级标题 H2

    这还是一个二级标题 H2
    --------

### 三级-六级标题

    ### 三级标题 H3
    ……
    ###### 六级标题 H6

只有一种写法了。

## 引用 Blockquotes
    > Smile, breathe and go slowly.

> Smile, breathe and go slowly.

## 列表 LIST

### 无序列表 Unordered lists
	- 第一点
	- 第二点

- 第一点
- 第二点

### 有序列表 Ordered lists

	3. 第一点
	2. 第二点

*有趣的是这里前面的数字不重要，无论写什么数字都会生成从1开始递增的有序列表。比如我上面这个例子。会生成。*

3. 第一点
2. 第二点

## 链接

### 行内式

    [曼珠沙华](http://blog.wileam.com/ "生活博客")

[曼珠沙华](http://blog.wileam.com/ "生活博客")

### 参考式

    [曼珠沙华][1], [技术博客][2]
    [1]: http://blog.wileam.com/ "(此处可选)生活博客"
    [2]: http://code.wileam.com/ "(此处可选)技术博客"

[曼珠沙华][1], [技术博客][2]
[1]: http://blog.wileam.com/ "(此处可选)生活博客"
[2]: http://code.wileam.com/ "(此处可选)技术博客"

注意最下面的参考链接是直接不会出现的。

## 代码块 CODE BLOCKS

缩进 4spaces/1Tab。

    <div class="container">
        <div class="row">
            <div class="span4"></div>
            <div class="span8"></div>
        </div>
    </div>

## 加粗/斜体 EMPHASIS

    **加粗**
    *斜体*

**加粗**
*斜体*

## 图像 IMAGES

###行内式

    ![Avatar](../uploads/avatar.jpg "Optional title")

![Avatar](../uploads/avatar.jpg "Optional title")

### 参考式

    ![Avatar-gavatar][3]
    [3]: ../uploads/avatar.jpg "(optional)avatar-1"

![Avatar-gavatar][3]
[3]: ../uploads/avatar.jpg "(optional)avatar-1"

目前markdown还不能更改大小，如果需要设置宽高需要写html \<img\>代码。

其他
--------

### 电子邮件 email

    <abc@gmail.com>

<abc@gmail.com>

### 反斜杠

    \*我就是想显示星号不想斜体\*

\*我就是想显示星号不想斜体\*

----
reference: [markdown syntax](http://daringfireball.net/projects/markdown/syntax)
本文源码：https://github.com/wileam/code/blob/master/source/_posts/markdown-syntax.md