# 手动创建项目页面

如果你是熟悉 Git 的命令行的，手动创建项目页面网站是非常直观易懂的。

## 做一个新的克隆

为了建立一个项目网页，你需要在你的库中新建一个新的“孤儿”分支（一个与现存分支没有共同的历史的分支）。最安全的做法是从一个新的克隆开始来做这件事：

```
$ git clone github.com/user/repository.git
# Clone our repository
Cloning into 'repository'...
remote: Counting objects: 2791, done.
remote: Compressing objects: 100% (1225/1225), done.
remote: Total 2791 (delta 1722), reused 2513 (delta 1493)
Receiving objects: 100% (2791/2791), 3.77 MiB | 969 KiB/s, done.
Resolving deltas: 100% (1722/1722), done.
```

## 新建一个 gh-pages 分支

一旦你拥有一个空的库，你将需要创建一个新的`gh-pages`分支且从工作目录和首页中去除所有的内容：

```
$ cd repository
$ git checkout --orphan gh-pages
Creates our branch, without any parents (it's an orphan!)
Switched to a new branch 'gh-pages'
$ git rm -rf .
Remove all files from the old working tree
rm '.gitignore'
```

提示：直到你第一次提交之前，`gh-pages`分支不会出现在`git branch`生成的分支列表中。

## 添加内容和推送

当你推送你的程序到页面库中，为了触发它，你必须首先验证你的邮箱地址。

现在你有一个空的工作目录。你可以在这个分支中创建一些内容和推送它到 GitHub 。例如：

```
$ echo "My Page" > index.html
$ git add index.html
$ git commit -a -m "First pages commit"
$ git push origin gh-pages
```

你的GitHub网址应该是可用了。如果你建立的代码不成功，你将会收到一封邮件。

## 加载你的新 GitHub 网页

在你推送`gh-pages`分支后，你的项目网页在`http(s)://<username>.github.io/<projectname>`上是可用的。记住，这个网页总是公开课进入的，当它发布的时候，尽管它的库是私有的。

关于如何给 GitHub 网页建立一个自定义的域名，可以看看<a href="https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/">给 GitHub 网页建立一个自定义的域名</a>
