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

<div align="center"><img width="65" height="75" src="https://filehole.github.io/images/posts/markdown/pangding-img.png"/></div>
```

**预览效果：**

**图片默认效果：**

![pangding](https://filehole.github.io/images/posts/markdown/pangding-img.png)

**修改后效果：**

<div align="center"><img width="65" height="75" src="https://filehole.github.io/images/posts/markdown/pangding-img.png"/></div>

## 格式化表格

表格在渲染之后很整洁好看，但是在文件源码里却可能是这样的：

```
|Header1|Header2|
|---|---|
|a|a|
|ab|ab|
|abc|abc|
```

不知道你能不能忍，反正我是不能忍。

好在广大网友们的智慧是无穷的，在各种编辑器里为 Markdown 提供了表格格式化功能，比如我使用 Vim 编辑器，就有 [vim-table-mode](https://github.com/dhruvasagar/vim-table-mode) 插件，它能帮我自动将表格格式化成这样：

```
| Header1 | Header2 |
|---------|---------|
| a       | a       |
| ab      | ab      |
| abc     | abc     |
```

是不是看着舒服多了？

如果你不使用 Vim，也没有关系，比如 Atom 编辑器的 [markdown-table-formatter](https://atom.io/packages/markdown-table-formatter) 插件，Sublime Text 3 的 [MarkdownTableFormatter](https://github.com/bitwiser73/MarkdownTableFormatter) 等等，都提供了类似的解决方案。

## 使用 Emoji

这个是 GitHub 对标准 Markdown 标记之外的扩展了，用得好能让文字生动一些。

示例代码：

```
我和我的小伙伴们都笑了。:smile:
```

示例效果：

我和我的小伙伴们都笑了。:smile:

更多可用 Emoji 代码参见 <https://www.webpagefx.com/tools/emoji-cheat-sheet/>。

## 行首缩进

直接在 Markdown 里用空格和 Tab 键缩进在渲染后会被忽略掉，需要借助 HTML 转义字符在行首添加空格来实现，`&ensp;` 代表半角空格，`&emsp;` 代表全角空格。

示例代码：

```
&emsp;&emsp;春天来了，又到了万物复苏的季节。
```

示例效果：

&emsp;&emsp;春天来了，又到了万物复苏的季节。

## 展示数学公式

如果是在 GitHub Pages，可以参考 <http://wanguolin.github.io/mathmatics_rending/> 使用 MathJax 来优雅地展示数学公式（非图片）。

如果是在 GitHub 项目的 README 等地方，目前我能找到的方案只能是贴图了，以下是一种比较方便的贴图方案：

1. 在 <https://www.codecogs.com/latex/eqneditor.php> 网页上部的输入框里输入 LaTeX 公式，比如 `$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$`；

2. 在网页下部拷贝 URL Encoded 的内容，比如以上公式生成的是 `https://latex.codecogs.com/png.latex?%24%24x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D%24%24`；

   ![](https://raw.githubusercontent.com/mzlogin/mzlogin.github.io/master/images/posts/markdown/latex-img.png)

3. 在文档需要的地方使用以上 URL 贴图，比如

   ```
   ![](https://latex.codecogs.com/png.latex?%24%24x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D%24%24)
   ```

   示例效果：

   ![](https://latex.codecogs.com/png.latex?%24%24x%3D%5Cfrac%7B-b%5Cpm%5Csqrt%7Bb%5E2-4ac%7D%7D%7B2a%7D%24%24)

## 任务列表

在 GitHub 和 GitLab 等网站，除了可以使用有序列表和无序列表外，还可以使用任务列表，很适合要列出一些清单的场景。

示例代码：

```
**购物清单**

- [ ] 一次性水杯
- [x] 西瓜
- [ ] 豆浆
- [x] 可口可乐
- [ ] 小茗同学
```

示例效果：

**购物清单**

- [ ] 一次性水杯
- [x] 西瓜
- [ ] 豆浆
- [x] 可口可乐
- [ ] 小茗同学

## 自动维护目录

有时候维护一份比较长的文档，希望能够自动根据文档中的标题生成目录（Table of Contents），并且当标题有变化时自动更新目录，能减轻工作量，也不易出错。

如果你使用 Vim 编辑器，那可以使用我维护的插件 [vim-markdown-toc](https://github.com/mzlogin/vim-markdown-toc) 来帮你完美地解决此事：

![](https://raw.githubusercontent.com/mzlogin/vim-markdown-toc/master/screenshots/english.gif)

插件地址：<https://github.com/mzlogin/vim-markdown-toc>

如果你使用其它编辑器，一般也能找到对应的解决方案，比如 Atom 编辑器的 [markdown-toc](https://atom.io/packages/markdown-toc) 插件，Sublime Text 的 [MarkdownTOC](https://packagecontrol.io/packages/MarkdownTOC) 插件等。

## 后话

好了，这一波的奇技淫巧就此告一段落，希望大家在了解这些之后能有所收获，更好地排版，专注写作。

如果你觉得本文对你有帮助，欢迎关注我的微信公众号 isprogrammer，获取更多有帮助的内容。

## 参考

* <https://raw.githubusercontent.com/matiassingers/awesome-readme/master/readme.md>
* <https://www.zybuluo.com/songpfei/note/247346>
