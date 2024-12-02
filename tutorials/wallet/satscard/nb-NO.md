---
name: Satscard
description: Oppsett og bruk av en Satscard med Nunchuk
---
![cover](assets/cover.webp)

Bitcoin er et elektronisk kontantsystem som lar oss utføre transaksjoner peer-to-peer. Imidlertid, for å være overbevist om at en transaksjon er uforanderlig, er det nødvendig å vente på flere bekreftelser (vanligvis 6), for å unngå ethvert forsøk på dobbeltutgifter fra avsenderen. Denne valideringsforsinkelsen kan noen ganger være upraktisk, spesielt når umiddelbar endelighet lik fysisk kontanter er ønsket. I motsetning til kontanter, hvor besittelsen av en seddel overføres øyeblikkelig, involverer Bitcoin-transaksjoner en ventetid før de definitivt anses som irreversible.

Her kommer Satscard inn. Det tilbyr en metode for å muliggjøre fysisk og øyeblikkelig overføring av bitcoins, uten å måtte utføre en on-chain transaksjon. Satscard fungerer som et bærerkort som tillater sikker overføring av eierskap til bitcoin, og tilbyr dermed en opplevelse nærmere tradisjonelle kontanter. I denne veiledningen vil jeg introdusere deg for denne løsningen.

## Hva er en Satscard?

Satscard fra Coinkite er etterfølgeren til Opendime. Det er et NFC-kort som tillater fysisk overføring av bitcoins, likt en seddel eller mynt. I motsetning til en tradisjonell hardware-lommebok, er Satscard et bærerkort, noe som betyr at fysisk besittelse av kortet tilsvarer eierskap til bitcoins som er sikret med nøklene lagret på det. Prisen varierer mellom $6.99 og $17.99 avhengig av designet som er valgt.

![SATSCARD](assets/notext/01.webp)

Satscard-chipen er utstyrt med 10 spor, noe som gjør det mulig å lagre bitcoins opptil 10 ganger på 10 forskjellige adresser. Hvert spor fungerer uavhengig og bør teoretisk sett bare brukes én gang for å låse bitcoins i det. For å bruke bitcoins, bare bryt forseglingen på sporet med en kompatibel applikasjon, som Nunchuk, ved å angi den 6-sifrede verifiseringskoden notert på baksiden av Satscard.

Kortet sikrer at den private nøkkelen som sikrer bitcoins på blockchain ikke kan beholdes av den tidligere eieren når de fysisk skiller lag med kortet. Mottakeren kan også verifisere gyldigheten av et spor og mengden lagret i det på tidspunktet for utvekslingen.

Dette systemet er spesielt nyttig for kjøp av fysiske varer med bitcoins, eller for å gi bitcoins som en gave.

## Hvordan kjøpe en Satscard?

Satscard er tilgjengelig for kjøp [på den offisielle Coinkite-nettsiden](https://store.coinkite.com/store/category/satscard). For å kjøpe den i en fysisk butikk, kan du også finne [listen over sertifiserte forhandlere](https://coinkite.com/resellers) på nettstedet.
Du trenger også en telefon som er kompatibel med NFC-kommunikasjon, eller en USB-enhet for å lese NFC-kort på standardfrekvensen 13.56 MHz.
## Hvordan laste et spor på en Satscard?

Når du har mottatt din Satscard, er det første steget å sjekke emballasjen for å forsikre deg om at den ikke har blitt åpnet. Hvis pakken er skadet, kan det indikere at kortet har blitt kompromittert og kanskje ikke er autentisk.

For å administrere Satscard, vil vi bruke mobilapplikasjonen **Nunchuk Wallet**. Sørg for at smarttelefonen din er NFC-kompatibel, deretter last ned Nunchuk fra [Google Play Store](https://play.google.com/store/apps/details?id=io.nunchuk.android), [App Store](https://apps.apple.com/us/app/nunchuk-bitcoin-wallet/id1563190073), eller direkte via dens [`.apk` fil](https://github.com/nunchuk-io/nunchuk-android/releases).
I teorien kan du direkte sende bitcoins til adressen som er spesifisert på baksiden av Satskortet ditt uten å bruke Nunchuk. Imidlertid fraråder jeg å gjøre dette, da vi først vil verifisere at adressen til det første sporet faktisk er avledet fra en privat nøkkel lagret i Satskortet og at det ikke er en svindeladresse.

Hvis du bruker Nunchuk for første gang, vil appen tilby deg å opprette en konto. For formålet med denne opplæringen, er det ikke nødvendig å opprette en. Så, velg "*Fortsett som gjest*" for å fortsette uten en konto.

Deretter klikker du på "*Uassistert lommebok*".

Neste, klikk på "*Jeg vil utforske på egen hånd*" knappen.

Når du er på Nunchuk-hjemmeskjermen, klikk på "*NFC*" logoen øverst på skjermen.

Hold Satskortet ditt mot baksiden av telefonen din for å skanne det.

Nunchuk viser mottaksadressen som tilsvarer det første sporet på Satskortet ditt. Normalt bør denne adressen være identisk med den som manuelt er skrevet på baksiden av kortet ditt. Kopier denne adressen og bruk den til å overføre bitcoinsene du ønsker å låse med dette sporet.

## Hvordan sjekke bitcoins på et spor?

Når transaksjonen er bekreftet, kan du sjekke saldoen knyttet til et spor på Satskortet ditt ved å skanne det med Nunchuk. Dermed kan mottakeren av bitcoinsene umiddelbart verifisere, via sin Nunchuk-app, at kortet faktisk inneholder bitcoinsene som skyldes dem.

Hvis motparten ikke har Nunchuk-appen, kan de fortsatt verifisere gyldigheten av Satskortet. Aktiver bare NFC på smarttelefonen deres og plasser Satskortet på baksiden av enheten. Dette vil automatisk åpne Satskort-nettstedet i en nettleser, hvor man kan sjekke gyldigheten av kortet samt mengden bitcoins knyttet til det.

## Hvordan ta ut bitcoins fra et spor?

Nå som det første sporet på Satskortet har blitt lastet med en viss mengde bitcoins, kan du overlevere kortet til betalingsmottakeren.

Hvis du er mottakeren, må du installere Nunchuk. Når du er i appen, klikk på "*NFC*" logoen øverst på skjermen.

Plasser Satskortet ditt på baksiden av telefonen din.

Nunchuk vil avsløre mengden sikret på adressen.

For å bryte forseglingen på den private nøkkelen og flytte bitcoinsene til en adresse du eier, klikk på "*Bryt forseglingen og fei saldoen*" knappen.

"*Fei til en lommebok*" alternativet lar deg direkte sende bitcoinsene til en lommebok som allerede er til stede i Nunchuk-appen din. For å overføre midlene til en annen mottaksadresse, velg "*Ta ut til en adresse*".
![SATSCARD](assets/notext/16.webp)
Skriv inn mottaksadressen der du ønsker å sende bitcoinene sikret av Satskortet. Sørg for at den innskrevne adressen er korrekt (dette er den eneste gangen du kan verifisere den), og klikk deretter på "*Opprett transaksjon*" knappen.

![SATSCARD](assets/notext/17.webp)

Skriv inn PIN-koden til Satskortet ditt. Denne 6-sifrede koden er notert på baksiden av det fysiske kortet.

![SATSCARD](assets/notext/18.webp)

Hold Satskortet ditt på baksiden av smarttelefonen din mens du signerer transaksjonen med den private nøkkelen lagret på NFC-kortet.

![SATSCARD](assets/notext/19.webp)

Transaksjonen din er nå signert og kringkastet på Bitcoin-nettverket, noe som betyr at sporet brukt på Satskortet ditt nå er tomt.

![SATSCARD](assets/notext/20.webp)

## Hvordan gjenbruke Satskortet?

I motsetning til engangsløsninger som Opendime, er Satskortet utstyrt med en brikke som inneholder 10 uavhengige spor, noe som tillater opptil 10 operasjoner med et enkelt kort. Det første sporet, forhåndskonfigurert på fabrikken av Coinkite, tilsvarer mottaksadressen skrevet på baksiden av Satskortet ditt.

![SATSCARD](assets/notext/21.webp)
For å aktivere de andre 9 sporene, må du generere nøkkelparet og adressen via Nunchuk-appen. På hjemmesiden til appen, klikk på "*NFC*" logoen øverst på skjermen.
![SATSCARD](assets/notext/22.webp)

Plasser Satskortet ditt på baksiden av telefonen din.

![SATSCARD](assets/notext/23.webp)

Nunchuk indikerer at ingen spor er aktive på kortet, noe som er normalt siden det første allerede har blitt brukt og det andre ennå ikke har blitt generert. For å se de tidligere brukte sporene, klikk på "*Vis uforseglede spor*". Det frarådes sterkt å gjenbruke disse sporene, da dette ville føre til adressegjenbruk skadelig for din on-chain personvern. Derfor vil vi sette opp et nytt spor ved å klikke på "*Ja*" knappen.

![SATSCARD](assets/notext/24.webp)

Du må nå velge hvordan du genererer din masterkjedekode.

Sporene på Satskortet følger BIP32-standarden, noe som betyr at derivasjonen av de kryptografiske nøklene som sikrer bitcoinene ikke er avhengig av en mnemonisk frase som i BIP39-lommebøker, men direkte på en master privat nøkkel og en masterkjedekode. Disse to elementene brukes som input i HMAC-SHA512-funksjonen for å generere et barnenøkkelpar. Hvert spor har sin egen master nøkkel og sin egen masterkjedekode. Det er bare ett nivå av derivasjon for hvert spor.

Nøkkelparet for det første sporet er forhåndsgenerert av Coinkite. Dette er grunnen til at du har direkte tilgang til det via Nunchuk, og hvorfor mottaksadressen er skrevet på baksiden av NFC-kortet. For de andre sporene, derimot, er du ansvarlig for å generere nøklene.

Master privatnøkkelen for hvert spor genereres direkte av Satskortet, og masterkjedekodene må leveres utenfra. For kjedekoden til ditt nye spor, har du to alternativer: la Nunchuk generere den automatisk ved å velge "*Automatisk*", eller opprette den selv ved å velge "*Avansert*" og skrive den inn i det dedikerte området. For at kjedekoden skal være effektiv, må den være så tilfeldig som mulig.

![SATSCARD](assets/notext/25.webp)
Skriv inn den 6-sifrede PIN-koden som er notert på baksiden av Satskortet ditt.
![SATSCARD](assets/notext/26.webp)

Plasser Satskortet ditt på baksiden av telefonen din.

![SATSCARD](assets/notext/27.webp)

En ny plass er vellykket konfigurert. Du kan nå se mottaksadressen for å sette inn bitcoins. For å fortsette med å laste, følg instruksjonene i avsnittet "*Hvordan laste en plass på et Satskort?*" i denne veiledningen.
Du kan gjenta denne prosessen opptil 10 ganger på hvert Satskort.

Gratulerer, du er nå oppdatert på hvordan du bruker Satskortet! Hvis du fant denne veiledningen nyttig, ville jeg sette pris på om du kunne legge igjen en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!