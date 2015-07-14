# 关于 GitHub 网站的自定义域

有两种自定义域可用于重定向 GitHub 的网站：*子域*和*先端域*。

## 子域

一个子域[通过您的DNS提供商来配置`CNAME`记录](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider)。

我们因为以下这些原因强烈建议您使用自定义子域：

- 它把我们内容分发网络的好处带给你的 GitHub 网页。
- 它不会受到 GitHub 服务底层 IP 地址变化影响。
- 网页将加载得更加快，因为拒绝服务保护可以更有效地实施。

##先端域
一个*先端域*通常<a href="https://help.github.com/articles/tips-for-configuring-an-a-record-with-your-dns-provider/">通过你的 DNS 供应商配置一个`A`、`ALLAS`或者`ANAME`</a>，和经常被分配给一个或更多的 IP 地址。

注意：一些 DNS 供应商支持配置先端域的 ALIAS 或者 ANAME 记录，但是没有专门的工业标准。一些 DNS 供应商（像 <a href="https://dnsimple.com/"> DNSimple </a>）允许先端域配置 ALIAS 或者 ANAME 指向其它域。

对于你的 GitHub 网页，我们推荐使用一个自定义的子域，而不是一个先端域。

## GitHub 网页怎样使用自定义域

<table>
<thead>
<tr>
<th align="left"> GitHub 网页种类</th>
<th align="center"> GitHub 的主机位置</th>
<th align="left">页面是怎么重定向的</th>
<th align="center">自定义域例子</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">用户网页</td>
<td align="center"><code>username.github.io</code></td>
<td align="left">自动重定向至已经设定好的自定义域</td>
<td align="center"><code>user.example.com</code></td>
</tr>
<tr>
<td align="left">组织网页</td>
<td align="center"><code>orgname.github.io</code></td>
<td align="left">自动重定向至已经设定好的自定义域</td>
<td align="center"><code>org.example.com</code></td>
</tr>
<tr>
<td align="left"><strong>用户账号</strong>拥有的项目网页
</td>
<td align="center"><code>username.github.io/projectname</code></td>
<td align="left">自动重定向到一个由用户指定的，用户网站自定义域的子目录（<code> user.example.com/projectname</code>），以及所有自定义域</td>
<td align="center"><code>project.example.com</code></td>
</tr>
<tr>
<td align="left"><strong>组织</strong>拥有的项目网页
</td>
<td align="center"><code>orgname.github.io/projectname</code></td>
<td align="left">自动重定向到一个由组织指定的，项目网站自定义域的子目录(<code>org.example.com/projectname</code>)，以及所有自定义域</td>
<td align="center"><code>project.example.com</code></td>
</tr>
</tbody>
</table>

解决自定义域的问题，可以参考<a href="https://help.github.com/articles/my-custom-domain-isn-t-working">“我的自定义域出现问题了。”</a>
