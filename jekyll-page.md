# 在页面中使用 Jekyll

除了支持常规的 HTML 内容之外，GitHub Pages 也支持 [Jekyll](https://github.com/jekyll/jekyll)，一个简单的，博客风格的静态网页生成器。Jekyll 使创建站点范围内的头部和底部变得简单，不需要在每个页面复制它们。它也提供[一些其他更深入的模板功能](http://jekyllrb.com/docs/templates/)。

## 使用 Jekyll

当你将内容推送到一个特别命名的分支版本库中运行，每个 GitHub Pages 是通过 Jekyll 处理。对于 User Pages，使用在`username.github.io`库的`master`分支。对于 Project Pages，使用项目中存储库中的`gh-pages`分支。因为一个普通的 HTML 网站也是一个有效的 Jekyll 网站，你不需要做什么特别的事情让您的标准 HTML 文件不变。 Jekyll [完整的文档](http://jekyllrb.com/docs/home/)，涵盖其功能和使用方法。只需启动提交 Jekyll 格式的文件，你就会在任何时间使用 Jekyll。

## 安装 Jekyll

我们强烈建议您的计算机上安装 Jekyll 预览您的网站，并在发布你的网站之前帮助检测出有问题的 GitHub Pages。

很幸运的是，在你的电脑上安装 Jekyll，并确保你的计算机最匹配 GitHub Pages 设置很容易，多亏了 [the GitHub Pages Gem](https://github.com/github/pages-gem)和我们的[依赖版本的页面](http://pages.github.com/versions)。要安装 Jekyll，你需要做几件事情：

1. **Ruby** - Jekyll 需要 Ruby 语言。如果你有一个苹果电脑，你很可能已经有 Ruby。如果你打开​​终端应用程序，然后运行命令`ruby --version`，可以证实这一点。你的 Ruby 版本至少应该是 2.0.0。如果你已经有了，你就已经完成这一步。跳至步骤 ＃2。否则，请按照以下[说明](https://www.ruby-lang.org/en/downloads/)安装 Ruby。

2. **Bundler** - 捆绑器的软件包管理器。它使 Ruby 软件版本像 Jekyll 一样。如果你将要在本地建设的 GitHub Pages，它能令你容易得多。如果你还没有安装 Bundler，你可以通过运行命令`gem install bundler`安装它。

3. **Jekyll** - 主要做的事。你将要创建一个名为`Gemfile`的文件在你的网站的库中并添加行`gem 'github-pages`。在此之后，只需运行命令，`bundle install`就可以了。如果你决定跳过步骤＃2，你仍然可以使用命令`gem install github-pages`安装 Jekyll，但你可能会碰到了命令行的麻烦。这里有一个`Gemfile`的例子，你可以使用（放置在存储库的根目录）：

```
source 'https://rubygems.org'
gem 'github-pages'
```

## 运行 Jekyll

为了以符合 GitHub Pages 构建服务器的方式运行 Jekyll，需要通过 Bundler 运行 Jekyll。在库的根目录使用命令`bundle exec jekyll serve`（在切换到项目库的`gh-pages`分支之后），然后应该能在`http://localhost:4000`访问你的网站。完整的 Jekyll 命令列表，请参见 [Jekyll 文档](http://jekyllrb.com/docs/usage/ "Jekyll文档")。

## 保持 Jekyll 是最新的

Jekyll 是一个动态开源项目，它会频繁地更新。当 GitHub Pages 服务器更新了，在你电脑上的软件就会过时，导致你的网站出现本地和发布在 GitHub 的样子不一致。保持 Jekyll 的更新，你可以输入命令`bundle`（或者如果你选择跳开第二步，运行` gem update github-pages`）。

## 配置 Jekyll

你可以通过创建一个 `_config.yml `来[配置 Jekyll 大部分属性](https://help.github.com/articles/using-jekyll-with-pages#configuring-jekyll)。

### 默认值

以下的默认值是 GitHub 设置的，你可以自由地重写`_config.yml`文件：

```
highlighter: pygments
github: [Repository metadata]
```

对于存储库的元数据对象的内容，请参阅 [GitHub Pages 库的元数据](https://help.github.com/articles/repository-metadata-on-github-pages)。

### 配置重写

我们可以重写下面的`_config.yml`中你不可以配置的值：

```
safe: true
lsi: false
source: your top-level directory
```

记住，如果你改变了`source`的设置，你的页面可能不能正确地建立。 GitHub Pages 把源文件作为最高级别的库目录来考虑。

## Frontmatter 是必须的

Jekyll 需要 Markdown 文件有一个 front-matter 定义在所有文件之上。Front-matter 只是一系列的元数据，由三个破折号划定：

```
---
title: This is my title
layout: post
---

Here is my page.
```

如果你喜欢，你可以选择从你的文件中删除 Front-matter，但是你仍然需要这三个破折号：

```
---
---

Here is my page.
```

如果你的文件在 *_posts* 目录中，你可完全删除这些破折号。
希望获取更过信息可以查看 [Jekyll 文档](http://jekyllrb.com/docs/frontmatter/)。

### 问题解决

如果你的 Jekyll 网站在你 push 它到 GitHub 后没有表现为合适的形式，在本地运行 Jekyll 对你检查错误很有用。为了做到这件事，你将会希望[使用 Jekyll 的相同版本和其它依赖](http://pages.github.com/versions/)。

为了保证你的本地开发环境是使用 Jekyll 的相同版本和 GutHub 网站的依赖，一旦 Jekyll 安装了，你可以定期地运行命令`gem update github-pages`（或者`bundle update github-pages`如果使用Bundler）。更多的信息，请参看 [GitHub Pages Gem 库](https://github.com/github/pages-gem)。

如果你的页面并没有建立在你 push 到 GitHub 之后，请参看 [GitHub Pages 建立失败问题解决](https://help.github.com/articles/troubleshooting-github-pages-build-failures)。

如果你 Jekyll 网页正在出现问题，请确定你没有使用和其它项目相同名字的分类，这个会引起路径冲突。例如，你有一个博客站点叫“简历”在你的用户网页库中，和一个项目名叫“简历”也有一个`gh-pages`的分支，它们会引起双方的冲突。

## 关闭 Jekyll

你可以通过在页面库的根目录下创建一个名为`.nojekyll`的文件并将其 push 到 GitHub 来完全退出 Jekyll。只有当您的站点使用以下划线开头的目录，这才是必要的。Jekyll 把这些当作特殊的目录，并且不将它们复制到最终目的地。

## 贡献

如果你希望 Jekyll 拥有某些功能，请自由地 [fork](https://github.com/jekyll/jekyll)，并发送一个 pull 请求。我们很高兴接受到用户的意见。