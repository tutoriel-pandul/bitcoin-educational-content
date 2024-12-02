---
name: Blockstream Green - Mobile
description: Setting up a mobile software wallet
---
![cover](assets/cover.webp)

A software wallet is an application installed on a computer, smartphone, or any other device connected to the Internet, allowing the management and security of one's Bitcoin wallet keys. Unlike hardware wallets, which isolate private keys, "hot" wallets thus operate in an environment potentially exposed to cyberattacks, increasing the risks of hacking and theft.

Software wallets are to be used for managing reasonable amounts of bitcoins, especially for daily transactions. This can also be an interesting option for people with a limited Bitcoin portfolio, for whom investing in a hardware wallet may seem disproportionate. However, their constant exposure to the Internet makes them less safe for storing your long-term savings or significant funds. For these, it is preferable to opt for more secure solutions, like hardware wallets.

In this tutorial, I will introduce you to one of the best mobile software wallet solutions: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

If you are interested in learning how to use Blockstream Green on a computer, please refer to this other tutorial:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Introduction to Blockstream Green

Blockstream Green is a software wallet available on both mobile and computer. Formerly known as *Green Address*, this wallet became a Blockstream project following its acquisition in 2016.

Green is an application that is particularly easy to use, making it interesting for beginners. It offers all the essential features of a good Bitcoin wallet, including RBF (*Replace-by-Fee*), an option to connect via Tor, the ability to connect one's own node, the SPV (*Simple Payment Verification*) option, labeling, and coin control.

Blockstream Green also supports the Liquid network, a Bitcoin sidechain developed by Blockstream for conducting fast and confidential transactions outside of the main blockchain. This tutorial focuses exclusively on Bitcoin, but a future one will address the use of Liquid.

## Installing and Setting Up the Blockstream Green App

The first step is naturally to download the Green app. Go to your app store:
- [For Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [For Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

For Android users, you also have the option to install the application via the `.apk` file [available on Blockstream's GitHub](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Launch the application, then check the box "*I accept the conditions...*".
![GREEN](assets/fr/04.webp)

When you open Green for the first time, the home screen appears without any configured wallets. Later, if you create or import wallets, they will appear in this interface. Before moving on to creating a wallet, I advise you to adjust the application settings according to your expectations. Click on "*Application Settings*".

![GREEN](assets/fr/05.webp)

The "*Enhanced Privacy*" option, available only on Android, improves privacy by disabling screenshots and hiding application previews. It also automatically locks access to the application as soon as your phone is locked, making your data more difficult to expose.

![GREEN](assets/fr/06.webp)

For those who wish to enhance their privacy, the application offers to route your traffic via Tor, a network that encrypts all your connections and makes your activities difficult to trace. Although this option may slightly slow down the application's performance, it is highly recommended to protect your privacy, especially if you are not using your own full node.

![GREEN](assets/fr/07.webp)

For users who have their own full node, Green Wallet offers the possibility to connect to it via an Electrum server, ensuring full control over Bitcoin network information and transaction broadcasting.

![GREEN](assets/fr/08.webp)

Another alternative feature is the "*SPV Verification*" option, which allows for direct verification of certain blockchain data, thus reducing the need to trust the default Blockstream node, although this method does not provide all the guarantees of a full node.

![GREEN](assets/fr/09.webp)

Once these settings are adjusted according to your needs, click the "*Save*" button and restart the application.

![GREEN](assets/fr/10.webp)

## Creating a Bitcoin Wallet on Blockstream Green

You are now ready to create a Bitcoin wallet. Click on the "*Get Started*" button.

![GREEN](assets/fr/11.webp)

You have the choice between creating a software wallet locally or managing a cold wallet via a hardware wallet. For this tutorial, we will focus on creating a hot wallet, so you will need to select the "*On This Device*" option. In a future tutorial, I will show you how to use the other option.

The "*Watch-only*" option, on the other hand, allows you to import an extended public key (`xpub`) to view transactions of a wallet without being able to spend the associated funds, which is convenient for monitoring a wallet on a hardware wallet, for example.

![GREEN](assets/fr/12.webp)
You can then choose to restore an existing Bitcoin wallet or create a new one. For the purposes of this tutorial, we will create a new wallet. However, if you need to regenerate an already existing Bitcoin wallet from its mnemonic phrase, for example, due to the loss of your hardware wallet, you will need to choose the second option.
![GREEN](assets/fr/13.webp)

You then have the choice between a 12-word or 24-word mnemonic phrase. This phrase will allow you to recover access to your wallet from any compatible software in case of problems with your phone. Currently, opting for a 24-word phrase does not offer more security than a 12-word phrase. Therefore, I recommend choosing a **12-word** mnemonic phrase.

Green will then provide you with your mnemonic phrase. Before continuing, make sure you are not being observed. Click on "*Show recovery phrase*" to display it on the screen.

![GREEN](assets/fr/14.webp)

**This mnemonic phrase gives full and unrestricted access to all your bitcoins.** Anyone in possession of this phrase can steal your funds, even without physical access to your phone.

It allows you to restore access to your bitcoins in case of loss, theft, or damage to your phone. It is therefore very important to carefully save it **on a physical medium (not digital)** and to store it in a secure location. You can write it down on a piece of paper, or for more security, if this wallet is important, I recommend engraving it on a stainless steel medium to protect against the risks of fires, floods, or collapses (for a hot wallet intended to secure a small amount of bitcoins, a simple paper backup is probably sufficient).

*Obviously, you should never share these words on the internet, contrary to what I am doing in this tutorial. This example wallet will be used only on the Testnet and will be deleted at the end of the tutorial.*

![GREEN](assets/fr/15.webp)

After correctly noting your mnemonic phrase on a physical medium, click on "*Continue*". Green Wallet will then ask you to confirm certain words from your phrase to verify that you have recorded them correctly. Fill in the blanks with the missing words.

![GREEN](assets/fr/16.webp)

Choose the PIN code for your device, which will be used to unlock your Green wallet. This is therefore a protection against unauthorized physical access. This PIN code does not play a part in the derivation of the cryptographic keys of your wallet. Thus, even without access to this PIN code, the possession of your 12 or 24-word mnemonic phrase will allow you to regain access to your bitcoins.
It is recommended to choose a 6-digit PIN that is as random as possible. Also, make sure to back up this code so you don't forget it, otherwise, you will be forced to recover your wallet using the mnemonic phrase. Subsequently, you can add a biometric locking option to avoid entering the PIN with each use. Generally speaking, biometrics are much less secure than the PIN itself. Therefore, by default, I advise against setting up this unlocking option.
![GREEN](assets/fr/17.webp)

Enter your PIN a second time to confirm it.

![GREEN](assets/fr/18.webp)

Wait for your wallet to be created, then click on the "*Create an account*" button.

![GREEN](assets/fr/19.webp)

You then have the choice between a standard single-signature wallet, which we will use in this tutorial, or a wallet protected by two-factor authentication (2FA).

![GREEN](assets/fr/20.webp)

The 2FA option on Green creates a 2/2 multisignature wallet, one key of which is kept by Blockstream. This means that to make a transaction, both keys are required: a local key protected by your PIN on your phone, and a remote key secured by 2FA on Blockstream's servers. In case of loss of access to 2FA or unavailability of Blockstream's services, recovery mechanisms based on time-lock scripts ensure the possibility of independently recovering your funds. Although this setup significantly reduces the risk of your bitcoins being stolen, it is more complex to manage and partially depends on Blockstream. For this tutorial, we will opt for a classic single-signature wallet, with keys stored locally on the phone.

And there you have it, your Bitcoin wallet has been successfully created using the Green app!

![GREEN](assets/fr/21.webp)

Before receiving your first bitcoins in your wallet, **I strongly advise you to perform a dry-run recovery test**. Note down a reference information, such as your xpub or the first receiving address, then delete your wallet on the Green app while it is still empty. Next, try to restore your wallet on Green using your paper backups. Check that the witness information generated after the restoration matches the one you initially noted. If this is the case, you can be assured that your paper backups are reliable. To learn more about how to perform a recovery test, I advise you to consult this other tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Setting up your wallet on Blockstream Green
If you want to customize your portfolio, click on the three small dots at the top right.
![GREEN](assets/fr/22.webp)

The "*Rename*" option allows you to customize the name of your portfolio, which is particularly useful if you manage multiple portfolios on the same app.

![GREEN](assets/fr/23.webp)

The "*Unit*" menu gives you the option to change the base unit of your portfolio. For example, you can choose to display it in satoshis rather than in bitcoins.

![GREEN](assets/fr/24.webp)

The "*Settings*" menu provides access to the different options of your Bitcoin wallet.

![GREEN](assets/fr/25.webp)

Here, for example, you will find your extended public key and its *descriptor*, useful if you plan to set up a watch-only wallet from this wallet.

![GREEN](assets/fr/26.webp)

You can also change the PIN code of your wallet and enable biometric login.

![GREEN](assets/fr/27.webp)

## Using Blockstream Green

Now that your Bitcoin wallet is set up, you're ready to receive your first sats! To do this, simply click on the "*Receive*" button.

![GREEN](assets/fr/28.webp)

Green will then display the first blank receiving address of your wallet. You can either scan the associated QR code or copy the address directly to send bitcoins to it. This type of address does not specify the amount to be sent by the payer. However, you can generate an address that requests a specific amount, by clicking on the three small dots at the top right, then on "*Request Amount*", and entering the desired amount.

Since you are using a Segwit v0 account (BIP84), your address will start with `bc1q...`. In my example, I'm using a Testnet wallet, so the prefix is slightly different.

![GREEN](assets/fr/29.webp)

When the transaction is broadcast on the network, it will appear in your wallet.

![GREEN](assets/fr/30.webp)

Wait to get enough confirmations to consider the transaction as final.

![GREEN](assets/fr/31.webp)

With bitcoins in your wallet, you can now also send them. Click on "*Send*".

![GREEN](assets/fr/32.webp)

On the next page, enter the recipient's address. You can enter it manually or scan a QR code.

![GREEN](assets/fr/33.webp)

Choose the payment amount.

![GREEN](assets/fr/34.webp)
At the bottom of the screen, you can select the fee rate for this transaction. You have the option to follow the application's recommendations or to customize your fees. The higher the fees compared to other pending transactions, the faster your transaction will be processed. To understand the fee market, you can visit [Mempool.space](https://mempool.space/) in the "*Transaction Fees*" section.
![GREEN](assets/fr/35.webp)

Click on "*Next*" to access a summary screen of your transaction. Verify that the address, amount, and fees are correct.

![GREEN](assets/fr/36.webp)

If everything is to your satisfaction, slide the green button at the bottom of the screen to the right to sign and broadcast the transaction on the Bitcoin network.

![GREEN](assets/fr/37.webp)

Your transaction will now appear on the dashboard of your Bitcoin wallet awaiting confirmation.

![GREEN](assets/fr/38.webp)

*This tutorial is based on [an original version belonging to Bitstack](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) written by Loïc Morel. Bitstack is a French Bitcoin neo-bank that offers the possibility to save in bitcoins, either through DCA (Dollar Cost Averaging) or via an automatic rounding system of daily expenses.*