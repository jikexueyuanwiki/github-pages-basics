# 建立一个 GitHub 网站的自定义域

你可以为了<a href="https://help.github.com/articles/user-organization-and-project-pages">用户、组织和项目页面</a>配置一个自定义域。

为了在不同类型的自定义域信息， 可以参看<a href="https://help.github.com/articles/about-custom-domains-for-github-pages-sites">“关于 GitHub 网站的自定义域”</a>

## 新建和上传一个 *CNAME* 文件

为了重定向你的GitHub网站，你必须新建和上传一个 *CNAME* 文件。这个文件包含你的库根目录的自定义域。更多资讯，请参看<a href="https://help.github.com/articles/adding-a-cname-file-to-your-repository">“为你的库添加一个*CNAME*文件”。</a>

## 通过你的DNS提供商配置自定义子域

如果你的自定义域是一个[子域](https://help.github.com/articles/about-custom-domains-for-github-pages-sites#subdomains "子域")，你必须通过你的 DNS 提供商配置 CNAME 记录。欲了解更多信息，请参见“[通过你的 DNS 提供商配置`CNAME`记录的技巧](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider "通过你的 DNS 提供商配置 CNAME 记录的技巧")。”

## 通过你的 DNS 提供商配置自定义先端域

如果你的自定义域是一个[先端域](https://help.github.com/articles/about-custom-domains-for-github-pages-sites#apex-domains "先端域")，你必须配置`ALIAS`、`ANAME`或通过 DNA 提供商配置`A`记录，欲了解更多信息，请参见“[通过你的DNS提供商配置`A`记录的技巧](https://help.github.com/articles/tips-for-configuring-an-a-record-with-your-dns-provider "通过你的 DNS 提供商配置 A 记录的技巧")。”