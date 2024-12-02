---
name: Blockstream Green - Desktop
description: コンピューター上でGreen Walletソフトウェアを使用する
---
![cover](assets/cover.webp)

このチュートリアルでは、コンピューター上でBlockstream Greenソフトウェアを使用して、ハードウェアウォレット上で安全なウォレットを管理する方法を探ります。ハードウェアウォレットを使用する際、このウォレットを管理するためにコンピューター上のソフトウェアを使用することが不可欠です。この管理ソフトウェアはプライベートキーにアクセスできません。ウォレットの残高を確認し、受信アドレスを生成し、ハードウェアウォレットによって署名されるトランザクションを構築してブロードキャストするためにのみ使用されます。Greenは、Bitcoinハードウェアウォレットを管理するための多くのソリューションの一つを代表しています。

2024年には、Blockstream GreenはLedger Nano S（旧バージョン）、Ledger Nano X、Trezor One、Trezor T、およびBlockstream Jadeデバイスとのみ互換性があります。

## Blockstream Greenの紹介

Blockstream Greenは、モバイルおよびデスクトップの両方で利用可能なソフトウェアです。元々はGreen Addressとして知られていたこのウォレットは、2016年の買収を経てBlockstreamプロジェクトの一部となりました。

Greenは非常にユーザーフレンドリーなアプリケーションであり、特に初心者に適しています。ホットウォレット、ハードウェアウォレット、およびLiquidサイドチェーン上のウォレットの管理など、さまざまな機能を提供します。また、ウォッチオンリーウォレットの設定にも使用できます。

![GREEN-DESKTOP](assets/fr/01.webp)

このチュートリアルでは、コンピューター上でソフトウェアを使用することにのみ焦点を当てます。Greenの他の使用法を探るには、専用のチュートリアルをご覧ください：

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Blockstream Greenソフトウェアのインストールと設定

まず、コンピューターにBlockstream Greenソフトウェアをインストールします。[公式ウェブサイト](https://blockstream.com/green/)にアクセスし、「*Download Now*」ボタンをクリックしてください。次に、お使いのオペレーティングシステムに従ってインストールプロセスに従ってください。

![GREEN-DESKTOP](assets/fr/02.webp)

アプリケーションを起動し、「*I accept the terms...*」のボックスをチェックします。

![GREEN-DESKTOP](assets/fr/03.webp)

Greenを初めて開くと、設定されたウォレットがないホーム画面が表示されます。後でウォレットを作成またはインポートすると、それらはこのインターフェースに表示されます。ウォレットの作成に進む前に、期待に応じてアプリケーションの設定を調整することをお勧めします。左下の設定アイコンをクリックしてください。

![GREEN-DESKTOP](assets/fr/04.webp)

「*General*」メニューでは、ソフトウェアの言語を変更し、実験的な機能を有効にすることができます。

![GREEN-DESKTOP](assets/fr/05.webp)
「*Network*」メニューでは、Tor経由での接続を有効にすることができます。Torはすべての接続を暗号化し、活動を追跡しにくくするネットワークです。このオプションはアプリケーションのパフォーマンスをわずかに低下させる可能性がありますが、特に自分のフルノードを使用していない場合、プライバシーを保護するために強く推奨されます。
![GREEN-DESKTOP](assets/fr/06.webp)

自分のフルノードを持っているユーザーに対して、GreenはElectrumサーバーを介してそれに接続することを可能にし、Bitcoinネットワーク情報とトランザクションのブロードキャストを完全に制御できます。これを行うには、「*Custom servers and validation*」メニューをクリックし、Electrumサーバー情報を入力してください。

![GREEN-DESKTOP](assets/fr/07.webp)
別の代替機能は、"*SPV検証*"オプションであり、特定のブロックチェーンデータの直接検証を可能にし、Blockstreamのデフォルトノードを信頼する必要性を減らしますが、この方法はフルノードのすべての保証を提供するわけではありません。このオプションは"*カスタムサーバーと検証*"メニューにも見つかります。
![GREEN-DESKTOP](assets/fr/08.webp)

これらの設定をあなたのニーズに合わせて調整したら、このインターフェースを終了できます。

## Blockstream Greenにビットコインウォレットをインポートする

これで、ビットコインウォレットをインポートする準備が整いました。"**Get Started**"ボタンをクリックしてください。

![GREEN-DESKTOP](assets/fr/09.webp)

ローカルソフトウェアウォレットを作成するか、ハードウェアウォレットを介してコールドウォレットを管理するかを選択できます。このチュートリアルでは、ハードウェアウォレットの管理に焦点を当てるため、"*On Hardware Wallet*"オプションを選択する必要があります。

一方、"*Watch-only*"オプションでは、関連する資金を使うことなくウォレットのトランザクションを表示するために拡張公開キー(`xpub`)をインポートできます。

![GREEN-DESKTOP](assets/fr/10.webp)

Jadeを使用している場合は、対応するボタンをクリックしてください。それ以外の場合は、"*Connect a different Hardware Device*"を選択してください。私の場合、Ledger Nano Sを使用しています。Ledgerユーザーの場合、Greenはこのバージョンのみをサポートしているため、ハードウェアウォレットに"*Bitcoin Legacy*"アプリケーションをインストールしてください。

![GREEN-DESKTOP](assets/fr/11.webp)

ハードウェアウォレットをコンピューターに接続し、Greenで選択してください。

![GREEN-DESKTOP](assets/fr/12.webp)

Greenがウォレットから情報をインポートするのを待ち、その後、アクセスできるようになります。

![GREEN-DESKTOP](assets/fr/13.webp)

この時点で、2つのシナリオが考えられます。以前にハードウェアウォレットを使用していた場合は、ソフトウェア上にアカウントが表示されるはずです。しかし、私のように、まだ使用していない状態でニーモニックフレーズを生成してハードウェアウォレットを初期化したばかりの場合は、アカウントを作成する必要があります。"*Create Account*"をクリックしてください。
![GREEN-DESKTOP](assets/fr/14.webp)
クラシックウォレットを使用したい場合は、"*Standard*"を選択してください。

![GREEN-DESKTOP](assets/fr/15.webp)

これでアカウントにアクセスできるようになりました。

![GREEN-DESKTOP](assets/fr/16.webp)

## Blockstream Greenでハードウェアウォレットを使用する

ビットコインウォレットの設定が完了したので、最初のsatsを受け取る準備ができました！これを行うには、単に"*Receive*"ボタンをクリックしてください。

![GREEN-DESKTOP](assets/fr/17.webp)

アドレスをコピーするには、"*Copy address*"ボタンをクリックするか、そのQRコードをスキャンしてください。

![GREEN-DESKTOP](assets/fr/18.webp)

トランザクションがネットワーク上でブロードキャストされると、ウォレットに表示されます。トランザクションを不変と見なすために十分な確認を得るまで待ってください。

![GREEN-DESKTOP](assets/fr/19.webp)

ウォレットにビットコインがあれば、それを送ることができます。"*Send*"ボタンをクリックしてください。

![GREEN-DESKTOP](assets/fr/20.webp)

次のページで、受取人のアドレスを入力します。手動で入力するか、ウェブカメラでQRコードをスキャンできます。

![GREEN-DESKTOP](assets/fr/21.webp)

支払い金額を選択してください。

![GREEN-DESKTOP](assets/fr/22.webp)
画面の下部で、この取引の手数料率を選択できます。アプリケーションの推奨事項に従うか、手数料をカスタマイズするオプションがあります。手数料が他の保留中の取引と比較して高いほど、取引の処理が速くなります。手数料市場を知るためには、"*Transaction Fees*" セクションで [Mempool.space](https://mempool.space/) を訪れることができます。
![GREEN-DESKTOP](assets/fr/23.webp)

取引で使用するUTXOsを特定して選択したい場合は、"*Manual coin selection*" ボタンをクリックしてください。

![GREEN-DESKTOP](assets/fr/24.webp)

取引の設定を確認し、すべてが期待通りであれば、"*Next*" をクリックしてください。

![GREEN-DESKTOP](assets/fr/25.webp)

もう一度アドレス、金額、手数料が正しいことを確認し、"*Confirm transaction*" をクリックしてください。

![GREEN-DESKTOP](assets/fr/26.webp)

ハードウェアウォレットの画面で取引のパラメータがすべて正しいことを確認し、それを使用して取引に署名してください。

![GREEN-DESKTOP](assets/fr/27.webp)

ハードウェアウォレットから取引が署名されると、Greenは自動的にそれをBitcoinネットワークにブロードキャストします。あなたの取引は、Bitcoinウォレットのダッシュボードに確認待ちとして表示されます。

![GREEN-DESKTOP](assets/fr/28.webp)

これで、Blockstream Greenソフトウェアを使用してハードウェアウォレット上でBitcoinウォレットを管理する方法を簡単に理解できました。
このチュートリアルが役立つと思われる場合は、以下でサムズアップをいただけると嬉しいです。この記事をソーシャルネットワークで共有していただけると幸いです。どうもありがとうございました！
また、ホットウォレットの設定についてのBlockstream Greenモバイルアプリの完全なチュートリアルもチェックすることをお勧めします：

https://planb.network/tutorials/wallet/blockstream-green