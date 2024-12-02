---
name: Blockstream Green - 仅限查看
description: 设置一个仅限查看的钱包
---
![cover](assets/cover.webp)

在本教程中，您将学习如何使用Blockstream Green应用在移动设备上轻松设置一个仅限查看的钱包。

## 什么是仅限查看钱包？

仅限查看钱包，或称为“仅限查看钱包”，是一种软件设计，允许用户观察与一个或多个特定比特币公钥相关的交易，而无需访问相应的私钥。

这种类型的应用程序仅保留监控比特币钱包所需的数据，包括查看其余额和交易历史，但它无法访问私钥。因此，使用仅限查看应用程序的钱包中的比特币是无法被支出的。

![GREEN-WATCH-ONLY](assets/fr/01.webp)

仅限查看通常与硬件钱包一起使用。后者允许在不连接互联网的设备上安全存储钱包的私钥，这种设备的攻击面极小，从而将私钥与可能存在漏洞的环境隔离。另一方面，仅限查看应用程序专门存储比特币钱包的扩展公钥（`xpub`、`zpub`等）。这个父密钥不允许发现关联的私钥，因此，不允许支出比特币。然而，它允许派生子公钥和接收地址。通过了解由硬件钱包保护的钱包的地址，仅限查看应用程序可以在比特币网络上跟踪这些交易，为用户提供监控余额和生成新接收地址的能力，而无需每次都连接他们的硬件钱包。

在本教程中，我提议发现移动设备上最受欢迎的仅限查看钱包解决方案之一：**Blockstream Green**。

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## 介绍Blockstream Green

Blockstream Green是一款可在移动设备和电脑上使用的软件。这个钱包原名为Green Address，2016年被Blockstream收购后成为了Blockstream项目的一部分。

Green是一个非常易于使用的应用程序，特别适合初学者。它提供各种功能，如热钱包、硬件钱包以及Liquid侧链上的钱包的管理。

在本教程中，我们将仅专注于创建一个仅限查看钱包。要探索Green的其他用途，我邀请您查阅我们的其他专门教程：

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## 安装和设置Blockstream Green应用
第一步自然是下载Green应用。前往您的应用商店：
- [对于Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [对于Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

对于Android用户，您还可以选择通过[Blockstream的GitHub上提供的`.apk`文件](https://github.com/Blockstream/green_android/releases)安装应用。

![GREEN-WATCH-ONLY](assets/fr/04.webp)

启动应用，然后勾选“*我接受条款...*”。

![GREEN-WATCH-ONLY](assets/fr/05.webp)
当您第一次打开Green时，主屏幕会显示出来，但没有配置钱包。稍后，如果您创建或导入钱包，它们将出现在此界面中。在开始创建钱包之前，我建议您根据您的期望调整应用的设置。点击“*应用设置*”。
![GREEN-WATCH-ONLY](assets/fr/06.webp)

仅在Android上可用的“*增强隐私*”选项，通过禁用截屏和隐藏应用预览来提高隐私。它还会在您的手机锁定时自动锁定对应用的访问，使您的数据更难以暴露。

![GREEN-WATCH-ONLY](assets/fr/07.webp)

对于希望增强隐私的用户，该应用提供通过Tor路由您的流量的选项，Tor是一个加密您所有连接并使您的活动难以追踪的网络。尽管这个选项可能会稍微降低应用的性能，但为了保护您的隐私，特别是如果您没有使用自己的完整节点，强烈推荐使用这个选项。

![GREEN-WATCH-ONLY](assets/fr/08.webp)

对于拥有自己完整节点的用户，Green Wallet提供了通过Electrum服务器连接到它的可能性，确保对比特币网络信息和交易广播的完全控制。

![GREEN-WATCH-ONLY](assets/fr/09.webp)

另一个替代功能是“*SPV验证*”选项，它允许直接验证某些区块链数据，从而减少对Blockstream默认节点的信任需求，尽管这种方法不提供完整节点的所有保证。

![GREEN-WATCH-ONLY](assets/fr/10.webp)

根据您的需求调整这些设置后，点击“*保存*”按钮并重启应用。

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## 在Blockstream Green上创建仅观察钱包
您现在已经准备好创建一个仅观察钱包。点击“*开始*”按钮。
![GREEN-WATCH-ONLY](assets/fr/12.webp)

您将可以选择几种类型的钱包。对于本教程，我们想要创建一个仅观察钱包，所以点击相应的按钮。

![GREEN-WATCH-ONLY](assets/fr/13.webp)

选择“*单一签名*”选项。

![GREEN-WATCH-ONLY](assets/fr/14.webp)

然后选择“*比特币*”。就我个人而言，我在测试网钱包上进行这个教程，但程序在主网上保持相同。

![GREEN-WATCH-ONLY](assets/fr/15.webp)

您将被要求提供一个扩展公钥（`xpub`、`zpub`等）或一个输出脚本描述符。

![GREEN-WATCH-ONLY](assets/fr/16.webp)

您需要从您希望通过您的仅观察钱包跟踪的钱包中检索此信息。扩展公钥在安全性方面不敏感，因为它不允许访问私钥，但它对您的隐私敏感，因为它揭示了您所有的公钥，因此揭示了您所有的比特币交易。

假设您正在使用Sparrow Wallet通过硬件钱包管理您的钱包，您将在“*设置*”部分找到这些信息。找到这些信息将取决于您使用的钱包管理软件，但通常在设置中找到。

![GREEN-WATCH-ONLY](assets/fr/17.webp)

复制您的扩展公钥并输入到Green应用中，然后点击“*连接*”。

![GREEN-WATCH-ONLY](assets/fr/18.webp)

然后，您将能够看到与此密钥相关的余额以及交易历史。
点击“*接收*”，您可以生成一个接收地址以在您的硬件钱包上接收比特币。然而，我不建议在未先在硬件钱包的屏幕上验证它持有与生成地址相关联的私钥之前使用此选项来锁定比特币。这是一个好习惯。

“*扫描*”选项允许您手动输入私钥，直接从您的Green应用中支出资金。除非在非常特定的情况下，我建议不要使用这个功能，因为它需要在手机上揭露您的私钥，这比您的硬件钱包更容易受到网络攻击。

现在您已经知道如何在智能手机上轻松设置一个仅限查看的钱包了！这是一个非常方便的工具，用于监控硬件钱包上的钱包，而无需每次都连接和解锁它。

如果您觉得这个教程有帮助，我会很感激如果您能在下面留个赞。欢迎在您的社交网络上分享这篇文章。非常感谢！

我还推荐查看这个关于设置热钱包的Blockstream Green应用的完整教程：

https://planb.network/tutorials/wallet/blockstream-green