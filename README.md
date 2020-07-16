# security
web安全学习总结

# 劫持
DNS劫持：类似使用导航系统时，导航被劫持，给了一条驶向贼窝的路线。

流量劫持：类似写信，信的内容被改过，收信人并不知情。

HTTP：

HTTP不能防DNS劫持，运营商可以把域名解析指向别的服务器，整个网页都换掉。

HTTP不能防流量劫持，内容是不加密的，运营商可以把源站返回的内容加料，比如加些小广告。

HTTPS：

HTTPS并不能防DNS劫持域名解析，假设运营商劫持了域名解析，浏览器由于证书校验不通过，假站点返回的内容也不能正常展示，所以劫持没有收益。只要不随意信任来源不明的证书，就能从功能上防DNS劫持。

HTTPS可以防流量劫持，因为内容是加密的。

## 防御 XSS 及 http劫持，更多的还是得依靠升级 https 和 CSP/CSP2(内容安全策略) 等非 JavaScript 技术，高明的攻击者可以绕过任何 JavaScript 防护。

# xss Cross Site Scripting（跨站脚本）

xss是指黑客往HTML文件中或者DOM中注入恶意脚本，从而再用户浏览页面时利用注入的恶意脚本对用户实施攻击的一种手段。

所有内联 on* 事件执行的代码

a标签 href 属性 javascript: 内嵌的代码

静态脚本、iframe 等恶意内容

动态添加的脚本文件、iframe 等恶意内容

document-write添加的内容

页面被 iframe 嵌套劫持

参考：https://zhuanlan.zhihu.com/p/96826532

# CSRF （Cross-site request forgery），中文名称：跨站请求伪造
参考：https://zhuanlan.zhihu.com/p/98062456
