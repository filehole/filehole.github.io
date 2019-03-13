---
layout: post
title: Markdown 笔记与教程
categories: Markdown
description: 快速学习 Markdown 语法
keywords: Markdown, 入门
---

本博客建设在 `github.io` 上，相关页面都是基于 Markdown 语法描述，所以这里也分享下关于 Markdown 的基本语法与常用技巧，后续会不定期更新，持续补充些个人经验。

---

我大概是在2015年左右接触到 Markdown 的，当时受够了纸质版笔记本总是扔在不同的地方，想用的时候又常常不能接着上回使用的地方，往往只能换个新的，回顾信息也不是很方便；而「有道云笔记」与『印象笔记」调整格式又不是很方便，当然这两款工具我也一直在使用，不过是使用场景不同罢了。调研了当时很多的工具，最终选取了 Markdown，本地使用的软件是 `Cmd Markdown`。最主要的原因就是好学，快速上手，如果只是简单使用的话可以 10 分钟内了解基本语法，同时搭配各类工具和网站的集成，也可以轻松支持如文档分享，多人协作等功能。
这是我自己本地的 Markdown 截图，基本每日工作记录，复盘与脑洞，以及个人学习记录，游戏心得等都可以通过它记录的。
![](/images/posts/markdown/cmd-markdown.png)

关于 Markdown 的「定义」：

> Markdown 是一种轻量级标记语言，创始人为 John Gruber。
> 它允许人们「使用易读易写的纯文本格式编写文档，然后转换成有效的 XHTML（或者 HTML）文档」。
>                                              ————维基百科

**目录**

* TOC
{:toc}

## 背景

### 特点

1. 快速上手，语法简单，同时满足基础的排版需求，符合直男审美。

2. 纯文本，易于管理与版本控制，可以轻松看到预览环境，方便调试。

3. 可以更专注于文字与内容本身，周边再也不会有什么「小短裙8折」之类的小广告。

### 使用场景

* 各类代码托管平台

    主流的代码托管平台，如 GitHub、GitLab、BitBucket、Coding、Gitee 等，都已经支持 Markdown 语法；很多开源项目的 README、开发文档、帮助文档、Wiki 等也都是用 Markdown 编写的。

* 技术社区、写作平台、论坛

    StackOverflow、CSDN、掘金、简书、GitBook、有道云笔记等，大量资源分享型网站也都支持。

* 个人使用

    比如我就在本地完成每日工作记录与规划，大事记，to-do list等。

当然就像 Android 系统一样，各家平台可能采用不同语言实现 Markdown 解析引擎，也经常存在不同程度的定制与扩展，这导致同一种写法在不同平台上体验并不完全一致。对于「强迫症患者」就经常花很长时间来调试排版，不过幸好已经形成一些公认的标准语法。

### 编辑工具

理论上任何一款文本编辑器都能用于编辑 Markdown 文档，还是看个人喜好与习惯吧，个人经验是熟练度的加成可以完爆所有工具上功能点的不完善，只不过上手度往往觉得很多人的熟练度加成。

* 现代编辑器

    VSCode / Atom

* 传统编辑器

    Vim / Emacs / Sublime Text / Notepad++

* IDE 自带编辑器

    IntelliJ IDEA / Android Studio / WebStorm

* 专用编辑器

    Ulysses / Mou / Typora / Markpad

* 在线编辑器

    各种支持 Markdown 的网站都提供了在线编辑器，在这里安利下 [Prose](https://prose.io/) 可以在线预览 github 上的 `.md` 文件，十分好用

## 基本语法

### 标题

**Markdown 语法：**

```
# atx-style 一级标题

## 二级标题

###### 六级标题

Setext-style 一级标题
===

二级标题
---
```

**预览效果：**

> # atx-style 一级标题
> 
> ## 二级标题
> 
> ###### 六级标题
>
> Setext-style 一级标题
> ===
>
> 二级标题
> ---

**对应 HTML：**

```html
<h1>atx-style 一级标题</h1>

<h2>二级标题</h2>

<h6>六级标题</h6>

<h1>Setext-style 一级标题</h1>

<h2>二级标题</h2>
```

### 段落

中间没有空行的连续不断的几行文字被视为一个段落。

**Markdown 语法：**

```
美人卷珠帘，

深坐颦蛾眉。
（句号后面没空格）

但见泪痕湿，

不知心恨谁。  
（句号后面有俩空格）
```

**预览效果：**

美人卷珠帘，

深坐颦蛾眉。
（句号后面没空格）

但见泪痕湿，

不知心恨谁。  
（句号后面有俩空格）

**对应 HTML：**

```html
<p>美人卷珠帘，</p>

<p>深坐颦蛾眉。
（句号后面没有空格）</p>

<p>但见泪痕湿，</p>

<p>
  不知心恨谁。
  <br>
  （句号后面有俩空格）
</p>
```

### 行内格式

对段落或者部分文本的强调效果。

**Markdown 语法：**

```
选中部分**加黑**

选中部分*斜体*
```

**预览效果：**

选中部分**加黑**

选中部分*斜体*

**对应 HTML：**

```html
<p>
  选中部分
  <strong>加黑</strong>
</p>
<p>
  选中部分
  <em>斜体</em>
</p>
```

### 引用块

**Markdown 语法：**

```
> 引用块 段落一
>
> 引用块 段落二
>> 引用块 段落二 内嵌引用块
>
> ### 引用块 标题
```

**预览效果：**

> 引用块 段落一
>
> 引用块 段落二
>
>> 引用块 段落二 内嵌引用块
>
> ### 引用块 标题

**对应 HTML：**

```html
<blockquote>
  <p>引用块 段落一</p>
  <p>引用块 段落二</p>
  <blockquote>
    <p>引用块 段落二 内嵌引用块</p>
  </blockquote>
  <h3 id="引用块 标题">引用块 标题</h3>
</blockquote>
```

### 超链接

Markdown 支持行内式链接和引用式链接。

**Markdown 语法：**

```
行内式 [GitHub](https://github.com/filehole) 链接。

行内式 带 title，[博客](https://filehole.github.io "文件洞的个人博客") 链接。

引用式 [博客][1] 链接。

引用式 带 title，[GitHub][2] 链接。

[1]: https://filehole.github.io
[2]: https://github.com/filehole "我的 GitHub 主页"
```

**预览效果：**

行内式 [GitHub](https://github.com/filehole) 链接。

行内式 带 title，[博客](https://filehole.github.io "文件洞的个人博客") 链接。

引用式 [博客][1] 链接。

引用式 带 title，[GitHub][2] 链接。

[1]: https://filehole.github.io
[2]: https://github.com/filehole "我的 GitHub 主页"

**对应 HTML：**

```html
<p>行内式 <a href="https://github.com/filehole">GitHub</a> 链接。</p>

<p>行内式 带 title，<a href="https://filehole.github.io" title="文件洞的个人博客">博客</a> 链接。</p>

<p>引用式 <a href="https://filehole.github.io">博客</a> 链接。</p>

<p>引用式 带 title，<a href="https://github.com/filehole" title="我的 GitHub 主页">GitHub</a> 链接。</p>
```

### 图片

在超链接的写法前加一个 `!`，就是引用图片的方法。

**Markdown 语法：**

```
![Alt text](https://filehole.github.io/favicon.ico "favicon")
```

**预览效果：**

![Alt text](https://filehole.github.io/favicon.ico "favicon")

**对应 HTML：**

```html
<img src="https://filehole.github.io/favicon.ico" alt="Alt text" title="favicon">
```

### 列表

包括有序列表和无序列表。

**Markdown 语法：**

```
- 秦朝
- 汉朝
- 唐朝

1. 秦朝
2. 汉朝
3. 唐朝
```

**预览效果：**

- 秦朝
- 汉朝
- 唐朝

1. 秦朝
2. 汉朝
3. 唐朝

**对应 HTML：**

```html
<ul>
  <li>秦朝</li>
  <li>汉朝</li>
  <li>唐朝</li>
</ul>
<ol>
  <li>秦朝</li>
  <li>汉朝</li>
  <li>唐朝</li>
</ol>
```

无序列表的标记可以使用 `+`、`-` 或 `*`，有序列表前的数字可以是乱序的。

### 代码块

支持行内代码和代码块。

**Markdown 语法：**

    Python 里使用 `requests` 包的 `requests.get()` 方法来获取返回数据。

    ```python
    import requests
    from bs4 import BeautifulSoup
    html = requests.get(current_url)
    soup = BeautifulSoup(html.text, 'html.parser')
    ```

**预览效果：**

Python 里使用 `requests` 包的 `requests.get()` 方法来获取返回数据。

```python
import requests
from bs4 import BeautifulSoup
html = requests.get(current_url)
soup = BeautifulSoup(html.text, 'html.parser')
```

**对应 HTML：**

```html
<p>Python 里使用 <code>requests</code> 包的 <code>requests.get()</code> 方法来获取返回数据。</p>

<div class="highlight highlight-source-python">
  <pre>
    <span class="pl-k">import</span> 
    (<span class="pl-smi">TextUtils</span>
    <span class="pl-k">.</span>isEmpty(text)) {
    <span class="pl-k">return</span> <span class="pl-c1">null</span>;}
  </pre>
</div>
```

上例中的语言标记 `java` 可选填，可用于在编辑器和渲染后的效果里添加语法高亮。

块式代码也可以对整个代码段缩进四个空格，或一个 Tab 来实现。

### 水平分割线

使用一个单独行里的三个或以上 `*`、`-` 来生产一条水平分割线，它们之间可以有空格。

**Markdown：**

```
***

-----

- - -
```

**预览效果：**

***

-----

- - -

**对应 HTML：**

```
<hr />

<hr />

<hr />
```

### 嵌入 HTML

Markdown 标记语言的目的不是替代 HTML，也不是发明一种更便捷的插入 HTML 标签的方式。它对应的只是 HTML 标签的一个很小的子集。

对于那些没有办法用 Markdown 语法来对应的 HTML 标签，直接使用 HTML 来写就好了。

## 扩展语法

本节的内容是介绍一些受到广泛支持的 Markdown 扩展语法。

### 表格

**Markdown：**

    | 编号  | 姓名（左） | 年龄（右） | 性别（中） |
    | ----- | :--------  | ---------: | :------:   |
    | 0     | 张三       | 28         | 男         |
    | 1     | 李四       | 29         | 男         |

**预览效果：**

| 编号  | 姓名（左） | 年龄（右） | 性别（中） |
| ----- | :--------  | ---------: | :------:   |
| 0     | 张三       | 28         | 男         |
| 1     | 李四       | 29         | 男         |

**对应 HTML：**

```html
<table>
  <thead>
    <tr>
      <th>编号</th>
      <th align="left">姓名（左）</th>
      <th align="right">年龄（右）</th>
      <th align="center">性别（中）</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td align="left">张三</td>
      <td align="right">28</td>
      <td align="center">男</td>
    </tr>
    <tr>
      <td>1</td>
      <td align="left">李四</td>
      <td align="right">29</td>
      <td align="center">男</td>
    </tr>
  </tbody>
</table>
```

### 任务列表

在 GitHub / GitLab 里有较好的支持。

**Markdown：**

```
- [x] 洗碗
- [ ] 清洗油烟机
- [ ] 拖地
```

**预览效果：**

- [x] 洗碗
- [ ] 清洗油烟机
- [ ] 拖地

**对应 HTML：**

```html
<ul class="contains-task-list">
  <li class="task-list-item"><input type="checkbox" id="" disabled="" class="task-list-item-checkbox" checked=""> 洗碗</li>
  <li class="task-list-item"><input type="checkbox" id="" disabled="" class="task-list-item-checkbox"> 清洗油烟机</li>
  <li class="task-list-item"><input type="checkbox" id="" disabled="" class="task-list-item-checkbox"> 拖地</li>
</ul>
```

如果是在 GitHub / GitLab 的 Issue 里，会附赠任务完成比例提示效果：

![task list 1](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/task-list-1.png)

还可以直接在网页上拖动调整顺序，勾选和取消勾选。

![task list 2](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/task-list-2.png)

### 删除线

**Markdown：**

```
后面三个字打上~~删除线~~。
```

**预览效果：**

后面三个字打上~~删除线~~。

**对应 HTML：**

```html
<p>后面三个字打上<del>删除线</del>。</p>
```

### 自动链接

自动链接扩展，即：当识别到 URL，或用 `<`、`>` 包括的 URL 时，会自动为其生成 `a` 标签。

**Markdown：**

```
https://github.com

<example@gmail.com>
```

**预览效果：**

https://github.com

<example@gmail.com>

**对应 HTML：**

```html
<p><a href="https://github.com">https://github.com</a></p>

<p><a href="mailto:example@gmail.com">example@gmail.com</a></p>
```

### emoji

以 GitHub Pages 为例。

**Markdown：**

```
:camel: :blush: :smile:
```

**预览效果：**

:camel: :blush: :smile:

**对应 HTML：**

```html
<p>
  <img class="emoji" title=":camel:" alt=":camel:" src="https://assets-cdn.github.com/images/icons/emoji/unicode/1f42b.png" height="20" width="20">
  <img class="emoji" title=":blush:" alt=":blush:" src="https://assets-cdn.github.com/images/icons/emoji/unicode/1f60a.png" height="20" width="20">
  <img class="emoji" title=":smile:" alt=":smile:" src="https://assets-cdn.github.com/images/icons/emoji/unicode/1f604.png" height="20" width="20">
</p>
```

## 奇技淫巧

脑洞清奇的工程师们还发掘了很多使用 Markdown 的方法，大部分都是引入第三方 JavaScript 插件来实现。对这部分我只做简述，对其中的部分功能比如作图等，还是推荐用专门的可视化工具去做。

### 画流程图和时序图

有部分网站和编辑器实现了对 Markdown 里流程图和时序图的支持，比如我们使用的项目管理工具 TAPD 的在线编辑器，还有 VSCode + 插件 Markdown Preview Enhanced 等。

以我们使用的项目管理工具 TAPD 的在线编辑器为例：

![流程图](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/tapd-markdown-flowchart.png)

![时序图](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/tapd-markdown-seq.png)

### 插入数学公式

仍然以 TAPD 为例：

![数学公式](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/tapd-markdown-math.png)

应该是利用 JavaScript 支持了 LaTeX 公式语法。

### 用 Markdown 做 PPT

有专门的工具 [Marp](https://github.com/yhatt/marp)，另外使用 VSCode + 插件 Markdown Preview Enhanced 也可以实现。

### 用 Markdown 写微信公众号

可以将公众号素材用 Markdown 编辑好后，贴到在线排版工具以后，复制到公众号编辑器里即可。有多种页面主题和代码主题可选择。

我维护的工具地址：<https://md.mazhuang.org>

![微信公众号](https://raw.githubusercontent.com/mzlogin/markdown-intro/master/assets/wechat-markdown.png)

### 更多

想象力丰富的工程师们还扩展了很多基于 Markdown 的玩法，包括但不限于：

* 自动生成 / 更新 Table of Contents
* 流程图 / 时序图
* 制作幻灯片
* 集成 PlantUML / GraphViz 的能力
* 导出 HTML / PDF / 电子书
* ...

以上功能基本都可以用 VSCode + 插件 Markdown Preview Enhanced 实现。

另外可以参考我以前的一篇博客 [关于 Markdown 的一些奇技淫巧](https://mazhuang.org/2017/09/01/markdown-odd-skills/)。

## 参考

* [Markdown: Syntax - DARING FIREBALL](https://daringfireball.net/projects/markdown/syntax)
* [Markdown - 维基百科](https://zh.wikipedia.org/wiki/Markdown)
* [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)
* [关于 Markdown 的一些奇技淫巧](https://mazhuang.org/2017/09/01/markdown-odd-skills/)

---

欢迎关注我的微信公众号，接收 markdown-intro 最新动态。

<div align="center"><img width="192px" height="192px" src="https://mazhuang.org/assets/images/qrcode.jpg"/></div>
