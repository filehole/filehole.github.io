---
layout: post
title: Markdown 的不定期更新
categories: Markdown
description: 介绍 Markdown 的一些高级用法或好玩的特性。
keywords: Markdown, 高阶
---

本文将会介绍一些 Markdown 的扩展语法，或者好玩的特性，希望大家也都能在自己写博客中寻找到只属于自己的快乐。
很多技巧是基于 GitHub 来利用兼容 HTML 的特性来实现。

> 当你老了
>
> 回顾一生
>
> 眼见风云千樯
>
> 还以为那是生命中普通的一天

## 在表格单元格里换行

借助于 HTML 里的 `<br />` 实现。

**Markdown 代码：**

```
| Header1 | Header2                          |
|---------|----------------------------------|
| item 1  | 1. one<br />2. two<br />3. three |
```

**预览效果：**

| Header1 | Header2                          |
|---------|----------------------------------|
| item 1  | 1. one<br />2. two<br />3. three |

## 图文混排

使用 `<img>` 标签来贴图，然后指定 `align` 属性。

**Markdown 代码：**：

```
<img align="right" src="https://filehole.github.io/images/posts/markdown/pangding-img.png"/>

这是一个胖丁的图片。

图片显示在文字的右边。

> 姓名：胖丁
>
> 外貌：胖丁是圆形的粉色球状神奇宝贝，有小的猫耳和大眼睛。
> 
> 身高：0.5m
>
> 体重：5.5kg
>
> HP：115
>
> 攻击：45
>
> 防御：20
>
> 速度：20

本行延伸到了图片的正下方，所以这个时候就可以看到这段话延伸在图片的下方的效果了。
```

**预览效果：**

<img align="right" src="https://filehole.github.io/images/posts/markdown/pangding-img.png"/>

这是一个胖丁的图片。

图片显示在文字的右边。

> 姓名：胖丁
>
> 外貌：胖丁是圆形的粉色球状神奇宝贝，有小的猫耳和大眼睛。
> 
> 身高：0.5m
>
> 体重：5.5kg
>
> HP：115
>
> 攻击：45
>
> 防御：20
>
> 速度：20

本行延伸到了图片的正下方，所以这个时候就可以看到这段话延伸在图片的下方的效果了。

## 控制图片大小和位置

标准的 Markdown 图片标记 `![]()` 无法指定图片的大小和位置，只能默认的图片大小，居左。

但如果什么都不能控制，还怎么满足程序员的控制欲呢，图片居中可以使用 `<div>` 标签加 `align` 属性来控制，图片宽高则用 `width` 和 `height` 来控制。

**Markdown 代码：**：

```
**图片默认效果：**

![pangding](https://filehole.github.io/images/posts/markdown/pangding-img.png)

**修改后效果：**

<div align="center"><img width="192" height="256" src="https://filehole.github.io/images/posts/markdown/pangding-img.png"/></div>
```

**预览效果：**

**图片默认效果：**

![pangding](https://filehole.github.io/images/posts/markdown/pangding-img.png)

**修改后效果：**

<div align="center"><img width="192" height="256" src="https://filehole.github.io/images/posts/markdown/pangding-img.png"/></div>

## 格式化表格

虽然 Markdown 的表格在渲染之后很整齐，但是在文件源码里你读到却可能是这样的：

```
| 级别  | 姓名 | 组织 | 技能 |
| :----- | :-----  | :----- | :----- |
| 上忍     | 旗木卡卡西       | 火之国木叶         | 雷切         |
| 影     | 宇智波鼬       | 晓         | 天照         |
| 影     | 大蛇丸       | 音忍村         | 禁术·秽土转生         |
| 下忍     | 漩涡鸣人       | 火之国木叶         | 多重影分身         |
```

相信很多人都是不能忍的。

好在我们程序员是战无不胜的，在各种编辑器里都为 Markdown 提供了表格格式化功能：
* Vim 编辑器，[vim-table-mode](https://github.com/dhruvasagar/vim-table-mode)
* Atom 编辑器，[markdown-table-formatter](https://atom.io/packages/markdown-table-formatter)
* Sublime Text 3，[MarkdownTableFormatter](https://github.com/bitwiser73/MarkdownTableFormatter)

格式化后就像这样

```
| 级别   | 姓名       | 组织       | 技能          |
| :----- | :-----     | :-----     | :-----        |
| 上忍   | 旗木卡卡西 | 火之国木叶 | 雷切          |
| 影     | 宇智波鼬   | 晓         | 天照          |
| 影     | 大蛇丸     | 音忍村     | 禁术·秽土转生 |
| 下忍   | 漩涡鸣人   | 火之国木叶 | 多重影分身    |
``` 

## 行首缩进

Markdown 里用空格和 Tab 键的缩进在渲染后会被忽略，所以需要借助 HTML 转义字符来实现，`&ensp;` 代表半角空格，`&emsp;` 代表全角空格。

示例代码：

```
&emsp;&emsp;你固定在哪一站上车？在哪一站下车？有人会在地下铁出口等你吗？
```

示例效果：

&emsp;&emsp;你固定在哪一站上车？在哪一站下车？有人会在地下铁出口等你吗？

## 自动维护目录

时候维护一份比较长的文档，希望能够自动根据文档中的标题生成目录（Table of Contents），并且当标题有变化时自动更新目录，能减轻工作量，也不易出错。

* Vim 编辑器，[vim-markdown-toc](https://github.com/mzlogin/vim-markdown-toc) 
* Atom 编辑器，[markdown-toc](https://atom.io/packages/markdown-toc) 
* Sublime Text，[MarkdownTOC](https://packagecontrol.io/packages/MarkdownTOC)

## 写在最后

这波更新就暂时到此，希望对大家有所帮助，可以更专注于自己的作品。
