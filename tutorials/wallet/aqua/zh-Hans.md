---
name: Aqua
description: 将比特币、闪电网络和Liquid集于一身的钱包
---
![cover](assets/cover.webp)

Aqua 是一个移动应用程序，它允许用户轻松创建一个用于比特币和Liquid的热钱包，并且还提供了使用闪电网络的可能性，无需管理节点的复杂性，这得益于集成的交换功能。它还支持跨各种网络管理USDT稳定币。

由Samson Mow领导的公司JAN3开发的Aqua应用程序最初是专门为拉丁美洲用户的需求而设计的，尽管它适用于全球任何用户。对于初学者和那些每天使用比特币进行支付的人来说，它特别有趣。

在本教程中，我们将探索如何使用Aqua的许多功能。但在此之前，让我们花点时间了解什么是比特币的侧链以及Liquid是如何工作的，这将使我们能够充分理解Aqua的兴趣点。

![AQUA](assets/fr/01.webp)

## 什么是侧链？

比特币协议有意设置了技术限制，以帮助维持网络的去中心化并确保所有用户之间的安全分布。然而，这些限制有时可能会让用户感到沮丧，特别是在由大量同时交易引起的拥堵期间。关于比特币可扩展性的辩论长期以来一直分裂着社区，特别是在区块大小战争期间。自那以后，比特币社区内普遍认为，可扩展性必须通过链下解决方案，在第二层系统上确保。这些解决方案中包括侧链，与闪电网络等其他系统相比，侧链仍然相对未知且使用不足。

侧链是一个独立的区块链，与主比特币区块链并行运行。它通过一种称为“*双向锚定*”的机制使用比特币作为记账单位。该系统允许在主链上锁定比特币以在侧链上复制其价值，其中它们作为由原始比特币支持的代币流通。这些代币通常与主链上锁定的比特币保持价值平价，且该过程可以逆转，以在比特币上检索资金。
侧链的目标是提供额外的功能或技术改进，如更快的交易、降低的费用或对智能合约的支持。这些创新并不总是可以直接在比特币区块链上实现，而不损害其去中心化或安全性。因此，侧链允许在保持比特币完整性的同时测试和探索新解决方案。然而，这些协议通常需要妥协，特别是在去中心化和安全性方面，这取决于所选择的治理模型和共识机制。
## 什么是Liquid？

Liquid 是建立在比特币之上的联合侧链，由Blockstream开发，旨在提高交易的速度、隐私和功能性。它使用建立在联盟上的双边锚定机制在主链上锁定比特币，并反过来创建Liquid-比特币（L-BTC），这些代币在Liquid上流通，同时仍由原始比特币支持。

![AQUA](assets/fr/02.webp)

Liquid网络基于一个由比特币生态系统中认可的实体组成的联盟，这些实体验证区块并管理双边锚定。除了L-BTC，Liquid还允许发行其他数字资产，如稳定币USDT或其他加密货币。

![AQUA](assets/fr/03.webp)

## 安装Aqua应用

第一步自然是下载Aqua应用。前往您的应用商店：
- [对于Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [对于Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
对于Android用户，您还可以选择通过GitHub上[可用的`.apk`文件](https://github.com/AquaWallet/aqua-wallet/releases)安装应用。

![AQUA](assets/fr/05.webp)

启动应用程序，然后勾选“*我已阅读并同意服务条款和隐私政策*”。

![AQUA](assets/fr/06.webp)

## 在Aqua上创建您的钱包

点击“*创建钱包*”按钮。

![AQUA](assets/fr/07.webp)

就这样，您的钱包已经创建好了！

![AQUA](assets/fr/08.webp)

但在此之前，由于这是一个自托管钱包，务必要物理备份您的助记词。**这个助记词提供了对您所有比特币的完全且不受限制的访问权限**。任何拥有这个短语的人都可以偷走您的资金，即使他们无法物理接触到您的手机。
它允许您在丢失、盗窃或手机损坏的情况下恢复对比特币的访问权限。因此，非常重要的是要小心地将其备份在物理介质（非数字化）上，并将其存放在安全的地方。您可以将其写在一张纸上，或者为了更高的安全性，如果这个钱包很重要，我建议将其刻在不锈钢介质上，以防止火灾、洪水或倒塌的风险（对于旨在保护少量比特币的热钱包来说，简单的纸质备份可能就足够了）。
要做到这一点，请点击设置菜单。

![AQUA](assets/fr/09.webp)

然后点击“*查看种子短语*”。对这个12个单词的短语进行物理备份。

![AQUA](assets/fr/10.webp)

在同一个设置菜单中，您还可以更改应用程序的语言以及使用的法定货币。

![AQUA](assets/fr/11.webp)

在您的钱包中接收您的第一笔比特币之前，**我强烈建议您进行一次干运恢复测试**。记下一个参考信息，比如您的xpub或第一个接收地址，然后在Aqua应用上删除您的钱包，同时保持它为空。接下来，尝试使用您的纸质备份在Aqua上恢复您的钱包。检查恢复后生成的见证信息是否与您最初记录的信息匹配。如果是这样，您就可以确信您的纸质备份是可靠的。要了解如何进行恢复测试的更多信息，我建议您参考这个教程：

https://planb.network/tutorials/wallet/recovery-test

## 在Aqua上接收比特币

现在您的钱包已经设置好了，您已经准备好接收您的第一笔sats了！只需在“*钱包*”菜单中点击“*接收*”按钮。

![AQUA](assets/fr/12.webp)

您可以选择通过onchain、Liquid或通过Lightning接收比特币。

![AQUA](assets/fr/13.webp)

对于onchain交易，Aqua将生成一个特定的接收地址，您可以在那里接收您的sats。

![AQUA](assets/fr/14.webp)

同样，如果选择Liquid，Aqua将为您提供一个Liquid地址。

![AQUA](assets/fr/15.webp)

如果您更愿意通过Lightning接收资金，您首先需要指定所需金额。

![AQUA](assets/fr/16.webp)

然后，点击“*生成发票*”。

![AQUA](assets/fr/17.webp)
Aqua 将创建一个发票以从 Lightning 钱包接收资金。需要注意的是，与 onchain 和 Liquid 选项不同，通过 Lightning 收到的资金将使用 Boltz 工具自动转换为 Liquid 上的 L-BTC，因为 Aqua 不是 Lightning 节点。这个过程允许您通过 Lightning 接收和发送资金，但无需将您的比特币保留在 Lightning 上。![AQUA](assets/fr/18.webp)

就我个人而言，我将首先通过 Lightning 向 Aqua 发送比特币。一旦使用提供的发票完成交易，就会收到确认。

![AQUA](assets/fr/19.webp)

要跟踪交换的进度，请返回到您的钱包主页并点击“*L2 Bitcoin*”账户，其中列出了 Lightning（通过交换）和 Liquid 交易。

![AQUA](assets/fr/20.webp)

在这里，您可以查看您的交易以及您的 L-BTC 余额。

![AQUA](assets/fr/21.webp)

## 用 Aqua 交换比特币

现在您的 Aqua 钱包中有资产，您可以直接从应用程序交换它们，要么将它们转移到主比特币区块链，要么转移到 Liquid。您还可以将您的比特币转换为稳定币 USDT（或其他）。要做到这一点，请访问“*Marketplace*”菜单。

![AQUA](assets/fr/22.webp)

点击“*Swaps*”。

![AQUA](assets/fr/23.webp)

在“*Transfer from*”框中，选择您想要交换的资产。目前，我只有 L-BTC，所以这就是我选择的。

![AQUA](assets/fr/24.webp)

在“*Transfer to*”框中，选择您交换的目标资产。就我而言，我选择了 Liquid 网络上的 USDT。

![AQUA](assets/fr/25.webp)

输入您希望转换的金额。

![AQUA](assets/fr/26.webp)

点击“*Continue*”确认。

![AQUA](assets/fr/27.webp)

确保交换设置符合您的要求，然后在屏幕底部滑动“*Swap*”按钮确认。

![AQUA](assets/fr/28.webp)

您的交换现在已确认。

![AQUA](assets/fr/29.webp)

如果我们回到我们的钱包，我们可以看到我们现在在 Liquid 上有了 USDT。

![AQUA](assets/fr/30.webp)

## 用 Aqua 发送比特币

现在您的 Aqua 钱包中有了比特币，您可以选择发送它们。点击“*Send*”按钮。

![AQUA](assets/fr/31.webp)

选择您想要发送的资产或选择执行交易的网络。就我而言，我将通过 Lightning 发送比特币。

![AQUA](assets/fr/32.webp)
接下来，输入发送付款所需的信息：对于 Bitcoin onchain 或 Liquid，您需要输入接收地址；对于 Lightning，需要一个发票。您可以直接将这些信息粘贴到指定字段中，或使用 QR 码图标打开您的相机并扫描地址或发票。然后点击“*Continue*”。
![AQUA](assets/fr/33.webp)

如果所有信息看起来都正确，再次点击“*Continue*”。

![AQUA](assets/fr/34.webp)
Aqua 接着向您展示交易的摘要。确保所有信息都是正确的，特别是目的地址、费用和金额。要确认交易，请滑动屏幕底部的“*滑动以发送*”按钮。
![AQUA](assets/fr/35.webp)

然后，会向您提供发送的确认。

![AQUA](assets/fr/36.webp)

就这样，您现在知道如何使用 Aqua 应用程序在单一界面上接收和支出比特币、闪电网络和Liquid 上的资金了。

如果您觉得这个教程有帮助，我会很感激您能在下面点个赞。欢迎在您的社交网络上分享这篇文章。非常感谢！

我还建议您查看关于 Blockstream Green 移动应用程序的另一个完整教程，这是设置您的 Liquid 钱包的另一个有趣解决方案：

https://planb.network/tutorials/wallet/blockstream-green-liquid