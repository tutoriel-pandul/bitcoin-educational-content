名前：Tails

説明：USBフラッシュドライブにTailsをインストールする
---

# USBフラッシュドライブにTailsをインストールする

_**Agora256のHari Seldonによる提案されたガイド**_

![image](assets/cover.jpeg)

監視や検閲から保護してくれる、携帯可能で記憶を持たないオペレーティングシステム。

## TailsをUSBフラッシュドライブにインストールする理由

Tails（https://tails.boum.org/）は、使用するコンピュータに痕跡を残さずに、いつでも安全なコンピュータを手に入れる最も簡単な方法です。

Tailsを使用するには、使用できるコンピュータ（親の家、友人の家、インターネットカフェなど）をシャットダウンし、Windows、macOS、またはLinuxの代わりにTails USBを起動します。

その後、通常のオペレーティングシステムとは独立した作業および通信スペースがあり、ハードディスクを使用しません。

Tailsはハードディスクに書き込まず、動作にはコンピュータのRAMのみを使用します。このRAMはTailsのシャットダウン時に完全に消去され、可能な痕跡をすべて削除します。

## 具体的な使用例

TailsのUSBフラッシュドライブを常に持ち歩く利点を具体的に示すために、Agora256チームによって編集された非網羅的なリストをいくつか紹介します：

- 検閲や匿名でインターネットおよびTorに接続して痕跡を残さずにサイトを閲覧する；
- 疑わしいサイトからPDFを開く；
- ElectrumウォレットでBitcoinのプライベートキーバックアップをテストする；
- 所有していないコンピュータでオフィススイート（LibreOffice）を使用して作業する；
- MicrosoftやAppleの世界から抜け出すためにLinux環境で最初のステップを踏む。

## Tailsに対する信頼性の確保方法

ソフトウェアの使用には常に信頼性が求められますが、それは盲目的である必要はありません。Tailsのようなツールは、ユーザーに信頼できる手段を提供しようとする必要があります。Tailsにとって、それは次のことを意味します：

- 公開されたソースコード：https://gitlab.tails.boum.org/；
- 有名なプロジェクトに基づいたプロジェクト：TorとDebian；
- 検証可能で再現可能なダウンロード；
- 異なる人々や組織からの推奨。

## インストールおよび使用ガイド

このインストールガイドは、インストールの各ステップを案内することを目的としています。公式ガイドと同様に、実行するアクションを詳細に説明するのではなく、適切な方向を指し示しながらヒントやテクニックを提供します。

実践的な経験のため、これらのアドバイスはmacOSとLinuxのプラットフォームに焦点を当てています。
🛠️
この手順を開始する前に、少なくとも150 MB/sの読み取り速度と8 GB以上のサイズを持つUSBキーを用意してください。理想的にはUSB 3.0タイプのものです。

前提条件：
- Tails専用の少なくとも8 GBのUSBキー1つ
- Linux、macOS（またはWindows）に接続されたインターネットに接続されたコンピューター
- インターネット接続速度に応じて合計約1時間（1.3 GBのダウンロードファイルをインストールするための30分を含む）の時間

## ステップ1：コンピューターからTailsをダウンロードする

![image](assets/1.jpeg)

> 🔗 Tailsの公式セクション：https://tails.boum.org/install/linux/index.fr.html#download

img拡張子のインストールファイルをダウンロードするには、インターネットのダウンロード速度に応じて時間がかかる場合がありますので、事前にダウンロードしておいてください。最新の高速な回線を使用している場合、5分未満で完了します。

ファイルを既知のフォルダ（例：ダウンロード）に保存しておく必要があります。これは次のステップに進むために必要です。

## ステップ2：ダウンロードを確認する

![image](assets/2.jpeg)

> 🔗 Tailsの公式セクション：https://tails.boum.org/install/linux/index.fr.html#verify

ダウンロードを確認することで、Tailsの開発者によって提供され、ダウンロード中に破損または傍受されていないことを確認できます。

ダウンロードしたファイルが期待どおりのものであることをPGPを使用して手動で確認することもできますが、高度な知識がない場合、この確認はダウンロードページのJavaScriptの確認と同じレベルのセキュリティを提供しますが、はるかに複雑でエラーの可能性があります。

ファイルを確認するには、公式セクションで提供されている「ダウンロードを選択する...」ボタンを使用してください。

## ステップ3：USBキーにTailsをインストールする

![image](assets/3.jpeg)

> 🔗 Tailsの公式セクション：
>
> - Linux：https://tails.boum.org/install/linux/index.fr.html#install
> - macOS：https://tails.boum.org/install/mac/index.fr.html#etcher および https://tails.boum.org/install/mac/index.fr.html#install

TailsをUSBキーにインストールするこのステップは、特に初めて行う場合には、ガイド全体で最も難しいステップです。最も重要なポイントは、オペレーティングシステムに応じて公式セクションで手順を選択することです：LinuxまたはmacOS。

その後、推奨されるようにツールをインストールし準備した後、img拡張子のファイルをUSBキーにコピーして（既存のデータを削除して）「起動可能」にする必要があります。

頑張ってください！そしてステップ4に進んでください。

## ステップ4：TailsのUSBキーで再起動する

![image](assets/4.jpeg)
> 🔗 Tailsの公式セクション: https://tails.boum.org/install/linux/index.fr.html#restart
新しいUSBキーを使用してコンピューターを起動する時間です。そのUSBキーをUSBポートの1つに挿入し、再起動してください！

> 💡ほとんどのコンピューターはTailsのUSBキーで自動的に起動しませんが、起動メニューのキーを押すことで、起動可能なデバイスのリストが表示されます。

通常、通常のハードディスクの代わりにUSBキーを選択する起動メニューを確実に表示するために押す必要があるキーを特定するために、以下は一部のメーカーによる非網羅的なリストです：

| メーカー | キー                 |
| --------- | ------------------ |
| Acer      | F12, F9, F2, Échap |
| Apple     | Option             |
| Asus      | Échap              |
| Clevo     | F7                 |
| Dell      | F12                |
| Fujitsu   | F12, Échap         |
| HP        | F9                 |
| Huawei    | F12                |
| Intel     | F10                |
| Lenovo    | F12                |
| MSI       | F11                |
| Samsung   | Échap, F12, F2     |
| Sony      | F11, Échap, F10    |
| Toshiba   | F12                |
| その他…   | F12, Échap         |

USBキーが選択されると、新しい起動画面が表示されます。これは非常に良い兆候ですので、コンピューターの起動を続けてください...

![image](assets/5.jpeg)

## ステップ5：Tailsへようこそ！

![image](assets/6.jpeg)

> 🔗 Tailsの公式セクション: https://tails.boum.org/install/linux/index.fr.html#tails

ブートローダーとローディング画面の1〜2分後、ウェルカムスクリーンが表示されます。

![image](assets/7.jpeg)

ウェルカムスクリーンでは、Language & Regionセクションで言語とキーボードのレイアウトを選択してください。Tailsを起動をクリックしてください。

![image](assets/8.jpeg)

もしコンピューターがワイヤレスネットワークに有線接続されていない場合は、Tailsの公式の指示に従ってワイヤレスネットワークに接続するためのヘルプを参照してください（"Testez votre Wi-Fi"セクション）。

ローカルネットワークに接続した後、Torへの接続アシスタントが表示され、Torネットワークに接続するのをサポートします。

![image](assets/9.jpeg)

匿名でウェブブラウジングを始め、Tailsに含まれるオプションやソフトウェアを探索してください。エラーを起こしても問題ありません。USBキーには何も変更されていないため、次回の再起動時にはすべての経験が忘れられます！

## 次のガイドでは...

自分のTails USBキーでさらに試してみた後、別の記事でより高度なトピックを探求します。
> Tailsの最新バージョンでキーを更新する; 永続的なストレージの設定と使用; 追加のソフトウェアをインストールする。
それまでの間、いつものように、質問があれば、Agora256コミュニティで共有してください。一緒に学び、今日よりも明日の自分をより良くするために！
_**Agora256のHari Seldonによる提案されたガイド; 元の投稿: https://agora256.com/installer-tails-usb/**_