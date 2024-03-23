---
permalink: /
title: "academicpages 是一个适用于学术个人网站的 GitHub Pages 模板。"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

这是由 [academicpages 模板](https://github.com/academicpages/academicpages.github.io) 提供支持并托管在 GitHub 页面上的网站的首页。[GitHub 页面](https://pages.github.com) 是一个免费服务，用于从存储在 GitHub 仓库中的代码和数据构建和托管网站，在向仓库进行新提交时会自动更新。该模板是从 [Minimal Mistakes Jekyll 主题](https://mmistakes.github.io/minimal-mistakes/) 中 fork 而来的，并扩展以支持学术内容，如出版物、演讲、教学、作品集、博客文章和动态生成的简历。您可以立即 fork [这个仓库](https://github.com/academicpages/academicpages.github.io)，修改配置和 markdown 文件，添加您自己的 PDF 文件和其他内容，免费拥有您自己的网站，无广告！该模板的早期版本用于支持我的个人网站 [stuartgeiger.com](http://stuartgeiger.com)，该网站使用了 [此 GitHub 仓库](https://github.com/staeiou/staeiou.github.io)。

数据驱动的个人网站
======
与许多其他基于 Jekyll 的 GitHub Pages 模板一样，academicpages 让您将网站的内容与形式分离开来。网站的内容和元数据存储在结构化的 markdown 文件中，而其他各种文件构成了主题，指定了如何将这些内容和元数据转换为 HTML 页面。您将这些各种 `markdown(.md)`、`YAML(.yml)`、HTML 和 CSS 文件保存在一个公共 GitHub 仓库中。每次您提交并推送更新到仓库时，[GitHub 页面](https://pages.github.com/) 服务会基于这些文件创建静态 HTML 页面，这些页面免费托管在 GitHub 的服务器上。

使用这种方式，许多动态内容管理系统（如 Wordpress）的许多功能都可以实现，而且使用的计算资源只有一小部分，且不易受到黑客攻击和 DDoS 攻击的影响。您还可以自由修改主题，而不必触及网站的内容。如果您在 Jekyll/HTML/CSS 中破坏了某些东西，您的演讲、出版物等 markdown 文件是安全的。您可以回滚更改，甚至删除仓库并重新开始 -- 只需确保保存 markdown 文件！

最后，您还可以编写脚本来处理站点上的结构化数据，例如 [this one](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb)，该脚本分析了关于演讲的页面中的元数据，以显示您演讲过的每个地点的 [a map of every location you've given a talk](https://academicpages.github.io/talkmap.html)。

开始
======
1. 如果您尚未拥有 GitHub 帐户，请注册并确认您的电子邮件（必需！）
2. 点击右上角的 "Use this template" 按钮。
3. 在 "New repository" 页面上，将您的仓库名称设置为 "[您的 GitHub 用户名].github.io"，这也将成为您网站的 URL。
4. 设置全局配置并添加您的内容。
5. 将任何文件（如 PDF、.zip 文件等）上传到 `files/` 目录。它们将显示在 `https://[your GitHub name].github.io/files/example.pdf`。
6. 通过转到仓库设置，在 "GitHub 页面" 部分检查状态。

全局配置
------
网站的主要配置文件位于基础目录中的 [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml)，它定义了侧边栏的内容和其他网站范围内的功能。您需要将默认变量替换为有关自己和您的站点 GitHub 仓库的变量。顶部菜单的配置文件位于 [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml)。例如，如果您没有作品集或博客文章，您可以从该 navigation.yml 文件中删除这些项目，以将它们从页眉中删除。

创建内容和元数据
------
对于网站内容，每种类型的内容都有一个 markdown 文件，存储在 `_publications`、`_talks`、`_posts`、`_teaching` 或 `_pages` 等目录中。例如，每个演讲都是 [_talks 目录](https://github.com/academicpages/academicpages.github.io/tree/master/_talks) 中的一个 markdown 文件。每个 markdown 文件的顶部都是有关演讲的结构化数据，主题将解析这些数据以执行许多有趣的操作。关于演讲的相同结构化数据用于生成 [Talks 页面](https://academicpages.github.io/talks)上的演讲列表，每个[单独页面](https://academicpages.github.io/talks/2012-03-01-talk-1)用于特定的演讲，[CV 页面](https://academicpages.github.io/cv)上的演讲部分以及[您曾经演讲过的地图](https://academicpages.github.io/talkmap.html)（如果运行此 [python 文件](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) 或 [Jupyter 笔记本](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb)，该文件根据 `_talks` 目录的内容创建地图的 HTML）。

**Markdown 生成器**

我还创建了 [一组 Jupyter 笔记本](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator)，它们可以将包含演讲或报告结构化数据的 CSV 转换为适用于 academicpages 模板的个别 markdown 文件，并且格式正确。该目录中的示例 CSV 是我用于创建自己个人网站 stuartgeiger.com 的。我通常的工作流程是，我维护一张关于我的出版物和演讲的电子表格，然后运行这些笔记本中的代码来生成 markdown 文件，然后提交并推送到 GitHub 仓库。

如何编辑您网站的 GitHub 仓库
------
许多人使用 git 客户端在本地计算机上创建文件，然后将它们推送到 GitHub 的服务器上。如果您对 git 不熟悉，您可以直接在 github.com 界面中编辑这些配置和 markdown 文件。导航到文件（比如[this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md)）并点击内容预览右上角的铅笔图标（在 "Raw | Blame | History" 按钮的右边）。

您可以点击铅笔图标右侧的垃圾桶图标来删除文件。您还可以通过导航到目录并点击 "Create new file" 或 "Upload files" 按钮来创建新文件或上传文件。

示例：编辑演讲的 markdown 文件
![编辑演讲的 markdown 文件](/images/editing-talk.png)

更多信息
------
有关配置 academicpages 的更多信息，请参阅[指南](https://academicpages.github.io/markdown/)。

也可以参考[Minimal Mistakes 主题的指南](https://mmistakes.github.io/minimal-mistakes/docs/configuration/)（此主题是从中 fork 出来的）。