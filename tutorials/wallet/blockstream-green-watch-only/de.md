---
name: Blockstream Green - Nur-Ansicht
description: Einrichtung einer Nur-Ansicht-Wallet
---
![cover](assets/cover.webp)

In diesem Tutorial lernen Sie, wie Sie einfach eine Nur-Ansicht-Wallet auf dem Mobilgerät mit der Blockstream Green App einrichten.

## Was ist eine Nur-Ansicht-Wallet?

Eine Nur-Ansicht-Wallet, oder "watch-only wallet", ist eine Art von Software, die es dem Benutzer ermöglicht, Transaktionen zu beobachten, die mit einem oder mehreren spezifischen Bitcoin-Öffentlichen Schlüsseln verbunden sind, ohne Zugang zu den entsprechenden privaten Schlüsseln zu haben.

Diese Art von Anwendung behält nur die Daten, die für die Überwachung einer Bitcoin-Wallet notwendig sind, einschließlich der Ansicht ihres Guthabens und der Transaktionshistorie, aber sie hat keinen Zugang zu den privaten Schlüsseln. Daher ist es unmöglich, die in der Wallet auf der Nur-Ansicht-App gehaltenen Bitcoins auszugeben.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Nur-Ansicht wird in der Regel zusätzlich zu einer Hardware-Wallet verwendet. Letztere ermöglicht die sichere Speicherung der privaten Schlüssel der Wallet auf einem Gerät, das nicht mit dem Internet verbunden ist, was eine minimale Angriffsfläche bietet und somit die privaten Schlüssel von potenziell gefährdeten Umgebungen isoliert. Die Nur-Ansicht-App speichert andererseits ausschließlich den erweiterten öffentlichen Schlüssel (`xpub`, `zpub` usw.) der Bitcoin-Wallet. Dieser Elternschlüssel erlaubt nicht die Entdeckung der zugehörigen privaten Schlüssel und folglich nicht das Ausgeben von Bitcoins. Er ermöglicht jedoch die Ableitung von Kind-öffentlichen Schlüsseln und Empfangsadressen. Mit Kenntnis der Adressen der durch die Hardware-Wallet gesicherten Wallet kann die Nur-Ansicht-App diese Transaktionen im Bitcoin-Netzwerk verfolgen und dem Benutzer die Möglichkeit bieten, sein Guthaben zu überwachen und neue Empfangsadressen zu generieren, ohne jedes Mal seine Hardware-Wallet verbinden zu müssen.

In diesem Tutorial schlage ich vor, eine der beliebtesten Nur-Ansicht-Wallet-Lösungen auf Mobilgeräten zu entdecken: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Einführung in Blockstream Green

Blockstream Green ist eine Software, die auf Mobilgeräten und Computern verfügbar ist. Früher als Green Address bekannt, wurde diese Wallet nach ihrer Übernahme im Jahr 2016 zu einem Blockstream-Projekt.

Green ist eine sehr einfach zu bedienende Anwendung, was sie besonders für Anfänger geeignet macht. Sie bietet verschiedene Funktionen, wie die Verwaltung von Hot Wallets, Hardware-Wallets sowie Wallets auf der Liquid-Seitenkette.

In diesem Tutorial konzentrieren wir uns ausschließlich auf die Erstellung einer Nur-Ansicht-Wallet. Um andere Verwendungen von Green zu erkunden, lade ich Sie ein, unsere anderen speziellen Tutorials zu konsultieren:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Installation und Einrichtung der Blockstream Green App
Der erste Schritt ist natürlich, die Green-App herunterzuladen. Gehen Sie zu Ihrem App-Store:
- [Für Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Für Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Android-Nutzer haben auch die Möglichkeit, die App über die `.apk`-Datei [auf Blockstreams GitHub](https://github.com/Blockstream/green_android/releases) zu installieren.

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Starten Sie die App und markieren Sie das Kästchen "*Ich akzeptiere die Bedingungen...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Wenn Sie Green zum ersten Mal öffnen, erscheint der Startbildschirm ohne eine konfigurierte Wallet. Später, wenn Sie Wallets erstellen oder importieren, werden diese in dieser Schnittstelle angezeigt. Bevor Sie mit der Erstellung einer Wallet fortfahren, rate ich Ihnen, die Einstellungen der App gemäß Ihren Erwartungen anzupassen. Klicken Sie auf "*Anwendungseinstellungen*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

Die Option "*Erweiterte Privatsphäre*", die nur auf Android verfügbar ist, verbessert die Privatsphäre, indem sie Screenshots deaktiviert und App-Vorschauen verbirgt. Sie sperrt auch automatisch den Zugang zur App, sobald Ihr Telefon gesperrt ist, was Ihre Daten schwerer zugänglich macht.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Für diejenigen, die ihre Privatsphäre verbessern möchten, bietet die App die Möglichkeit, Ihren Verkehr über Tor zu leiten, ein Netzwerk, das alle Ihre Verbindungen verschlüsselt und Ihre Aktivitäten schwer zu verfolgen macht. Obwohl diese Option die Leistung der App leicht verlangsamen kann, wird sie dringend empfohlen, um Ihre Privatsphäre zu schützen, insbesondere wenn Sie nicht Ihren eigenen Full Node verwenden.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Für Benutzer, die ihren eigenen Full Node haben, bietet Green Wallet die Möglichkeit, sich über einen Electrum-Server damit zu verbinden, was die vollständige Kontrolle über Bitcoin-Netzwerkinformationen und das Senden von Transaktionen gewährleistet.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Eine weitere alternative Funktion ist die Option "*SPV-Verifizierung*", die eine direkte Überprüfung bestimmter Blockchain-Daten ermöglicht und somit die Notwendigkeit verringert, dem Standard-Node von Blockstream zu vertrauen, obwohl diese Methode nicht alle Garantien eines Full Node bietet.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Sobald diese Einstellungen gemäß Ihren Bedürfnissen angepasst sind, klicken Sie auf den "*Speichern*" Knopf und starten Sie die App neu.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Erstellung einer Watch-Only-Wallet auf Blockstream Green
Sie sind jetzt bereit, eine Watch-Only-Wallet zu erstellen. Klicken Sie auf den "*Loslegen*" Knopf.
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Sie haben die Wahl zwischen mehreren Arten von Wallets. Für dieses Tutorial möchten wir eine Watch-Only-Wallet erstellen, also klicken Sie auf den entsprechenden Knopf.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Wählen Sie die Option "*Einzelne Signatur*".

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Wählen Sie dann "*Bitcoin*". Ich führe dieses Tutorial an einer Testnet-Wallet durch, aber das Verfahren bleibt dasselbe im Mainnet.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Sie werden gebeten, entweder einen erweiterten öffentlichen Schlüssel (`xpub`, `zpub` usw.) oder einen Output-Skript-Deskriptor anzugeben.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Sie müssen diese Informationen von der Wallet abrufen, die Sie über Ihre Watch-Only-Wallet verfolgen möchten. Der erweiterte öffentliche Schlüssel ist in Bezug auf die Sicherheit nicht sensibel, da er keinen Zugang zu privaten Schlüsseln ermöglicht, aber er ist sensibel für Ihre Privatsphäre, da er alle Ihre öffentlichen Schlüssel und damit alle Ihre Bitcoin-Transaktionen offenbart.

Stellen Sie sich vor, Sie verwenden Sparrow Wallet, um Ihre Wallet auf einem Hardware-Wallet zu verwalten, finden Sie diese Informationen im Abschnitt "*Einstellungen*". Das Auffinden dieser Informationen hängt von der Wallet-Verwaltungssoftware ab, die Sie verwenden, aber sie befindet sich in der Regel in den Einstellungen.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Kopieren Sie Ihren erweiterten öffentlichen Schlüssel und geben Sie ihn in die Green-App ein, dann klicken Sie auf "*Verbinden*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Dann können Sie das Guthaben, das mit diesem Schlüssel verbunden ist, sowie den Transaktionsverlauf sehen.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Indem Sie auf "*Empfangen*" klicken, können Sie eine Empfangsadresse generieren, um Bitcoins auf Ihrem Hardware-Wallet zu empfangen. Ich rate jedoch davon ab, diese Option zu nutzen, ohne zuvor auf dem Bildschirm des Hardware-Wallets zu überprüfen, ob es den privaten Schlüssel besitzt, der mit der generierten Adresse verknüpft ist, bevor Sie ihn verwenden, um Bitcoins zu sperren. Dies ist eine gute Praxis, der man folgen sollte.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

Die Option "*Sweep*" ermöglicht es Ihnen, einen privaten Schlüssel manuell einzugeben, um Mittel direkt aus Ihrer Green-Anwendung zu verwenden. Außer in sehr spezifischen Fällen empfehle ich, diese Funktion nicht zu nutzen, da sie erfordert, Ihren privaten Schlüssel auf einem Telefon preiszugeben, das viel anfälliger für Cyberangriffe ist als Ihr Hardware-Wallet.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
Und da haben Sie es, jetzt wissen Sie, wie Sie ganz einfach ein Watch-Only-Wallet auf Ihrem Smartphone einrichten können! Es ist ein sehr praktisches Werkzeug, um ein Wallet auf einem Hardware-Wallet zu überwachen, ohne es jedes Mal verbinden und entsperren zu müssen.

Wenn Sie dieses Tutorial hilfreich fanden, würde ich mich freuen, wenn Sie unten einen Daumen hoch hinterlassen könnten. Fühlen Sie sich frei, diesen Artikel in Ihren sozialen Netzwerken zu teilen. Vielen Dank!

Ich empfehle auch, dieses vollständige Tutorial zur Blockstream Green-Anwendung zu überprüfen, um ein Hot Wallet einzurichten:

https://planb.network/tutorials/wallet/blockstream-green