# 在 DNS 提供者上配置 CNAME 记录的技巧

要[设置一个自定义子域名](set-custom-domains.md)，你必须要在你的 DNS 提供者上配置一个 `CNAME` 记录，这可能会或可能不会和你的网络主机提供者相同。

要获取更多自定义子域名的信息，可详见“[关于 GitHub 网页站点的自定义域.](custom-domains.md)”。

提示：你可以仅仅只为 GitHub Pages 配置一个自定义域名或者一个自定义顶端域名，[除非你使用了一个 `www` 的子域名](tip-cname.md)。

## 在 DNS 提供者上配置自定义子域名

与你的 DNS 提供者一起，创建一个 CNAME 记录指的是从该域到 `username.github.io`。DNS 的变化会占用一整天去扩散蔓延。

不要在 GitHub Pages 中使用通配符 DNS 记录（例如 `*.example.com` ）！一个通配符 DNS 记录可以让任何人在其中一个子域名中登录到 GitHub Pages。 

为确保你的 CNAME 记录设置正确，使用 [dig](http://linux.die.net/man/1/dig) 命令：

```
$ dig www.example.com +nostats +nocomments +nocmd  
;www.example.com.                     IN      A
www.example.com.              3592    IN      CNAME   username.github.io.
username.github.io.           43192   IN      CNAME   github.map.fastly.net.
github.map.fastly.net.        22      IN      A       199.27.76.133
```

## 配置一个 `www` 子域名

如果你配置一个[顶端域名](custom-domains.md)（例如 `example.com` ）和一个匹配的 `www` 子域名（例如 `www.example.com` ），GitHub 服务器会自动地创建双重定向。

例如：

- 如果你的 `CNAME` 文件包含 `example.com`，那么 `www.example.com` 会定向到 `example.com`。
- 如果你的 `CNAME` 文件包含 `www.example.com`，那么 `example.com` 会定向到 `www.example.com`。

你可以使用除了 `www` 以外的一个自定义子域名和一个自定义顶端域名来通过域名重定向（有时候也叫“域名转发”）。但是，请注意，这只能用于用户和组织的 Pages，而不是项目的 Pages。

# 进一步了解

- “[在 GitHub 页面上设置一个自定义域](set-custom-domains.md)”。

