---
name: Blockstream Green - 2FA
description: 在Green Wallet上设置2/2多签名
---
![封面](assets/cover.webp)

软件钱包是安装在计算机、智能手机或任何其他连接到互联网的设备上的应用程序，允许管理和保护一个人的比特币钱包密钥。与隔离私钥的硬件钱包不同，“热”钱包因此在可能暴露于网络攻击的环境中运行，增加了被黑客攻击和盗窃的风险。

软件钱包适用于管理合理数量的比特币，特别是用于日常交易。对于比特币资产有限的人来说，这也是一个有趣的选择，对他们来说，投资硬件钱包可能看起来不成比例。然而，它们不断暴露于互联网使得它们不太适合存储长期储蓄或大量资金。对于这些情况，最好选择更安全的解决方案，如硬件钱包。

在本教程中，我将向您展示如何通过在Blockstream Green上使用“2FA”选项来增强热钱包的安全性。

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## 介绍Blockstream Green

Blockstream Green是一款可在移动设备和桌面上使用的软件钱包。这个钱包最初被称为*Green Address*，在2016年被Blockstream收购后成为了Blockstream的项目。

Green是一个特别易于使用的应用程序，对初学者来说很有吸引力。它提供了一个好的比特币钱包的所有基本功能，包括RBF（*Replace-by-Fee*）、通过Tor连接的选项、连接自己的节点、SPV（*Simple Payment Verification*）选项、标签和币控制。

Blockstream Green还支持Liquid网络，这是Blockstream为在主区块链之外进行快速和保密交易而开发的比特币侧链。在本教程中，我们专注于比特币，但我还制作了另一个教程来学习如何在Green上使用Liquid：

https://planb.network/tutorials/wallet/blockstream-green-liquid

## 2/2多签名（2FA）选项

在Green上，您当然可以创建一个经典的“单签名”热钱包。但您还有“2FA多签名”选项，这允许您在不过度复杂化日常管理的情况下提高热钱包的安全性。
因此，您将设置一个2/2多签名钱包，这意味着每笔交易都需要两个密钥的签名。第一个密钥，来自您的12或24个单词的助记词，通过手机上的PIN码在本地保护。您对这个密钥拥有完全的控制权。第二个密钥由Blockstream的服务器持有，其用于签名的使用需要认证，这可以通过电子邮件、短信、电话呼叫或者，正如我们将在本教程中看到的，通过认证应用程序（Authy、Google Authenticator等）来实现。

为了确保在Blockstream出现故障时（例如，如果公司破产或持有第二个密钥的服务器被销毁）您的自主性，您的多签名钱包应用了一个时间锁机制。这个机制在大约一年后（或确切地说是51,840个区块，但这个值可以更改）将2/2多签名转换为1/2多签名，之后您的钱包只需要您的本地密钥就可以花费比特币。因此，如果您失去了访问Blockstream服务器或2FA认证的能力，您只需等待最多一年就能够自由使用您的比特币，而不依赖于Blockstream。
![GREEN 2FA MULTISIG](assets/fr/02.webp)
这种方法显著提高了您的热钱包的安全性，同时让您控制您的比特币并便于其日常使用。然而，它需要定期刷新时间锁以维护2FA的安全性。一旦您收到比特币，受2FA保护的资金的360天倒计时就开始了。如果在收到它们360天后您没有进行消费这些资金的交易，您的比特币将只受您的本地密钥保护，而没有2FA。

这个限制使得2FA选项更适合于消费钱包，其中定期交易自动续订时间锁。对于长期储蓄钱包来说，这可能是个问题，因为您需要考虑在时间锁到期前每年对自己进行一次扫荡交易。

这种安全方法的另一个缺点是您需要使用少数脚本模式。这意味着，从隐私角度来看，事情变得复杂：很少有人使用与您相同类型的脚本，这使得外部观察者更容易识别您的钱包足迹。此外，这些脚本会由于它们较大的大小而导致更高的交易费用。
如果您更愿意不使用2FA选项，只是想在Green上设置一个“单签名”钱包，我邀请您查看这个其他教程：
https://planb.network/tutorials/wallet/blockstream-green-liquid

## 安装和设置Blockstream Green软件

第一步自然是下载Green应用。前往您的应用商店：
- [对于Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [对于Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

对于Android用户，您还可以选择通过[Blockstream的GitHub上提供的`.apk`文件](https://github.com/Blockstream/green_android/releases)安装应用。

![GREEN 2FA MULTISIG](assets/fr/04.webp)

启动应用，然后勾选“*我接受条款...*”。

![GREEN 2FA MULTISIG](assets/fr/05.webp)

当您第一次打开Green时，主屏幕会显示出没有配置的钱包。稍后，如果您创建或导入钱包，它们将出现在此界面中。在创建钱包之前，我建议您根据您的期望调整应用设置。点击“*应用设置*”。

![GREEN 2FA MULTISIG](assets/fr/06.webp)

“*增强隐私*”选项，仅在Android上可用，通过禁用截屏和隐藏应用预览来提高隐私。它还会在您的手机锁定时自动锁定对应用的访问，使您的数据更难以暴露。

![GREEN 2FA MULTISIG](assets/fr/07.webp)

对于那些希望增强隐私的用户，应用提供了通过Tor路由您的流量的选项，Tor是一个加密您所有连接并使您的活动难以追踪的网络。尽管这个选项可能稍微降低应用的性能，但为了保护您的隐私，特别是如果您不使用自己的完整节点，强烈推荐使用这个选项。

![GREEN 2FA MULTISIG](assets/fr/08.webp)

对于拥有自己完整节点的用户，Green Wallet提供了通过Electrum服务器连接到它的可能性，确保对比特币网络信息和交易广播的完全控制。
![GREEN 2FA MULTISIG](assets/fr/09.webp)
另一个替代功能是“*SPV 验证*”选项，它允许直接验证某些区块链数据，从而减少了对 Blockstream 默认节点的信任需求，尽管这种方法并不提供全节点的所有保证。
![GREEN 2FA MULTISIG](assets/fr/10.webp)
根据您的需求调整这些设置后，点击“*保存*”按钮并重启应用程序。

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## 在 Blockstream Green 上创建比特币钱包

您现在已经准备好创建比特币钱包了。点击“*开始*”按钮。

![GREEN 2FA MULTISIG](assets/fr/12.webp)

您可以选择本地创建一个软件钱包或通过硬件钱包管理一个冷钱包。在本教程中，我们将重点介绍创建一个热钱包，因此您需要选择“*在此设备上*”选项。

![GREEN 2FA MULTISIG](assets/fr/13.webp)

接下来，您可以选择恢复现有的比特币钱包或创建一个新的。出于本教程的目的，我们将创建一个新钱包。然而，如果您需要从助记词重新生成现有的比特币钱包，例如，由于丢失了旧手机，您将需要选择第二个选项。

![GREEN 2FA MULTISIG](assets/fr/14.webp)

然后您可以选择 12 个词或 24 个词的助记词。这个短语将允许您在手机出现问题时从任何兼容软件中恢复对您钱包的访问。目前，选择 24 个词的短语并不比 12 个词的短语提供更多的安全性。因此，我推荐选择**12 个词**的助记词。

Green 将为您提供您的助记词。继续之前，请确保您没有被观察。点击“*显示恢复短语*”以在屏幕上显示它。

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**这个助记词给予了对您所有比特币的完全和不受限制的访问权限**。任何拥有这个短语的人都可以偷走您的资金，即使没有物理访问您的手机（在 Green 上的 2/2 钱包的定时锁过期或 2FA 的情况下）。

它允许您在手机丢失、被盗或损坏的情况下恢复对本地密钥的访问。因此，将其仔细保存在**物理介质（非数字）**上并存放在安全的地方非常重要。您可以将其写在一张纸上，或者为了更高的安全性，如果这个钱包很重要，我推荐将其刻在不锈钢介质上以防火灾、洪水或倒塌的风险（对于旨在保护少量比特币的热钱包，简单的纸质备份可能就足够了）。
*显然，您永远不应该像我在本教程中所做的那样在互联网上分享这些词。这个示例钱包只会在 Testnet 上使用，并将在教程结束时删除。*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

在物理介质上正确记录下您的助记词后，点击“*继续*”。Green 钱包接下来会要求您确认短语中的一些词，以验证您已正确记录它们。用缺失的词填写空白处。

![GREEN 2FA MULTISIG](assets/fr/17.webp)
为您的设备选择PIN码，这将用于解锁您的Green钱包。因此，它是防止未经授权的物理访问的一种保护。这个PIN码不参与您钱包的加密密钥的派生过程。因此，即使没有这个PIN码的访问权限，拥有您的12个或24个单词的助记词短语也将允许您重新获得对本地密钥的访问权限。
建议选择尽可能随机的6位数PIN码。同时，确保保存这个代码，以免您忘记它，否则，您将被迫从助记词短语中恢复您的钱包。您可以稍后添加生物识别锁定选项，以避免每次都输入PIN码。一般来说，生物识别的安全性远不如PIN码本身。因此，默认情况下，我建议不要设置这种解锁选项。

![GREEN 2FA MULTISIG](assets/fr/18.webp)

再次输入您的PIN码以确认。

![GREEN 2FA MULTISIG](assets/fr/19.webp)

等待您的钱包创建完成，然后点击“*创建账户*”按钮。

![GREEN 2FA MULTISIG](assets/fr/20.webp)

然后您可以选择标准的单签名钱包或双因素认证（2FA）保护的钱包。在本教程中，我们将选择第二个选项。

![GREEN 2FA MULTISIG](assets/fr/21.webp)

就这样，您的比特币多重签名钱包已经通过Green应用成功创建！

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## 设置2FA

点击您的账户。

![GREEN 2FA MULTISIG](assets/fr/23.webp)

点击绿色按钮“*通过添加2FA增加您账户的安全性*”。

![GREEN 2FA MULTISIG](assets/fr/24.webp)
然后您将有选项选择访问2/2多重签名的第二把钥匙的认证方法。在本教程中，我们将使用认证应用程序。如果您不熟悉这类应用，我建议查看我们关于Authy的教程：
https://planb.network/tutorials/others/authy

选择“*认证器应用程序*”。

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green随后会显示一个二维码和一个恢复密钥。如果您丢失了Authy应用，这个密钥允许您恢复对2FA的访问。建议安全备份此密钥，尽管如前所述，您总是可以在时间锁过期后重新获得对您比特币的访问权限。

在您的认证应用中添加一个新代码，然后扫描Green提供的二维码。

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*显然，您永远不应该在互联网上分享这个密钥和二维码，与我在本教程中所做的相反。这个示例钱包只会在Testnet上使用，并将在教程结束时删除。*

点击“*继续*”按钮。

![GREEN 2FA MULTISIG](assets/fr/27.webp)

输入您的认证应用上显示的动态6位数代码。

![GREEN 2FA MULTISIG](assets/fr/28.webp)

双因素认证现在已启用。

![GREEN 2FA MULTISIG](assets/fr/29.webp)
通过浏览这个菜单，您还可以调整时间锁的持续时间。这个倒计时从接收比特币开始，一旦时间锁到期，您的资金只能使用您的本地密钥进行消费，无需使用双因素认证（2FA）。默认持续时间设置为12个月，但对于储蓄钱包，选择15个月可能更明智，以减少时间锁更新的频率。相反，对于消费钱包，6个月的时间锁可能更合适，因为它将随着您的日常交易频繁更新，较短的时间锁可以减少在2FA出现问题时的等待时间。选择最适合您的时间锁持续时间取决于您。
![GREEN 2FA MULTISIG](assets/fr/30.webp)

您现在可以退出这个菜单。您的多重签名钱包已经准备好了！

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## 在Blockstream Green上设置您的钱包

如果您希望自定义您的钱包，请点击右上角的三个小点。

![GREEN 2FA MULTISIG](assets/fr/32.webp)
“*重命名*”选项允许您自定义钱包的名称，这特别有用，如果您在同一个应用上管理多个钱包。
![GREEN 2FA MULTISIG](assets/fr/33.webp)

“*单位*”菜单让您有机会更改钱包的基本单位。例如，您可以选择以聪而不是比特币来显示它。

![GREEN 2FA MULTISIG](assets/fr/34.webp)

“*设置*”菜单提供了访问您的比特币钱包不同选项的途径。

![GREEN 2FA MULTISIG](assets/fr/35.webp)

在这里，例如，您将找到您的扩展公钥及其*描述符*，如果您计划从这个钱包设置一个仅观察钱包，这会很有用。

![GREEN 2FA MULTISIG](assets/fr/36.webp)

您还可以更改钱包的PIN码并启用生物识别登录。

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## 使用Blockstream Green

现在您的比特币钱包已经设置好了，您已经准备好接收您的第一批sats了！为此，只需点击“*接收*”按钮。

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green接下来会显示您钱包的第一个空白接收地址。您可以扫描关联的二维码或直接复制地址来发送比特币到这个地址。这种类型的地址不指定付款人要发送的金额。然而，您可以通过点击右上角的三个小点，然后点击“*请求金额*”，并输入所需金额，来生成一个请求特定金额的地址。

![GREEN 2FA MULTISIG](assets/fr/39.webp)

当交易在网络上广播时，它将出现在您的钱包中。

![GREEN 2FA MULTISIG](assets/fr/40.webp)

等待获得足够的确认来考虑交易为最终完成。

![GREEN 2FA MULTISIG](assets/fr/41.webp)

有了比特币在您的钱包里，您现在也可以发送它们。点击“*发送*”。

![GREEN 2FA MULTISIG](assets/fr/42.webp)

在接下来的页面上，输入收件人的地址。您可以手动输入或扫描二维码。

![GREEN 2FA MULTISIG](assets/fr/43.webp)

选择支付金额。
![GREEN 2FA MULTISIG](assets/fr/44.webp)在屏幕底部，您可以为此交易选择费率。您可以选择跟随应用程序的推荐或自定义您的费用。与其他待处理交易相比，费用越高，您的交易处理速度就越快。要了解费用市场，您可以在“*交易费用*”部分访问[Mempool.space](https://mempool.space/)。
![GREEN 2FA MULTISIG](assets/fr/45.webp)

点击“*下一步*”访问您交易的摘要屏幕。验证地址、金额和费用是否正确。

![GREEN 2FA MULTISIG](assets/fr/46.webp)

如果一切看起来都不错，将屏幕底部的绿色按钮向右滑动，以在比特币网络上签名并广播交易。

![GREEN 2FA MULTISIG](assets/fr/47.webp)

这是您需要输入认证码以解锁由Blockstream持有的多签名第二钥匙的时刻。输入您的认证应用上显示的6位数代码。

![GREEN 2FA MULTISIG](assets/fr/48.webp)

您的交易现在将出现在您的比特币钱包的仪表板上，等待确认。

![GREEN 2FA MULTISIG](assets/fr/49.webp)

就这样，您现在知道如何使用Blockstream Green的2FA选项轻松设置2/2多签名钱包了！

如果您觉得这个教程有帮助，我会很感激如果您能在下面留下绿色的赞。欢迎在您的社交网络上分享这篇文章。非常感谢！

我还推荐查看这个关于设置Liquid钱包的Blockstream Green移动应用的完整教程：

https://planb.network/tutorials/wallet/blockstream-green-liquid