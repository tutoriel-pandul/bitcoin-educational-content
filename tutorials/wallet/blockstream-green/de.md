---
name: Blockstream Green - Mobile
description: Einrichtung einer mobilen Software-Wallet
---
![cover](assets/cover.webp)

Eine Software-Wallet ist eine Anwendung, die auf einem Computer, Smartphone oder einem anderen mit dem Internet verbundenen Gerät installiert wird und das Management und die Sicherheit der Bitcoin-Wallet-Schlüssel eines Benutzers ermöglicht. Im Gegensatz zu Hardware-Wallets, die private Schlüssel isolieren, operieren "Hot" Wallets in einer Umgebung, die potenziell Cyberangriffen ausgesetzt ist, was die Risiken von Hacking und Diebstahl erhöht.

Software-Wallets sollen für die Verwaltung vernünftiger Bitcoin-Mengen verwendet werden, insbesondere für tägliche Transaktionen. Dies kann auch eine interessante Option für Personen mit einem begrenzten Bitcoin-Portfolio sein, für die die Investition in eine Hardware-Wallet unverhältnismäßig erscheinen mag. Ihre ständige Exposition gegenüber dem Internet macht sie jedoch weniger sicher für die Aufbewahrung Ihrer langfristigen Ersparnisse oder bedeutender Geldmittel. Für diese ist es vorzuziehen, sicherere Lösungen wie Hardware-Wallets zu wählen.

In diesem Tutorial werde ich Ihnen eine der besten mobilen Software-Wallet-Lösungen vorstellen: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Wenn Sie daran interessiert sind zu lernen, wie man Blockstream Green auf einem Computer verwendet, beziehen Sie sich bitte auf dieses andere Tutorial:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Einführung in Blockstream Green

Blockstream Green ist eine Software-Wallet, die sowohl auf Mobilgeräten als auch auf Computern verfügbar ist. Früher als *Green Address* bekannt, wurde diese Wallet nach ihrer Übernahme im Jahr 2016 zu einem Blockstream-Projekt.

Green ist eine Anwendung, die besonders einfach zu verwenden ist, was sie für Anfänger interessant macht. Sie bietet alle wesentlichen Funktionen einer guten Bitcoin-Wallet, einschließlich RBF (*Replace-by-Fee*), einer Option zur Verbindung über Tor, der Möglichkeit, den eigenen Knoten anzuschließen, der SPV (*Simple Payment Verification*)-Option, Beschriftung und Coin-Kontrolle.

Blockstream Green unterstützt auch das Liquid-Netzwerk, eine von Blockstream entwickelte Bitcoin-Seitenkette für schnelle und vertrauliche Transaktionen außerhalb der Haupt-Blockchain. Dieses Tutorial konzentriert sich ausschließlich auf Bitcoin, aber ein zukünftiges wird die Verwendung von Liquid behandeln.

## Installation und Einrichtung der Blockstream Green-App

Der erste Schritt ist natürlich, die Green-App herunterzuladen. Gehen Sie zu Ihrem App-Store:
- [Für Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Für Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Android-Nutzer haben auch die Möglichkeit, die Anwendung über die `.apk`-Datei [auf Blockstreams GitHub](https://github.com/Blockstream/green_android/releases) zu installieren.

![GREEN](assets/fr/03.webp)
Starten Sie die Anwendung und markieren Sie das Kästchen "*Ich akzeptiere die Bedingungen...*".
![GREEN](assets/fr/04.webp)

Wenn Sie Green zum ersten Mal öffnen, erscheint der Startbildschirm ohne konfigurierte Wallets. Später, wenn Sie Wallets erstellen oder importieren, werden diese in dieser Schnittstelle erscheinen. Bevor Sie mit der Erstellung einer Wallet fortfahren, rate ich Ihnen, die Anwendungseinstellungen gemäß Ihren Erwartungen anzupassen. Klicken Sie auf "*Anwendungseinstellungen*".

![GREEN](assets/fr/05.webp)

Die Option "*Erweiterte Privatsphäre*", die nur auf Android verfügbar ist, verbessert die Privatsphäre, indem sie Screenshots deaktiviert und Anwendungsvorschauen verbirgt. Sie sperrt auch automatisch den Zugang zur Anwendung, sobald Ihr Telefon gesperrt ist, was Ihre Daten schwieriger zu exponieren macht.

![GREEN](assets/fr/06.webp)
Für diejenigen, die ihre Privatsphäre verbessern möchten, bietet die Anwendung die Möglichkeit, Ihren Datenverkehr über Tor zu leiten, ein Netzwerk, das alle Ihre Verbindungen verschlüsselt und Ihre Aktivitäten schwer nachvollziehbar macht. Obwohl diese Option die Leistung der Anwendung leicht verlangsamen kann, wird sie dringend empfohlen, um Ihre Privatsphäre zu schützen, insbesondere wenn Sie nicht Ihren eigenen Full Node verwenden.
![GREEN](assets/fr/07.webp)

Für Benutzer, die ihren eigenen Full Node besitzen, bietet Green Wallet die Möglichkeit, sich über einen Electrum-Server damit zu verbinden, was die vollständige Kontrolle über Bitcoin-Netzwerkinformationen und das Senden von Transaktionen gewährleistet.

![GREEN](assets/fr/08.webp)

Eine weitere alternative Funktion ist die "*SPV-Verifizierung*" Option, die eine direkte Überprüfung bestimmter Blockchain-Daten ermöglicht und somit die Notwendigkeit verringert, dem standardmäßigen Blockstream-Node zu vertrauen, obwohl diese Methode nicht alle Garantien eines Full Node bietet.

![GREEN](assets/fr/09.webp)

Sobald diese Einstellungen gemäß Ihren Bedürfnissen angepasst sind, klicken Sie auf den "*Speichern*" Knopf und starten Sie die Anwendung neu.

![GREEN](assets/fr/10.webp)

## Erstellen eines Bitcoin-Wallets auf Blockstream Green

Sie sind jetzt bereit, ein Bitcoin-Wallet zu erstellen. Klicken Sie auf den "*Loslegen*" Knopf.

![GREEN](assets/fr/11.webp)

Sie haben die Wahl zwischen der Erstellung eines Software-Wallets lokal oder der Verwaltung eines Cold Wallets über ein Hardware-Wallet. Für dieses Tutorial konzentrieren wir uns auf die Erstellung eines Hot Wallets, daher müssen Sie die Option "*Auf diesem Gerät*" auswählen. In einem zukünftigen Tutorial werde ich Ihnen zeigen, wie Sie die andere Option nutzen können.

Die Option "*Nur-Ansicht*" ermöglicht es Ihnen andererseits, einen erweiterten öffentlichen Schlüssel (`xpub`) zu importieren, um Transaktionen eines Wallets anzusehen, ohne die damit verbundenen Mittel ausgeben zu können, was beispielsweise für die Überwachung eines Wallets auf einem Hardware-Wallet praktisch ist.

![GREEN](assets/fr/12.webp)
Dann können Sie wählen, ob Sie ein bestehendes Bitcoin-Wallet wiederherstellen oder ein neues erstellen möchten. Für die Zwecke dieses Tutorials werden wir ein neues Wallet erstellen. Wenn Sie jedoch ein bereits bestehendes Bitcoin-Wallet aus seiner mnemonischen Phrase wiederherstellen müssen, zum Beispiel aufgrund des Verlusts Ihres Hardware-Wallets, müssen Sie die zweite Option wählen.
![GREEN](assets/fr/13.webp)

Dann haben Sie die Wahl zwischen einer 12-Wort- oder 24-Wort-mnemonischen Phrase. Diese Phrase ermöglicht es Ihnen, im Falle von Problemen mit Ihrem Telefon den Zugriff auf Ihr Wallet von jeder kompatiblen Software aus wiederherzustellen. Derzeit bietet die Wahl einer 24-Wort-Phrase keine größere Sicherheit als eine 12-Wort-Phrase. Daher empfehle ich, eine **12-Wort** mnemonische Phrase zu wählen.

Green wird Ihnen dann Ihre mnemonische Phrase zur Verfügung stellen. Bevor Sie fortfahren, stellen Sie sicher, dass Sie nicht beobachtet werden. Klicken Sie auf "*Wiederherstellungsphrase anzeigen*", um sie auf dem Bildschirm anzuzeigen.

![GREEN](assets/fr/14.webp)

**Diese mnemonische Phrase gibt vollen und uneingeschränkten Zugriff auf all Ihre Bitcoins.** Jeder, der im Besitz dieser Phrase ist, kann Ihre Mittel stehlen, selbst ohne physischen Zugang zu Ihrem Telefon.

Sie ermöglicht es Ihnen, den Zugang zu Ihren Bitcoins im Falle von Verlust, Diebstahl oder Beschädigung Ihres Telefons wiederherzustellen. Es ist daher sehr wichtig, sie **auf einem physischen Medium (nicht digital)** sorgfältig zu speichern und an einem sicheren Ort aufzubewahren. Sie können sie auf ein Stück Papier schreiben oder, für mehr Sicherheit, wenn dieses Wallet wichtig ist, empfehle ich, sie in ein Edelstahlmedium zu gravieren, um gegen die Risiken von Bränden, Überschwemmungen oder Einstürzen zu schützen (für ein Hot Wallet, das dazu bestimmt ist, eine kleine Menge an Bitcoins zu sichern, ist wahrscheinlich eine einfache Papierkopie ausreichend).
*Offensichtlich sollten Sie diese Wörter niemals im Internet teilen, im Gegensatz zu dem, was ich in diesem Tutorial mache. Diese Beispiel-Wallet wird nur im Testnet verwendet und am Ende des Tutorials gelöscht.*
![GREEN](assets/fr/15.webp)

Nachdem Sie Ihre mnemonische Phrase korrekt auf einem physischen Medium notiert haben, klicken Sie auf "*Weiter*". Green Wallet wird Sie dann bitten, bestimmte Wörter aus Ihrer Phrase zu bestätigen, um zu überprüfen, ob Sie sie korrekt aufgezeichnet haben. Füllen Sie die Lücken mit den fehlenden Wörtern aus.

![GREEN](assets/fr/16.webp)

Wählen Sie den PIN-Code für Ihr Gerät, der zum Entsperren Ihrer Green-Wallet verwendet wird. Dies ist also ein Schutz gegen unbefugten physischen Zugriff. Dieser PIN-Code spielt keine Rolle bei der Ableitung der kryptografischen Schlüssel Ihrer Wallet. Somit können Sie auch ohne Zugang zu diesem PIN-Code durch den Besitz Ihrer 12- oder 24-Wort-mnemonischen Phrase wieder Zugang zu Ihren Bitcoins erhalten.
Es wird empfohlen, einen 6-stelligen PIN zu wählen, der so zufällig wie möglich ist. Stellen Sie außerdem sicher, dass Sie diesen Code sichern, damit Sie ihn nicht vergessen, sonst werden Sie gezwungen sein, Ihre Wallet mit der mnemonischen Phrase wiederherzustellen. Anschließend können Sie eine biometrische Sperrmöglichkeit hinzufügen, um die Eingabe des PINs bei jeder Nutzung zu vermeiden. Allgemein gesprochen sind Biometrien viel weniger sicher als der PIN selbst. Daher rate ich standardmäßig davon ab, diese Entsperrmöglichkeit einzurichten.
![GREEN](assets/fr/17.webp)

Geben Sie Ihren PIN ein zweites Mal ein, um ihn zu bestätigen.

![GREEN](assets/fr/18.webp)

Warten Sie, bis Ihre Wallet erstellt wurde, und klicken Sie dann auf den Button "*Ein Konto erstellen*".

![GREEN](assets/fr/19.webp)

Dann haben Sie die Wahl zwischen einer Standard-Wallet mit Einzelunterschrift, die wir in diesem Tutorial verwenden werden, oder einer Wallet, die durch eine Zwei-Faktor-Authentifizierung (2FA) geschützt ist.

![GREEN](assets/fr/20.webp)

Die 2FA-Option bei Green erstellt eine 2/2-Multisignatur-Wallet, von der ein Schlüssel von Blockstream aufbewahrt wird. Das bedeutet, dass für eine Transaktion beide Schlüssel erforderlich sind: ein lokaler Schlüssel, der durch Ihren PIN auf Ihrem Telefon geschützt ist, und ein entfernter Schlüssel, der durch 2FA auf den Servern von Blockstream gesichert ist. Im Falle eines Verlusts des Zugangs zu 2FA oder der Nichtverfügbarkeit von Blockstreams Diensten, stellen Wiederherstellungsmechanismen basierend auf Zeit-Schloss-Skripten die Möglichkeit sicher, Ihre Gelder unabhängig wiederherzustellen. Obwohl diese Einrichtung das Risiko, dass Ihre Bitcoins gestohlen werden, erheblich reduziert, ist sie komplexer zu verwalten und hängt teilweise von Blockstream ab. Für dieses Tutorial werden wir uns für eine klassische Einzelunterschrift-Wallet entscheiden, mit lokal auf dem Telefon gespeicherten Schlüsseln.

Und da haben Sie es, Ihre Bitcoin-Wallet wurde erfolgreich mit der Green-App erstellt!

![GREEN](assets/fr/21.webp)

Bevor Sie Ihre ersten Bitcoins in Ihrer Wallet empfangen, **rate ich Ihnen dringend, einen Trockenlauf-Wiederherstellungstest durchzuführen**. Notieren Sie eine Referenzinformation, wie Ihren xpub oder die erste Empfangsadresse, dann löschen Sie Ihre Wallet in der Green-App, während sie noch leer ist. Versuchen Sie anschließend, Ihre Wallet auf Green mit Ihren Papier-Backups wiederherzustellen. Überprüfen Sie, ob die nach der Wiederherstellung generierte Zeugeninformation mit der ursprünglich notierten übereinstimmt. Wenn dies der Fall ist, können Sie sicher sein, dass Ihre Papier-Backups zuverlässig sind. Um mehr darüber zu erfahren, wie man einen Wiederherstellungstest durchführt, rate ich Ihnen, dieses andere Tutorial zu konsultieren:

https://planb.network/tutorials/wallet/recovery-test

## Einrichten Ihrer Wallet auf Blockstream Green
Wenn Sie Ihr Portfolio anpassen möchten, klicken Sie auf die drei kleinen Punkte oben rechts.
![GREEN](assets/fr/22.webp)
Die Option "*Umbenennen*" ermöglicht es Ihnen, den Namen Ihres Portfolios anzupassen, was besonders nützlich ist, wenn Sie mehrere Portfolios in derselben App verwalten.
![GREEN](assets/fr/23.webp)

Das Menü "*Einheit*" gibt Ihnen die Möglichkeit, die Basiseinheit Ihres Portfolios zu ändern. Sie können beispielsweise wählen, es in Satoshis anstatt in Bitcoins anzuzeigen.

![GREEN](assets/fr/24.webp)

Das Menü "*Einstellungen*" bietet Zugriff auf die verschiedenen Optionen Ihrer Bitcoin-Wallet.

![GREEN](assets/fr/25.webp)

Hier finden Sie beispielsweise Ihren erweiterten öffentlichen Schlüssel und dessen *Deskriptor*, nützlich, wenn Sie planen, aus dieser Wallet eine Nur-Ansicht-Wallet einzurichten.

![GREEN](assets/fr/26.webp)

Sie können auch den PIN-Code Ihrer Wallet ändern und die biometrische Anmeldung aktivieren.

![GREEN](assets/fr/27.webp)

## Blockstream Green verwenden

Jetzt, da Ihre Bitcoin-Wallet eingerichtet ist, sind Sie bereit, Ihre ersten Sats zu erhalten! Klicken Sie dazu einfach auf den Button "*Empfangen*".

![GREEN](assets/fr/28.webp)

Green zeigt dann die erste leere Empfangsadresse Ihrer Wallet an. Sie können entweder den zugehörigen QR-Code scannen oder die Adresse direkt kopieren, um Bitcoins darauf zu senden. Diese Art von Adresse gibt den zu sendenden Betrag nicht an. Sie können jedoch eine Adresse generieren, die einen bestimmten Betrag anfordert, indem Sie oben rechts auf die drei kleinen Punkte klicken, dann auf "*Betrag anfordern*" und den gewünschten Betrag eingeben.

Da Sie ein Segwit v0-Konto (BIP84) verwenden, beginnt Ihre Adresse mit `bc1q...`. In meinem Beispiel verwende ich eine Testnet-Wallet, daher ist das Präfix etwas anders.

![GREEN](assets/fr/29.webp)

Wenn die Transaktion im Netzwerk übertragen wird, erscheint sie in Ihrer Wallet.

![GREEN](assets/fr/30.webp)

Warten Sie, bis Sie genügend Bestätigungen erhalten haben, um die Transaktion als endgültig zu betrachten.

![GREEN](assets/fr/31.webp)

Mit Bitcoins in Ihrer Wallet können Sie diese nun auch senden. Klicken Sie auf "*Senden*".

![GREEN](assets/fr/32.webp)

Geben Sie auf der nächsten Seite die Adresse des Empfängers ein. Sie können sie manuell eingeben oder einen QR-Code scannen.

![GREEN](assets/fr/33.webp)

Wählen Sie den Zahlungsbetrag.

![GREEN](assets/fr/34.webp)
Am unteren Bildschirmrand können Sie die Gebührenrate für diese Transaktion auswählen. Sie haben die Möglichkeit, den Empfehlungen der Anwendung zu folgen oder Ihre Gebühren individuell anzupassen. Je höher die Gebühren im Vergleich zu anderen ausstehenden Transaktionen sind, desto schneller wird Ihre Transaktion bearbeitet. Um den Gebührenmarkt zu verstehen, können Sie [Mempool.space](https://mempool.space/) im Abschnitt "*Transaktionsgebühren*" besuchen.
![GREEN](assets/fr/35.webp)

Klicken Sie auf "*Weiter*", um einen Zusammenfassungsbildschirm Ihrer Transaktion zu erreichen. Überprüfen Sie, ob die Adresse, der Betrag und die Gebühren korrekt sind.

![GREEN](assets/fr/36.webp)

Wenn alles zu Ihrer Zufriedenheit ist, schieben Sie den grünen Button am unteren Bildschirmrand nach rechts, um die Transaktion zu signieren und im Bitcoin-Netzwerk zu übertragen.

![GREEN](assets/fr/37.webp)

Ihre Transaktion wird nun auf dem Dashboard Ihrer Bitcoin-Wallet auf Bestätigung warten.

![GREEN](assets/fr/38.webp)
*Dieses Tutorial basiert auf [einer Originalversion, die zu Bitstack gehört](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet), geschrieben von Loïc Morel. Bitstack ist eine französische Bitcoin-Neobank, die die Möglichkeit bietet, in Bitcoins zu sparen, entweder durch DCA (Dollar Cost Averaging) oder über ein automatisches Rundungssystem der täglichen Ausgaben.*