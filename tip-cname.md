# 在域名服务器提供者上配置 CNAME 记录的技巧

要[设置一个自定义子域](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/)，你必须要在你的域名服务器提供者上配置一个 `CNAME` 记录，这可能会或可能不会和你的网络主机提供者相同。

要获取更多自定义子域的信息，可详见“[关于 GitHub 网页站点的自定义域.](https://help.github.com/articles/about-custom-domains-for-github-pages-sites#subdomains)”

提示：你可以仅仅只为 GitHub 的网页站点配置一个自定义域或者一个自定义顶点域，[除非你使用了一个 `www` 的子域](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider/#configuring-a-www-subdomain)。

## 在域名服务器提供者上配置自定义子域

与你的域名服务器提供者一起，创建一个 CNAME 记录指的是从该域到 `username.github.io` 。域名服务器的变化会占用一整天去扩散蔓延。

不要在 GitHub 页面中使用通配符域名服务器记录（例如 `*.example.com` ）！一个通配符域名服务器记录可以让任何人在其中一个子域中登录到 GitHub 页面站点。 

为确保你的 CNAME 记录设置正确，使用 [dig](http://linux.die.net/man/1/dig) 命令：

```
$ dig www.example.com +nostats +nocomments +nocmd  
;www.example.com.                     IN      A
www.example.com.              3592    IN      CNAME   username.github.io.
username.github.io.           43192   IN      CNAME   github.map.fastly.net.
github.map.fastly.net.        22      IN      A       199.27.76.133
```

## 配置一个 `www` 子域

如果你配置一个[顶点域](https://help.github.com/articles/about-custom-domains-for-github-pages-sites#apex-domains)（例如 `example.com` ）和一个匹配的 `www` 子域（例如 `www.example.com` ）， GitHub 服务器会自动地创建两重定向。

例如：

- 如果你的 `CNAME` 文件包含 `example.com` ，那么 `www.example.com` 会定向到 `example.com` 。
- 如果你的 `CNAME` 文件包含 `www.example.com` ，那么 `example.com` 会定向到 `www.example.com`。

你可以使用除了 `www` 以外的一个自定义子域和一个自定义顶点域来通过域名重定向（有时候也叫“域名转发”）。但是，请注意，这只能用于用户和组织的页面，而不是项目的页面。

# 进一步了解

- “[在 GitHub 页面上设置一个自定义域](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages)”

