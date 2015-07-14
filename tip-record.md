# 在你的 DNS 提供者上配置一个 A 记录的技巧

要[设置一个自定义顶点域名](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages)，你必须要在你的 DNS 提供者上配置一个 `ALIAS`，`ANAME` ，或者 `A` 记录，这可能会或者可能不会和你的网络主机提供者相同。

**警告**：不要在你的 DNS 提供者上为你的自定义顶点域名创建一个 `CNAME` 记录！这样做可能会导致与其他服务，如电子邮件，在该域的问题。

要获取更多的自定义顶点域信息，详见“[关于 GitHub 页面站点的自定义顶点域名](https://help.github.com/articles/about-custom-domains-for-github-pages-sites#apex-domains)”

**提示**：你可以仅仅只为 GitHub Pages 站点配置一个自定义子域名或者一个自定义顶点域名，[除非你使用一个 `www` 子域](https://help.github.com/articles/tips-for-configuring-an-a-record-with-your-dns-provider/#configuring-a-www-subdomain)。

## 在你的 DNS 上配置一个 A 记录

在你的 DNS 提供者上，创建 A 记录来解决以下的IP地址：

- 192.30.252.153
- 192.30.252.154 

为了确保你的 A 记录设置正确，使用 `dig` 命令：

```
$ dig example.com +nostats +nocomments +nocmd
;example.com
example.com.   73  IN  A 192.30.252.153
example.com.   73  IN  A 192.30.252.154
```

## 在你的 DNS 提供者上配置一个 `ALIAS` 或者一个 `ANAME` 记录

如果你的 DNS 提供者支持 ALIAS 记录（例如是 [DNSimple](https://dnsimple.com/) ）或者 ANAME 记录（例如是 [DNS Made Easy](http://www.dnsmadeeasy.com/services/aname-records/) ），你可以选择创建一个 `ALIAS` 记录或者一个 `ANAME` 记录来代替 `username.github.io`。

**注意**：一些 DNS 提供者允许顶点域名配置一个 ALIAS 记录指向其他的域名。

为了确保你的 `ALIAS` 或者 `ANAME` 记录设置正确，使用 `dig` 命令：

```
$ dig example.com +nostats +nocomments +nocmd
example.com.     3600    IN A     199.27.XX.XXX
```

在这里显示的 IP 地址必须要和 `dig username.github.io` 所显示的最终的 IP 地址相匹配。

## 配置一个 `www` 子域

如果你配置一个顶点域名（例如 `example.com` ）和一个匹配的 `www` [子域](https://help.github.com/articles/about-custom-domains-for-github-pages-sites#subdomains)（例如 `www.example.com` ），GitHub 服务器会自动的创建两重定向。

例如：

- 如果你的 `CNAME` 文件包含 `example.com`，那么 `www.example.com` 会定向到 `example.com`。
	
- 如果你的 `CNAME` 文件包含 `www.example.com`，那么 `example.com` 会定向到 `www.example.com`。

你可以使用除 `www` 以外的一个自定义子域和一个自定义顶点域一起通过域名重定向（有时也称为“域名转发”）。但是，请注意，这仅仅只用于用户和组织的页面，而非项目页面。

# 进一步了解
	
- “[在 GitHub 页面上设置一个自定义域](set-custom-domains.md)”
