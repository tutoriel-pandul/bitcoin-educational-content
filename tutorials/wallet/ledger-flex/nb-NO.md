---
name: Ledger Flex
description: Sette opp og bruke Ledger Flex
---

![cover](assets/cover.webp)

En maskinvarelommebok er en elektronisk enhet dedikert til å håndtere og sikre de private nøklene til en Bitcoin-lommebok. I motsetning til programvarelommebøker (eller varme lommebøker) installert på generelle maskiner ofte koblet til internett, tillater maskinvarelommebøker fysisk isolasjon av private nøkler, noe som reduserer risikoen for hacking og tyveri.

Hovedmålet med en maskinvarelommebok er å minimere enhetens funksjonaliteter for å redusere dens angrepsflate. Mindre angrepsflate betyr også færre potensielle angrepsvektorer, dvs. færre svake punkter i systemet som angripere kunne utnytte for å få tilgang til bitcoins.

Det anbefales å bruke en maskinvarelommebok for å sikre dine bitcoins, spesielt hvis du holder betydelige mengder, enten i absolutt verdi eller som en andel av dine totale eiendeler.

Maskinvarelommebøker brukes i kombinasjon med lommebokforvaltningsprogramvare på en datamaskin eller smarttelefon. Denne programvaren håndterer opprettelsen av transaksjoner, men den kryptografiske signaturen som er nødvendig for å validere disse transaksjonene, gjøres kun innenfor maskinvarelommeboken. Dette betyr at de private nøklene aldri blir eksponert for et potensielt sårbart miljø.

Maskinvarelommebøker tilbyr dobbel beskyttelse for brukeren: på den ene siden sikrer de dine bitcoins mot fjernangrep ved å holde de private nøklene frakoblet, og på den andre siden tilbyr de generelt bedre fysisk motstand mot forsøk på å ekstrahere nøklene. Og det er nettopp på disse 2 sikkerhetskriteriene man kan bedømme og rangere de forskjellige modellene som er tilgjengelige på markedet.

I denne opplæringen foreslår jeg å oppdage en av disse løsningene: **Ledger Flex**.

![LEDGER FLEX](assets/notext/01.webp)

## Introduksjon til Ledger Flex

Ledger Flex er en maskinvarelommebok produsert av det franske selskapet Ledger, markedsført til en pris av 249 €.

![LEDGER FLEX](assets/notext/02.webp)

Den har en stor E Ink-berøringsskjerm, en svart-hvitt skjermteknologi. Dette er den samme teknologien som finnes i elektroniske lesere. E Ink-skjermen tillater en klar og lesbar visning, selv i sterkt sollys, og forbruker svært lite energi, eller ingen i det hele tatt når skjermen er statisk. Den fungerer ved å bruke mikrokapsler som inneholder svarte og hvite pigmentpartikler. Når en elektrisk ladning påføres, beveger de svarte eller hvite partiklene seg til overflaten av skjermen, slik at tekst eller bilder kan dannes.
Ledger Flex er utstyrt med en CC EAL6+ sertifisert "sikker element"-brikke, som tilbyr deg avansert beskyttelse mot fysiske angrep på maskinvaren. Skjermen styres direkte av denne brikken. Et vanlig kritikkpunkt er at koden for denne brikken ikke er åpen kildekode, noe som krever et visst nivå av tillit til integriteten til denne komponenten. Imidlertid blir dette elementet revidert av uavhengige eksperter.

Når det gjelder bruk, tilbyr Ledger Flex flere tilkoblingsmuligheter: Bluetooth, USB-C og NFC. Den store skjermen gjør det enkelt å verifisere detaljene i transaksjonen din. Ledger skiller seg også ut fra konkurrentene med sin raske adopsjon av nye Bitcoin-funksjoner, som for eksempel Miniscript.

Etter å ha testet den, er jeg imponert over produktets kvalitet. Brukeropplevelsen er utmerket, og enheten er intuitiv. Det er en utmerket maskinvarelommebok. Imidlertid har den 2 store ulemper i min mening: manglende evne til å verifisere brikkekoden og, selvfølgelig, prisen, som er betydelig høyere enn konkurrentene. Til sammenligning selges den mest avanserte modellen fra Foundation til $199, Coinkites til $219.99, mens den nyeste Trezor, også utstyrt med en stor berøringsskjerm, tilbys til 169€.

## Hvordan kjøpe en Ledger Flex?

Ledger Flex er tilgjengelig for kjøp [på den offisielle nettsiden](https://shop.ledger.com/pages/ledger-flex). For å kjøpe den i en fysisk butikk, kan du også finne [listen over sertifiserte forhandlere](https://www.ledger.com/reseller) på Ledger sin nettside.

## Forutsetninger

Når du har mottatt din Ledger Flex, er det første steget å undersøke emballasjen for å forsikre deg om at den ikke har blitt åpnet.

![LEDGER FLEX](assets/notext/03.webp)

Ledgers emballasje skal inkludere 2 forseglingstape. Hvis disse tapene mangler eller er skadet, kan det indikere at maskinvarelommeboken har blitt kompromittert og kanskje ikke er autentisk.

![LEDGER FLEX](assets/notext/04.webp)

Når du åpner, bør du finne følgende gjenstander i esken:

- Ledger Flex;
- En USB-C-kabel;
- En brukermanual;
- Kort for å skrive ned din mnemonic frase.

![LEDGER FLEX](assets/notext/05.webp)

For denne veiledningen, vil du trenge 2 stykker programvare: Ledger Live for å initialisere Ledger Flex, og Sparrow Wallet for å håndtere din Bitcoin-lommebok. Last ned [Ledger Live](https://www.ledger.com/ledger-live) og [Sparrow Wallet](https://sparrowwallet.com/download/) fra deres offisielle nettsider.

![LEDGER FLEX](assets/notext/06.webp)
Vi vil snart tilby en veiledning om hvordan du kan verifisere autentisiteten og integriteten til programvaren du laster ned. Jeg anbefaler sterkt å gjøre det her for Ledger Live og Sparrow.

## Hvordan initialisere en Ledger Flex med Ledger Live?

Slå på din Ledger Flex ved å trykke på knappen på høyre side i noen sekunder.

![LEDGER FLEX](assets/notext/07.webp)

Bla gjennom de forskjellige introduksjonssidene.

![LEDGER FLEX](assets/notext/08.webp)

Velg alternativet "_Sett opp uten Ledger Live_", deretter klikk på "_Hopp over Ledger Live_" knappen.

![LEDGER FLEX](assets/notext/09.webp)

Du vil deretter bli bedt om å velge et navn for din Ledger. Klikk på "_Sett navn_", og deretter skriv inn navnet du velger.

![LEDGER FLEX](assets/notext/10.webp)

Velg PIN-koden for enheten din, som vil bli brukt til å låse opp din Ledger. Dette er derfor en beskyttelse mot uautorisert fysisk tilgang. Denne PIN-koden spiller ikke en rolle i utledningen av lommebokens kryptografiske nøkler. Så, selv uten tilgang til denne PIN-koden, vil å ha din 24-ords mnemonic frase tillate deg å gjenopprette tilgangen til dine bitcoins.

Det anbefales å velge en 8-sifret PIN-kode, så tilfeldig som mulig. Også, sørg for å lagre denne koden på et annet sted enn der din Ledger Flex er lagret (for eksempel, i en passordbehandler).

![LEDGER FLEX](assets/notext/11.webp)

Skriv inn din PIN en andre gang for å bekrefte den.

![LEDGER FLEX](assets/notext/12.webp)

Du vil deretter bli bedt om å velge mellom å gjenopprette en eksisterende lommebok eller å opprette en ny. I denne veiledningen dekker vi oppretting av en ny lommebok fra bunnen av, så velg alternativet "_Sett opp som en ny Ledger_" for å generere en ny mnemonic frase.

![LEDGER FLEX](assets/notext/13.webp)

Din Flex vil gi instruksjoner om hvordan du håndterer din gjenopprettingsfrase.
**Denne mnemonic-frasen gir full og ubegrenset tilgang til alle dine bitcoins**. Enhver som er i besittelse av denne frasen kan stjele midlene dine, selv uten fysisk tilgang til din Ledger. Den 24-ords frasen muliggjør gjenoppretting av tilgang til dine bitcoins i tilfelle tap, tyveri, eller skade på din Ledger Flex. Det er derfor svært viktig å nøye lagre og oppbevare den på et sikkert sted.
Du kan skrive den ned på papparket som følger med din Ledger, eller for økt sikkerhet, anbefaler jeg å gravere den på et medium av rustfritt stål for å beskytte mot risikoer som branner, flommer, eller kollapser.

Du kan bla gjennom disse instruksjonene og hoppe over sider ved å berøre skjermen.

![LEDGER FLEX](assets/notext/14.webp)
Ledger vil skape din mnemonic-frase ved hjelp av sin tilfeldige nummergenerator. Sørg for at du ikke blir observert under denne operasjonen. Skriv ned ordene som Ledger gir deg på det fysiske mediet du velger. Avhengig av din sikkerhetsstrategi, kan du vurdere å lage flere komplette fysiske kopier av frasen (men viktigst av alt, ikke del den opp). Det er viktig å holde ordene nummerert og i sekvensiell rekkefølge.
**_Åpenbart, du bør aldri dele disse ordene på internett, i motsetning til det jeg gjør i denne opplæringen. Denne eksempellommeboken vil kun bli brukt på Testnet og vil bli slettet ved slutten av opplæringen._**

![LEDGER FLEX](assets/notext/15.webp)

For å gå til neste gruppe ord, klikk på "_Neste_" knappen. Når alle ordene er notert, klikk på "_Ferdig_" knappen for å gå videre til neste steg.

![LEDGER FLEX](assets/notext/16.webp)

Klikk på "_Start bekreftelse_" knappen, deretter velg ordene fra din mnemonic-frase i deres rekkefølge for å bekrefte at du har notert dem riktig. Fortsett denne prosedyren til det 24. ordet.

![LEDGER FLEX](assets/notext/17.webp)

Hvis frasen du bekrefter matcher nøyaktig den som Flex ga deg i forrige steg, kan du fortsette. Hvis ikke, indikerer dette at din fysiske sikkerhetskopi av mnemonic-frasen er feil, og du trenger å starte prosessen på nytt.

![LEDGER FLEX](assets/notext/18.webp)

Og der har du det, din seed har blitt korrekt opprettet på din Ledger Flex. Før vi går videre til å opprette en ny Bitcoin-lommebok fra denne seeden, la oss utforske enhetsinnstillingene sammen.

## Hvordan endre innstillingene på din Ledger?

For å låse og låse opp din Ledger, trykk på sideknappen. Du vil da bli bedt om å angi PIN-koden du satte i forrige steg.

![LEDGER FLEX](assets/notext/19.webp)

For å få tilgang til innstillingene, klikk på tannhjulsymbolet nederst til venstre på enheten din.

![LEDGER FLEX](assets/notext/20.webp)

Menyen "_Name_" lar deg endre navnet på din Ledger.

![LEDGER FLEX](assets/notext/21.webp)

I "_About this Ledger_," vil du finne informasjon om din Flex.

![LEDGER FLEX](assets/notext/22.webp)

I menyen "_Lock screen_," har du muligheten til å endre bildet som vises på låseskjermen ved å velge "_Customize lock screen picture_". Takket være enhetens E Ink-skjermteknologi, er det mulig å holde skjermen konstant på uten å forbruke batteri. E Ink-skjermer bruker ikke energi for å opprettholde et statisk bilde. Imidlertid forbruker de energi under skjermendringer.
Undermenyen "_Auto-lock_" lar deg konfigurere og aktivere automatisk låsing av din Ledger etter en bestemt periode med inaktivitet.
![LEDGER FLEX](assets/notext/23.webp)
"_Sounds_" menyen lar deg slå lydene på din Flex av eller på. Og i "Language" menyen, kan du endre visningsspråket.
![LEDGER FLEX](assets/notext/24.webp)

Ved å klikke på høyre pil, kan du få tilgang til andre innstillinger. "_Change PIN_" lar deg endre din PIN-kode.

![LEDGER FLEX](assets/notext/25.webp)

"_Bluetooth_" og "_NFC_" menyene lar deg administrere disse kommunikasjonene.

![LEDGER FLEX](assets/notext/26.webp)

I "_Battery_" kan du spesielt sette en automatisk nedstengning av Ledger.

![LEDGER FLEX](assets/notext/27.webp)

"_Advanced_" seksjonen gir deg tilgang til mer sofistikerte sikkerhetsinnstillinger. Det anbefales å holde "_PIN shuffle_" alternativet aktivert for å forbedre sikkerheten. Det er også i denne menyen at du kan konfigurere en BIP39 passfrase.

![LEDGER FLEX](assets/notext/28.webp)

Passfrasen er et valgfritt passord som, kombinert med gjenopprettingsfrasen, gir et ekstra lag med sikkerhet for lommeboken din.

For øyeblikket er lommeboken din generert fra en mnemonisk frase bestående av 24 ord. Denne gjenopprettingsfrasen er veldig viktig, da den lar deg gjenopprette alle nøklene til lommeboken din i tilfelle tap. Imidlertid utgjør den et enkelt feilpunkt (SPOF). Hvis den blir kompromittert, er bitcoinene i fare. Dette er hvor passfrasen kommer inn. Det er et valgfritt passord, som du kan velge vilkårlig, som legges til den mnemoniske frasen for å styrke lommebokens sikkerhet.

Passfrasen bør ikke forveksles med PIN-koden. Den spiller en rolle i derivasjonen av dine kryptografiske nøkler. Den fungerer i tandem med den mnemoniske frasen, og endrer frøet som nøklene genereres fra. Så selv om noen får tak i din 24-ords frase, uten passfrasen, kan de ikke få tilgang til midlene dine. Å bruke en passfrase skaper i hovedsak en ny lommebok med distinkte nøkler. Å endre (selv litt) passfrasen vil generere en annen lommebok.

Passfrasen er et veldig kraftig verktøy for å forbedre sikkerheten til dine bitcoins. Det er imidlertid veldig viktig å forstå hvordan den fungerer før du implementerer den, for å unngå å miste tilgangen til lommeboken din. Jeg vil forklare hvordan du bruker passfrasen i en annen dedikert opplæring.

![LEDGER FLEX](assets/notext/29.webp)
Til slutt, den siste innstillingssiden lar deg tilbakestille din Ledger. Bare fortsett med denne tilbakestillingen hvis du er sikker på at den ikke inneholder noen nøkler som sikrer bitcoins, da du kan permanent miste tilgangen til dine midler.
![LEDGER FLEX](assets/notext/30.webp)

## Hvordan installere Bitcoin-applikasjonen?

Start med å starte Ledger Live-programvaren på datamaskinen din, deretter koble til og lås opp din Ledger Flex.

![LEDGER FLEX](assets/notext/31.webp)

I Ledger Live, gå til "_My Ledger_" menyen. Du vil bli bedt om å autorisere tilgang til din Flex.

![LEDGER FLEX](assets/notext/32.webp)

Valider tilgangen på din Ledger ved å klikke på "_Allow_" knappen.

![LEDGER FLEX](assets/notext/33.webp)

Først, hvis firmwaren til din Ledger Flex ikke er oppdatert, vil Ledger Live automatisk tilby å oppdatere den. Hvis aktuelt, klikk på "_Update firmware_", deretter på "_Install update_" for å starte installasjonen.

![LEDGER FLEX](assets/notext/34.webp)

På din Ledger, klikk på "_Install_" knappen, og vent under installasjonen.

![LEDGER FLEX](assets/notext/35.webp)

Firmwaren til din Ledger Flex er nå oppdatert.
![LEDGER FLEX](assets/notext/36.webp)
Om du ønsker, kan du endre låseskjermens bakgrunnsbilde på din Ledger Flex. For å gjøre dette, klikk på "_Legg til >_".

![LEDGER FLEX](assets/notext/37.webp)

Klikk på "_Last opp fra datamaskin_" knappen og velg ditt bakgrunnsbilde fra dine bilder.

![LEDGER FLEX](assets/notext/38.webp)

Du kan beskjære bildet ditt.

![LEDGER FLEX](assets/notext/39.webp)

Velg en kontrast fra de forskjellige alternativene, deretter klikker du på "_Bekreft kontrast_".

![LEDGER FLEX](assets/notext/40.webp)

På din Flex, klikk på "_Last opp bilde_" knappen.

![LEDGER FLEX](assets/notext/41.webp)

Hvis du er fornøyd med bildet, klikk på "_Behold_" for å sette det som låseskjermens bakgrunnsbilde.

![LEDGER FLEX](assets/notext/42.webp)

Til slutt, vil vi legge til Bitcoin-applikasjonen. For å gjøre dette, på Ledger Live, klikk på "_Installer_" knappen ved siden av "_Bitcoin (BTC)_".

![LEDGER FLEX](assets/notext/43.webp)

Applikasjonen vil installeres på din Flex.

![LEDGER FLEX](assets/notext/44.webp)

Fra nå av, vil du ikke lenger trenge Ledger Live-programvaren for den regelmessige forvaltningen av lommeboken din. Du kan returnere til den av og til for å oppdatere firmwaren når nye versjoner er tilgjengelige. For alt annet, vil vi bruke Sparrow Wallet, som er et mye mer omfattende verktøy for effektiv forvaltning av en Bitcoin-lommebok.

## Hvordan sette opp en ny Bitcoin-lommebok med Sparrow?

Åpne Sparrow Wallet og hopp over introduksjonssidene for å få tilgang til hjemmeskjermen. Sjekk at du er ordentlig koblet til en node ved å observere bryteren plassert nederst til høyre på skjermen.
![LEDGER FLEX](assets/notext/45.webp)

Jeg anbefaler sterkt å bruke din egen Bitcoin-node. I denne veiledningen bruker jeg en offentlig node (gul) fordi jeg er på testnet, men for normal bruk, er det bedre å velge en lokal Bitcoin Core (grønn) eller en Electrum-server koblet til en ekstern node (blå).

Klikk på "_Fil_" menyen deretter "_Ny Lommebok_".

![LEDGER FLEX](assets/notext/46.webp)

Velg et navn for denne lommeboken, deretter klikk på "_Opprett Lommebok_".

![LEDGER FLEX](assets/notext/47.webp)

I nedtrekksmenyen for "_Script Type_", velg typen av script som vil bli brukt for å sikre dine bitcoins. Jeg anbefaler å velge "_Taproot_", eller hvis ikke tilgjengelig, "_Native SegWit_".

![LEDGER FLEX](assets/notext/48.webp)

Klikk på "_Koblet Maskinvarelommebok_" knappen.

![LEDGER FLEX](assets/notext/49.webp)

Koble din Ledger Flex til datamaskinen, lås den opp med din PIN-kode, deretter åpne "_Bitcoin_" applikasjonen. I denne veiledningen bruker jeg "_Bitcoin Testnet_" applikasjonen, men prosedyren forblir den samme for hovednettet.

![LEDGER FLEX](assets/notext/50.webp)

På Sparrow, klikk på "_Skann_" knappen.

![LEDGER FLEX](assets/notext/51.webp)

Deretter klikker du på "_Importer Keystore_".

![LEDGER FLEX](assets/notext/52.webp)

Du kan nå se detaljene til lommeboken din, inkludert den utvidede offentlige nøkkelen til din første konto. Klikk på "_Bruk_" knappen for å fullføre opprettelsen av lommeboken.
Velg et sterkt passord for å sikre tilgangen til Sparrow Wallet. Dette passordet vil sikre tilgangssikkerheten til lommebokdataene dine på Sparrow, noe som hjelper til med å beskytte dine offentlige nøkler, adresser, etiketter og transaksjonshistorikk mot uautorisert tilgang.

Jeg anbefaler deg å lagre dette passordet i en passordbehandler slik at du ikke glemmer det.

Og der har du det, lommeboken din er nå opprettet!

Før du mottar dine første bitcoins i lommeboken, anbefaler jeg sterkt at du utfører en tørrkjøringsgjenopprettingstest. Noter et referansestykke informasjon, som din xpub, og deretter tilbakestiller du din Ledger Flex mens lommeboken fortsatt er tom. Etterpå, prøv å gjenopprette lommeboken din på Ledger ved hjelp av dine papirbackuper. Sjekk at xpub generert etter gjenoppretting matcher den du opprinnelig noterte. Hvis dette er tilfellet, kan du være sikker på at dine papirbackuper er pålitelige.

## Hvordan motta bitcoins med Ledger Flex?

Klikk på "_Motta_" fanen.

Koble din Ledger Flex til datamaskinen, lås den opp med din PIN-kode, og deretter åpner du "_Bitcoin_" applikasjonen.

Før du bruker adressen som er gitt av Sparrow Wallet, verifiser den på skjermen til din Ledger Flex. Denne praksisen lar deg bekrefte at adressen som vises på Sparrow ikke er svindel og at Ledger faktisk holder den private nøkkelen som er nødvendig for å bruke bitcoins sikret med denne adressen senere.

For å utføre denne verifiseringen, klikk på "_Vis Adresse_" knappen.

Sørg for at adressen som vises på din Ledger Flex matcher den som er angitt på Sparrow Wallet. Det anbefales også å utføre denne verifiseringen rett før du gir adressen din til avsenderen, for å være sikker på dens gyldighet.

Du kan legge til en "_Etikett_" for å beskrive kilden til bitcoins som vil bli sikret med denne adressen. Dette er en god praksis som hjelper deg å bedre håndtere dine UTXOer.

For mer informasjon om etikettering, anbefaler jeg også at du sjekker ut denne andre opplæringen:

https://planb.network/tutorials/privacy/utxo-labelling

Du kan deretter bruke denne adressen til å motta bitcoins.

## Hvordan sende bitcoins med Ledger Flex?

Nå som du har mottatt dine første sats i lommeboken sikret med Flex, kan du også bruke dem! Koble din Ledger til datamaskinen, lås den opp, start Sparrow Wallet, og gå deretter til "_Send_" fanen for å konstruere en ny transaksjon.

Hvis du ønsker å gjøre "_coin control_", det vil si, spesifikt velge hvilke UTXOer som skal forbrukes i transaksjonen, gå til "_UTXOer_" fanen. Velg UTXOene du ønsker å bruke, og klikk deretter på "_Send Valgte_". Du vil bli omdirigert til samme skjerm av "_Send_" fanen, men med dine UTXOer allerede valgt for transaksjonen.

Skriv inn destinasjonsadressen. Du kan også legge inn flere adresser ved å klikke på "_+ Legg til_" knappen.

Noter en "_Etikett_" for å huske formålet med denne utgiften.
Velg beløpet som skal sendes til denne adressen.

Juster transaksjonsgebyrets rate i henhold til det nåværende markedet.

Sørg for at alle innstillingene for transaksjonen din er korrekte, og klikk deretter på "_Opprett Transaksjon_".

Hvis alt er til din tilfredshet, klikk på "_Fullfør Transaksjon for Signering_".

Klikk på "_Signer_".

Klikk på "_Signer_" ved siden av din Ledger Flex.

Verifiser transaksjonsinnstillingene på Flex-skjermen din, inkludert mottakerens mottaksadresse, sendt beløp, og gebyrbeløpet.

For å signere, hold fingeren din på "_Hold for å signere_" knappen.

Transaksjonen din er nå signert. Klikk på "_Kringkast Transaksjon_" for å kringkaste den på Bitcoin-nettverket.

Du kan finne den i "_Transaksjoner_" fanen i Sparrow Wallet.

Gratulerer, du er nå oppdatert på grunnleggende bruk av Ledger Flex med Sparrow Wallet! I en fremtidig opplæring vil vi se hvordan man bruker Ledger Flex med Liana for å utnytte Miniscript.

Hvis du fant denne opplæringen nyttig, ville jeg sette pris på en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

