# Developer-Certificates
苹果开发者账号那些事儿

一、关于证书
苹果使用密文签名技术来验证App的合法性，不管是iOS应用还是Mac应用都需要相应的签名证书来作为测试或发布App用。这里主要谈谈iOS的证书，当然，Mac的证书也基本类似。

在开发iOS应用的时候，我们需要签名证书（开发证书）来验证，并允许我们在真机上对App进行测试。另外，在发布App到App store的时候，我们也需要证书(发布证书)来做验证。那么什么是签名证书，如何获取签名证书，下面听我慢慢道来。

首先，证书（Certificate）是用来证明某一件事是否成立的，好比拿到的获奖证书，是证明参加比赛并获奖的凭证。类似，在iOS开发中，用证书来证明你是否具有某些权限或者能力来做某事。代码签名验证允许我们的操作系统来判断是谁对App进行了签名，在安装了Xcode后，Xcode会在项目编译期间使用你的代码签名验证，这个验证由一个由Apple认证过的公钥-私钥对组成，私钥存储在你的钥匙串中（Mac本地，在系统实用工具中），公钥包含在证书（Certificates）中，证书在本地钥匙串和开发者账号中都有存储，这种公钥-私钥验证授权的方式在很多地方都有使用到，比如Git中的SSH协议也是通过这种方式来确认访问权限。另外，还有一个我们可以叫做媒介证书的证书来确保我们的证书（Certificates）是经过授权而发布的。如下图所示：


当安装好Xcode时，媒介证书（Intermediate Certificate）就已经安装到我们的钥匙串中去了。通过在开发者账号（Developer Account）和本地（Mac）都经过验证的证书（Certificate）我们就可以利用合法的证书进行App的测试和发布了。
