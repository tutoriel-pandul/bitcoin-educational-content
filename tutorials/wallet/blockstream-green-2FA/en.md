---
name: Blockstream Green - 2FA
description: Setting up a 2/2 multisig on Green Wallet
---
![cover](assets/cover.webp)

A software wallet is an application installed on a computer, smartphone, or any other device connected to the Internet, allowing the management and security of one's Bitcoin wallet keys. Unlike hardware wallets, which isolate private keys, "hot" wallets thus operate in an environment potentially exposed to cyberattacks, increasing the risks of hacking and theft.

Software wallets are to be used for managing reasonable amounts of bitcoins, especially for daily transactions. This can also be an interesting option for people with a limited Bitcoin portfolio, for whom investing in a hardware wallet may seem disproportionate. However, their constant exposure to the Internet makes them less safe for storing your long-term savings or significant funds. For these, it is preferable to opt for more secure solutions, like hardware wallets.

In this tutorial, I will show you how to enhance the security of a hot wallet by using the "2FA" option on Blockstream Green.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Introduction to Blockstream Green

Blockstream Green is a software wallet available on mobile and desktop. Formerly known as *Green Address*, this wallet became a Blockstream project following its acquisition in 2016.

Green is an application that is particularly easy to use, making it interesting for beginners. It offers all the essential features of a good Bitcoin wallet, including RBF (*Replace-by-Fee*), an option to connect via Tor, the ability to connect one's own node, the SPV (*Simple Payment Verification*) option, labeling, and coin control.

Blockstream Green also supports the Liquid network, a Bitcoin sidechain developed by Blockstream for conducting fast and confidential transactions outside of the main blockchain. In this tutorial, we focus exclusively on Bitcoin, but I have also made another tutorial to learn how to use Liquid on Green:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## The 2/2 multisig (2FA) option

On Green, you can certainly create a classic "singlesig" hot wallet. But you also have the "2FA multisig" option, which allows you to improve the security of your hot wallet without overly complicating its daily management.
You will therefore set up a 2/2 multisig wallet, which means that each transaction will require the signature of two keys. The first key, derived from your 12 or 24-word mnemonic phrase, is secured locally with a PIN code on your phone. You have full control over this key. The second key is held by Blockstream's servers, and its use for signing requires authentication, which can be achieved via a code received by email, SMS, phone call, or, as we will see in this tutorial, via an authentication app (Authy, Google Authenticator, etc.).

To ensure your autonomy in the event of a Blockstream failure (for example, if the company goes bankrupt or the servers holding the second key are destroyed), a timelock mechanism is applied to your multisig. This mechanism transforms the 2/2 multisig into a 1/2 multisig after about one year (or precisely 51,840 blocks, but this value can be changed), after which your wallet will only need your local key to spend the bitcoins. Thus, if you lose access to Blockstream's servers or to 2FA authentication, you just need to wait up to a year to be able to freely use your bitcoins with your app, without depending on Blockstream.

![GREEN 2FA MULTISIG](assets/fr/02.webp)

This method significantly increases the security of your hot wallet, while leaving you in control of your bitcoins and facilitating its daily use. However, it requires regularly refreshing the timelock to maintain the security of the 2FA. The 360-day countdown, during which your funds are protected by the 2FA, starts as soon as you receive bitcoins. If, 360 days after receiving them, you have not made a transaction spending those funds, your bitcoins will only be protected by your local key, without the 2FA.

This constraint makes the 2FA option more suited to a spending wallet, where regular transactions automatically renew the timelocks. For a long-term savings wallet, this can be problematic, as you will need to think about performing a sweep transaction to yourself each year before the timelock expires.

Another downside of this security method is that you will need to use minority script patterns. This means that, from a privacy standpoint, things get complicated: very few people use the same type of script as you, allowing an external observer to more easily identify your wallet footprint. Moreover, these scripts will result in higher transaction fees due to their larger size.
If you prefer not to use the 2FA option and simply want to set up a "singlesig" wallet on Green, I invite you to check out this other tutorial:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Installing and Setting Up Blockstream Green Software

The first step is naturally to download the Green app. Go to your app store:
- [For Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [For Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

For Android users, you also have the option to install the app via the `.apk` file [available on Blockstream's GitHub](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Launch the app, then check the box "*I accept the terms...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

When you open Green for the first time, the home screen appears without any configured wallet. Later, if you create or import wallets, they will appear in this interface. Before moving on to creating a wallet, I advise you to adjust the app settings according to your expectations. Click on "*Application Settings*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

The "*Enhanced Privacy*" option, available only on Android, improves privacy by disabling screenshots and hiding app previews. It also automatically locks access to the app as soon as your phone is locked, making your data more difficult to expose.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

For those who wish to enhance their privacy, the app offers to route your traffic through Tor, a network that encrypts all your connections and makes your activities difficult to trace. Although this option may slightly slow down the app's performance, it is highly recommended to protect your privacy, especially if you are not using your own full node.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

For users who have their own full node, Green Wallet offers the possibility to connect to it via an Electrum server, ensuring full control over Bitcoin network information and transaction broadcasting.

![GREEN 2FA MULTISIG](assets/fr/09.webp)

Another alternative feature is the "*SPV Verification*" option, which allows for direct verification of certain blockchain data, thus reducing the need to trust Blockstream's default node, although this method does not provide all the guarantees of a full node.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Once these settings are adjusted according to your needs, click on the "*Save*" button and restart the application.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Creating a Bitcoin Wallet on Blockstream Green

You are now ready to create a Bitcoin wallet. Click on the "*Get Started*" button.

![GREEN 2FA MULTISIG](assets/fr/12.webp)

You have the choice between creating a software wallet locally or managing a cold wallet via a hardware wallet. For this tutorial, we will focus on creating a hot wallet, so you will need to select the "*On This Device*" option.

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Next, you can choose to restore an existing Bitcoin wallet or create a new one. For the purposes of this tutorial, we will create a new wallet. However, if you need to regenerate an existing Bitcoin wallet from its mnemonic phrase, for example, due to the loss of your old phone, you will need to choose the second option.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

You then have the choice between a 12-word or 24-word mnemonic phrase. This phrase will allow you to recover access to your wallet from any compatible software in case of issues with your phone. Currently, opting for a 24-word phrase does not offer more security than a 12-word phrase. Therefore, I recommend choosing a **12-word** mnemonic phrase.

Green will then provide you with your mnemonic phrase. Before continuing, make sure you are not being observed. Click on "*Show recovery phrase*" to display it on the screen.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**This mnemonic phrase gives complete and unrestricted access to all your bitcoins**. Anyone in possession of this phrase can steal your funds, even without physical access to your phone (under conditions of expired timelock or 2FA in the case of a 2/2 wallet on Green).

It allows you to restore access to your local keys in case of loss, theft, or damage to your phone. It is therefore very important to carefully save it **on a physical medium (not digital)** and to store it in a secure location. You can write it down on a piece of paper, or for more security, if this wallet is important, I recommend engraving it on a stainless steel medium to protect against the risks of fires, floods, or collapses (for a hot wallet intended to secure a small amount of bitcoins, a simple paper backup is probably sufficient).
*Obviously, you should never share these words on the internet, unlike what I am doing in this tutorial. This example wallet will be used only on the Testnet and will be deleted at the end of the tutorial.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

After correctly noting your mnemonic phrase on a physical medium, click on "*Continue*". Green Wallet will then ask you to confirm some words from your phrase to verify that you have recorded them correctly. Fill in the blanks with the missing words.

![GREEN 2FA MULTISIG](assets/fr/17.webp)

Choose the PIN code for your device, which will be used to unlock your Green wallet. It is therefore a protection against unauthorized physical access. This PIN code does not play a part in the derivation of your wallet's cryptographic keys. Thus, even without access to this PIN code, the possession of your 12 or 24-word mnemonic phrase will allow you to regain access to your local keys.

It is recommended to choose a 6-digit PIN code as random as possible. Also, make sure to save this code so you don't forget it, otherwise, you will be forced to recover your wallet from the mnemonic phrase. You can later add an option for biometric locking to avoid entering the PIN every time. Generally speaking, biometrics is much less secure than the PIN itself. Therefore, by default, I advise against setting up this unlocking option.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Enter your PIN a second time to confirm it.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Wait while your wallet is being created, then click on the "*Create an account*" button.

![GREEN 2FA MULTISIG](assets/fr/20.webp)

You then have the choice between a standard single-signature wallet or a wallet protected by two-factor authentication (2FA). In this tutorial, we will choose the second option.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

And there you have it, your Bitcoin multisig wallet has been successfully created using the Green app!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Setting up 2FA

Click on your account.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Click on the green button "*Increase the security of your account by adding 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
You will then have the option to choose the authentication method to access the second key of your 2/2 multisig. For this tutorial, we will use an authentication app. If you are not familiar with this type of app, I recommend consulting our tutorial on Authy:
https://planb.network/tutorials/others/authy

Select "*Authenticator Application*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green will then display a QR code and a recovery key. This key allows you to restore access to your 2FA in case you lose your Authy app. It is recommended to make a secure backup of this key, although you can always regain access to your bitcoins after the expiration of the timelock, as explained earlier.

In your authentication app, add a new code, then scan the QR code provided by Green.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Obviously, you should never share this key and QR code on the internet, contrary to what I am doing in this tutorial. This example wallet will be used only on the Testnet and will be deleted at the end of the tutorial.*

Click on the "*Continue*" button.

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Enter the dynamic 6-digit code present on your authentication app.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

Two-factor authentication is now enabled.

![GREEN 2FA MULTISIG](assets/fr/29.webp)

By browsing this menu, you can also adjust the duration of the timelock. This countdown starts upon receiving bitcoins, and once the timelock expires, your funds can be spent only with your local key, without requiring the 2FA. The default duration is set to 12 months, but for a savings wallet, choosing 15 months may be wise to minimize the frequency of timelock renewals. Conversely, for a spending wallet, a timelock of 6 months may be preferable, as it will be frequently renewed with your daily transactions, and a shorter timelock reduces the wait in case of problems with the 2FA. It's up to you to determine the timelock duration that suits you best.

![GREEN 2FA MULTISIG](assets/fr/30.webp)

You can now exit this menu. Your multisig wallet is ready!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Setting up your wallet on Blockstream Green

If you wish to customize your wallet, click on the three small dots at the top right.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
The "*Rename*" option allows you to customize the name of your wallet, which is particularly useful if you manage multiple wallets on the same application.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

The "*Unit*" menu gives you the option to change the base unit of your wallet. For example, you can choose to display it in satoshis rather than in bitcoins.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

The "*Settings*" menu provides access to the different options of your Bitcoin wallet.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Here, for example, you will find your extended public key and its *descriptor*, useful if you plan to set up a watch-only wallet from this wallet.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

You can also change the PIN code of your wallet and enable biometric login.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Using Blockstream Green

Now that your Bitcoin wallet is set up, you're ready to receive your first sats! To do this, simply click on the "*Receive*" button.

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green will then display the first blank receiving address of your wallet. You can either scan the associated QR code or copy the address directly to send bitcoins to it. This type of address does not specify the amount to be sent by the payer. However, you can generate an address that requests a specific amount, by clicking on the three small dots at the top right, then on "*Request Amount*", and entering the desired amount.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

When the transaction is broadcast on the network, it will appear in your wallet.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Wait to get enough confirmations to consider the transaction as final.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

With bitcoins in your wallet, you can now also send them. Click on "*Send*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

On the following page, enter the recipient's address. You can enter it manually or scan a QR code.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Choose the payment amount.

![GREEN 2FA MULTISIG](assets/fr/44.webp)
At the bottom of the screen, you can select the fee rate for this transaction. You have the option to follow the application's recommendations or to customize your fees. The higher the fees compared to other pending transactions, the faster your transaction will be processed. To understand the fee market, you can visit [Mempool.space](https://mempool.space/) in the "*Transaction Fees*" section.
![GREEN 2FA MULTISIG](assets/fr/45.webp)

Click on "*Next*" to access a summary screen of your transaction. Verify that the address, amount, and fees are correct.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

If everything looks good to you, slide the green button at the bottom of the screen to the right to sign and broadcast the transaction on the Bitcoin network.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

This is the moment when you need to enter your authentication code to unlock the second key of the multisig held by Blockstream. Enter the 6-digit code displayed on your authentication app.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Your transaction will now appear on the dashboard of your Bitcoin wallet awaiting confirmation.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

And there you have it, you now know how to easily set up a 2/2 multisig wallet using Blockstream Green's 2FA option!

If you found this tutorial helpful, I would appreciate it if you could leave a green thumb below. Feel free to share this article on your social networks. Thank you very much!

I also recommend checking out this other complete tutorial on the Blockstream Green mobile app for setting up a Liquid wallet:

https://planb.network/tutorials/wallet/blockstream-green-liquid