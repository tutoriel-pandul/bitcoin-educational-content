---
name: Blockstream Green - Liquid
description: Einrichtung einer Wallet auf der Liquid Network Sidechain
---
![cover](assets/cover.webp)
Das Bitcoin-Protokoll hat absichtliche technische Einschränkungen, die dazu beitragen, die Dezentralisierung des Netzwerks zu erhalten und die Sicherheitsverteilung unter allen Nutzern zu gewährleisten. Diese Grenzen können jedoch manchmal Nutzer frustrieren, insbesondere während Stauungen, die durch ein hohes Volumen an gleichzeitigen Transaktionen verursacht werden. Die Debatte über die Skalierbarkeit von Bitcoin hat die Gemeinschaft lange gespalten, besonders während des Blocksize-Krieges. Seit dieser Episode ist es in der Bitcoin-Gemeinschaft weitgehend anerkannt, dass die Skalierbarkeit durch Off-Chain-Lösungen auf Second-Layer-Systemen sichergestellt werden muss. Zu diesen Lösungen gehören Sidechains, die im Vergleich zu anderen Systemen wie dem Lightning Network noch relativ unbekannt und wenig genutzt sind.

Eine Sidechain ist eine unabhängige Blockchain, die parallel zur Haupt-Bitcoin-Blockchain betrieben wird. Sie verwendet Bitcoin als Recheneinheit durch einen Mechanismus, der als "*Two-Way Peg*" bekannt ist. Dieses System ermöglicht es, Bitcoins auf der Hauptkette zu sperren, um ihren Wert auf der Sidechain zu replizieren, wo sie als Token zirkulieren, die durch die ursprünglichen Bitcoins gedeckt sind. Diese Token halten normalerweise eine Wertparität mit den auf der Hauptkette gesperrten Bitcoins, und der Prozess kann umgekehrt werden, um die Mittel auf Bitcoin zurückzugewinnen.

Das Ziel von Sidechains ist es, zusätzliche Funktionalitäten oder technische Verbesserungen anzubieten, wie schnellere Transaktionen, reduzierte Gebühren oder Unterstützung für Smart Contracts. Diese Innovationen können nicht immer direkt auf der Bitcoin-Blockchain implementiert werden, ohne deren Dezentralisierung oder Sicherheit zu beeinträchtigen. Sidechains ermöglichen es daher, neue Lösungen zu testen und zu erkunden, während die Integrität von Bitcoin bewahrt wird. Diese Protokolle erfordern jedoch oft Kompromisse, insbesondere in Bezug auf Dezentralisierung und Sicherheit, abhängig vom gewählten Governance-Modell und Konsensmechanismus.

Heute ist die bekannteste Sidechain wahrscheinlich Liquid. In diesem Tutorial werde ich Ihnen zunächst vorstellen, was Liquid ist, und Sie dann anleiten, wie Sie es einfach durch die Blockstream Green-Anwendung nutzen können, um seine Vorteile zu nutzen.

![LIQUID GREEN](assets/fr/01.webp)

## Was ist das Liquid Network?

Liquid ist eine föderierte Sidechain, die auf Bitcoin aufbaut, entwickelt von Blockstream, mit dem Ziel, die Geschwindigkeit, Privatsphäre und Funktionalitäten von Transaktionen zu verbessern. Es verwendet einen bilateralen Verankerungsmechanismus, der auf einer Föderation basiert, um Bitcoins auf der Hauptkette zu sperren und im Gegenzug Liquid-Bitcoins (L-BTC), Token, die auf Liquid zirkulieren und dennoch durch die ursprünglichen Bitcoins gedeckt sind, zu erstellen.

![LIQUID GREEN](assets/fr/02.webp)
Das Liquid-Netzwerk basiert auf einer Föderation von Teilnehmern, bestehend aus anerkannten Entitäten aus dem Bitcoin-Ökosystem, die Blöcke validieren und die bilaterale Verankerung verwalten. Neben L-BTC ermöglicht Liquid auch die Ausgabe anderer digitaler Vermögenswerte, wie Stablecoins oder andere Kryptowährungen.
![LIQUID GREEN](assets/fr/03.webp)

## Einführung in Blockstream Green

Blockstream Green ist eine Software-Wallet, die auf Mobilgeräten und Desktops verfügbar ist. Früher als *Green Address* bekannt, wurde diese Wallet nach ihrer Übernahme im Jahr 2016 zu einem Blockstream-Projekt.

Green ist eine Anwendung, die besonders einfach zu verwenden ist, was sie für Anfänger interessant macht. Sie bietet alle wesentlichen Funktionen einer guten Bitcoin-Wallet, einschließlich RBF (*Replace-by-Fee*), einer Option zur Verbindung über Tor, der Möglichkeit, Ihren eigenen Knoten anzuschließen, der SPV (*Simple Payment Verification*)-Option, Beschriftung und Coin-Kontrolle.

Blockstream Green unterstützt auch das Liquid-Netzwerk, und das werden wir in diesem Tutorial erkunden. Wenn Sie Green für andere Anwendungen nutzen möchten, empfehle ich auch, diese anderen Tutorials zu konsultieren:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Installation und Einrichtung der Blockstream Green-Anwendung

Der erste Schritt besteht natürlich darin, die Green-Anwendung herunterzuladen. Gehen Sie zu Ihrem App-Store:
- [Für Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet) ;
- [Für Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Android-Nutzer haben zudem die Möglichkeit, die Anwendung über die `.apk`-Datei [auf Blockstreams GitHub](https://github.com/Blockstream/green_android/releases) zu installieren.

![LIQUID GREEN](assets/fr/05.webp)

Starten Sie die Anwendung und markieren Sie das Kästchen "*Ich akzeptiere die Bedingungen...*".

![LIQUID GREEN](assets/fr/06.webp)

Wenn Sie Green zum ersten Mal öffnen, erscheint der Startbildschirm ohne konfigurierte Wallets. Später, wenn Sie Wallets erstellen oder importieren, werden diese in dieser Schnittstelle angezeigt. Bevor Sie mit der Erstellung einer Wallet fortfahren, rate ich Ihnen, die Anwendungseinstellungen gemäß Ihren Erwartungen anzupassen. Klicken Sie auf "*Anwendungseinstellungen*".

![LIQUID GREEN](assets/fr/07.webp)

Die Option "*Erweiterte Privatsphäre*", die nur auf Android verfügbar ist, verbessert die Privatsphäre, indem sie Screenshots deaktiviert und Anwendungsvorschauen verbirgt. Sie sperrt auch automatisch den Zugang zur Anwendung, sobald Ihr Telefon gesperrt ist, und macht Ihre Daten schwerer zugänglich.
![LIQUID GREEN](assets/fr/08.webp)
Für diejenigen, die ihre Privatsphäre verstärken möchten, bietet die App die Möglichkeit, Ihren Verkehr über Tor zu leiten, ein Netzwerk, das alle Ihre Verbindungen verschlüsselt und Ihre Aktivitäten schwer nachvollziehbar macht. Obwohl diese Option die Leistung der App leicht verlangsamen kann, wird sie dringend empfohlen, um Ihre Privatsphäre zu schützen, insbesondere wenn Sie nicht Ihren eigenen Full Node verwenden.

![LIQUID GREEN](assets/fr/09.webp)

Für Benutzer, die ihren eigenen Full Node haben, ermöglicht es Green Wallet, sich über einen Electrum-Server damit zu verbinden, wodurch vollständige Kontrolle über Bitcoin-Netzwerkinformationen und Transaktionsübermittlungen gewährleistet wird. Diese Funktion ist jedoch für traditionelle Bitcoin-Wallets relevant, daher benötigen Sie sie nicht, wenn Sie Liquid verwenden.

![LIQUID GREEN](assets/fr/10.webp)

Eine weitere alternative Funktion ist die Option "*SPV-Verifizierung*", die eine direkte Überprüfung bestimmter Blockchain-Daten ermöglicht und so die Notwendigkeit verringert, dem Standard-Node von Blockstream zu vertrauen, obwohl diese Methode nicht alle Zusicherungen eines Full Node bietet. Auch dies betrifft nur Ihre Onchain-Bitcoin-Wallets und nicht Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Sobald diese Einstellungen gemäß Ihren Bedürfnissen angepasst sind, klicken Sie auf den "*Speichern*" Button und starten Sie die App neu.

![LIQUID GREEN](assets/fr/12.webp)

## Erstellung einer Liquid-Wallet auf Blockstream Green

Sie sind jetzt bereit, eine Liquid-Wallet zu erstellen. Klicken Sie auf den "*Loslegen*" Button.

![LIQUID GREEN](assets/fr/13.webp)

Sie haben die Wahl zwischen der Erstellung einer Software-Wallet lokal oder der Verwaltung einer Cold-Wallet über eine Hardware-Wallet. Für dieses Tutorial konzentrieren wir uns auf die Erstellung einer Hot-Wallet auf Liquid, daher müssen Sie die Option "*Auf diesem Gerät*" auswählen. Sie können auch eine kompatible Hardware-Wallet, wie die Blockstream Jade, verwenden, um Ihre Liquid-Wallet zu sichern.

![LIQUID GREEN](assets/fr/14.webp)
Sie können dann wählen, ob Sie eine bestehende Bitcoin-Wallet wiederherstellen oder eine neue erstellen möchten. Für die Zwecke dieses Tutorials werden wir eine neue Wallet erstellen. Wenn Sie jedoch eine bestehende Liquid-Wallet aus ihrer mnemonischen Phrase regenerieren müssen, zum Beispiel aufgrund des Verlusts Ihrer Hardware-Wallet, müssen Sie die zweite Option wählen.
![LIQUID GREEN](assets/fr/15.webp)

Dann haben Sie die Wahl zwischen einer 12-Wort- oder einer 24-Wort-mnemonischen Phrase. Diese Phrase ermöglicht es Ihnen, im Falle von Problemen mit Ihrem Telefon den Zugang zu Ihrer Wallet von jeder kompatiblen Software aus wiederherzustellen. Derzeit bietet eine 24-Wort-Phrase keine größere Sicherheit als eine 12-Wort-Phrase. Daher empfehle ich, eine **12-Wort** mnemonische Phrase zu wählen.
Green wird Ihnen dann Ihre mnemonische Phrase zur Verfügung stellen. Bevor Sie fortfahren, stellen Sie sicher, dass Sie nicht beobachtet werden. Klicken Sie auf "*Wiederherstellungsphrase anzeigen*", um sie auf dem Bildschirm anzuzeigen.
![LIQUID GREEN](assets/fr/16.webp)

**Diese mnemonische Phrase gibt vollen und uneingeschränkten Zugang zu all Ihren Bitcoins.** Jeder, der im Besitz dieser Phrase ist, kann Ihre Mittel stehlen, selbst ohne physischen Zugang zu Ihrem Telefon.

Sie ermöglicht es Ihnen, den Zugang zu Ihren Bitcoins im Falle von Verlust, Diebstahl oder Beschädigung Ihres Telefons wiederherzustellen. Daher ist es sehr wichtig, sie **auf einem physischen Medium (nicht digital)** sorgfältig zu speichern und an einem sicheren Ort aufzubewahren. Sie können sie auf ein Stück Papier schreiben oder, für mehr Sicherheit, wenn diese Wallet bedeutend ist, empfehle ich, sie in ein Edelstahlmedium zu gravieren, um sie vor den Risiken von Bränden, Überschwemmungen oder Einstürzen zu schützen (für eine Hot Wallet, die dazu bestimmt ist, eine kleine Menge Bitcoins zu sichern, ist wahrscheinlich eine einfache Papierkopie ausreichend).

*Offensichtlich sollten Sie diese Wörter niemals im Internet teilen, im Gegensatz zu dem, was ich in diesem Tutorial mache. Diese Beispiel-Wallet wird nur im Liquid Testnet verwendet und am Ende des Tutorials gelöscht.*

![LIQUID GREEN](assets/fr/17.webp)

Nachdem Sie Ihre mnemonische Phrase korrekt auf einem physischen Medium notiert haben, klicken Sie auf "*Weiter*". Green Wallet wird Sie dann bitten, einige Wörter aus Ihrer Phrase zu bestätigen, um zu überprüfen, dass Sie sie korrekt aufgezeichnet haben. Füllen Sie die Lücken mit den fehlenden Wörtern aus.

![LIQUID GREEN](assets/fr/18.webp)

Wählen Sie den PIN-Code für Ihr Gerät, der verwendet wird, um Ihre Green-Wallet zu entsperren. Es handelt sich also um einen Schutz gegen unbefugten physischen Zugang. Dieser PIN-Code spielt keine Rolle bei der Ableitung der kryptografischen Schlüssel Ihrer Wallet. Somit ermöglicht der Besitz Ihrer 12- oder 24-Wort-mnemonischen Phrase auch ohne Zugang zu diesem PIN-Code, den Zugang zu Ihren Bitcoins wiederherzustellen.

Es wird empfohlen, einen 6-stelligen PIN-Code zu wählen, der so zufällig wie möglich ist. Stellen Sie außerdem sicher, dass Sie diesen Code speichern, damit Sie ihn nicht vergessen, sonst werden Sie gezwungen sein, Ihre Wallet aus der mnemonischen Phrase wiederherzustellen. Später können Sie eine biometrische Sperrmöglichkeit hinzufügen, um die Eingabe des PINs jedes Mal, wenn Sie sie verwenden, zu vermeiden. Allgemein gesprochen sind Biometrien viel weniger sicher als der PIN selbst. Daher rate ich standardmäßig davon ab, diese Entsperrmöglichkeit einzurichten.

![LIQUID GREEN](assets/fr/19.webp)

Geben Sie Ihren PIN ein zweites Mal ein, um ihn zu bestätigen.

![LIQUID GREEN](assets/fr/20.webp)
Warten Sie, bis Ihre Wallet erstellt wurde, und klicken Sie dann auf den Button "*Ein Konto erstellen*".
![LIQUID GREEN](assets/fr/21.webp)
Im Feld "*Assets*" wählen Sie "*Liquid Bitcoin*". Sie haben dann die Wahl zwischen einer Standard-Einzelunterschriften-Wallet, die wir in diesem Tutorial verwenden werden, oder einer Wallet, die durch eine Zwei-Faktor-Authentifizierung (2FA) geschützt ist.
![LIQUID GREEN](assets/fr/22.webp)

Und voilà, Ihre Liquid-Wallet wurde erfolgreich mit der Green-App erstellt!

![LIQUID GREEN](assets/fr/23.webp)

Bevor Sie Ihre ersten Bitcoins in Ihrer Liquid-Wallet empfangen, **rate ich Ihnen dringend, einen leeren Wiederherstellungstest durchzuführen**. Notieren Sie eine Referenzinformation, wie Ihren xpub oder die erste Empfangsadresse, dann löschen Sie Ihre Wallet in der Green-App, während sie noch leer ist. Versuchen Sie anschließend, Ihre Wallet in Green mit Ihren Papier-Backups wiederherzustellen. Überprüfen Sie, ob die nach der Wiederherstellung generierte Zeugenaussage mit der ursprünglich notierten übereinstimmt. Wenn ja, können Sie sicher sein, dass Ihre Papier-Backups zuverlässig sind. Um mehr darüber zu erfahren, wie man einen Wiederherstellungstest durchführt, rate ich Ihnen, dieses andere Tutorial zu konsultieren:

https://planb.network/tutorials/wallet/recovery-test

## Einrichtung Ihrer Liquid-Wallet

Wenn Sie Ihre Wallet anpassen möchten, klicken Sie auf die drei kleinen Punkte oben rechts.

![LIQUID GREEN](assets/fr/24.webp)

Die Option "*Umbenennen*" ermöglicht es Ihnen, den Namen Ihrer Wallet anzupassen, was besonders nützlich ist, wenn Sie mehrere Wallets in derselben Anwendung verwalten.

![LIQUID GREEN](assets/fr/25.webp)

Das Menü "*Einheit*" gibt Ihnen die Möglichkeit, die Basiseinheit Ihrer Wallet zu ändern. Sie können beispielsweise wählen, ob sie in Satoshis statt in Bitcoins angezeigt wird.

![LIQUID GREEN](assets/fr/26.webp)

Das Menü "*Einstellungen*" bietet Zugang zu den verschiedenen Optionen Ihrer Bitcoin-Wallet.

![LIQUID GREEN](assets/fr/27.webp)

Hier finden Sie beispielsweise Ihren *Deskriptor*, der nützlich sein kann, wenn Sie planen, eine Nur-Ansicht-Wallet aus dieser Liquid-Wallet einzurichten.

![LIQUID GREEN](assets/fr/28.webp)

Sie können auch den PIN-Code Ihrer Wallet ändern und die biometrische Anmeldung aktivieren.

![LIQUID GREEN](assets/fr/29.webp)

## Verwendung Ihrer Liquid-Wallet

Jetzt, da Ihre Liquid-Wallet eingerichtet ist, sind Sie bereit, Ihre ersten L-sats zu empfangen!
Wenn Sie noch keine L-BTC besitzen, stehen Ihnen mehrere Optionen zur Verfügung. Die erste Möglichkeit besteht darin, sie direkt an Sie senden zu lassen. Wenn jemand Sie in Bitcoins auf Liquid bezahlen möchte, geben Sie ihm einfach eine Empfangsadresse. Die andere Lösung besteht darin, Ihre Onchain-Bitcoins oder die im Lightning-Netzwerk gegen L-BTC zu tauschen. Dazu können Sie [eine Brücke wie Boltz](https://boltz.exchange/) verwenden. Geben Sie einfach Ihre Liquid-Adresse auf der Website ein und tätigen Sie die Zahlung entweder über das Lightning-Netzwerk oder Onchain.
![LIQUID GREEN](assets/fr/30.webp)

Um eine Liquid-Adresse zu generieren, klicken Sie auf den Button "*Empfangen*".

![LIQUID GREEN](assets/fr/31.webp)

Green zeigt dann die erste leere Empfangsadresse Ihrer Wallet an. Sie können entweder den zugehörigen QR-Code scannen oder die Adresse direkt kopieren, um L-BTC darauf zu senden.

![LIQUID GREEN](assets/fr/32.webp)

Wenn die Transaktion im Netzwerk übertragen wird, erscheint sie in Ihrer Wallet.

![LIQUID GREEN](assets/fr/33.webp)

Warten Sie, bis Sie genügend Bestätigungen erhalten haben, um die Transaktion als endgültig zu betrachten. Auf Liquid sollten Bestätigungen schnell sein, da alle Minuten ein Block veröffentlicht wird.

![LIQUID GREEN](assets/fr/34.webp)
Mit L-sats in Ihrem Liquid-Wallet können Sie diese nun auch versenden. Klicken Sie auf "*Senden*".
![LIQUID GREEN](assets/fr/35.webp)

Auf der nächsten Seite geben Sie die Liquid-Adresse des Empfängers ein. Sie können diese manuell eingeben oder ihren QR-Code scannen.

![LIQUID GREEN](assets/fr/36.webp)

Wählen Sie den Betrag der Zahlung.

![LIQUID GREEN](assets/fr/37.webp)

Klicken Sie auf "*Weiter*", um zu einer Zusammenfassungsseite Ihrer Transaktion zu gelangen. Überprüfen Sie, ob die Adresse, der Betrag und die Gebühren korrekt sind.

![LIQUID GREEN](assets/fr/38.webp)

Wenn alles für Sie gut aussieht, schieben Sie den grünen Button am unteren Bildschirmrand nach rechts, um die Transaktion zu signieren und im Bitcoin-Netzwerk zu verbreiten.

![LIQUID GREEN](assets/fr/39.webp)

Ihre Transaktion wird nun im Dashboard Ihres Bitcoin-Wallets als ausstehend angezeigt.

![LIQUID GREEN](assets/fr/40.webp)

Und voilà, jetzt wissen Sie, wie Sie die Liquid-Seitenkette mit der Blockstream Green-Anwendung einfach nutzen können!

Wenn Ihnen dieses Tutorial geholfen hat, würde ich mich über einen Daumen hoch unten freuen. Fühlen Sie sich frei, diesen Artikel in Ihren sozialen Netzwerken zu teilen. Vielen Dank!

Ich empfehle auch, dieses weitere vollständige Tutorial über die Blockstream Green Mobile-App zu entdecken, um ein Onchain-Bitcoin-Hot-Wallet einzurichten:

https://planb.network/tutorials/wallet/blockstream-green