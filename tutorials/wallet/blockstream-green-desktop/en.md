---
name: Blockstream Green - Desktop
description: Using the Green Wallet software on a computer
---
![cover](assets/cover.webp)

In this tutorial, we will explore how to use the Blockstream Green software on a computer to manage a secure wallet on a hardware wallet. When using a hardware wallet, it is essential to use software on your computer to manage this wallet. This management software does not have access to the private keys; it is used only to check the balance of your wallet, generate receiving addresses, and construct and broadcast transactions that will be signed by the hardware wallet. Green represents one of the many solutions available for managing your Bitcoin hardware wallet.

In 2024, Blockstream Green is only compatible with Ledger Nano S (older version), Ledger Nano X, Trezor One, Trezor T, and Blockstream Jade devices.

## Introduction to Blockstream Green

Blockstream Green is software available on both mobile and desktop. Formerly known as Green Address, this wallet became a Blockstream project following its acquisition in 2016.

Green is a very user-friendly application, making it particularly suitable for beginners. It offers various features, such as the management of hot wallets, hardware wallets, as well as wallets on the Liquid sidechain. You can also use it to set up a watch-only wallet.

![GREEN-DESKTOP](assets/fr/01.webp)

In this tutorial, we will focus solely on using the software on a computer. To explore other uses of Green, I invite you to check out our other dedicated tutorials:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Installing and Setting Up Blockstream Green Software

Start by installing the Blockstream Green software on your computer. Go to [the official website](https://blockstream.com/green/) and click on the "*Download Now*" button. Then follow the installation process according to your operating system.

![GREEN-DESKTOP](assets/fr/02.webp)

Launch the application, then check the box "*I accept the terms...*".

![GREEN-DESKTOP](assets/fr/03.webp)

When you open Green for the first time, the home screen appears without any configured wallet. Later, if you create or import wallets, they will appear in this interface. Before moving on to creating a wallet, I advise you to adjust the application's settings according to your expectations. Click on the settings icon at the bottom left.

![GREEN-DESKTOP](assets/fr/04.webp)

In the "*General*" menu, you can change the software language and enable experimental features if you wish.

![GREEN-DESKTOP](assets/fr/05.webp)
In the "*Network*" menu, you can enable connection via Tor, a network that encrypts all your connections and makes your activities difficult to trace. Although this option may slightly slow down the application's performance, it is highly recommended to protect your privacy, especially if you are not using your own full node.
![GREEN-DESKTOP](assets/fr/06.webp)

For users who have their own full node, Green offers the possibility to connect to it via an Electrum server, ensuring full control over Bitcoin network information and transaction broadcasting. To do this, click on the "*Custom servers and validation*" menu, then enter your Electrum server information.

![GREEN-DESKTOP](assets/fr/07.webp)

Another alternative feature is the "*SPV Verification*" option, which allows for direct verification of certain blockchain data, thus reducing the need to trust Blockstream's default node, although this method does not provide all the guarantees of a full node. This option is also found in the "*Custom servers and validation*" menu.

![GREEN-DESKTOP](assets/fr/08.webp)

Once these settings are adjusted according to your needs, you can exit this interface.

## Importing a Bitcoin Wallet into Blockstream Green

You are now ready to import your Bitcoin wallet. Click on the "**Get Started**" button.

![GREEN-DESKTOP](assets/fr/09.webp)

You have the choice between creating a local software wallet or managing a cold wallet via a hardware wallet. For this tutorial, we will focus on managing a hardware wallet, so you will need to select the "*On Hardware Wallet*" option.

The "*Watch-only*" option, on the other hand, allows you to import an extended public key (`xpub`) to view the transactions of a wallet without being able to spend the associated funds.

![GREEN-DESKTOP](assets/fr/10.webp)

If you are using a Jade, click on the corresponding button. Otherwise, select "*Connect a different Hardware Device*". In my case, I'm using a Ledger Nano S. For Ledger users, make sure to install the "*Bitcoin Legacy*" application on your hardware wallet, as Green only supports this version.

![GREEN-DESKTOP](assets/fr/11.webp)

Connect your hardware wallet to the computer and select it on Green.

![GREEN-DESKTOP](assets/fr/12.webp)

Wait while Green imports the information from your wallet, after which you will be able to access it.

![GREEN-DESKTOP](assets/fr/13.webp)

At this point, two scenarios are possible. If you had already used your hardware wallet before, you should see your account appear on the software. But if, like me, you have just initialized your hardware wallet by generating a mnemonic phrase without having used it yet, you will need to create an account. Click on "*Create Account*".
![GREEN-DESKTOP](assets/fr/14.webp)
Choose "*Standard*" if you wish to use a classic wallet.

![GREEN-DESKTOP](assets/fr/15.webp)

You now have access to your account.

![GREEN-DESKTOP](assets/fr/16.webp)

## Using a hardware wallet with Blockstream Green

Now that your Bitcoin wallet is set up, you're ready to receive your first sats! To do this, simply click on the "*Receive*" button.

![GREEN-DESKTOP](assets/fr/17.webp)

Click on the "*Copy address*" button to copy the address, or scan its QR code.

![GREEN-DESKTOP](assets/fr/18.webp)

Once the transaction is broadcasted on the network, it will appear in your wallet. Wait to get enough confirmations to consider the transaction as immutable.

![GREEN-DESKTOP](assets/fr/19.webp)

With bitcoins in your wallet, you are now able to send them. Click on the "*Send*" button.

![GREEN-DESKTOP](assets/fr/20.webp)

On the following page, enter the recipient's address. You can enter it manually or scan a QR code with your webcam.

![GREEN-DESKTOP](assets/fr/21.webp)

Choose the payment amount.

![GREEN-DESKTOP](assets/fr/22.webp)

At the bottom of the screen, you can select the fee rate for this transaction. You have the option to follow the application's recommendations or customize your fees. The higher the fees compared to other pending transactions, the faster your transaction will be processed. To know the fee market, you can visit [Mempool.space](https://mempool.space/) in the "*Transaction Fees*" section.

![GREEN-DESKTOP](assets/fr/23.webp)

If you wish to specifically select which UTXOs to use in your transaction, click on the "*Manual coin selection*" button.

![GREEN-DESKTOP](assets/fr/24.webp)

Check the settings of your transaction and, if everything is as you expect, click on "*Next*".

![GREEN-DESKTOP](assets/fr/25.webp)

Verify once again that the address, amount, and fees are correct, then click on "*Confirm transaction*".

![GREEN-DESKTOP](assets/fr/26.webp)

Make sure all the transaction parameters are correct on your hardware wallet's screen, then sign the transaction using it.

![GREEN-DESKTOP](assets/fr/27.webp)

Once the transaction is signed from the hardware wallet, Green automatically broadcasts it on the Bitcoin network. Your transaction will then appear on the dashboard of your Bitcoin wallet, pending confirmation.

![GREEN-DESKTOP](assets/fr/28.webp)

And there you have it, you now know how to easily set up the Blockstream Green software to manage your Bitcoin wallet on a hardware wallet.
If you found this tutorial helpful, I would appreciate it if you could leave a thumbs up below. Feel free to share this article on your social networks. Thank you very much!
I also recommend checking out this complete tutorial on the Blockstream Green mobile app for setting up a hot wallet:

https://planb.network/tutorials/wallet/blockstream-green