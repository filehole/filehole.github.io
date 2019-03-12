# 文件洞 filehole

个人博客：<https://filehole.github.io>，欢迎 Star 和 Fork。

## 目录

<!-- vim-markdown-toc GFM -->

* [效果预览](#效果预览)
* [Fork 指南](#fork-指南)
* [Tips](#贴心提示)
* [个人思考](#经验与思考)
* [致谢](#致谢)

<!-- vim-markdown-toc -->

## 效果预览

**[在线预览 &rarr;](https://filehole.github.io)**

![screenshot home](https://filehole.github.io/assets/images/screenshots/home.png)
![New OAuth App](https://filehole.github.io/assets/images/readme/create-new-OAuth-App.png)

## Fork 指南

Fork 本项目可以轻松地建立你自己的 git blog，当然还需要做一些事情才能让你的页面「正确」跑起来。

1. 设置正确的项目名称与分支。

   按照 GitHub Pages 的规定，名称为 `username.github.io` 的项目的 master 分支，或者其它名称的项目的 gh-pages 分支可以自动生成 GitHub Pages 页面，例如本项目即为 `filehole/filehole.github.io`，对应的地址为 https://filehole.github.io。

2. 修改域名。

   如果你需要绑定自己的其他域名，那么可以在根目录下建立 CNAME 文件，写入相应的域名；如果后续不再需要绑定自己的域名，那么删掉 CNAME 文件即可。

3. 修改配置。

   绝大部分的配置基本都集中在 \_config.yml 文件中，只需要替换其中与个人信息相关的部分即可，比如网站的 url、title、subtitle 和第三方评论模块的配置等。

   **评论模块：** 目前支持 disqus、gitment 和 gitalk，选用其中一种就可以了，推荐使用 gitalk。它们各自的配置指南链接在 \_config.yml 文件的 Comments 一节里都贴出来了。

   *gitalk* 创建流程
   >- 进入 Settings -> Developer settings -> OAuth Apps
   >- 创建新的应用 New OAuth App ![New OAuth App](https://filehole.github.io/assets/images/readme/create-new-OAuth-App.png)
   >- 获取创建好的应用的参数，最重要的即 Client ID 与 Client Secret
   >- 在 github 中创建留存对应评论的仓库，例如 blog-comments
   >- 修改 \_config.yml 文件中的代码段

   ```
   gitalk:
    owner: filehole
    repo: blog-comments
    clientID: 683ed0e1d6c3c8c981e7
    clientSecret: 56e148ce618c029c862514d13ef888b797835389
   ```

4. 删除原有的文章与图片。

   如下文件夹中除了 template.md 文件外，都可以全部删除，然后添加你自己的内容。

   * \_posts 文件夹中是已发布的博客文章。
   * \_drafts 文件夹中是尚未发布的博客文章。
   * \_wiki 文件夹中是已发布的 wiki 页面。
   * images 文件夹中是文章和页面里使用的图片。

5. 修改「关于」页面。

   pages/about.md 文件内容对应网站的「关于」页面，里面的内容多为个人相关，将它们替换成个人信息，包括 \_data 目录下的 skills.yml 和 social.yml 文件里的数据。

## Tips

1. 排版建议遵照一定的规范，推荐 [中文文案排版指北（简体中文版）][1]。

2. 在本地预览博客效果可以参考 [Setting up your Pages site locally with Jekyll][2]。

## 个人思考

* 简约，尽量每个页面都不展示多余的内容。

* 如果写技术文章，那先将技术原理完全理清了再开始写，一边摸索技术一边组织文章效率较低。

* 杜绝难断句、难理解的长句子，如果不能将其拆分成几个简洁的短句，说明脑中的理解并不清晰。

## 致谢

本博客主要借鉴于 [DONGChuan](https://dongchuan.github.io) ，特此感谢！

[1]: https://github.com/mzlogin/chinese-copywriting-guidelines
[2]: https://help.github.com/articles/setting-up-your-pages-site-locally-with-jekyll/
