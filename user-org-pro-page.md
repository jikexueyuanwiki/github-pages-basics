# 用户、组织和项目 Pages

这里有两种基本的 GitHub Pages 类型：*用户/组织 Pages 和项目 Pages。*它们极其相似，但是有一些很重要的差别。

两种类型的 Pages 都是使用 HTTP 服务，不是 HTTPS。你不应该使用它处理敏感信息，像发送密码或者信用卡号码。

请注意 Pages 发布之后都是公开的，即使它所在的库是私有的。

## 用户/组织 Pages

**用户/组织 Pages** 存在于一个特定的 GitHub Pages 文件专有库中。你将使用用户名来命名这个库，比如 [atmos/atmos.github.io](https://github.com/atmos/atmos.github.io)。

- 你必须使用`username.github.io`这样的命名体制。
- `master`分支上的内容将用于构建和发布你的 GitHub Pages 网页。

你只可以使用你自己的用户名创建用户或者组织 Pages 的库。像`joe/bob.github.io`这样的命名将不能构建用户 Pages 网站。

当用户 Pages 构建完之后，打开`http(s)://<username>.github.io`就可以正常使用了。

### 构建你的用户 & 组织 Pages

用户 Pages 的构建可以通过任何经过认证邮件的账户。它也可以使用 [部署 keys](https://developer.github.com/guides/managing-deploy-keys/#deploy-keys) 来自动化这个过程。

组织 Pages 的构建可以通过任何有 push 权限的成员和有认证邮件的用户。想要自动构建，你可以 [设置一个机器用户](https://developer.github.com/guides/managing-deploy-keys/#machine-users) 作为你的组织的成员。组织 Pages 不支持部署 keys。

## 项目 Pages

不像用户和组织的 Pages，**项目 Pages** 是作为一个项目保存在同一个库中。个人账户和组织都可以创建项目 Pages。个人账户的项目 Pages 的 URL将会是这样 ` http(s)://<username>.github.io/<projectname> `，但组织的 URL 是`http(s)://<orgname>.github.io/<projectname> `。创建项目 Pages 的步骤两者都是相同的。 

项目 Pages 与用户和组织 Pages 很相似，但有一些轻微的不同：

- `gh-pages`分支用来构建和发布项目 Pages 网站。

- 如果没有 [自定义的域名](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages)，项目 Pages 网站将服务在用户 Pages 网站的子域名下：`username.github.io/projectname `。

- 用户和组织 Pages 网站的 [自定义域名](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages) 适用于这个账户托管的所有重定向项目 Pages 的相同域名。使用自定义域名的项目 Pages 网站同样在个人账户的`username.github.io/projectname`和组织的` orgname.github.io/projectname`中有效。

- [自定义的 404s](https://help.github.com/articles/custom-404-pages) 只用在使用了自定义域名的网站。否则，将使用用户 Pages 404。