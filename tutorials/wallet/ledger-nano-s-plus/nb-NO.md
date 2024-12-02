---
name: Ledger Nano S Plus
description: Oppsett og bruk av Ledger Nano S Plus
---
![cover](assets/cover.webp)

En maskinvarelommebok er en elektronisk enhet dedikert til å håndtere og sikre de private nøklene til en Bitcoin-lommebok. I motsetning til programvarelommebøker (eller varme lommebøker) installert på allmennmaskiner ofte koblet til internett, tillater maskinvarelommebøker fysisk isolasjon av private nøkler, noe som reduserer risikoen for hacking og tyveri.

Hovedmålet med en maskinvarelommebok er å minimere enhetens funksjonaliteter så mye som mulig for å redusere dens angrepsflate. En mindre angrepsflate betyr også færre potensielle angrepsvektorer, dvs. færre svakheter i systemet som angripere kunne utnytte for å få tilgang til bitcoins.

Det anbefales å bruke en maskinvarelommebok for å sikre dine bitcoins, spesielt hvis du holder betydelige mengder, enten i absolutt verdi eller som en andel av dine totale eiendeler.

Maskinvarelommebøker brukes i kombinasjon med en lommebokforvaltningsprogramvare på en datamaskin eller smarttelefon. Denne programvaren håndterer opprettelsen av transaksjoner, men den kryptografiske signaturen som er nødvendig for å validere disse transaksjonene, gjøres kun innenfor maskinvarelommeboken. Dette betyr at de private nøklene aldri blir eksponert for et potensielt sårbart miljø.

Maskinvarelommebøker tilbyr dobbel beskyttelse for brukeren: på den ene siden sikrer de dine bitcoins mot fjernangrep ved å holde de private nøklene offline, og på den andre siden tilbyr de generelt bedre fysisk motstand mot forsøk på å ekstrahere nøklene. Og det er nettopp på disse 2 sikkerhetskriteriene man kan bedømme og rangere de forskjellige modellene som er tilgjengelige på markedet.

I denne veiledningen foreslår jeg å oppdage en av disse løsningene: **Ledger Nano S Plus**.

![NANO S PLUS LEDGER](assets/notext/01.webp)

## Introduksjon til Ledger Nano S Plus

Ledger Nano S Plus er en maskinvarelommebok produsert av det franske selskapet Ledger, markedsført til en pris av 79 €.

![NANO S PLUS LEDGER](assets/notext/02.webp)

Nano S Plus er utstyrt med en CC EAL6+ sertifisert brikke ("*sikkerhetselement*"), som tilbyr deg avansert beskyttelse mot fysiske angrep på maskinvaren. Skjermen og knappene styres direkte av denne brikken. Et kritikkpunkt som ofte nevnes, er at koden til denne brikken ikke er åpen kildekode, noe som krever en viss tillit til integriteten til denne komponenten. Likevel blir dette elementet revidert av uavhengige eksperter.

Når det gjelder bruk, opererer Ledger Nano S Plus utelukkende gjennom en kablet USB-C-tilkobling.

Ledger skiller seg ut fra konkurrentene med sin alltid meget raske adopsjon av nye Bitcoin-funksjoner, som for eksempel Taproot eller Miniscript, noe som er høyt verdsatt.
Etter å ha testet den, finner jeg at Ledger Nano S Plus er en utmerket inngangsmodell for maskinvarelommebøker. Den tilbyr et høyt nivå av sikkerhet for en rimelig pris. Dens største ulempe sammenlignet med andre enheter i samme prisklasse er det faktum at firmwarekoden ikke er åpen kildekode. I tillegg er skjermen til Nano S Plus relativt liten sammenlignet med dyrere modeller, som Ledger Flex eller Coldcard Q1. Likevel er grensesnittet veldig godt designet: til tross for sine to knapper og lille skjerm, forblir den enkel å bruke, inkludert for avanserte funksjoner som BIP39-passfrasen. Ledger Nano S Plus har ikke et batteri, Air-gap-tilkobling, kamera eller micro SD-port, men dette er ganske normalt for denne prisklassen.
Etter min mening er Ledger Nano S Plus et godt alternativ for å sikre din Bitcoin-lommebok, og passer for både nybegynnere og mellomliggende brukere. Imidlertid foretrekker jeg personlig Trezor Safe 3 i denne prisklassen, som tilbyr omtrent de samme alternativene. Fordelen med Trezor, etter min mening, er i håndteringen av dens sikre element: den mnemoniske frasen og nøklene forvaltes utelukkende av åpen kildekode, men nyter fortsatt godt av beskyttelsen av brikken. Ulempen med Trezor er at de noen ganger er veldig trege med å implementere nye funksjoner, i motsetning til Ledger.
## Hvordan kjøpe en Ledger Nano S Plus?

Ledger Nano S Plus er tilgjengelig for salg [på den offisielle nettsiden](https://shop.ledger.com/products/ledger-nano-s-plus). For å kjøpe den i en fysisk butikk, kan du også finne [listen over sertifiserte forhandlere](https://www.ledger.com/reseller) på Ledger-nettstedet.

## Forutsetninger

Når du har mottatt din Ledger Nano, er det første steget å sjekke emballasjen for å forsikre deg om at den ikke har blitt åpnet. Hvis den er skadet, kan dette indikere at maskinvarelommeboken har blitt kompromittert og kanskje ikke er autentisk.

Ved åpning, bør du finne følgende gjenstander i esken:
- Ledger Nano S Plus;
- En USB-C til USB-A kabel;
- En brukermanual;
- Kort for å skrive ned din mnemoniske frase.

For denne veiledningen, vil du trenge 2 programvareapplikasjoner: Ledger Live for å initialisere Ledger, og Sparrow Wallet for å håndtere din Bitcoin-lommebok. Last ned [Ledger Live](https://www.ledger.com/ledger-live) og [Sparrow Wallet](https://sparrowwallet.com/download/) fra deres offisielle nettsider.

![NANO S PLUS LEDGER](assets/notext/03.webp)
For disse to programvarene, anbefaler jeg sterkt å sjekke både deres autentisitet (med GnuPG) og deres integritet (via hashen) før du installerer dem på maskinen din. Hvis du ikke er sikker på hvordan du gjør dette, kan du følge denne andre veiledningen:
https://planb.network/tutorials/others/integrity-authenticity

## Hvordan initialisere en Ledger Nano?

Koble din Nano til datamaskinen hvor Ledger Live og Sparrow Wallet er installert. For å navigere på din Ledger, bruk venstre knapp for å gå til venstre og høyre knapp for å gå til høyre. For å velge eller bekrefte et alternativ, trykk begge knappene samtidig.

![NANO S PLUS LEDGER](assets/notext/04.webp)

Bla gjennom de forskjellige introduksjonssidene og klikk deretter på de 2 knappene for å begynne.

![NANO S PLUS LEDGER](assets/notext/05.webp)

Velg alternativet "*Sett opp som en ny enhet*".

![NANO S PLUS LEDGER](assets/notext/06.webp)

Velg PIN-koden som vil bli brukt for å låse opp din Ledger. Dette er derfor en beskyttelse mot uautorisert fysisk tilgang. Denne PIN-koden spiller ingen rolle i derivasjonen av lommebokens kryptografiske nøkler. Så, selv uten tilgang til denne PIN-koden, vil å ha din 24-ords mnemoniske frase tillate deg å gjenopprette tilgangen til dine bitcoins.

![NANO S PLUS LEDGER](assets/notext/07.webp)

Det anbefales å velge en 8-sifret PIN, så tilfeldig som mulig. Også, sørg for å lagre denne koden på et annet sted enn der din Ledger Nano S Plus er lagret (for eksempel, i en passordbehandler).

Bruk knappene for å flytte over sifrene, deretter velg hvert siffer ved å klikke begge knappene samtidig.

![NANO S PLUS LEDGER](assets/notext/08.webp)

Skriv inn din PIN en andre gang for å bekrefte den.
![NANO S PLUS LEDGER](assets/notext/09.webp)
Din Nano gir instruksjoner om hvordan du skal håndtere din gjenopprettingsfrase.

**Denne mnemoniske frasen gir full og ubegrenset tilgang til alle dine bitcoins**. Enhver som er i besittelse av denne frasen kan stjele dine midler, selv uten fysisk tilgang til din Ledger. Den 24-ords frasen lar deg gjenopprette tilgangen til dine bitcoins i tilfelle tap, tyveri eller skade på din Ledger Nano. Det er derfor svært viktig å nøye lagre og oppbevare den på et sikkert sted.

Du kan skrive den ned på papparket som følger med din Ledger, eller for mer sikkerhet, anbefaler jeg å gravere den inn på et medium av rustfritt stål for å beskytte mot risikoer som branner, flommer eller kollapser.

Du kan bla gjennom disse instruksjonene og hoppe over sider ved å klikke på høyre knapp.

![NANO S PLUS LEDGER](assets/notext/10.webp)
Ledger vil skape din mnemoniske frase ved hjelp av sin tilfeldige nummergenerator. Sørg for at du ikke blir observert under denne operasjonen. Skriv ned ordene som Ledger gir deg på det fysiske mediet du har valgt. Avhengig av din sikkerhetsstrategi, kan du vurdere å lage flere komplette fysiske kopier av frasen (men viktig, ikke del den opp). Det er avgjørende å holde ordene nummerert og i sekvensiell rekkefølge.
***Åpenbart, du bør aldri dele disse ordene på internett, i motsetning til det jeg gjør i denne opplæringen. Denne eksempellommeboken vil kun bli brukt på Testnet og vil bli slettet etter opplæringen.***

![NANO S PLUS LEDGER](assets/notext/11.webp)

For å gå til de neste ordene, klikk på høyre knapp.

![NANO S PLUS LEDGER](assets/notext/12.webp)

Når alle ordene er notert, klikk på de 2 knappene for å gå til neste steg.

![NANO S PLUS LEDGER](assets/notext/13.webp)

Klikk på de to knappene "*Bekreft din gjenopprettingsfrase*", deretter velg ordene i din mnemoniske frase i deres rekkefølge for å bekrefte at du har notert dem korrekt. Bruk venstre og høyre knapper for å navigere mellom alternativene, deretter velg det korrekte ordet ved å klikke på de 2 knappene. Fortsett denne prosedyren til det 24. ordet.

![NANO S PLUS LEDGER](assets/notext/14.webp)

Hvis frasen du bekrefter matcher nøyaktig den som Ledger ga deg i forrige steg, kan du fortsette. Hvis ikke, indikerer det at din fysiske sikkerhetskopi av den mnemoniske frasen er feil, og du må starte prosessen på nytt.

![NANO S PLUS LEDGER](assets/notext/15.webp)

Og der har du det, din seed har blitt korrekt opprettet på din Ledger Nano S Plus. Før vi fortsetter med å opprette en ny Bitcoin-lommebok fra denne seeden, la oss utforske enhetsinnstillingene sammen.

## Hvordan endre innstillingene på din Ledger?

For å få tilgang til innstillingene, hold ned de 2 knappene i noen sekunder.

![NANO S PLUS LEDGER](assets/notext/16.webp)

Klikk på "*Innstillinger*" menyen.

![NANO S PLUS LEDGER](assets/notext/17.webp)

Og velg "*Generelt*".

![NANO S PLUS LEDGER](assets/notext/18.webp)

I "*Språk*" menyen, kan du endre visningsspråket.

![NANO S PLUS LEDGER](assets/notext/19.webp)

I "*Lysstyrke*" menyen, kan du justere skjermens lysstyrke. Vi er ikke interessert i resten av de generelle innstillingene for øyeblikket.

![NANO S PLUS LEDGER](assets/notext/20.webp)

Nå, gå til "*Sikkerhet*" innstillingsseksjonen.

![NANO S PLUS LEDGER](assets/notext/21.webp)
"*Endre PIN*" lar deg endre PIN-koden din. ![NANO S PLUS LEDGER](assets/notext/22.webp)
"*Passordfrase*" lar deg sette opp en BIP39-passordfrase. Passordfrasen er et valgfritt passord som, kombinert med din gjenopprettingsfrase, gir et ekstra sikkerhetslag for lommeboken din.

![NANO S PLUS LEDGER](assets/notext/23.webp)

For øyeblikket er lommeboken din generert fra en mnemonisk frase bestående av 24 ord. Denne gjenopprettingsfrasen er veldig viktig fordi den lar deg gjenopprette alle nøklene til lommeboken din i tilfelle tap. Imidlertid utgjør den et enkelt feilpunkt (SPOF). Hvis den blir kompromittert, er dine bitcoins i fare. Dette er hvor passordfrasen kommer inn. Det er et valgfritt passord, som du kan velge vilkårlig, som legges til den mnemoniske frasen for å forbedre lommebokens sikkerhet.

Passordfrasen bør ikke forveksles med PIN-koden. Den spiller en rolle i derivasjonen av dine kryptografiske nøkler. Den fungerer i tandem med den mnemoniske frasen, og endrer frøet som nøklene genereres fra. Så selv om noen får tak i din 24-ords frase, uten passordfrasen, kan de ikke få tilgang til midlene dine. Å bruke en passordfrase skaper i hovedsak en ny lommebok med distinkte nøkler. Å endre (selv litt) passordfrasen vil generere en annen lommebok.

Passordfrasen er et veldig kraftig verktøy for å forbedre sikkerheten til dine bitcoins. Det er imidlertid veldig viktig å forstå hvordan den fungerer før du implementerer den, for å unngå å miste tilgangen til lommeboken din. Dette er grunnen til at jeg råder deg til å konsultere denne andre opplæringen dedikert hvis du ønsker å sette opp en passordfrase på din Ledger:

https://planb.network/tutorials/wallet/passphrase-ledger

"*PIN-lås*" menyen lar deg konfigurere og aktivere automatisk låsing av din Ledger etter en bestemt periode med inaktivitet.

![NANO S PLUS LEDGER](assets/notext/24.webp)

"*Skjermsparer*" menyen lar deg justere hvilemodusen til din Ledger Nano. Merk at skjermspareren ikke krever PIN-inntasting ved oppvåkning, med mindre "*PIN-lås*" alternativet er aktivert for å samsvare med hvilemodus. Denne funksjonen er spesielt nyttig for Ledger Nano X-enheter utstyrt med et batteri, for å redusere deres energiforbruk.

![NANO S PLUS LEDGER](assets/notext/25.webp)

Til slutt lar "*Tilbakestill enhet*" menyen deg tilbakestille din Ledger. Bare fortsett med denne tilbakestillingen hvis du er sikker på at den ikke inneholder noen nøkler som sikrer bitcoins, da du kan miste tilgangen til midlene dine permanent. Dette alternativet kan være nyttig for å utføre en tom gjenopprettingstest, men jeg vil snakke litt mer om dette senere.

![NANO S PLUS LEDGER](assets/notext/26.webp)
## Hvordan installere Bitcoin-applikasjonen?

Start med å starte Ledger Live-programvaren på datamaskinen din, deretter koble til og låse opp din Ledger Nano. I Ledger Live, gå til "*Min Ledger*" menyen. Du vil bli bedt om å autorisere tilgang til din Nano.

![NANO S PLUS LEDGER](assets/notext/27.webp)

Valider tilgang på din Ledger ved å klikke på de to knappene.

![NANO S PLUS LEDGER](assets/notext/28.webp)

Først, på Ledger Live, sørg for at "*Ekte sjekk*" vises. Dette bekrefter at enheten din er autentisk.

![NANO S PLUS LEDGER](assets/notext/29.webp)

Hvis firmwaren til din Ledger Nano ikke er oppdatert, vil Ledger Live automatisk tilby å oppdatere den. Om nødvendig, klikk på "*Oppdater firmware*", deretter på "*Installer oppdatering*" for å starte installasjonen. På din Ledger, klikk på de to knappene for å bekrefte, deretter vent under installasjonen.
Til slutt vil vi legge til Bitcoin-applikasjonen. For å gjøre dette, klikk på "*Installer*" knappen ved siden av "*Bitcoin (BTC)*" på Ledger Live.
![NANO S PLUS LEDGER](assets/notext/30.webp)

Applikasjonen vil installeres på din Nano.

![NANO S PLUS LEDGER](assets/notext/31.webp)

Fra nå av vil du ikke lenger trenge Ledger Live-programvaren for den regelmessige forvaltningen av lommeboken din. Du kan av og til returnere til den for å oppdatere firmwaren når nye versjoner er tilgjengelige. For alt annet vil vi bruke Sparrow Wallet, som er et mye mer omfattende verktøy for effektiv forvaltning av en Bitcoin-lommebok.

![NANO S PLUS LEDGER](assets/notext/32.webp)

## Hvordan sette opp en ny Bitcoin-lommebok med Sparrow?

Åpne Sparrow Wallet og hopp over introduksjonssidene for å få tilgang til hjemmeskjermen. Sjekk at du er korrekt tilkoblet en node ved å observere bryteren som er plassert nederst til høyre på skjermen.

![NANO S PLUS LEDGER](assets/notext/33.webp)

Jeg anbefaler sterkt å bruke din egen Bitcoin-node. I denne veiledningen bruker jeg en offentlig node (gul) fordi jeg er på testnet, men for normal bruk er det bedre å velge en lokal Bitcoin Core (grønn) eller en Electrum-server koblet til en ekstern node (blå).

Klikk på "*Fil*" menyen deretter "*Ny Lommebok*".

![NANO S PLUS LEDGER](assets/notext/34.webp)

Velg et navn for denne lommeboken, deretter klikk på "*Opprett Lommebok*".

![NANO S PLUS LEDGER](assets/notext/35.webp)

I nedtrekksmenyen for "*Script Type*", velg typen av script som vil bli brukt for å sikre dine bitcoins. Jeg anbefaler å velge "*Taproot*", eller hvis ikke tilgjengelig, "*Native SegWit*".

![NANO S PLUS LEDGER](assets/notext/36.webp)
Klikk på "*Tilkoblet Maskinvarelommebok*" knappen.
![NANO S PLUS LEDGER](assets/notext/37.webp)

Hvis du ikke allerede har gjort det, koble din Ledger Nano S Plus til datamaskinen, lås den opp med din PIN-kode, og deretter åpne "*Bitcoin*" applikasjonen ved å klikke på de 2 knappene en gang på Bitcoin-logoen.

*I denne veiledningen bruker jeg Bitcoin Testnet-applikasjonen, men prosedyren forblir den samme for hovednettet.*

![NANO S PLUS LEDGER](assets/notext/38.webp)

På Sparrow, klikk på "*Skann*" knappen.

![NANO S PLUS LEDGER](assets/notext/39.webp)

Deretter klikker du på "*Importer Keystore*".

![NANO S PLUS LEDGER](assets/notext/40.webp)

Du kan nå se detaljene i lommeboken din, inkludert den utvidede offentlige nøkkelen til din første konto. Klikk på "*Bruk*" knappen for å fullføre opprettelsen av lommeboken.

![NANO S PLUS LEDGER](assets/notext/41.webp)

Velg et sterkt passord for å sikre tilgangen til Sparrow Wallet. Dette passordet vil sikre tilgangssikkerheten til lommebokdataene dine på Sparrow, som hjelper til med å beskytte dine offentlige nøkler, adresser, etiketter og transaksjonshistorikk mot uautorisert tilgang.

Jeg råder deg til å lagre dette passordet i en passordbehandler slik at du ikke glemmer det.

![NANO S PLUS LEDGER](assets/notext/42.webp)

Og der har du det, lommeboken din er nå opprettet!

![NANO S PLUS LEDGER](assets/notext/43.webp)
Før du mottar dine første bitcoins i lommeboken din, **anbefaler jeg på det sterkeste at du utfører en tørrkjøringsgjenopprettingstest**. Noter et referansestykket informasjon, som din xpub, deretter tilbakestill din Ledger Nano mens lommeboken fortsatt er tom. Etterpå, prøv å gjenopprette lommeboken din på Ledger ved hjelp av dine papirbackuper. Sjekk at xpub-en som genereres etter gjenopprettingen matcher den du opprinnelig noterte. Hvis så er tilfellet, kan du være sikker på at dine papirbackuper er pålitelige.
For å lære mer om hvordan du utfører en gjenopprettingstest, anbefaler jeg at du konsulterer denne andre veiledningen:

https://planb.network/tutorials/wallet/recovery-test

## Hvordan motta bitcoins med Ledger Nano?

Klikk på "*Motta*" fanen.

![NANO S PLUS LEDGER](assets/notext/44.webp)

Koble din Ledger Nano S Plus til datamaskinen, lås den opp med din PIN-kode, og åpne deretter "*Bitcoin*" applikasjonen.

![NANO S PLUS LEDGER](assets/notext/45.webp)
Før du bruker adressen som tilbys av Sparrow Wallet, verifiser den på din Ledgers skjerm. Denne praksisen lar deg bekrefte at adressen som vises på Sparrow ikke er svindel og at maskinvarelommeboken faktisk inneholder den private nøkkelen som er nødvendig for å bruke bitcoinsene som er sikret med denne adressen senere. Dette hjelper deg med å unngå flere typer angrep.
For å utføre denne verifiseringen, klikk på "*Vis Adresse*" knappen.

![NANO S PLUS LEDGER](assets/notext/46.webp)

Sørg for at adressen som vises på din Ledger matcher den som er angitt på Sparrow Wallet. Det anbefales også å utføre denne verifiseringen rett før du gir adressen din til avsenderen, for å være sikker på dens gyldighet. Du kan bruke knappene for å se hele adressen.

![NANO S PLUS LEDGER](assets/notext/47.webp)

Deretter klikker du på "*Godkjenn*" hvis adressene faktisk er identiske.

![NANO S PLUS LEDGER](assets/notext/48.webp)

Du kan legge til en "*Etikett*" for å beskrive kilden til bitcoinsene som vil bli sikret med denne adressen. Dette er en god praksis som hjelper deg med å bedre håndtere dine UTXOer.

![NANO S PLUS LEDGER](assets/notext/49.webp)

For mer informasjon om etikettering, anbefaler jeg også at du sjekker ut denne andre veiledningen:

https://planb.network/tutorials/privacy/utxo-labelling

Du kan deretter bruke denne adressen til å motta bitcoins.

![NANO S PLUS LEDGER](assets/notext/50.webp)

## Hvordan sende bitcoins med Ledger Nano?

Nå som du har mottatt dine første sats i lommeboken sikret med Nano S Plus, kan du også bruke dem! Koble din Ledger til datamaskinen, lås den opp, start Sparrow Wallet, og gå deretter til "*Send*" fanen for å konstruere en ny transaksjon.

![NANO S PLUS LEDGER](assets/notext/51.webp)

Hvis du ønsker å gjøre "*coin control*", som betyr å spesifikt velge hvilke UTXOer du vil bruke i transaksjonen, gå til "*UTXOer*" fanen. Velg UTXOene du ønsker å bruke, og klikk deretter på "*Send Valgte*". Du vil bli omdirigert til samme skjerm som "*Send*" fanen, men med dine UTXOer allerede valgt for transaksjonen.

![NANO S PLUS LEDGER](assets/notext/52.webp)

Skriv inn mottakeradressen. Du kan også legge til flere adresser ved å klikke på "*+ Legg til*" knappen.

![NANO S PLUS LEDGER](assets/notext/53.webp)

Noter en "*Etikett*" for å huske formålet med denne utgiften.

![NANO S PLUS LEDGER](assets/notext/54.webp)
Velg beløpet som skal sendes til denne adressen.
![NANO S PLUS LEDGER](assets/notext/55.webp)

Justér transaksjonsgebyrsatsen i henhold til gjeldende markedsforhold.

![NANO S PLUS LEDGER](assets/notext/56.webp)
Sørg for at alle innstillingene for transaksjonen din er korrekte, deretter klikk på "*Opprett Transaksjon*".
![NANO S PLUS LEDGER](assets/notext/57.webp)

Hvis alt ser bra ut for deg, klikk på "*Fullfør Transaksjon for Signering*".

![NANO S PLUS LEDGER](assets/notext/58.webp)

Klikk på "*Signer*".

![NANO S PLUS LEDGER](assets/notext/59.webp)

Klikk på "*Signer*" ved siden av din Ledger Nano S Plus.

![NANO S PLUS LEDGER](assets/notext/60.webp)

Verifiser transaksjonsinnstillingene på skjermen til din Ledger, inkludert mottakerens adresse, sendt beløp, og gebyrbeløpet.

![NANO S PLUS LEDGER](assets/notext/61.webp)

Hvis alt ser bra ut for deg, trykk på de to knappene på "*Signer transaksjon*" for å signere.

![NANO S PLUS LEDGER](assets/notext/62.webp)

Transaksjonen din er nå signert. Dobbeltsjekk at alt ser bra ut for deg, deretter klikk på "*Kringkast Transaksjon*" for å kringkaste den på Bitcoin-nettverket.

![NANO S PLUS LEDGER](assets/notext/63.webp)

Du kan finne den i "*Transaksjoner*" fanen i Sparrow Wallet.

![NANO S PLUS LEDGER](assets/notext/64.webp)

Gratulerer, du er nå oppdatert på grunnleggende bruk av Ledger Nano S Plus med Sparrow Wallet! I en fremtidig opplæring vil vi se på hvordan man bruker Ledger med Liana for å utnytte Miniscript.

Hvis du fant denne opplæringen nyttig, ville jeg sette pris på om du kunne legge igjen en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

Jeg anbefaler også at du sjekker ut denne komplette opplæringen om Ledger Flex:

https://planb.network/tutorials/wallet/ledger-flex