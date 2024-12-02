---
name: Aqua
description: Bitcoin, Lightning und Liquid in einer einzigen Wallet
---
![cover](assets/cover.webp)

Aqua ist eine mobile Anwendung, die die einfache Erstellung einer Hot Wallet für Bitcoin und Liquid ermöglicht und auch die Möglichkeit bietet, Lightning ohne die Komplexität der Verwaltung eines Knotens zu nutzen, dank integrierter Swaps. Es unterstützt auch das Management von USDT-Stablecoins über verschiedene Netzwerke hinweg.

Entwickelt von der Firma JAN3 unter der Leitung von Samson Mow, wurde die Aqua-Anwendung zunächst speziell für die Bedürfnisse von Nutzern in Lateinamerika konzipiert, obwohl sie für jeden Nutzer weltweit geeignet ist. Sie ist besonders interessant für Anfänger und diejenigen, die Bitcoin täglich für ihre Zahlungen verwenden.

In diesem Tutorial werden wir erkunden, wie man die vielen Funktionen von Aqua nutzen kann. Aber bevor wir das tun, nehmen wir uns einen Moment Zeit, um zu verstehen, was eine Sidechain bei Bitcoin ist und wie Liquid funktioniert, was es uns ermöglichen wird, das Interesse an Aqua vollständig zu erfassen.

![AQUA](assets/fr/01.webp)

## Was ist eine Sidechain?

Das Bitcoin-Protokoll hat absichtliche technische Einschränkungen, die dazu beitragen, die Dezentralisierung des Netzwerks zu erhalten und eine Verteilung der Sicherheit unter allen Nutzern zu gewährleisten. Diese Grenzen können jedoch manchmal Nutzer frustrieren, insbesondere während Staus, die durch ein hohes Volumen gleichzeitiger Transaktionen verursacht werden. Die Debatte über die Skalierbarkeit von Bitcoin hat die Gemeinschaft lange gespalten, insbesondere während des Blocksize-Krieges. Seit dieser Episode wird innerhalb der Bitcoin-Gemeinschaft weithin anerkannt, dass die Skalierbarkeit durch Off-Chain-Lösungen auf Second-Layer-Systemen sichergestellt werden muss. Zu diesen Lösungen gehören Sidechains, die im Vergleich zu anderen Systemen wie dem Lightning Network noch relativ unbekannt und wenig genutzt sind.

Eine Sidechain ist eine unabhängige Blockchain, die parallel zur Haupt-Bitcoin-Blockchain betrieben wird. Sie verwendet Bitcoin als Recheneinheit durch einen Mechanismus, der als "*Two-Way Peg*" bekannt ist. Dieses System ermöglicht es, Bitcoins auf der Hauptkette zu sperren, um ihren Wert auf der Sidechain zu replizieren, wo sie als Token zirkulieren, die durch die ursprünglichen Bitcoins gedeckt sind. Diese Token halten normalerweise eine Wertparität mit den gesperrten Bitcoins auf der Hauptkette, und der Prozess kann umgekehrt werden, um die Mittel auf Bitcoin zurückzuholen.
Das Ziel von Sidechains ist es, zusätzliche Funktionalitäten oder technische Verbesserungen zu bieten, wie schnellere Transaktionen, reduzierte Gebühren oder Unterstützung für Smart Contracts. Diese Innovationen können nicht immer direkt auf der Bitcoin-Blockchain implementiert werden, ohne deren Dezentralisierung oder Sicherheit zu gefährden. Sidechains ermöglichen es daher, neue Lösungen zu testen und zu erkunden, während die Integrität von Bitcoin erhalten bleibt. Diese Protokolle erfordern jedoch oft Kompromisse, insbesondere in Bezug auf Dezentralisierung und Sicherheit, abhängig vom gewählten Governance-Modell und Konsensmechanismus.
## Was ist Liquid?

Liquid ist eine föderierte Sidechain, die auf Bitcoin aufbaut, entwickelt von Blockstream, mit dem Ziel, die Geschwindigkeit, Privatsphäre und Funktionalitäten von Transaktionen zu verbessern. Es verwendet einen bilateralen Verankerungsmechanismus, der auf einer Föderation basiert, um Bitcoins auf der Hauptkette zu sperren und im Gegenzug Liquid-Bitcoins (L-BTC), Token, die auf Liquid zirkulieren und dennoch durch die ursprünglichen Bitcoins gedeckt sind, zu erstellen.

![AQUA](assets/fr/02.webp)

Das Liquid-Netzwerk basiert auf einer Föderation von Teilnehmern, bestehend aus anerkannten Entitäten aus dem Bitcoin-Ökosystem, die die Blöcke validieren und die bilaterale Verankerung verwalten. Neben L-BTC ermöglicht Liquid auch die Ausgabe anderer digitaler Vermögenswerte, wie des Stablecoin USDT oder anderer Kryptowährungen.

![AQUA](assets/fr/03.webp)

## Installation der Aqua-App

Der erste Schritt ist natürlich, die Aqua-App herunterzuladen. Gehen Sie zu Ihrem App-Store:
- [Für Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Für Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
Für Android-Nutzer besteht auch die Möglichkeit, die App über die `.apk`-Datei [auf ihrem GitHub](https://github.com/AquaWallet/aqua-wallet/releases) zu installieren.

Starten Sie die App und markieren Sie das Kästchen "*Ich habe die Allgemeinen Geschäftsbedingungen & Datenschutzbestimmungen gelesen und akzeptiert*".

## Erstellen Ihres Wallets auf Aqua

Klicken Sie auf den Button "*Wallet erstellen*".

Und voilà, Ihr Wallet ist bereits erstellt!

Aber bevor Sie weitermachen, da es sich um ein Self-Custody-Wallet handelt, ist es zwingend erforderlich, eine physische Sicherung Ihrer mnemonischen Phrase anzufertigen. **Diese mnemonische Phrase bietet vollständigen und uneingeschränkten Zugang zu all Ihren Bitcoins**. Jeder, der im Besitz dieser Phrase ist, kann Ihre Mittel stehlen, selbst ohne physischen Zugang zu Ihrem Telefon.
Sie ermöglicht es Ihnen, den Zugang zu Ihren Bitcoins im Falle eines Verlusts, Diebstahls oder einer Beschädigung Ihres Telefons wiederherzustellen. Es ist daher sehr wichtig, sie sorgfältig auf einem physischen Medium (nicht digital) zu sichern und an einem sicheren Ort aufzubewahren. Sie können sie auf ein Stück Papier schreiben oder, für mehr Sicherheit, falls dieses Wallet bedeutend ist, empfehle ich, sie in ein Edelstahlmedium zu gravieren, um gegen Risiken von Feuern, Überschwemmungen oder Einstürzen zu schützen (für ein Hot Wallet, das dazu bestimmt ist, eine kleine Menge Bitcoins zu sichern, ist eine einfache Papierkopie wahrscheinlich ausreichend).
Um dies zu tun, klicken Sie auf das Einstellungsmenü.

Klicken Sie dann auf "*Seed Phrase anzeigen*". Machen Sie eine physische Sicherung dieser 12-Wort-Phrase.

In diesem Einstellungsmenü können Sie auch die Sprache der Anwendung sowie die verwendete Fiat-Währung ändern.

Bevor Sie Ihre ersten Bitcoins in Ihrem Wallet erhalten, **rate ich Ihnen dringend, einen Dry-Run-Recovery-Test durchzuführen**. Notieren Sie eine Referenzinformation, wie Ihren xpub oder die erste Empfangsadresse, dann löschen Sie Ihr Wallet in der Aqua-App, während es noch leer ist. Versuchen Sie anschließend, Ihr Wallet auf Aqua mit Ihren Papierkopien wiederherzustellen. Überprüfen Sie, ob die nach der Wiederherstellung generierte Zeugeninformation mit der ursprünglich notierten übereinstimmt. Wenn dies der Fall ist, können Sie sicher sein, dass Ihre Papierkopien zuverlässig sind. Um mehr darüber zu erfahren, wie ein Wiederherstellungstest durchgeführt wird, rate ich Ihnen, dieses andere Tutorial zu konsultieren:

https://planb.network/tutorials/wallet/recovery-test

## Bitcoins auf Aqua empfangen

Jetzt, da Ihr Wallet eingerichtet ist, sind Sie bereit, Ihre ersten Sats zu empfangen! Klicken Sie einfach auf den Button "*Empfangen*" im Menü "*Wallet*".

Sie können wählen, ob Sie Bitcoins onchain, auf Liquid oder über Lightning erhalten möchten.

Für Onchain-Transaktionen generiert Aqua eine spezifische Empfangsadresse, auf der Sie Ihre Sats erhalten können.

Ebenso wird Ihnen Aqua bei der Wahl von Liquid eine Liquid-Adresse zur Verfügung stellen.

Wenn Sie es vorziehen, Mittel über Lightning zu erhalten, müssen Sie zuerst den gewünschten Betrag angeben.

Klicken Sie dann auf "*Rechnung erstellen*".
Aqua wird eine Rechnung erstellen, um Gelder von einem Lightning-Wallet zu erhalten. Es ist wichtig zu beachten, dass im Gegensatz zu Onchain- und Liquid-Optionen, Gelder, die über Lightning empfangen werden, automatisch mit dem Boltz-Tool in L-BTC auf Liquid umgewandelt werden, da Aqua kein Lightning-Knoten ist. Dieser Prozess ermöglicht es Ihnen, Gelder über Lightning zu empfangen und zu senden, ohne jemals Ihre Bitcoins auf Lightning zu halten. ![AQUA](assets/fr/18.webp)

Persönlich werde ich damit beginnen, Bitcoins über Lightning an Aqua zu senden. Sobald die Transaktion mit der bereitgestellten Rechnung abgeschlossen ist, wird eine Bestätigung erhalten.

![AQUA](assets/fr/19.webp)

Um den Fortschritt des Tauschs zu verfolgen, kehren Sie zur Startseite Ihres Wallets zurück und klicken auf das Konto "*L2 Bitcoin*", das Lightning (über Swap) und Liquid-Transaktionen auflistet.

![AQUA](assets/fr/20.webp)

Hier können Sie Ihre Transaktion sowie Ihr Guthaben in L-BTC einsehen.

![AQUA](assets/fr/21.webp)

## Bitcoins mit Aqua tauschen

Jetzt, da Sie Vermögenswerte in Ihrem Aqua-Wallet haben, haben Sie die Möglichkeit, diese direkt über die App zu tauschen, entweder um sie auf die Haupt-Bitcoin-Blockchain oder zu Liquid zu übertragen. Sie können Ihre Bitcoins auch in die Stablecoin USDT (oder andere) umwandeln. Um dies zu tun, greifen Sie auf das Menü "*Marketplace*" zu.

![AQUA](assets/fr/22.webp)

Klicken Sie auf "*Swaps*".

![AQUA](assets/fr/23.webp)

Im Feld "*Transfer from*" wählen Sie das Asset aus, das Sie tauschen möchten. Derzeit habe ich nur L-BTC, also wähle ich das aus.

![AQUA](assets/fr/24.webp)

Im Feld "*Transfer to*" wählen Sie das Ziel-Asset Ihres Tauschs. Ich habe mich für USDT im Liquid-Netzwerk entschieden.

![AQUA](assets/fr/25.webp)

Geben Sie den Betrag ein, den Sie umwandeln möchten.

![AQUA](assets/fr/26.webp)

Bestätigen Sie durch Klicken auf "*Continue*".

![AQUA](assets/fr/27.webp)

Stellen Sie sicher, dass die Tauscheinstellungen Ihren Wünschen entsprechen, und bestätigen Sie dann, indem Sie den "*Swap*" Button am unteren Bildschirmrand verschieben.

![AQUA](assets/fr/28.webp)

Ihr Tausch ist jetzt bestätigt.

![AQUA](assets/fr/29.webp)

Wenn wir zu unserem Wallet zurückkehren, können wir sehen, dass wir jetzt USDT auf Liquid haben.

![AQUA](assets/fr/30.webp)

## Bitcoins mit Aqua senden

Jetzt, da Sie Bitcoins in Ihrem Aqua-Wallet haben, haben Sie die Möglichkeit, diese zu senden. Klicken Sie auf den Button "*Send*".

![AQUA](assets/fr/31.webp)

Wählen Sie das Asset aus, das Sie senden möchten, oder wählen Sie das Netzwerk für die Durchführung der Transaktion. Ich werde Bitcoins über Lightning senden.

![AQUA](assets/fr/32.webp)
Geben Sie als Nächstes die erforderlichen Informationen für das Senden der Zahlung ein: Für Bitcoin Onchain oder Liquid müssen Sie eine Empfangsadresse eingeben; für Lightning ist eine Rechnung erforderlich. Sie können diese Informationen direkt in das vorgesehene Feld einfügen oder das QR-Code-Symbol verwenden, um Ihre Kamera zu öffnen und die Adresse oder Rechnung zu scannen. Klicken Sie dann auf "*Continue*".
![AQUA](assets/fr/33.webp)

Klicken Sie erneut auf "*Continue*", wenn alle Informationen korrekt erscheinen.

![AQUA](assets/fr/34.webp)
Aqua präsentiert Ihnen dann eine Zusammenfassung der Transaktion. Stellen Sie sicher, dass alle Informationen korrekt sind, insbesondere die Zieladresse, die Gebühren und der Betrag. Um die Transaktion zu bestätigen, schieben Sie den Button "*Slide to send*", der sich unten auf dem Bildschirm befindet.

![AQUA](assets/fr/35.webp)

Anschließend erhalten Sie eine Bestätigung der Sendung.

![AQUA](assets/fr/36.webp)

Und voilà, jetzt wissen Sie, wie Sie die Aqua-App verwenden können, um Gelder in Bitcoin, Lightning und Liquid zu empfangen und auszugeben, alles über eine einzige Schnittstelle.

Wenn Sie dieses Tutorial hilfreich fanden, würde ich mich freuen, wenn Sie unten einen Daumen hoch hinterlassen könnten. Fühlen Sie sich frei, diesen Artikel in Ihren sozialen Netzwerken zu teilen. Vielen Dank!

Ich empfehle Ihnen auch, dieses weitere vollständige Tutorial über die Blockstream Green Mobile-App anzusehen, die eine weitere interessante Lösung für die Einrichtung Ihrer Liquid-Wallet darstellt:

https://planb.network/tutorials/wallet/blockstream-green-liquid