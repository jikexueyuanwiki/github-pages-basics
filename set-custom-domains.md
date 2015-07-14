# 建立 GitHub Pages 的自定义域名

你可以为[用户、组织和项目 Pages](user-org-pro-page.md) 配置一个自定义域名。

获取在不同类型的自定义域名信息，可以参看[关于 GitHub 网站的自定义域](custom-domains.md)。

## 新建和上传一个 *CNAME* 文件

为了重定向你的 GitHub Pages，你必须新建和上传一个 *CNAME* 文件。这个文件包含你的库根目录的自定义域名。更多资讯，请参看[为你的库添加一个 CNAME 文件](cname-file.md)。

## 通过你的 DNS 提供商配置自定义子域名

如果你的自定义域名是一个[子域名](custom-domains.md)，你必须通过你的 DNS 提供商配置 CNAME 记录。欲了解更多信息，请参见[通过你的 DNS 提供商配置`CNAME`记录的技巧](tip-cname.md)。

## 通过你的 DNS 提供商配置自定义顶端域名

如果你的自定义域名是一个[顶端域名](custom-domains.md)，你必须配置`ALIAS`、`ANAME`或通过 DNA 提供商配置`A`记录，欲了解更多信息，请参见[通过你的DNS提供商配置`A`记录的技巧](tip-record.md)。