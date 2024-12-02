---
name: Blockstream Green - Desktop
description: Nutzung der Green Wallet-Software auf einem Computer
---
![cover](assets/cover.webp)

In diesem Tutorial werden wir untersuchen, wie man die Blockstream Green-Software auf einem Computer verwendet, um eine sichere Wallet auf einem Hardware-Wallet zu verwalten. Bei der Verwendung eines Hardware-Wallets ist es wesentlich, Software auf Ihrem Computer zu nutzen, um dieses Wallet zu verwalten. Diese Verwaltungssoftware hat keinen Zugriff auf die privaten Schlüssel; sie wird nur verwendet, um das Guthaben Ihres Wallets zu überprüfen, Empfangsadressen zu generieren und Transaktionen zu erstellen und zu übertragen, die vom Hardware-Wallet signiert werden. Green repräsentiert eine der vielen verfügbaren Lösungen für die Verwaltung Ihres Bitcoin-Hardware-Wallets.

Im Jahr 2024 ist Blockstream Green nur kompatibel mit Ledger Nano S (ältere Version), Ledger Nano X, Trezor One, Trezor T und Blockstream Jade Geräten.

## Einführung in Blockstream Green

Blockstream Green ist eine Software, die sowohl auf Mobilgeräten als auch auf Desktops verfügbar ist. Früher als Green Address bekannt, wurde diese Wallet nach ihrer Übernahme durch Blockstream im Jahr 2016 zu einem Blockstream-Projekt.

Green ist eine sehr benutzerfreundliche Anwendung, was sie besonders für Anfänger geeignet macht. Sie bietet verschiedene Funktionen, wie die Verwaltung von Hot Wallets, Hardware-Wallets sowie Wallets auf der Liquid-Seitenkette. Sie können es auch verwenden, um eine Watch-Only-Wallet einzurichten.

![GREEN-DESKTOP](assets/fr/01.webp)

In diesem Tutorial konzentrieren wir uns ausschließlich auf die Verwendung der Software auf einem Computer. Um andere Verwendungsmöglichkeiten von Green zu erkunden, lade ich Sie ein, unsere anderen speziellen Tutorials zu besuchen:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Installation und Einrichtung der Blockstream Green-Software

Beginnen Sie mit der Installation der Blockstream Green-Software auf Ihrem Computer. Gehen Sie auf [die offizielle Website](https://blockstream.com/green/) und klicken Sie auf den Button "*Download Now*". Folgen Sie dann dem Installationsprozess entsprechend Ihrem Betriebssystem.

![GREEN-DESKTOP](assets/fr/02.webp)

Starten Sie die Anwendung und markieren Sie das Kästchen "*Ich akzeptiere die Bedingungen...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Wenn Sie Green zum ersten Mal öffnen, erscheint der Startbildschirm ohne konfiguriertes Wallet. Später, wenn Sie Wallets erstellen oder importieren, werden diese in dieser Schnittstelle erscheinen. Bevor Sie mit der Erstellung eines Wallets fortfahren, rate ich Ihnen, die Einstellungen der Anwendung gemäß Ihren Erwartungen anzupassen. Klicken Sie auf das Einstellungssymbol unten links.

![GREEN-DESKTOP](assets/fr/04.webp)

Im Menü "*Allgemein*" können Sie die Software-Sprache ändern und experimentelle Funktionen aktivieren, wenn Sie möchten.

![GREEN-DESKTOP](assets/fr/05.webp)
Im Menü "*Netzwerk*" können Sie die Verbindung über Tor aktivieren, ein Netzwerk, das alle Ihre Verbindungen verschlüsselt und Ihre Aktivitäten schwer nachvollziehbar macht. Obwohl diese Option die Leistung der Anwendung leicht verlangsamen kann, wird sie dringend empfohlen, um Ihre Privatsphäre zu schützen, insbesondere wenn Sie nicht Ihren eigenen Full Node verwenden.
![GREEN-DESKTOP](assets/fr/06.webp)

Für Benutzer, die ihren eigenen Full Node haben, bietet Green die Möglichkeit, sich über einen Electrum-Server damit zu verbinden, um vollständige Kontrolle über Bitcoin-Netzwerkinformationen und die Übertragung von Transaktionen zu gewährleisten. Um dies zu tun, klicken Sie auf das Menü "*Benutzerdefinierte Server und Validierung*", und geben Sie Ihre Electrum-Serverinformationen ein.

![GREEN-DESKTOP](assets/fr/07.webp)
Eine weitere alternative Funktion ist die Option "*SPV-Verifizierung*", die eine direkte Überprüfung bestimmter Blockchain-Daten ermöglicht und somit die Notwendigkeit verringert, dem Standardknoten von Blockstream zu vertrauen, obwohl diese Methode nicht alle Garantien eines Vollknotens bietet. Diese Option findet sich auch im Menü "*Benutzerdefinierte Server und Validierung*".
![GREEN-DESKTOP](assets/fr/08.webp)

Sobald diese Einstellungen nach Ihren Bedürfnissen angepasst sind, können Sie diese Schnittstelle verlassen.

## Ein Bitcoin-Wallet in Blockstream Green importieren

Sie sind jetzt bereit, Ihr Bitcoin-Wallet zu importieren. Klicken Sie auf den Button "**Get Started**".

![GREEN-DESKTOP](assets/fr/09.webp)

Sie haben die Wahl zwischen der Erstellung eines lokalen Software-Wallets oder der Verwaltung eines Cold Wallets über ein Hardware-Wallet. Für dieses Tutorial konzentrieren wir uns auf die Verwaltung eines Hardware-Wallets, daher müssen Sie die Option "*On Hardware Wallet*" auswählen.

Die Option "*Watch-only*" ermöglicht es Ihnen andererseits, einen erweiterten öffentlichen Schlüssel (`xpub`) zu importieren, um die Transaktionen eines Wallets anzusehen, ohne die damit verbundenen Mittel ausgeben zu können.

![GREEN-DESKTOP](assets/fr/10.webp)

Wenn Sie ein Jade verwenden, klicken Sie auf den entsprechenden Button. Andernfalls wählen Sie "*Connect a different Hardware Device*". In meinem Fall verwende ich ein Ledger Nano S. Für Ledger-Benutzer: Stellen Sie sicher, dass Sie die Anwendung "*Bitcoin Legacy*" auf Ihrem Hardware-Wallet installiert haben, da Green nur diese Version unterstützt.

![GREEN-DESKTOP](assets/fr/11.webp)

Verbinden Sie Ihr Hardware-Wallet mit dem Computer und wählen Sie es in Green aus.

![GREEN-DESKTOP](assets/fr/12.webp)

Warten Sie, während Green die Informationen von Ihrem Wallet importiert, danach werden Sie darauf zugreifen können.

![GREEN-DESKTOP](assets/fr/13.webp)

An diesem Punkt sind zwei Szenarien möglich. Wenn Sie Ihr Hardware-Wallet bereits zuvor verwendet haben, sollten Sie Ihr Konto in der Software sehen. Aber wenn Sie, wie ich, Ihr Hardware-Wallet gerade erst mit der Erzeugung einer mnemonischen Phrase initialisiert haben, ohne es bisher verwendet zu haben, müssen Sie ein Konto erstellen. Klicken Sie auf "*Create Account*".
![GREEN-DESKTOP](assets/fr/14.webp)
Wählen Sie "*Standard*", wenn Sie ein klassisches Wallet verwenden möchten.

![GREEN-DESKTOP](assets/fr/15.webp)

Sie haben jetzt Zugang zu Ihrem Konto.

![GREEN-DESKTOP](assets/fr/16.webp)

## Ein Hardware-Wallet mit Blockstream Green verwenden

Jetzt, da Ihr Bitcoin-Wallet eingerichtet ist, sind Sie bereit, Ihre ersten Sats zu erhalten! Klicken Sie dazu einfach auf den Button "*Receive*".

![GREEN-DESKTOP](assets/fr/17.webp)

Klicken Sie auf den Button "*Copy address*", um die Adresse zu kopieren, oder scannen Sie ihren QR-Code.

![GREEN-DESKTOP](assets/fr/18.webp)

Sobald die Transaktion im Netzwerk verbreitet ist, wird sie in Ihrem Wallet erscheinen. Warten Sie, bis Sie genügend Bestätigungen erhalten haben, um die Transaktion als unveränderlich zu betrachten.

![GREEN-DESKTOP](assets/fr/19.webp)

Mit Bitcoins in Ihrem Wallet sind Sie jetzt in der Lage, diese zu senden. Klicken Sie auf den Button "*Send*".

![GREEN-DESKTOP](assets/fr/20.webp)

Geben Sie auf der folgenden Seite die Adresse des Empfängers ein. Sie können sie manuell eingeben oder einen QR-Code mit Ihrer Webcam scannen.

![GREEN-DESKTOP](assets/fr/21.webp)

Wählen Sie den Zahlungsbetrag.

![GREEN-DESKTOP](assets/fr/22.webp)
Am unteren Bildschirmrand können Sie die Gebührenrate für diese Transaktion auswählen. Sie haben die Möglichkeit, den Empfehlungen der Anwendung zu folgen oder Ihre Gebühren individuell anzupassen. Je höher die Gebühren im Vergleich zu anderen ausstehenden Transaktionen sind, desto schneller wird Ihre Transaktion bearbeitet. Um den Gebührenmarkt zu kennen, können Sie [Mempool.space](https://mempool.space/) im Abschnitt "*Transaction Fees*" besuchen.
![GREEN-DESKTOP](assets/fr/23.webp)

Wenn Sie speziell auswählen möchten, welche UTXOs in Ihrer Transaktion verwendet werden sollen, klicken Sie auf den Button "*Manual coin selection*".

![GREEN-DESKTOP](assets/fr/24.webp)

Überprüfen Sie die Einstellungen Ihrer Transaktion und, wenn alles wie erwartet ist, klicken Sie auf "*Next*".

![GREEN-DESKTOP](assets/fr/25.webp)

Überprüfen Sie noch einmal, ob die Adresse, der Betrag und die Gebühren korrekt sind, dann klicken Sie auf "*Confirm transaction*".

![GREEN-DESKTOP](assets/fr/26.webp)

Stellen Sie sicher, dass alle Transaktionsparameter auf dem Bildschirm Ihres Hardware-Wallets korrekt sind, und signieren Sie dann die Transaktion damit.

![GREEN-DESKTOP](assets/fr/27.webp)

Sobald die Transaktion vom Hardware-Wallet signiert wurde, überträgt Green sie automatisch im Bitcoin-Netzwerk. Ihre Transaktion wird dann im Dashboard Ihres Bitcoin-Wallets als ausstehend angezeigt.

![GREEN-DESKTOP](assets/fr/28.webp)

Und so einfach ist es, die Blockstream Green Software einzurichten, um Ihr Bitcoin-Wallet auf einem Hardware-Wallet zu verwalten.
Wenn Sie dieses Tutorial hilfreich fanden, würde ich mich über ein Daumen hoch unten freuen. Fühlen Sie sich frei, diesen Artikel in Ihren sozialen Netzwerken zu teilen. Vielen Dank!
Ich empfehle auch, dieses vollständige Tutorial über die Blockstream Green Mobile-App zur Einrichtung eines Hot Wallets zu lesen:

https://planb.network/tutorials/wallet/blockstream-green