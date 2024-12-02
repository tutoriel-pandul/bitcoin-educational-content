---
name: Aqua
description: Bitcoin, Lightning, and Liquid in a single wallet
---
![cover](assets/cover.webp)

Aqua is a mobile application that allows for the easy creation of a hot wallet for Bitcoin and Liquid, and also offers the possibility to use Lightning without the complexity of managing a node, thanks to integrated swaps. It also supports the management of USDT stablecoins across various networks.

Developed by the company JAN3 under the leadership of Samson Mow, the Aqua application was initially designed specifically for the needs of users in Latin America, although it is suitable for any user worldwide. It is particularly interesting for beginners and those who use Bitcoin daily for their payments.

In this tutorial, we will explore how to use the many features of Aqua. But before that, let's take a moment to understand what a sidechain on Bitcoin is and how Liquid works, which will allow us to fully grasp the interest of Aqua.

![AQUA](assets/fr/01.webp)

## What is a sidechain?

The Bitcoin protocol has intentional technical limitations that help maintain the decentralization of the network and ensure a distribution of security among all users. However, these limits can sometimes frustrate users, especially during congestion caused by a high volume of simultaneous transactions. The debate over Bitcoin's scalability has long divided the community, particularly during the Blocksize War. Since that episode, it is widely recognized within the Bitcoin community that scalability must be ensured by off-chain solutions, on second-layer systems. Among these solutions are sidechains, which are still relatively unknown and underused compared to other systems like the Lightning Network.

A sidechain is an independent blockchain that operates in parallel to the main Bitcoin blockchain. It uses bitcoin as a unit of account through a mechanism called "*two-way peg*". This system allows for locking bitcoins on the main chain to replicate their value on the sidechain, where they circulate as tokens backed by the original bitcoins. These tokens normally maintain a value parity with the locked bitcoins on the main chain, and the process can be reversed to retrieve the funds on Bitcoin.
The goal of sidechains is to offer additional functionalities or technical improvements, such as faster transactions, reduced fees, or support for smart contracts. These innovations cannot always be implemented directly on the Bitcoin blockchain without compromising its decentralization or security. Sidechains thus allow for testing and exploring new solutions while preserving the integrity of Bitcoin. However, these protocols often require compromises, particularly in terms of decentralization and security, depending on the chosen governance model and consensus mechanism.
## What is Liquid?

Liquid is a federated sidechain built on top of Bitcoin, developed by Blockstream, aiming to enhance the speed, privacy, and functionalities of transactions. It uses a bilateral anchoring mechanism established on a federation to lock bitcoins on the main chain and create in return Liquid-bitcoins (L-BTC), tokens circulating on Liquid while remaining backed by the original bitcoins.

![AQUA](assets/fr/02.webp)

The Liquid network is based on a federation of participants, composed of recognized entities from the Bitcoin ecosystem, who validate the blocks and manage the bilateral anchoring. In addition to L-BTC, Liquid also allows the issuance of other digital assets, like the stablecoin USDT or other cryptocurrencies.

![AQUA](assets/fr/03.webp)

## Installing the Aqua App

The first step is naturally to download the Aqua app. Go to your app store:
- [For Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [For Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).

![AQUA](assets/fr/04.webp)

For Android users, you also have the option to install the app via the `.apk` file [available on their GitHub](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Launch the app, then check the box "*I have read and agreed to the Terms of Service & Privacy Policy*".

![AQUA](assets/fr/06.webp)

## Creating Your Wallet on Aqua

Click on the "*Create Wallet*" button.

![AQUA](assets/fr/07.webp)

And there you have it, your wallet is already created!

![AQUA](assets/fr/08.webp)

But before anything else, since this is a self-custody wallet, it is imperative to make a physical backup of your mnemonic phrase. **This mnemonic phrase provides complete and unrestricted access to all your bitcoins**. Anyone in possession of this phrase can steal your funds, even without physical access to your phone.
It allows you to restore access to your bitcoins in case of loss, theft, or damage to your phone. It is therefore very important to back it up carefully on a physical medium (not digital) and to store it in a secure location. You can write it down on a piece of paper, or for more security, if this wallet is significant, I recommend engraving it on a stainless steel medium to protect against the risks of fires, floods, or collapses (for a hot wallet intended to secure a small amount of bitcoins, a simple paper backup is probably sufficient).
To do this, click on the settings menu.

![AQUA](assets/fr/09.webp)

Then click on "*View Seed Phrase*". Make a physical backup of this 12-word phrase.

![AQUA](assets/fr/10.webp)

In this same settings menu, you can also change the language of the application as well as the fiat currency used.

![AQUA](assets/fr/11.webp)

Before receiving your first bitcoins in your wallet, **I strongly advise you to perform a dry-run recovery test**. Note down a reference information, such as your xpub or the first receiving address, then delete your wallet on the Aqua app while it is still empty. Next, try to restore your wallet on Aqua using your paper backups. Check that the witness information generated after the restoration matches the one you initially noted. If this is the case, you can be assured that your paper backups are reliable. To learn more about how to perform a recovery test, I advise you to consult this other tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Receiving bitcoins on Aqua

Now that your wallet is set up, you are ready to receive your first sats! Simply click on the "*Receive*" button in the "*Wallet*" menu.

![AQUA](assets/fr/12.webp)

You can choose to receive bitcoins onchain, on Liquid, or via Lightning.

![AQUA](assets/fr/13.webp)

For onchain transactions, Aqua will generate a specific receiving address where you can receive your sats.

![AQUA](assets/fr/14.webp)

Similarly, by opting for Liquid, Aqua will provide you with a Liquid address.

![AQUA](assets/fr/15.webp)

If you prefer to receive funds via Lightning, you will first need to specify the desired amount.

![AQUA](assets/fr/16.webp)

Then, click on "*Generate Invoice*".

![AQUA](assets/fr/17.webp)
Aqua will create an invoice to receive funds from a Lightning wallet. It's important to note that, unlike onchain and Liquid options, funds received via Lightning will be automatically converted to L-BTC on Liquid using the Boltz tool, since Aqua is not a Lightning node. This process allows you to receive and send funds via Lightning, but without ever keeping your bitcoins on Lightning.
![AQUA](assets/fr/18.webp)

Personally, I will start by sending bitcoins via Lightning to Aqua. Once the transaction is completed with the provided invoice, a confirmation is received.

![AQUA](assets/fr/19.webp)

To follow the progress of the swap, return to the homepage of your wallet and click on the "*L2 Bitcoin*" account, which lists Lightning (via swap) and Liquid transactions.

![AQUA](assets/fr/20.webp)

Here, you can view your transaction as well as your balance in L-BTC.

![AQUA](assets/fr/21.webp)

## Swapping bitcoins with Aqua

Now that you have assets in your Aqua wallet, you have the option to swap them directly from the app, either to transfer them to the main Bitcoin blockchain or to Liquid. You can also convert your bitcoins into the stablecoin USDT (or others). To do this, access the "*Marketplace*" menu.

![AQUA](assets/fr/22.webp)

Click on "*Swaps*".

![AQUA](assets/fr/23.webp)

In the "*Transfer from*" box, choose the asset you want to exchange. Currently, I only have L-BTC, so that's what I select.

![AQUA](assets/fr/24.webp)

In the "*Transfer to*" box, choose the target asset of your swap. For my part, I opted for USDT on the Liquid network.

![AQUA](assets/fr/25.webp)

Enter the amount you wish to convert.

![AQUA](assets/fr/26.webp)

Confirm by clicking on "*Continue*".

![AQUA](assets/fr/27.webp)

Make sure the swap settings are to your liking, then confirm by sliding the "*Swap*" button at the bottom of the screen.

![AQUA](assets/fr/28.webp)

Your swap is now confirmed.

![AQUA](assets/fr/29.webp)

If we go back to our wallet, we can see that we now have USDT on Liquid.

![AQUA](assets/fr/30.webp)

## Sending bitcoins with Aqua

Now that you have bitcoins in your Aqua wallet, you have the option to send them. Click on the "*Send*" button.

![AQUA](assets/fr/31.webp)

Choose the asset you want to send or select the network to perform the transaction. For my part, I will send bitcoins via Lightning.

![AQUA](assets/fr/32.webp)
Next, enter the necessary information for sending the payment: for Bitcoin onchain or Liquid, you need to enter a receiving address; for Lightning, an invoice is required. You can paste this information directly into the designated field or use the QR code icon to open your camera and scan the address or invoice. Then click on "*Continue*".
![AQUA](assets/fr/33.webp)

Click on "*Continue*" again if all the information appears correct.

![AQUA](assets/fr/34.webp)

Aqua then presents you with a summary of the transaction. Ensure all the information is correct, especially the destination address, fees, and amount. To confirm the transaction, slide the "*Slide to send*" button located at the bottom of the screen.

![AQUA](assets/fr/35.webp)

A confirmation of the sending is then provided to you.

![AQUA](assets/fr/36.webp)

And there you have it, you now know how to use the Aqua app to receive and spend funds on Bitcoin, Lightning, and Liquid, all from a single interface.

If you found this tutorial helpful, I would appreciate it if you could leave a thumbs up below. Feel free to share this article on your social networks. Thank you very much!

I also advise you to check out this other complete tutorial on the Blockstream Green mobile app, which is another interesting solution for setting up your Liquid wallet:

https://planb.network/tutorials/wallet/blockstream-green-liquid