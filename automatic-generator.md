# 用自动生成器新建页面 

你可以使用 GitHub 的页面自动生成器一个项目的网页、用户和组织。

## 用户和组织页面

为了生成用户和组织的网页，你需要<a href="https://help.github.com/articles/creating-a-new-repository/">生成一个库</a>叫作`username.github.io`。用户名和组织名<b>必须</b>是你自己的或者你的GitHub页面不会建立的。页面自动生成器是容易通过库的设置页面进入的。你可以<a href="https://help.github.com/articles/user-organization-and-project-pages">从这里</a>阅读更多关于用户和组织页面。

警告： GitHub 的网页在互联网上是公开的可进入的，尽管它们的库是私有的。如果你有一些敏感的数据在你的页面库中，你可能想把它在发布前去除。

## 项目页面

你可以用页面自动生成器为了任何项目库去发布 GitHub 网页。

警告：你必须新建一个合乎命名规则描述的库，否则你将不能把它发布到你的 GitHub 网页。

## 页面自动生成器

1. 在 GitHub 上打开库的页面。
2. 在你的库右面的侧边栏，点击![](images/automatic-generator1.png)。

![](images/cautomatic-generator2.png)

3. 点击<b>页面自动生成器</b>按钮。

![](images/automatic-generator3.png)

4. 编辑的的内容在 Markdown 编辑器。
5. 点击<b>继续布置</b>按钮。
6. 在主题中预览你的内容。

![](images/automatic-generator4.png)

7. 当你找到你喜欢的主题，点击<b>发布页面</b>。

![](images/automatic-generator5.png)

在你的 GitHub 网页生成之后，你可以得到它 HTML 代码的本地复制。如果你生成一个项目网页，取得和生成一个新的分支。

``` 
$ cd repository
$ git fetch origin
remote: Counting objects: 92, done.
remote: Compressing objects: 100% (63/63), done.
remote: Total 68 (delta 41), reused 0 (delta 0)
Unpacking objects: 100% (68/68), done.
From https://github.com/user/repo.git
* [new branch]      gh-pages     -> origin/gh-pages
$git checkout gh-pages
Branch gh-pages set up to track remote branch gh-pages from origin.
Switched to a new branch 'gh-pages'
```

如果你生成了一个用户网页，代码会在`master`的分支，而不是`gh-pages`的分支，所以仅仅释放`master`然后推送出去就可以了。

```
$cd repository
$git checkout master
Switched to branch 'master'
git pull origin master
remote: Counting objects: 92, done.
remote: Compressing objects: 100% (63/63), done.
remote: Total 68 (delta 41), reused 0 (delta 0)
Receiving objects: 100% (424/424), 329.32 KiB | 178 KiB/s, done.
Resolving deltas: 100% (68/68), done.
From https://github.com/user/repo.git
 * branch      master     -> FETCH_HEAD
Updating abc1234..def5678
Fast-forward
index.html                                     |  265 ++++
...
98 files changed, 18123 insertions(+), 1 deletion(-)
create mode 100644 index.html
...
```