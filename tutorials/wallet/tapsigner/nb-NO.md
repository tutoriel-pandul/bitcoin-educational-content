---
name: Tapsigner
description: Oppsett og bruk av en Tapsigner med Nunchuk
---
![cover](assets/cover.webp)

En maskinvarelommebok er en elektronisk enhet dedikert til håndtering og sikkerhet for private nøkler i en Bitcoin-lommebok. I motsetning til programvarelommebøker (eller varme lommebøker) installert på generelle maskiner ofte koblet til internett, tillater maskinvarelommebøker fysisk isolasjon av private nøkler, noe som reduserer risikoen for hacking og tyveri.

Hovedmålet med en maskinvarelommebok er å minimere enhetens funksjonaliteter for å redusere dens angrepsflate. En mindre angrepsflate betyr også færre potensielle angrepsvektorer, dvs. færre svake punkter i systemet som angripere kunne utnytte for å få tilgang til bitcoinene.

Det anbefales å bruke en maskinvarelommebok for å sikre dine bitcoins, spesielt hvis du holder betydelige mengder, enten i absolutt verdi eller som en andel av dine totale eiendeler.

Maskinvarelommebøker brukes i kombinasjon med en lommebokforvaltningsprogramvare på en datamaskin eller smarttelefon. Denne programvaren håndterer opprettelsen av transaksjoner, men den kryptografiske signaturen som er nødvendig for å validere disse transaksjonene, gjøres utelukkende innenfor maskinvarelommeboken. Dette betyr at de private nøklene aldri blir eksponert for et potensielt sårbart miljø.

Maskinvarelommebøker tilbyr dobbel beskyttelse for brukeren: på den ene siden sikrer de dine bitcoins mot fjernangrep ved å holde de private nøklene frakoblet, og på den andre siden tilbyr de generelt bedre fysisk motstand mot forsøk på å ekstrahere nøklene. Og det er nettopp på disse 2 sikkerhetskriteriene man kan bedømme og rangere de forskjellige modellene som er tilgjengelige på markedet.

I denne veiledningen foreslår jeg å oppdage en av disse løsningene: Tapsigner av Coinkite.

## Introduksjon til Tapsigner

Tapsigner er en maskinvarelommebok designet i form av et NFC-kort av selskapet Coinkite, også kjent for å produsere Coldcards.

![TAPSIGNER NUNCHUK](assets/notext/01.webp)

Tapsigner tillater lagring av et par bestående av en hovedprivat nøkkel og en kjedekode i samsvar med BIP32, for å utlede et tre av kryptografiske nøkler. Disse nøklene kan brukes til å signere transaksjoner ved å plassere Tapsigneren mot en telefon eller en NFC-kortleser.
Dette NFC-kortet selges for $19.99, som er veldig rimelig sammenlignet med andre maskinvarelommebøker tilgjengelig på markedet. Imidlertid, på grunn av formatet, tilbyr Tapsigner ikke like mange alternativer som andre enheter. Det er åpenbart ingen batteri, ingen kamera, eller mikro SD-kortleser, ettersom det er et kort. Etter min mening er dens største ulempe mangelen på en skjerm på maskinvarelommeboken, noe som gjør den mer sårbar for visse typer fjernangrep. Dette tvinger brukeren til å signere blindt og stole på det de ser på dataskjermen sin.

Til tross for sine begrensninger, kan Tapsigner være interessant på grunn av sin reduserte pris. Denne lommeboken kan spesielt brukes til å forbedre sikkerheten til en utgiftslommebok i tillegg til en sparelommebok beskyttet av en maskinvarelommebok utstyrt med en skjerm. Den representerer også en god løsning for de som holder små mengder bitcoins og ikke ønsker å investere hundre euro i en mer sofistikert enhet. Videre kan bruk av Tapsigner i multisig-konfigurasjoner, eller potensielt i lommeboksystemer med tidsbegrensning i fremtiden, tilby interessante fordeler.

## Hvordan kjøpe en Tapsigner?

Tapsigner er tilgjengelig for kjøp [på den offisielle Coinkite-nettsiden](https://store.coinkite.com/store/category/tapsigner). For å kjøpe den i en fysisk butikk, kan du også finne [listen over sertifiserte forhandlere](https://coinkite.com/resellers) på nettstedet.
Du trenger også en telefon som er kompatibel med NFC-kommunikasjon, eller en USB-enhet for å lese NFC-kort på standardfrekvensen på 13,56 MHz.
## Hvordan initialisere en Tapsigner med Nunchuk?

Når du har mottatt din Tapsigner, er det første steget å undersøke emballasjen for å sikre at den ikke har blitt åpnet. Hvis pakken er skadet, kan det indikere at kortet har blitt kompromittert og kanskje ikke er autentisk. CoinKite vil levere din Tapsigner med et etui som blokkerer radiobølger. Sørg for at det er til stede i pakken din.

![TAPSIGNER NUNCHUK](assets/notext/02.webp)

For å administrere lommeboken, vil vi bruke **Nunchuk Wallet** mobilappen. Sørg for at smarttelefonen din er NFC-kompatibel, deretter last ned Nunchuk fra [Google Play Store](https://play.google.com/store/apps/details?id=io.nunchuk.android), [App Store](https://apps.apple.com/us/app/nunchuk-bitcoin-wallet/id1563190073) eller direkte via dens [`.apk` fil](https://github.com/nunchuk-io/nunchuk-android/releases).

![TAPSIGNER NUNCHUK](assets/notext/03.webp)
Hvis du bruker Nunchuk for første gang, vil appen be deg om å opprette en konto. For formålet med denne veiledningen, er det ikke nødvendig å opprette en. Så, velg "*Fortsett som gjest*" for å fortsette uten en konto.
![TAPSIGNER NUNCHUK](assets/notext/04.webp)

Deretter klikker du på "*Uassistert lommebok*".

![TAPSIGNER NUNCHUK](assets/notext/05.webp)

Neste, klikk på "*Jeg vil utforske på egen hånd*" knappen.

![TAPSIGNER NUNCHUK](assets/notext/06.webp)

Når du er i Nunchuk, klikk på "*+*" knappen ved siden av "*Nøkler*" fanen.

![TAPSIGNER NUNCHUK](assets/notext/07.webp)

Velg "*Legg til NFC-nøkkel*".

![TAPSIGNER NUNCHUK](assets/notext/08.webp)

Deretter klikker du på "*Legg til TAPSIGNER*".

![TAPSIGNER NUNCHUK](assets/notext/09.webp)

Klikk på "*Fortsett*" og deretter plasser din Tapsigner NFC-kort mot smarttelefonen din.

![TAPSIGNER NUNCHUK](assets/notext/10.webp)

Hvis din Tapsigner er ny, vil Nunchuk tilby å initialisere den. Klikk på "*Ja*".

![TAPSIGNER NUNCHUK](assets/notext/11.webp)

Du må nå velge hvordan du genererer din masterkjedekode.

Tapsigner bruker BIP32-standarden. Dette betyr at derivasjonen av dine kryptografiske nøkler som sikrer dine bitcoins ikke er avhengig av en mnemonisk frase som BIP39-lommebøker, men direkte på master privatnøkkelen og masterkjedekoden. Disse 2 elementene blir ført gjennom HMAC-funksjonen for å deterministisk og hierarkisk derivere resten av lommeboken din.

Master privatnøkkelen genereres direkte av TRNG (*True Random Number Generator*) integrert i din Tapsigner. Masterkjedekoden, på den annen side, må leveres utenfra. På dette steget har du et valg: la Nunchuk generere den automatisk ved å klikke på "*Automatisk*", eller generere den selv ved å velge "*Avansert*" og angi den i det angitte feltet.

![TAPSIGNER NUNCHUK](assets/notext/12.webp)
Neste steg er å velge en PIN-kode. I området for "*Start-PIN*" skriver du inn PIN-koden som står på baksiden av din Tapsigner.
![TAPSIGNER NUNCHUK](assets/notext/13.webp)

Velg en PIN-kode for å sikre fysisk tilgang til din Tapsigner. Denne PIN-koden spiller ingen rolle i prosessen med å gjenopprette lommeboken. Dens eneste funksjon er å låse opp din Tapsigner for å signere transaksjoner. Sørg for å lagre denne PIN-koden for å unngå å glemme den. Klikk på "*Fortsett*" for å gå videre.

![TAPSIGNER NUNCHUK](assets/notext/14.webp)
Plasser nå ditt Tapsigner-kort på baksiden av telefonen din for å initialisere det.
![TAPSIGNER NUNCHUK](assets/notext/15.webp)

Nunchuk vil deretter generere gjenopprettingsfilen for lommeboken din, som lar deg få tilgang til dine bitcoins igjen i tilfelle du mister ditt NFC-kort. Denne filen er kryptert med sikkerhetskoden skrevet på baksiden av din Tapsigner. For å gjenopprette dine bitcoins, vil du absolutt trenge denne filen samt koden for å dekryptere den. Det er derfor viktig å lage en papirkopi av denne koden, for hvis du mister ditt NFC-kort, vil også tilgangen til denne koden gå tapt, siden den for øyeblikket kun er skrevet på kortet. Sørg også for å lage flere sikkerhetskopier av din krypterte gjenopprettingsfil.

![TAPSIGNER NUNCHUK](assets/notext/16.webp)

Velg et navn for lommeboken din.

![TAPSIGNER NUNCHUK](assets/notext/17.webp)

Grunnlaget for lommeboken din er nå satt opp. For å verifisere autentisiteten til din Tapsigner, kan du når som helst klikke på knappen "*Kjør helsesjekk*".

![TAPSIGNER NUNCHUK](assets/notext/18.webp)

Skriv inn din PIN.

![TAPSIGNER NUNCHUK](assets/notext/19.webp)

Plasser deretter kortet ditt på baksiden av telefonen.

![TAPSIGNER NUNCHUK](assets/notext/20.webp)

## Hvordan opprette en lommebok på en Tapsigner?

Tilbake på Nunchuk-hjemmesiden kan du se at din Tapsigner er registrert i de tilgjengelige signeringsenhetene.

![TAPSIGNER NUNCHUK](assets/notext/21.webp)

Du må nå generere nøklene for din Bitcoin-lommebok. For å gjøre dette, klikk på "*+*" knappen til høyre for fanen "*Lommebøker*".

![TAPSIGNER NUNCHUK](assets/notext/22.webp)

Klikk på "*Opprett ny lommebok*".

![TAPSIGNER NUNCHUK](assets/notext/23.webp)

Velg deretter alternativet "*Opprett en ny lommebok ved hjelp av eksisterende nøkler*".

![TAPSIGNER NUNCHUK](assets/notext/24.webp)

Velg et navn for lommeboken din og klikk deretter på "*Fortsett*".

![TAPSIGNER NUNCHUK](assets/notext/25.webp)

Velg din Tapsigner som signeringsenhet for dette nye nøkkelsettet, og klikk deretter på "*Fortsett*".

![TAPSIGNER NUNCHUK](assets/notext/26.webp)

Hvis alt er til din tilfredshet, bekreft opprettelsen.

![TAPSIGNER NUNCHUK](assets/notext/27.webp)
Du kan deretter lagre konfigurasjonsfilen til lommeboken din. Denne filen inneholder utelukkende dine offentlige nøkler, noe som betyr at selv om noen får tilgang til den, kan de ikke stjele dine bitcoins. Imidlertid kan de følge alle transaksjonene dine. Derfor utgjør denne filen kun en risiko for ditt personvern. I noen tilfeller kan det være essensielt for å gjenopprette lommeboken din. ![TAPSIGNER NUNCHUK](assets/notext/28.webp)

Og der har du det, lommeboken din er vellykket opprettet!

![TAPSIGNER NUNCHUK](assets/notext/29.webp)

Når du ikke bruker din Tapsigner, husk å oppbevare den i etuiet som følger med fra Coinkite, som blokkerer radiobølger for å beskytte mot uautoriserte avlesninger.

## Hvordan motta bitcoins på Tapsigner?

For å motta bitcoins, klikk på lommeboken din.

![TAPSIGNER NUNCHUK](assets/notext/30.webp)

Bruk deretter den genererte adressen for å motta bitcoins. Hvis du tidligere har mottatt bitcoins på denne lommeboken, må du klikke på "*Motta*" knappen for å generere en ny tom mottaksadresse.

![TAPSIGNER NUNCHUK](assets/notext/31.webp)

Når avsenderens transaksjon er kringkastet, vil du se den dukke opp på lommeboken din.

![TAPSIGNER NUNCHUK](assets/notext/32.webp)

Klikk på "*Vis mynter*".

![TAPSIGNER NUNCHUK](assets/notext/33.webp)

Velg din nye UTXO.

![TAPSIGNER NUNCHUK](assets/notext/34.webp)

Klikk på "*+*" ved siden av "*Tags*" for å legge til en etikett på din UTXO. Dette er en god praksis, da det hjelper deg å huske opprinnelsen til myntene dine og optimalisere ditt personvern for fremtidige utgifter.

![TAPSIGNER NUNCHUK](assets/notext/35.webp)

Velg en eksisterende etikett eller opprett en ny, og klikk deretter på "*Lagre*". Du har også muligheten til å opprette "*samlinger*" for å organisere myntene dine på en mer strukturert måte.

![TAPSIGNER NUNCHUK](assets/notext/36.webp)

## Hvordan sende bitcoins med Tapsigner?

Nå som du har bitcoins i lommeboken din, kan du også sende dem. For å gjøre dette, klikk på lommeboken du foretrekker.

![TAPSIGNER NUNCHUK](assets/notext/37.webp)

Klikk på "*Send*" knappen.

![TAPSIGNER NUNCHUK](assets/notext/38.webp)

Velg beløpet du vil sende, og klikk deretter på "*Fortsett*".

![TAPSIGNER NUNCHUK](assets/notext/39.webp)

Legg til en "*notat*" til din fremtidige transaksjon for å huske formålet med den.

![TAPSIGNER NUNCHUK](assets/notext/40.webp)
Deretter, manuelt skriv inn mottakerens adresse i det angitte feltet.
![TAPSIGNER NUNCHUK](assets/notext/41.webp)

Du kan også skanne en QR-kode kodet adresse ved å klikke på ikonet som ligger øverst til høyre på skjermen.

![TAPSIGNER NUNCHUK](assets/notext/42.webp)

Klikk på "*Opprett Transaksjon*" knappen.

![TAPSIGNER NUNCHUK](assets/notext/43.webp)

Verifiser detaljene i transaksjonen din, og klikk deretter på "*Signer*" knappen ved siden av din Tapsigner.

![TAPSIGNER NUNCHUK](assets/notext/44.webp)

Skriv inn din PIN for å låse den opp.

![TAPSIGNER NUNCHUK](assets/notext/45.webp)

Plasser deretter Tapsigner på baksiden av smarttelefonen din.
![TAPSIGNER NUNCHUK](assets/notext/46.webp)
Transaksjonen din er nå signert. Sjekk en siste gang at alt er korrekt, deretter klikk på "*Broadcast Transaction*" for å kringkaste den på Bitcoin-nettverket.

![TAPSIGNER NUNCHUK](assets/notext/47.webp)

Transaksjonen din venter nå på bekreftelse.

![TAPSIGNER NUNCHUK](assets/notext/48.webp)

## Hvordan gjenopprette lommeboken i tilfelle tap av Tapsigner?

Hvis du har mistet din Tapsigner, kan du gjenopprette lommeboken din ved å bruke koden notert på baksiden av kortet. Det er derfor viktig å lagre denne koden separat fra Tapsigner, fordi hvis kortet går tapt, vil også tilgangen til denne koden gå tapt. Du vil også trenge den krypterte sikkerhetskopi av lommeboken.

For gjenoppretting vil vi bruke Nunchuk-appen, men husk at dette betyr å midlertidig sikre midlene dine i en hot wallet. Hvis din Tapsigner sikret betydelige beløp, vurder å følge samme gjenopprettingsprosess med en ny Coldcard i stedet.

Åpne Nunchuk-appen og klikk på "*+*" knappen ved siden av "*Keys*" fanen.

![TAPSIGNER NUNCHUK](assets/notext/49.webp)

Velg "*Add NFC key*".

![TAPSIGNER NUNCHUK](assets/notext/50.webp)

Velg alternativet "*Recover TAPSIGNER key from backup*".

![TAPSIGNER NUNCHUK](assets/notext/51.webp)

Du blir deretter omdirigert til enhetens filutforsker. Finn og velg den krypterte sikkerhetskopi-filen av lommeboken din. Normalt starter navnet på denne filen med `backup...`.

![TAPSIGNER NUNCHUK](assets/notext/52.webp)

Skriv inn passordet som dekrypterer sikkerhetskopi-filen. Dette passordet tilsvarer det som opprinnelig ble notert på baksiden av din Tapsigner.

![TAPSIGNER NUNCHUK](assets/notext/53.webp)
Deretter velger du et navn for din gjenopprettede lommebok.
![TAPSIGNER NUNCHUK](assets/notext/54.webp)

Du har nå gjenvunnet tilgangen til dine bitcoins. Lommeboken din håndteres nå som en hot wallet synlig i "*Keys*" fanen i Nunchuk-appen. Neste steg er å opprette et nytt sett med kryptografiske nøkler i "*Wallets*" seksjonen ved å assosiere denne nøkkelen med den. For å gjøre dette, kan du følge stegene på nytt i "*How to create a wallet on a Tapsigner?*" delen av denne opplæringen.

![TAPSIGNER NUNCHUK](assets/notext/55.webp)

Hvis du har mistet din Tapsigner, anbefaler jeg sterkt at du umiddelbart overfører dine bitcoins til en annen lommebok du eier, ideelt beskyttet av en hardware wallet. Faktisk kan Tapsigneren du mistet potensielt være i feil hender. Det er derfor viktig å tømme lommeboken du nettopp har gjenopprettet og å slutte å bruke den.

Gratulerer, du er nå oppdatert på hvordan du bruker Tapsigner! Hvis du fant denne opplæringen nyttig, ville jeg sette pris på om du kunne legge igjen en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!