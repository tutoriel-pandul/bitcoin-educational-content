---
name: Blockstream Green - 桌面版
description: 在计算机上使用Green Wallet软件
---
![cover](assets/cover.webp)

在本教程中，我们将探讨如何在计算机上使用Blockstream Green软件，以管理硬件钱包上的安全钱包。使用硬件钱包时，使用计算机上的软件来管理这个钱包是必不可少的。这个管理软件无法访问私钥；它仅用于检查钱包的余额、生成接收地址以及构建和广播将由硬件钱包签名的交易。Green代表了管理比特币硬件钱包的众多解决方案之一。

到2024年，Blockstream Green仅与Ledger Nano S（旧版本）、Ledger Nano X、Trezor One、Trezor T和Blockstream Jade设备兼容。

## 介绍Blockstream Green

Blockstream Green是一款可在移动设备和桌面上使用的软件。这个钱包原名为Green Address，自2016年被Blockstream收购后成为了Blockstream的项目。

Green是一个非常用户友好的应用程序，特别适合初学者。它提供了各种功能，如热钱包、硬件钱包以及Liquid侧链上的钱包的管理。您还可以使用它来设置仅观察钱包。

![GREEN-DESKTOP](assets/fr/01.webp)

在本教程中，我们将仅关注在计算机上使用软件。要探索Green的其他用途，我邀请您查看我们的其他专门教程：

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## 安装和设置Blockstream Green软件

首先在您的计算机上安装Blockstream Green软件。前往[官方网站](https://blockstream.com/green/)，然后点击“*立即下载*”按钮。然后根据您的操作系统遵循安装过程。

![GREEN-DESKTOP](assets/fr/02.webp)

启动应用程序，然后勾选“*我接受条款...*”。

![GREEN-DESKTOP](assets/fr/03.webp)

当您第一次打开Green时，主屏幕会显示出没有配置的钱包。稍后，如果您创建或导入钱包，它们将出现在此界面中。在创建钱包之前，我建议您根据您的期望调整应用程序的设置。点击左下角的设置图标。

![GREEN-DESKTOP](assets/fr/04.webp)

在“*常规*”菜单中，您可以更改软件语言并启用实验功能（如果您愿意）。

![GREEN-DESKTOP](assets/fr/05.webp)
在“*网络*”菜单中，您可以启用通过Tor的连接，Tor网络加密了您的所有连接并使您的活动难以追踪。尽管这个选项可能稍微降低应用程序的性能，但为了保护您的隐私（特别是如果您没有使用自己的完整节点），强烈推荐使用此选项。
![GREEN-DESKTOP](assets/fr/06.webp)

对于拥有自己完整节点的用户，Green提供了通过Electrum服务器连接到它的可能性，确保对比特币网络信息和交易广播的完全控制。要做到这一点，请点击“*自定义服务器和验证*”菜单，然后输入您的Electrum服务器信息。

![GREEN-DESKTOP](assets/fr/07.webp)
另一种替代功能是“*SPV 验证*”选项，它允许直接验证某些区块链数据，从而减少了对 Blockstream 默认节点的信任需求，尽管这种方法并不提供全节点的所有保证。这个选项也可以在“*自定义服务器和验证*”菜单中找到。
![GREEN-DESKTOP](assets/fr/08.webp)

一旦根据您的需求调整了这些设置，您就可以退出这个界面。

## 将比特币钱包导入 Blockstream Green

您现在已经准备好导入您的比特币钱包。点击“**开始**”按钮。

![GREEN-DESKTOP](assets/fr/09.webp)

您可以选择创建一个本地软件钱包或通过硬件钱包管理一个冷钱包。对于本教程，我们将重点介绍管理硬件钱包，因此您需要选择“*在硬件钱包上*”选项。

另一方面，“*仅查看*”选项允许您导入一个扩展公钥（`xpub`）来查看钱包的交易，而无法花费相关资金。

![GREEN-DESKTOP](assets/fr/10.webp)

如果您使用的是 Jade，点击相应的按钮。否则，选择“*连接其他硬件设备*”。在我的案例中，我使用的是 Ledger Nano S。对于 Ledger 用户，请确保在您的硬件钱包上安装了“*比特币传统*”应用程序，因为 Green 只支持这个版本。

![GREEN-DESKTOP](assets/fr/11.webp)

将您的硬件钱包连接到计算机并在 Green 上选择它。

![GREEN-DESKTOP](assets/fr/12.webp)

等待 Green 导入您钱包的信息，之后您将能够访问它。

![GREEN-DESKTOP](assets/fr/13.webp)

此时，有两种可能的情况。如果您之前已经使用过您的硬件钱包，您应该会在软件上看到您的账户出现。但如果像我一样，您刚刚通过生成助记词初始化了您的硬件钱包而还没有使用过它，您将需要创建一个账户。点击“*创建账户*”。
![GREEN-DESKTOP](assets/fr/14.webp)
如果您希望使用经典钱包，请选择“*标准*”。

![GREEN-DESKTOP](assets/fr/15.webp)

您现在可以访问您的账户了。

![GREEN-DESKTOP](assets/fr/16.webp)

## 使用 Blockstream Green 和硬件钱包

现在您的比特币钱包已经设置好了，您已经准备好接收您的第一笔 sats 了！为此，只需点击“*接收*”按钮。

![GREEN-DESKTOP](assets/fr/17.webp)

点击“*复制地址*”按钮复制地址，或扫描其二维码。

![GREEN-DESKTOP](assets/fr/18.webp)

一旦交易在网络上广播，它将出现在您的钱包中。等待获得足够的确认以将交易视为不可变。

![GREEN-DESKTOP](assets/fr/19.webp)

有了比特币在您的钱包中，您现在可以发送它们了。点击“*发送*”按钮。

![GREEN-DESKTOP](assets/fr/20.webp)

在接下来的页面中，输入收件人的地址。您可以手动输入，也可以用您的网络摄像头扫描二维码。

![GREEN-DESKTOP](assets/fr/21.webp)

选择支付金额。

![GREEN-DESKTOP](assets/fr/22.webp)
在屏幕底部，您可以为此次交易选择费率。您可以选择遵循应用程序的推荐或自定义您的费用。与其他待处理交易相比，费用越高，您的交易处理速度就越快。要了解费用市场，您可以在“*交易费用*”部分访问[Mempool.space](https://mempool.space/)。

![GREEN-DESKTOP](assets/fr/23.webp)

如果您希望特别选择在交易中使用哪些UTXOs，请点击“*手动币种选择*”按钮。

![GREEN-DESKTOP](assets/fr/24.webp)

检查您的交易设置，如果一切如您所预期，点击“*下一步*”。

![GREEN-DESKTOP](assets/fr/25.webp)

再次确认地址、金额和费用是否正确，然后点击“*确认交易*”。

![GREEN-DESKTOP](assets/fr/26.webp)

确保硬件钱包屏幕上的所有交易参数都正确，然后使用它签署交易。

![GREEN-DESKTOP](assets/fr/27.webp)

一旦硬件钱包签署了交易，Green自动在比特币网络上广播它。您的交易随后将出现在您的比特币钱包的仪表板上，等待确认。

![GREEN-DESKTOP](assets/fr/28.webp)

就这样，您现在知道如何轻松设置Blockstream Green软件来管理您在硬件钱包上的比特币钱包了。
如果您觉得这个教程有帮助，我会很感激您在下面留个赞。欢迎在您的社交网络上分享这篇文章。非常感谢！
我还推荐查看这个关于设置热钱包的Blockstream Green移动应用的完整教程：

https://planb.network/tutorials/wallet/blockstream-green