---
name: Blockstream Green - 2FA
description: Einrichtung eines 2/2 Multisig auf Green Wallet
---
![cover](assets/cover.webp)

Eine Software-Wallet ist eine Anwendung, die auf einem Computer, Smartphone oder einem anderen mit dem Internet verbundenen Gerät installiert wird und das Management und die Sicherheit der Bitcoin-Wallet-Schlüssel eines Benutzers ermöglicht. Im Gegensatz zu Hardware-Wallets, die private Schlüssel isolieren, operieren "Hot" Wallets in einer Umgebung, die potenziell Cyberangriffen ausgesetzt ist, was die Risiken von Hacking und Diebstahl erhöht.

Software-Wallets sollten für die Verwaltung vernünftiger Bitcoin-Mengen verwendet werden, insbesondere für tägliche Transaktionen. Dies kann auch eine interessante Option für Personen mit einem begrenzten Bitcoin-Portfolio sein, für die die Investition in eine Hardware-Wallet unverhältnismäßig erscheinen mag. Ihre ständige Exposition gegenüber dem Internet macht sie jedoch weniger sicher für die Aufbewahrung Ihrer langfristigen Ersparnisse oder bedeutender Geldmittel. Für diese ist es vorzuziehen, sicherere Lösungen wie Hardware-Wallets zu wählen.

In diesem Tutorial zeige ich Ihnen, wie Sie die Sicherheit einer Hot Wallet durch Verwendung der "2FA"-Option auf Blockstream Green verbessern können.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Einführung in Blockstream Green

Blockstream Green ist eine Software-Wallet, die auf Mobilgeräten und Desktops verfügbar ist. Ursprünglich als *Green Address* bekannt, wurde diese Wallet nach ihrer Übernahme im Jahr 2016 zu einem Blockstream-Projekt.

Green ist eine Anwendung, die besonders einfach zu bedienen ist, was sie für Anfänger interessant macht. Sie bietet alle wesentlichen Funktionen einer guten Bitcoin-Wallet, einschließlich RBF (*Replace-by-Fee*), einer Option zur Verbindung über Tor, der Möglichkeit, den eigenen Knoten anzuschließen, der SPV (*Simple Payment Verification*)-Option, Beschriftung und Coin-Kontrolle.

Blockstream Green unterstützt auch das Liquid-Netzwerk, eine von Blockstream entwickelte Bitcoin-Seitenkette für schnelle und vertrauliche Transaktionen außerhalb der Haupt-Blockchain. In diesem Tutorial konzentrieren wir uns ausschließlich auf Bitcoin, aber ich habe auch ein anderes Tutorial erstellt, um zu lernen, wie man Liquid auf Green verwendet:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## Die 2/2 Multisig (2FA) Option

Auf Green können Sie sicherlich eine klassische "Singlesig" Hot Wallet erstellen. Aber Sie haben auch die "2FA Multisig"-Option, die es Ihnen ermöglicht, die Sicherheit Ihrer Hot Wallet zu verbessern, ohne deren tägliche Verwaltung übermäßig zu komplizieren.
Sie werden also eine 2/2 Multisig-Wallet einrichten, was bedeutet, dass jede Transaktion die Unterschrift von zwei Schlüsseln erfordert. Der erste Schlüssel, abgeleitet von Ihrer 12- oder 24-Wort-Mnemonik-Phrase, wird lokal mit einer PIN auf Ihrem Telefon gesichert. Sie haben die volle Kontrolle über diesen Schlüssel. Der zweite Schlüssel wird von den Servern von Blockstream gehalten, und seine Verwendung zur Signierung erfordert eine Authentifizierung, die über einen Code per E-Mail, SMS, Telefonanruf oder, wie wir in diesem Tutorial sehen werden, über eine Authentifizierungs-App (Authy, Google Authenticator usw.) erreicht werden kann.

Um Ihre Autonomie im Falle eines Ausfalls von Blockstream zu gewährleisten (zum Beispiel, wenn das Unternehmen insolvent geht oder die Server, die den zweiten Schlüssel halten, zerstört werden), wird ein Timelock-Mechanismus auf Ihr Multisig angewendet. Dieser Mechanismus verwandelt das 2/2 Multisig nach etwa einem Jahr (oder genau 51.840 Blöcken, aber dieser Wert kann geändert werden) in ein 1/2 Multisig, nach dem Ihre Wallet nur noch Ihren lokalen Schlüssel benötigt, um die Bitcoins auszugeben. Wenn Sie also den Zugang zu den Servern von Blockstream oder zur 2FA-Authentifizierung verlieren, müssen Sie nur bis zu einem Jahr warten, um Ihre Bitcoins mit Ihrer App frei nutzen zu können, ohne von Blockstream abhängig zu sein.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
Diese Methode erhöht die Sicherheit Ihrer Hot Wallet erheblich, während Sie die Kontrolle über Ihre Bitcoins behalten und deren tägliche Nutzung erleichtern. Es erfordert jedoch, regelmäßig den Timelock zu erneuern, um die Sicherheit der 2FA zu gewährleisten. Der 360-Tage-Countdown, währenddessen Ihre Gelder durch die 2FA geschützt sind, beginnt, sobald Sie Bitcoins erhalten. Wenn Sie 360 Tage nach deren Erhalt keine Transaktion durchgeführt haben, die diese Gelder ausgibt, werden Ihre Bitcoins nur durch Ihren lokalen Schlüssel ohne die 2FA geschützt.

Diese Einschränkung macht die 2FA-Option besser geeignet für eine Ausgaben-Wallet, bei der regelmäßige Transaktionen die Timelocks automatisch erneuern. Für eine langfristige Spar-Wallet kann dies problematisch sein, da Sie daran denken müssen, jedes Jahr vor Ablauf des Timelocks eine Sweep-Transaktion an sich selbst durchzuführen.

Ein weiterer Nachteil dieser Sicherheitsmethode ist, dass Sie Minderheits-Scriptmuster verwenden müssen. Das bedeutet, dass aus Datenschutzsicht die Dinge kompliziert werden: Sehr wenige Menschen verwenden denselben Typ von Script wie Sie, was es einem externen Beobachter erleichtert, Ihren Wallet-Fußabdruck zu identifizieren. Darüber hinaus führen diese Scripts aufgrund ihrer größeren Größe zu höheren Transaktionsgebühren.
Wenn Sie die 2FA-Option nicht verwenden möchten und einfach eine "Singlesig"-Wallet auf Green einrichten möchten, lade ich Sie ein, dieses andere Tutorial zu besuchen:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Installation und Einrichtung der Blockstream Green Software

Der erste Schritt ist natürlich, die Green-App herunterzuladen. Gehen Sie zu Ihrem App-Store:
- [Für Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Für Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

Für Android-Nutzer besteht auch die Möglichkeit, die App über die `.apk`-Datei [auf Blockstreams GitHub](https://github.com/Blockstream/green_android/releases) zu installieren.

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Starten Sie die App und markieren Sie das Kästchen "*Ich akzeptiere die Bedingungen...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Wenn Sie Green zum ersten Mal öffnen, erscheint der Startbildschirm ohne eine konfigurierte Wallet. Später, wenn Sie Wallets erstellen oder importieren, werden diese in dieser Schnittstelle erscheinen. Bevor Sie mit der Erstellung einer Wallet fortfahren, rate ich Ihnen, die App-Einstellungen gemäß Ihren Erwartungen anzupassen. Klicken Sie auf "*Anwendungseinstellungen*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

Die Option "*Erweiterter Datenschutz*", die nur auf Android verfügbar ist, verbessert den Datenschutz, indem sie Screenshots deaktiviert und App-Vorschauen verbirgt. Sie sperrt auch automatisch den Zugriff auf die App, sobald Ihr Telefon gesperrt ist, was Ihre Daten schwerer zugänglich macht.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

Für diejenigen, die ihren Datenschutz verbessern möchten, bietet die App die Möglichkeit, Ihren Verkehr durch Tor zu leiten, ein Netzwerk, das alle Ihre Verbindungen verschlüsselt und Ihre Aktivitäten schwer zu verfolgen macht. Obwohl diese Option die Leistung der App leicht verlangsamen kann, wird sie dringend empfohlen, um Ihren Datenschutz zu schützen, insbesondere wenn Sie nicht Ihren eigenen Full Node verwenden.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

Für Benutzer, die ihren eigenen Full Node haben, bietet Green Wallet die Möglichkeit, sich über einen Electrum-Server damit zu verbinden, was volle Kontrolle über Bitcoin-Netzwerkinformationen und das Senden von Transaktionen gewährleistet.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
Eine weitere alternative Funktion ist die Option "*SPV-Verifizierung*", die eine direkte Überprüfung bestimmter Blockchain-Daten ermöglicht und somit die Notwendigkeit verringert, dem Standard-Node von Blockstream zu vertrauen, obwohl diese Methode nicht alle Garantien eines Vollknotens bietet.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Sobald diese Einstellungen nach Ihren Bedürfnissen angepasst sind, klicken Sie auf den "*Speichern*" Button und starten Sie die Anwendung neu.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Erstellen eines Bitcoin-Wallets auf Blockstream Green

Sie sind jetzt bereit, ein Bitcoin-Wallet zu erstellen. Klicken Sie auf den "*Loslegen*" Button.

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Sie haben die Wahl zwischen der Erstellung eines Software-Wallets lokal oder der Verwaltung eines Cold-Wallets über ein Hardware-Wallet. Für dieses Tutorial konzentrieren wir uns auf die Erstellung eines Hot-Wallets, daher müssen Sie die Option "*Auf diesem Gerät*" auswählen.

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Als Nächstes können Sie wählen, ob Sie ein bestehendes Bitcoin-Wallet wiederherstellen oder ein neues erstellen möchten. Für die Zwecke dieses Tutorials werden wir ein neues Wallet erstellen. Wenn Sie jedoch ein bestehendes Bitcoin-Wallet aus seiner mnemonischen Phrase regenerieren müssen, zum Beispiel aufgrund des Verlusts Ihres alten Telefons, müssen Sie die zweite Option wählen.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Dann haben Sie die Wahl zwischen einer 12-Wort- oder einer 24-Wort-mnemonischen Phrase. Diese Phrase ermöglicht es Ihnen, im Falle von Problemen mit Ihrem Telefon den Zugriff auf Ihr Wallet von jeder kompatiblen Software aus wiederherzustellen. Derzeit bietet die Wahl einer 24-Wort-Phrase keine größere Sicherheit als eine 12-Wort-Phrase. Daher empfehle ich, eine **12-Wort** mnemonische Phrase zu wählen.

Green wird Ihnen dann Ihre mnemonische Phrase zur Verfügung stellen. Bevor Sie fortfahren, stellen Sie sicher, dass Sie nicht beobachtet werden. Klicken Sie auf "*Wiederherstellungsphrase anzeigen*", um sie auf dem Bildschirm anzuzeigen.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**Diese mnemonische Phrase gibt vollständigen und uneingeschränkten Zugriff auf all Ihre Bitcoins**. Jeder, der im Besitz dieser Phrase ist, kann Ihre Mittel stehlen, selbst ohne physischen Zugriff auf Ihr Telefon (unter Bedingungen eines abgelaufenen Zeitlimits oder 2FA im Falle eines 2/2-Wallets auf Green).

Sie ermöglicht es Ihnen, den Zugriff auf Ihre lokalen Schlüssel im Falle von Verlust, Diebstahl oder Beschädigung Ihres Telefons wiederherzustellen. Es ist daher sehr wichtig, sie sorgfältig **auf einem physischen Medium (nicht digital)** zu speichern und an einem sicheren Ort aufzubewahren. Sie können sie auf ein Stück Papier schreiben oder, für mehr Sicherheit, wenn dieses Wallet wichtig ist, empfehle ich, sie in ein Edelstahlmedium zu gravieren, um gegen die Risiken von Bränden, Überschwemmungen oder Einstürzen zu schützen (für ein Hot-Wallet, das dazu bestimmt ist, eine kleine Menge Bitcoins zu sichern, ist wahrscheinlich eine einfache Papierkopie ausreichend).
*Offensichtlich sollten Sie diese Wörter niemals im Internet teilen, im Gegensatz zu dem, was ich in diesem Tutorial mache. Dieses Beispiel-Wallet wird nur im Testnet verwendet und am Ende des Tutorials gelöscht.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Nachdem Sie Ihre mnemonische Phrase korrekt auf einem physischen Medium notiert haben, klicken Sie auf "*Weiter*". Green Wallet wird Sie dann bitten, einige Wörter aus Ihrer Phrase zu bestätigen, um zu überprüfen, dass Sie sie korrekt aufgezeichnet haben. Füllen Sie die Lücken mit den fehlenden Wörtern aus.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Wählen Sie den PIN-Code für Ihr Gerät, der verwendet wird, um Ihre Green-Wallet zu entsperren. Es handelt sich daher um einen Schutz gegen unbefugten physischen Zugriff. Dieser PIN-Code spielt keine Rolle bei der Ableitung der kryptografischen Schlüssel Ihrer Wallet. Somit können Sie auch ohne Zugang zu diesem PIN-Code durch die Besitznahme Ihrer 12- oder 24-Wörter-Mnemonik-Phrase wieder Zugang zu Ihren lokalen Schlüsseln erhalten.
Es wird empfohlen, einen 6-stelligen PIN-Code zu wählen, der so zufällig wie möglich ist. Stellen Sie außerdem sicher, dass Sie diesen Code speichern, damit Sie ihn nicht vergessen, da Sie sonst gezwungen sind, Ihre Wallet von der Mnemonik-Phrase wiederherzustellen. Sie können später eine Option für die biometrische Verriegelung hinzufügen, um die Eingabe des PINs jedes Mal zu vermeiden. Allgemein gesprochen ist die Biometrik viel weniger sicher als der PIN selbst. Daher rate ich standardmäßig davon ab, diese Entsperrungsoption einzurichten.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Geben Sie Ihren PIN ein zweites Mal ein, um ihn zu bestätigen.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Warten Sie, während Ihre Wallet erstellt wird, und klicken Sie dann auf den Button "*Ein Konto erstellen*".

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Sie haben dann die Wahl zwischen einer Standard-Wallet mit Einzelunterschrift oder einer Wallet, die durch eine Zwei-Faktor-Authentifizierung (2FA) geschützt ist. In diesem Tutorial werden wir die zweite Option wählen.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

Und voilà, Ihre Bitcoin-Multisig-Wallet wurde erfolgreich mit der Green-App erstellt!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Einrichtung der 2FA

Klicken Sie auf Ihr Konto.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Klicken Sie auf den grünen Button "*Erhöhen Sie die Sicherheit Ihres Kontos durch Hinzufügen von 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Dann haben Sie die Möglichkeit, die Authentifizierungsmethode zu wählen, um auf den zweiten Schlüssel Ihres 2/2-Multisig zuzugreifen. Für dieses Tutorial werden wir eine Authentifizierungs-App verwenden. Wenn Sie mit dieser Art von App nicht vertraut sind, empfehle ich, unser Tutorial über Authy zu konsultieren:
https://planb.network/tutorials/others/authy

Wählen Sie "*Authenticator Application*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green wird dann einen QR-Code und einen Wiederherstellungsschlüssel anzeigen. Dieser Schlüssel ermöglicht es Ihnen, den Zugang zu Ihrer 2FA wiederherzustellen, falls Sie Ihre Authy-App verlieren. Es wird empfohlen, eine sichere Sicherung dieses Schlüssels zu machen, obwohl Sie immer nach Ablauf des Timelocks, wie zuvor erklärt, wieder Zugang zu Ihren Bitcoins erhalten können.

In Ihrer Authentifizierungs-App fügen Sie einen neuen Code hinzu und scannen dann den von Green bereitgestellten QR-Code.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Offensichtlich sollten Sie diesen Schlüssel und QR-Code niemals im Internet teilen, im Gegensatz zu dem, was ich in diesem Tutorial mache. Dieses Beispiel-Wallet wird nur im Testnet verwendet und am Ende des Tutorials gelöscht.*

Klicken Sie auf den Button "*Weiter*".

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Geben Sie den dynamischen 6-stelligen Code ein, der in Ihrer Authentifizierungs-App angezeigt wird.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

Die Zwei-Faktor-Authentifizierung ist jetzt aktiviert.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Beim Durchsuchen dieses Menüs können Sie auch die Dauer des Timelocks anpassen. Dieser Countdown beginnt, sobald Sie Bitcoins erhalten, und sobald der Timelock abgelaufen ist, können Ihre Mittel nur mit Ihrem lokalen Schlüssel ausgegeben werden, ohne dass die 2FA erforderlich ist. Die Standarddauer ist auf 12 Monate eingestellt, aber für ein Sparkonto könnte die Wahl von 15 Monaten klug sein, um die Häufigkeit der Timelock-Erneuerungen zu minimieren. Umgekehrt könnte für ein Ausgabenkonto ein Timelock von 6 Monaten vorzuziehen sein, da es mit Ihren täglichen Transaktionen häufig erneuert wird und ein kürzerer Timelock die Wartezeit im Falle von Problemen mit der 2FA reduziert. Es liegt an Ihnen, die Timelock-Dauer zu bestimmen, die am besten zu Ihnen passt.
![GREEN 2FA MULTISIG](assets/fr/30.webp)

Sie können nun dieses Menü verlassen. Ihr Multisig-Wallet ist einsatzbereit!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Einrichten Ihres Wallets auf Blockstream Green

Wenn Sie Ihr Wallet anpassen möchten, klicken Sie auf die drei kleinen Punkte oben rechts.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
Die Option "*Umbenennen*" ermöglicht es Ihnen, den Namen Ihres Wallets anzupassen, was besonders nützlich ist, wenn Sie mehrere Wallets in derselben Anwendung verwalten.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

Das Menü "*Einheit*" gibt Ihnen die Möglichkeit, die Basiseinheit Ihres Wallets zu ändern. Sie können beispielsweise wählen, es in Satoshis anstatt in Bitcoins anzuzeigen.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

Das Menü "*Einstellungen*" bietet Zugang zu den verschiedenen Optionen Ihres Bitcoin-Wallets.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Hier finden Sie beispielsweise Ihren erweiterten öffentlichen Schlüssel und dessen *Deskriptor*, nützlich, wenn Sie planen, ein Nur-Lese-Wallet aus diesem Wallet einzurichten.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

Sie können auch den PIN-Code Ihres Wallets ändern und die biometrische Anmeldung aktivieren.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Nutzung von Blockstream Green

Jetzt, da Ihr Bitcoin-Wallet eingerichtet ist, sind Sie bereit, Ihre ersten Sats zu erhalten! Klicken Sie dazu einfach auf den Button "*Empfangen*".

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green zeigt dann die erste leere Empfangsadresse Ihres Wallets an. Sie können entweder den zugehörigen QR-Code scannen oder die Adresse direkt kopieren, um Bitcoins darauf zu senden. Diese Art von Adresse gibt den zu sendenden Betrag nicht an. Sie können jedoch eine Adresse generieren, die einen bestimmten Betrag anfordert, indem Sie auf die drei kleinen Punkte oben rechts klicken, dann auf "*Betrag anfordern*" und den gewünschten Betrag eingeben.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Wenn die Transaktion im Netzwerk übertragen wird, erscheint sie in Ihrem Wallet.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Warten Sie, bis Sie genügend Bestätigungen erhalten haben, um die Transaktion als endgültig zu betrachten.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

Mit Bitcoins in Ihrem Wallet können Sie diese nun auch senden. Klicken Sie auf "*Senden*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

Geben Sie auf der folgenden Seite die Adresse des Empfängers ein. Sie können sie manuell eingeben oder einen QR-Code scannen.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Wählen Sie den Zahlungsbetrag.
![GREEN 2FA MULTISIG](assets/fr/44.webp)Am unteren Bildschirmrand können Sie die Gebührenrate für diese Transaktion auswählen. Sie haben die Möglichkeit, den Empfehlungen der Anwendung zu folgen oder Ihre Gebühren individuell anzupassen. Je höher die Gebühren im Vergleich zu anderen ausstehenden Transaktionen sind, desto schneller wird Ihre Transaktion bearbeitet. Um den Gebührenmarkt zu verstehen, können Sie im Abschnitt "*Transaktionsgebühren*" auf [Mempool.space](https://mempool.space/) vorbeischauen.
![GREEN 2FA MULTISIG](assets/fr/45.webp)

Klicken Sie auf "*Weiter*", um einen Zusammenfassungsbildschirm Ihrer Transaktion zu erreichen. Überprüfen Sie, ob die Adresse, der Betrag und die Gebühren korrekt sind.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Wenn alles für Sie gut aussieht, schieben Sie den grünen Button am unteren Bildschirmrand nach rechts, um die Transaktion zu signieren und im Bitcoin-Netzwerk zu verbreiten.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

Dies ist der Moment, in dem Sie Ihren Authentifizierungscode eingeben müssen, um den zweiten Schlüssel des Multisig, der von Blockstream gehalten wird, freizuschalten. Geben Sie den 6-stelligen Code ein, der in Ihrer Authentifizierungs-App angezeigt wird.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Ihre Transaktion wird nun auf dem Dashboard Ihrer Bitcoin-Wallet als ausstehend angezeigt.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

Und voilà, jetzt wissen Sie, wie Sie mithilfe der 2FA-Option von Blockstream Green ganz einfach ein 2/2-Multisig-Wallet einrichten können!

Wenn Ihnen dieses Tutorial geholfen hat, würde ich mich freuen, wenn Sie unten einen grünen Daumen hinterlassen könnten. Fühlen Sie sich frei, diesen Artikel in Ihren sozialen Netzwerken zu teilen. Vielen Dank!

Ich empfehle auch, dieses weitere vollständige Tutorial zur Einrichtung eines Liquid-Wallets mit der Blockstream Green Mobile-App zu überprüfen:

https://planb.network/tutorials/wallet/blockstream-green-liquid