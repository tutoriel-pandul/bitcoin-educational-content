---
name: Blockstream Green - Liquid
description: 在Liquid Network侧链上设置钱包
---
![cover](assets/cover.webp)
比特币协议具有一些故意设置的技术限制，这有助于维护网络的去中心化并确保所有用户之间的安全分布。然而，这些限制有时会让用户感到沮丧，尤其是在因大量同时交易而导致的拥堵期间。关于比特币可扩展性的争论长期以来一直分裂着社区，特别是在区块大小战争期间。自那以后，比特币社区普遍认识到，必须通过二层系统上的链外解决方案来确保可扩展性。这些解决方案中包括侧链，与诸如闪电网络这样的其他系统相比，侧链仍然相对鲜为人知且使用不足。

侧链是一个独立的区块链，与主比特币区块链并行运作。它通过一种称为“*双向锚定*”的机制使用比特币作为计价单位。该系统允许在主链上锁定比特币以在侧链上复制其价值，其中它们作为由原始比特币支持的代币流通。这些代币通常与主链上锁定的比特币保持价值平衡，且该过程可以逆转，以在比特币上恢复资金。

侧链的目标是提供额外的功能或技术改进，如更快的交易、降低的费用或对智能合约的支持。这些创新并不总是可以直接在比特币区块链上实现，而不影响其去中心化或安全性。因此，侧链允许在保持比特币完整性的同时测试和探索新解决方案。然而，这些协议通常需要妥协，特别是在去中心化和安全性方面，这取决于所选择的治理模型和共识机制。

如今，最著名的侧链可能是Liquid。在本教程中，我将首先向您介绍Liquid是什么，然后指导您如何通过Blockstream Green应用轻松开始使用它，以利用其优势。

![LIQUID GREEN](assets/fr/01.webp)

## 什么是Liquid Network？

Liquid是一个建立在比特币之上的联盟侧链，由Blockstream开发，旨在提高交易的速度、隐私和功能性。它使用基于联盟的双边锚定机制在主链上锁定比特币，并反过来创建Liquid-比特币（L-BTC），这些代币在Liquid上流通，同时仍由原始比特币支持。

![LIQUID GREEN](assets/fr/02.webp)
Liquid网络基于一个由比特币生态系统中认可的实体组成的联盟，这些实体验证区块并管理双边锚定。除了L-BTC，Liquid还允许发行其他数字资产，如稳定币或其他加密货币。
![LIQUID GREEN](assets/fr/03.webp)

## 介绍Blockstream Green

Blockstream Green是一款可在移动设备和桌面上使用的软件钱包。这款钱包原名为*Green Address*，在2016年被Blockstream收购后成为了Blockstream的项目。

Green是一款特别易于使用的应用程序，对初学者来说很有趣。它提供了一个好的比特币钱包的所有基本功能，包括RBF（*Replace-by-Fee*）、通过Tor连接的选项、连接自己的节点、SPV（*Simple Payment Verification*）选项、标签和币控制。

Blockstream Green还支持Liquid网络，这就是我们将在本教程中探索的内容。如果您希望将Green用于其他应用，我还推荐查阅这些其他教程：

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## 安装并设置Blockstream Green应用程序

首先自然是下载Green应用程序。前往您的应用商店：
- [对于Android用户](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet)；
- [对于Apple用户](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590)。

![LIQUID GREEN](assets/fr/04.webp)

对于Android用户，您还可以选择通过[Blockstream的GitHub上提供的`.apk`文件](https://github.com/Blockstream/green_android/releases)安装应用程序。

![LIQUID GREEN](assets/fr/05.webp)

启动应用程序，然后勾选“*我接受条款...*”。

![LIQUID GREEN](assets/fr/06.webp)

当您第一次打开Green时，主屏幕会显示出来，但没有配置任何钱包。稍后，如果您创建或导入钱包，它们将出现在此界面中。在创建钱包之前，我建议您根据您的期望调整应用程序设置。点击“*应用程序设置*”。

![LIQUID GREEN](assets/fr/07.webp)

“*增强隐私*”选项，仅在Android上可用，通过禁用截屏和隐藏应用程序预览来提高隐私。它还会在您的手机锁定时自动锁定对应用程序的访问，使您的数据更难以暴露。
![LIQUID GREEN](assets/fr/08.webp)
对于那些寻求增强隐私的用户，该应用提供了一个选项，通过Tor路由您的流量，Tor是一个加密您所有连接并使您的活动难以追踪的网络。尽管此选项可能稍微降低应用程序的性能，但强烈推荐使用它来保护您的隐私，特别是如果您没有使用自己的完整节点。

![LIQUID GREEN](assets/fr/09.webp)

对于拥有自己完整节点的用户，Green Wallet允许您通过Electrum服务器连接到它，确保对比特币网络信息和交易广播的完全控制。然而，此功能与传统比特币钱包相关，因此如果您使用的是Liquid，就不需要它。

![LIQUID GREEN](assets/fr/10.webp)

另一个替代功能是“*SPV验证*”选项，它允许直接验证某些区块链数据，从而减少对Blockstream默认节点的信任需求，尽管这种方法不提供完整节点的所有保证。同样，这只会涉及您的链上比特币钱包，而不是Liquid。

![LIQUID GREEN](assets/fr/11.webp)

根据您的需求调整这些设置后，点击“*保存*”按钮并重启应用程序。

![LIQUID GREEN](assets/fr/12.webp)

## 在Blockstream Green上创建Liquid钱包

您现在已经准备好创建Liquid钱包了。点击“*开始*”按钮。

![LIQUID GREEN](assets/fr/13.webp)

您可以选择本地创建软件钱包或通过硬件钱包管理冷钱包。对于本教程，我们将重点介绍在Liquid上创建热钱包，因此您需要选择“*在此设备上*”选项。您也可以使用兼容的硬件钱包，如Blockstream Jade，来保护您的Liquid钱包。

![LIQUID GREEN](assets/fr/14.webp)
接下来，您可以选择恢复已有的比特币钱包或创建一个新钱包。在本教程中，我们将创建一个新钱包。然而，如果您需要从助记词重新生成一个已有的Liquid钱包，例如因为硬件钱包的丢失，您需要选择第二个选项。
![LIQUID GREEN](assets/fr/15.webp)

然后您可以在12个词或24个词的助记词之间做选择。这个短语将允许您在手机出现问题时，从任何兼容软件中恢复对钱包的访问。目前，选择24个词的短语并不比12个词的短语提供更多的安全性。因此，我推荐选择**12个词**的助记词。
Green接下来会提供您的助记词。在继续之前，请确保没有人在观察您。点击“*显示恢复短语*”将其显示在屏幕上。
![LIQUID GREEN](assets/fr/16.webp)

**这个助记词提供了对您所有比特币的完全且不受限制的访问。**任何拥有这个短语的人都可以偷走您的资金，即使没有物理访问您的手机。

它允许您在手机丢失、被盗或损坏的情况下恢复对比特币的访问。因此，非常重要的是要仔细地将其**保存在物理介质上（非数字化）**并存放在安全的地方。您可以将其写在一张纸上，或者为了更高的安全性，如果这个钱包很重要，我推荐将其刻在不锈钢介质上，以防火灾、洪水或倒塌的风险（对于旨在保护少量比特币的热钱包，简单的纸质备份可能就足够了）。

*显然，您永远不应该在互联网上分享这些词，与我在本教程中所做的相反。这个示例钱包将仅在Liquid测试网上使用，并将在教程结束时删除。*

![LIQUID GREEN](assets/fr/17.webp)

在物理介质上正确记录下您的助记词后，点击“*继续*”。Green钱包接下来会要求您确认短语中的一些词，以验证您是否正确记录了它们。用缺失的词填空。

![LIQUID GREEN](assets/fr/18.webp)

为您的设备选择PIN码，这将用于解锁您的Green钱包。因此，它是一种防止未经授权的物理访问的保护。这个PIN码不参与您钱包的加密密钥的派生。因此，即使没有这个PIN码的访问权限，拥有您的12个或24个词的助记词也将允许您重新获得对比特币的访问。

建议选择尽可能随机的6位PIN码。同时，确保保存这个代码，以免您忘记它，否则，您将被迫从助记词恢复您的钱包。稍后，您可以添加生物识别锁定选项，以避免每次使用时都输入PIN码。一般来说，生物识别比PIN码本身的安全性要低得多。因此，默认情况下，我建议不要设置这个解锁选项。

![LIQUID GREEN](assets/fr/19.webp)

再次输入您的PIN码以确认。

![LIQUID GREEN](assets/fr/20.webp)
等待您的钱包创建完成，然后点击“*创建账户*”按钮。
![LIQUID GREEN](assets/fr/21.webp)
在“*资产*”框中，选择“*Liquid Bitcoin*”。然后，您可以选择标准的单签名钱包，我们将在本教程中使用，或者由两因素认证（2FA）保护的钱包。
![LIQUID GREEN](assets/fr/22.webp)

就这样，您已经成功地使用Green应用创建了您的Liquid钱包！

![LIQUID GREEN](assets/fr/23.webp)

在您的Liquid钱包上收到第一笔比特币之前，**我强烈建议您进行一次空恢复测试**。记下一个参考信息，比如您的xpub或第一个接收地址，然后在Green应用上删除您的钱包，当它还是空的时候。接下来，尝试使用您的纸质备份在Green上恢复您的钱包。检查恢复后生成的见证信息是否与您最初记录的信息匹配。如果是这样，您就可以确信您的纸质备份是可靠的。要了解更多关于如何进行恢复测试的信息，我建议您参考这个其他教程：

https://planb.network/tutorials/wallet/recovery-test

## 设置您的Liquid钱包

如果您希望自定义您的钱包，请点击右上角的三个小点。

![LIQUID GREEN](assets/fr/24.webp)

“*重命名*”选项允许您自定义钱包的名称，这在您在同一应用上管理多个钱包时特别有用。

![LIQUID GREEN](assets/fr/25.webp)

“*单位*”菜单让您有机会更改钱包的基本单位。例如，您可以选择以satoshi而不是比特币来显示它。

![LIQUID GREEN](assets/fr/26.webp)

“*设置*”菜单提供了访问您的比特币钱包不同选项的途径。

![LIQUID GREEN](assets/fr/27.webp)

在这里，您将找到例如您的*描述符*，如果您计划从这个Liquid钱包设置一个仅观察钱包，这可能会很有用。

![LIQUID GREEN](assets/fr/28.webp)

您还可以更改钱包的PIN码并启用生物识别登录。

![LIQUID GREEN](assets/fr/29.webp)

## 使用您的Liquid钱包

现在您的Liquid钱包已经设置好了，您已经准备好接收您的第一笔L-sats了！
如果您还没有拥有L-BTC，有几个可用的选项。第一个是直接让别人发送给您。如果有人想用Liquid上的比特币支付给您，只需给他们一个接收地址。另一个解决方案是将您的链上比特币或那些在闪电网络上的比特币兑换成L-BTC。为此，您可以使用[如Boltz之类的桥](https://boltz.exchange/)。只需在网站上输入您的Liquid地址，然后通过闪电网络或链上进行支付。
![LIQUID GREEN](assets/fr/30.webp)

要生成一个Liquid地址，请点击“*接收*”按钮。

![LIQUID GREEN](assets/fr/31.webp)

Green将会显示您钱包的第一个空白接收地址。您可以扫描关联的二维码或直接复制地址来发送L-BTC到这个地址。

![LIQUID GREEN](assets/fr/32.webp)

当交易在网络上广播时，它将出现在您的钱包中。

![LIQUID GREEN](assets/fr/33.webp)

等待获得足够的确认来认为交易是最终的。在Liquid上，确认应该很快，因为每分钟都会发布一个区块。

![LIQUID GREEN](assets/fr/34.webp)
在您的Liquid钱包中拥有L-sats后，您现在也可以发送它们。点击“*发送*”。
![LIQUID GREEN](assets/fr/35.webp)

在下一页，输入接收者的Liquid地址。您可以手动输入或扫描他们的二维码。

![LIQUID GREEN](assets/fr/36.webp)

选择支付金额。

![LIQUID GREEN](assets/fr/37.webp)

点击“*下一步*”访问您的交易摘要屏幕。检查地址、金额和费用是否正确。

![LIQUID GREEN](assets/fr/38.webp)

如果一切看起来都不错，将屏幕底部的绿色按钮向右滑动，以在比特币网络上签名并广播交易。

![LIQUID GREEN](assets/fr/39.webp)

您的交易现在将出现在您的比特币钱包的仪表板上，等待确认。

![LIQUID GREEN](assets/fr/40.webp)

就这样，您现在知道如何使用Blockstream Green应用程序轻松使用Liquid侧链了！

如果您觉得这个教程有帮助，我会非常感激您在下面点个赞。欢迎在您的社交网络上分享这篇文章。非常感谢！

我还推荐探索这个关于设置onchain比特币热钱包的Blockstream Green移动应用程序的完整教程：

https://planb.network/tutorials/wallet/blockstream-green