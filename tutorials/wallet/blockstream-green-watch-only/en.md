---
name: Blockstream Green - Watch-Only
description: Setting up a watch-only wallet
---
![cover](assets/cover.webp)

In this tutorial, you will learn how to easily set up a watch-only wallet on mobile using the Blockstream Green app.

## What is a Watch-Only Wallet?

A watch-only wallet, or "watch-only wallet," is a type of software designed to allow the user to observe transactions associated with one or more specific Bitcoin public keys, without having access to the corresponding private keys.

This type of application only retains the data necessary for monitoring a Bitcoin wallet, including viewing its balance and transaction history, but it does not have access to the private keys. Therefore, it is impossible to spend the bitcoins held in the wallet on the watch-only app.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Watch-only is generally used in addition to a hardware wallet. The latter allows for the secure storage of the wallet's private keys on a device not connected to the internet, which has a minimal attack surface, thus isolating the private keys from potentially vulnerable environments. The watch-only app, on the other hand, exclusively stores the extended public key (`xpub`, `zpub`, etc.) of the Bitcoin wallet. This parent key does not allow for the discovery of the associated private keys and, consequently, does not permit the spending of bitcoins. However, it allows for the derivation of child public keys and receiving addresses. With knowledge of the addresses of the wallet secured by the hardware wallet, the watch-only app can track these transactions on the Bitcoin network, offering the user the ability to monitor their balance and generate new receiving addresses, without having to connect their hardware wallet each time.

In this tutorial, I propose to discover one of the most popular watch-only wallet solutions on mobile: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Introduction to Blockstream Green

Blockstream Green is software available on mobile and computer. Formerly known as Green Address, this wallet became a Blockstream project following its acquisition in 2016.

Green is a very easy-to-use application, making it particularly suitable for beginners. It offers various features, such as the management of hot wallets, hardware wallets, as well as wallets on the Liquid sidechain.

In this tutorial, we will focus solely on creating a watch-only wallet. To explore other uses of Green, I invite you to consult our other dedicated tutorials:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Installing and Setting Up the Blockstream Green App
The first step is naturally to download the Green app. Go to your app store:
- [For Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [For Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

For Android users, you also have the option to install the app via the `.apk` file [available on Blockstream's GitHub](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Launch the app, then check the box "*I accept the terms...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)

When you open Green for the first time, the home screen appears without a configured wallet. Later, if you create or import wallets, they will appear in this interface. Before moving on to creating a wallet, I advise you to adjust the app's settings according to your expectations. Click on "*Application Settings*".

![GREEN-WATCH-ONLY](assets/fr/06.webp)

The "*Enhanced Privacy*" option, available only on Android, improves privacy by disabling screenshots and hiding app previews. It also automatically locks access to the app as soon as your phone is locked, making your data more difficult to expose.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

For those who wish to enhance their privacy, the app offers to route your traffic through Tor, a network that encrypts all your connections and makes your activities difficult to trace. Although this option may slightly slow down the app's performance, it is highly recommended to protect your privacy, especially if you are not using your own full node.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

For users who have their own full node, Green Wallet offers the possibility to connect to it via an Electrum server, ensuring full control over Bitcoin network information and transaction broadcasting.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Another alternative feature is the "*SPV Verification*" option, which allows for direct verification of certain blockchain data, thus reducing the need to trust Blockstream's default node, although this method does not provide all the guarantees of a full node.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Once these settings are adjusted according to your needs, click the "*Save*" button and restart the app.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Creating a watch-only wallet on Blockstream Green
You are now ready to create a watch-only wallet. Click on the "*Get Started*" button.
![GREEN-WATCH-ONLY](assets/fr/12.webp)

You will have the choice between several types of wallets. For this tutorial, we want to create a watch-only wallet, so click on the corresponding button.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Choose the "*Single Signature*" option.

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Then select "*Bitcoin*". For my part, I am conducting this tutorial on a testnet wallet, but the procedure remains the same on the mainnet.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

You will be asked to provide either an extended public key (`xpub`, `zpub`, etc.), or an output script descriptor.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

You will need to retrieve this information from the wallet you wish to follow via your watch-only wallet. The extended public key is not sensitive in terms of security, as it does not allow access to private keys, but it is sensitive for your privacy, since it reveals all your public keys and therefore all your Bitcoin transactions.

Imagine you are using Sparrow Wallet to manage your wallet on a hardware wallet, you will find this information in the "*Settings*" section. Finding this information will depend on the wallet management software you are using, but it is generally found in the settings.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Copy your extended public key and enter it into the Green app, then click on "*Connect*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

You will then be able to see the balance associated with this key as well as the transaction history.

![GREEN-WATCH-ONLY](assets/fr/19.webp)

By clicking on "*Receive*", you can generate a receiving address to receive bitcoins on your hardware wallet. However, I advise against using this option without first verifying on the hardware wallet's screen that it holds the private key associated with the generated address, before using it to lock bitcoins. This is a good practice to follow.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

The "*Sweep*" option allows you to manually enter a private key to spend funds directly from your Green application. Except in very specific cases, I recommend not using this function, as it requires revealing your private key on a phone, which is much more vulnerable to cyber attacks than your hardware wallet.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
And there you have it, you now know how to easily set up a watch-only wallet on your smartphone! It's a very handy tool for monitoring a wallet on a hardware wallet without having to connect and unlock it every time.

If you found this tutorial helpful, I would appreciate it if you could leave a thumbs up below. Feel free to share this article on your social networks. Thank you very much!

I also recommend checking out this complete tutorial on the Blockstream Green application to set up a hot wallet:

https://planb.network/tutorials/wallet/blockstream-green