---
name: Blockstream Green - Liquid
description: Setting up a wallet on the Liquid Network sidechain
---
![cover](assets/cover.webp)
The Bitcoin protocol has intentional technical limitations that help maintain the network's decentralization and ensure security distribution among all users. However, these limits can sometimes frustrate users, especially during congestion caused by a high volume of simultaneous transactions. The debate over Bitcoin's scalability has long divided the community, particularly during the Blocksize War. Since that episode, it is widely recognized within the Bitcoin community that scalability must be ensured by off-chain solutions, on second-layer systems. Among these solutions are sidechains, which are still relatively unknown and underused compared to other systems like the Lightning Network.

A sidechain is an independent blockchain that operates in parallel to the main Bitcoin blockchain. It uses bitcoin as a unit of account through a mechanism called "*two-way peg*". This system allows locking bitcoins on the main chain to replicate their value on the sidechain, where they circulate as tokens backed by the original bitcoins. These tokens normally maintain a value parity with the bitcoins locked on the main chain, and the process can be reversed to recover the funds on Bitcoin.

The goal of sidechains is to offer additional functionalities or technical improvements, such as faster transactions, reduced fees, or support for smart contracts. These innovations cannot always be implemented directly on the Bitcoin blockchain without compromising its decentralization or security. Sidechains thus allow for testing and exploring new solutions while preserving the integrity of Bitcoin. However, these protocols often require compromises, particularly in terms of decentralization and security, depending on the chosen governance model and consensus mechanism.

Today, the most well-known sidechain is probably Liquid. In this tutorial, I will first introduce you to what Liquid is, and then guide you on how to start using it easily through the Blockstream Green application, to take advantage of its benefits.

![LIQUID GREEN](assets/fr/01.webp)

## What is Liquid Network?

Liquid is a federated sidechain built on top of Bitcoin, developed by Blockstream, aiming to improve the speed, privacy, and functionalities of transactions. It uses a bilateral anchoring mechanism established on a federation to lock bitcoins on the main chain and create, in return, Liquid-bitcoins (L-BTC), tokens circulating on Liquid while remaining backed by the original bitcoins.

![LIQUID GREEN](assets/fr/02.webp)
The Liquid network is based on a federation of participants, consisting of recognized entities from the Bitcoin ecosystem, who validate blocks and manage bilateral anchoring. In addition to L-BTC, Liquid also allows the issuance of other digital assets, such as stablecoins or other cryptocurrencies.
![LIQUID GREEN](assets/fr/03.webp)

## Introduction to Blockstream Green

Blockstream Green is a software wallet available on mobile and desktop. Formerly known as *Green Address*, this wallet became a Blockstream project following its acquisition in 2016.

Green is an application that is particularly easy to use, making it interesting for beginners. It offers all the essential features of a good Bitcoin wallet, including RBF (*Replace-by-Fee*), an option to connect via Tor, the ability to connect your own node, the SPV (*Simple Payment Verification*) option, labeling, and coin control.

Blockstream Green also supports the Liquid network, and that's what we're going to explore in this tutorial. If you wish to use Green for other applications, I also recommend consulting these other tutorials:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Installing and Setting Up the Blockstream Green Application

The first step is naturally to download the Green application. Go to your application store:
- [For Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet) ;
- [For Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

For Android users, you also have the option to install the application via the `.apk` file [available on Blockstream's GitHub](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Launch the application, then check the box "*I accept the terms...*".

![LIQUID GREEN](assets/fr/06.webp)

When you open Green for the first time, the home screen appears without any wallets configured. Later, if you create or import wallets, they will appear in this interface. Before moving on to creating a wallet, I advise you to adjust the application settings according to your expectations. Click on "*Application Settings*".

![LIQUID GREEN](assets/fr/07.webp)

The "*Enhanced Privacy*" option, available only on Android, improves privacy by disabling screenshots and hiding application previews. It also automatically locks access to the application as soon as your phone is locked, making your data more difficult to expose.
![LIQUID GREEN](assets/fr/08.webp)
For those looking to enhance their privacy, the app offers the option to route your traffic through Tor, a network that encrypts all your connections and makes your activities difficult to trace. Although this option may slightly slow down the app's performance, it is highly recommended to protect your privacy, especially if you're not using your own full node.

![LIQUID GREEN](assets/fr/09.webp)

For users who have their own full node, Green Wallet allows you to connect to it via an Electrum server, ensuring full control over Bitcoin network information and transaction broadcasting. However, this feature is relevant for traditional Bitcoin wallets, so you don't need it if you're using Liquid.

![LIQUID GREEN](assets/fr/10.webp)

Another alternative feature is the "*SPV Verification*" option, which allows for direct verification of certain blockchain data, thereby reducing the need to trust Blockstream's default node, although this method does not provide all the assurances of a full node. Again, this will only concern your onchain Bitcoin wallets, and not Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Once these settings are adjusted according to your needs, click the "*Save*" button and restart the app.

![LIQUID GREEN](assets/fr/12.webp)

## Creating a Liquid Wallet on Blockstream Green

You are now ready to create a Liquid wallet. Click the "*Get Started*" button.

![LIQUID GREEN](assets/fr/13.webp)

You have the choice between creating a software wallet locally or managing a cold wallet via a hardware wallet. For this tutorial, we will focus on creating a hot wallet on Liquid, so you will need to select the "*On This Device*" option. You can also use a compatible hardware wallet, such as the Blockstream Jade, to secure your Liquid wallet.

![LIQUID GREEN](assets/fr/14.webp)

You can then choose to restore an existing Bitcoin wallet or create a new one. For the purposes of this tutorial, we will create a new wallet. However, if you need to regenerate an existing Liquid wallet from its mnemonic phrase, for example, due to the loss of your hardware wallet, you will need to choose the second option.

![LIQUID GREEN](assets/fr/15.webp)

You then have the choice between a 12-word or a 24-word mnemonic phrase. This phrase will allow you to recover access to your wallet from any compatible software in case of issues with your phone. Currently, opting for a 24-word phrase does not offer more security than a 12-word phrase. Therefore, I recommend choosing a **12-word** mnemonic phrase.
Green will then provide you with your mnemonic phrase. Before continuing, make sure you are not being observed. Click on "*Show recovery phrase*" to display it on the screen.
![LIQUID GREEN](assets/fr/16.webp)

**This mnemonic phrase gives full and unrestricted access to all your bitcoins.** Anyone in possession of this phrase can steal your funds, even without physical access to your phone.

It allows you to restore access to your bitcoins in case of loss, theft, or damage to your phone. Therefore, it is very important to carefully save it **on a physical medium (not digital)** and to store it in a secure location. You can write it down on a piece of paper, or for more security, if this wallet is significant, I recommend engraving it on a stainless steel medium to protect against the risks of fires, floods, or collapses (for a hot wallet intended to secure a small amount of bitcoins, a simple paper backup is probably sufficient).

*Obviously, you should never share these words on the internet, contrary to what I am doing in this tutorial. This example wallet will be used only on the Liquid Testnet and will be deleted at the end of the tutorial.*

![LIQUID GREEN](assets/fr/17.webp)

After correctly noting your mnemonic phrase on a physical medium, click on "*Continue*". Green Wallet will then ask you to confirm some words from your phrase to verify that you have recorded them correctly. Fill in the blanks with the missing words.

![LIQUID GREEN](assets/fr/18.webp)

Choose the PIN code for your device, which will be used to unlock your Green wallet. It is therefore a protection against unauthorized physical access. This PIN code does not play a part in the derivation of your wallet's cryptographic keys. Thus, even without access to this PIN code, the possession of your 12 or 24-word mnemonic phrase will allow you to regain access to your bitcoins.

It is recommended to choose a 6-digit PIN code as random as possible. Also, make sure to save this code so you don't forget it, otherwise, you will be forced to recover your wallet from the mnemonic phrase. Later, you can add a biometric locking option to avoid entering the PIN every time you use it. Generally speaking, biometrics are much less secure than the PIN itself. Therefore, by default, I advise against setting up this unlocking option.

![LIQUID GREEN](assets/fr/19.webp)

Enter your PIN a second time to confirm it.

![LIQUID GREEN](assets/fr/20.webp)
Wait for your wallet to be created, then click on the "*Create an account*" button.
![LIQUID GREEN](assets/fr/21.webp)

In the "*Assets*" box, select "*Liquid Bitcoin*". You then have the choice between a standard single-signature wallet, which we will use in this tutorial, or a wallet protected by two-factor authentication (2FA).

![LIQUID GREEN](assets/fr/22.webp)

And there you have it, your Liquid wallet has been successfully created using the Green app!

![LIQUID GREEN](assets/fr/23.webp)

Before receiving your first bitcoins on your Liquid wallet, **I strongly advise you to perform an empty recovery test**. Note down a reference information, such as your xpub or the first receiving address, then delete your wallet on the Green app while it is still empty. Next, try to restore your wallet on Green using your paper backups. Check that the witness information generated after the restoration matches the one you initially noted. If so, you can be assured that your paper backups are reliable. To learn more about how to perform a recovery test, I advise you to consult this other tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Setting up your Liquid Wallet

If you wish to customize your wallet, click on the three small dots at the top right.

![LIQUID GREEN](assets/fr/24.webp)

The "*Rename*" option allows you to customize the name of your wallet, which is particularly useful if you manage multiple wallets on the same application.

![LIQUID GREEN](assets/fr/25.webp)

The "*Unit*" menu gives you the option to change the base unit of your wallet. For example, you can choose to display it in satoshis rather than in bitcoins.

![LIQUID GREEN](assets/fr/26.webp)

The "*Settings*" menu provides access to the different options of your Bitcoin wallet.

![LIQUID GREEN](assets/fr/27.webp)

Here you will find, for example, your *descriptor* which can be useful if you plan to set up a watch-only wallet from this Liquid wallet.

![LIQUID GREEN](assets/fr/28.webp)

You can also change the PIN code of your wallet and enable biometric login.

![LIQUID GREEN](assets/fr/29.webp)

## Using your Liquid Wallet

Now that your Liquid wallet is set up, you are ready to receive your first L-sats!
If you don't yet own L-BTC, there are several options available to you. The first is to have it sent directly to you. If someone wants to pay you in bitcoins on Liquid, simply give them a receiving address. The other solution is to exchange your onchain bitcoins or those on the Lightning network for L-BTC. To do this, you can use [a bridge such as Boltz](https://boltz.exchange/). Just enter your Liquid address on the site, then make the payment either via the Lightning network or onchain.
![LIQUID GREEN](assets/fr/30.webp)

To generate a Liquid address, click on the "*Receive*" button.

![LIQUID GREEN](assets/fr/31.webp)

Green will then display the first blank receiving address of your wallet. You can either scan the associated QR code or copy the address directly to send L-BTC to it.

![LIQUID GREEN](assets/fr/32.webp)

When the transaction is broadcast on the network, it will appear in your wallet.

![LIQUID GREEN](assets/fr/33.webp)

Wait to get enough confirmations to consider the transaction as final. On Liquid, confirmations should be quick, as a block is published every minute.

![LIQUID GREEN](assets/fr/34.webp)

With L-sats in your Liquid wallet, you can now also send them. Click on "*Send*".

![LIQUID GREEN](assets/fr/35.webp)

On the next page, enter the Liquid address of the recipient. You can enter it manually or scan their QR code.

![LIQUID GREEN](assets/fr/36.webp)

Choose the amount of the payment.

![LIQUID GREEN](assets/fr/37.webp)

Click on "*Next*" to access a summary screen of your transaction. Check that the address, amount, and fees are correct.

![LIQUID GREEN](assets/fr/38.webp)

If everything looks good to you, slide the green button at the bottom of the screen to the right to sign and broadcast the transaction on the Bitcoin network.

![LIQUID GREEN](assets/fr/39.webp)

Your transaction will now appear on the dashboard of your Bitcoin wallet pending confirmation.

![LIQUID GREEN](assets/fr/40.webp)

And there you have it, you now know how to easily use the Liquid sidechain with the Blockstream Green application!

If you found this tutorial helpful, I would appreciate a thumbs up below. Feel free to share this article on your social networks. Thank you very much!

I also recommend discovering this other complete tutorial on the Blockstream Green mobile app to set up an onchain Bitcoin hot wallet:

https://planb.network/tutorials/wallet/blockstream-green