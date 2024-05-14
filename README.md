
# 学术页面

![pages-build-deployment](https://github.com/academicpages/academicpages.github.io/actions/workflows/pages/pages-build-deployment/badge.svg)

学术页面是一个用于学术网站的 Github Pages 模板。

# 入门指南

1. 如果您没有 GitHub 帐户，请注册一个并确认您的电子邮件（必需！）
2. 单击右上角的 "Use this template" 按钮。
3. 在 "New repository" 页面上，将您的存储库名称设置为 "[your GitHub name].github.io"，这也将是您的网站的 URL。
4. 设置站点全局配置并添加您的内容。
5. 将任何文件（如 PDF、.zip 文件等）上传到 `files/` 目录。它们将显示在 https://[your GitHub name].github.io/files/example.pdf。
6. 通过转到存储库设置，在 "GitHub pages" 部分检查状态。
7. （可选）使用 `markdown_generator` 文件夹中的 Jupyter 笔记本或 Python 脚本从 TSV 文件生成出版物和演讲的 markdown 文件。

请参阅 [academicpasges](https://academicpages.github.io/) 获取更多信息。

## 本地运行

当您初始工作网站时，能够在将更改推送到 GitHub 之前本地预览更改非常有用。要在本地工作，您需要：

1. 克隆存储库并按上述说明进行更新。
2. 确保您已安装 `ruby-dev`、`bundler` 和 `nodejs`：`sudo apt install ruby-dev ruby-bundler nodejs`。
3. 运行 `bundle install` 来安装 ruby 依赖项。如果出现错误，请删除 `Gemfile.lock` 并重试。
4. 运行 `jekyll serve -l -H localhost` 来生成 HTML 并从 `localhost:4000` 提供它。本地服务器将在更改时自动重建和刷新页面。
5. 如果第4点提示错误，请使用如下命令进行构建与编译：`bundle exec jekyll build`，该命令将生成HTML；`bundle exec jekyll serve`，该命令将自动实时生成HTML，并可以在浏览器网址栏输入`http://127.0.0.1:4000/`来查看生成的页面。

# 维护

有关模板的错误报告和功能请求应通过 GitHub 提交。有关如何为模板设置样式的问题，请随时在 GitHub 上开始新的讨论。

此存储库由 [Stuart Geiger](https://github.com/staeiou) 从 [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/) fork（然后分离）而来，后者由 Michael Rose 在 2016 年版权并根据 MIT 许可证发布（请参阅 LICENSE.md）。目前由 [Robert Zupko](https://github.com/rjzupkoii) 维护，并欢迎其他维护者。

## 修复 Bug 和增强功能

如果您有要作为拉取请求提交的错误修复和增强功能，您将需要 fork 这个存储库，而不是将其用作模板。这也将允许您将模板的副本同步到您的 fork 中。

不幸的是，模板主题如学术页面存在一个逻辑问题，使得获取核心主题的 bug 修复和更新有些棘手。如果您使用此模板并自定义它，则可能会在尝试同步时遇到合并冲突。如果您想要保存各种 `.yml` 配置文件和 markdown 文件，您可以删除存储库并重新 fork 它。或者您可以手动打补丁。

