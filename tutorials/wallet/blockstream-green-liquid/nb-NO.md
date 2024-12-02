---
name: Blockstream Green - Liquid
description: Oppsett av en lommebok på Liquid Network sidechain
---
![cover](assets/cover.webp)
Bitcoin-protokollen har bevisste tekniske begrensninger som hjelper med å opprettholde nettverkets desentralisering og sikre sikkerhetsfordeling blant alle brukere. Imidlertid kan disse grensene noen ganger frustrere brukere, spesielt under trengsel forårsaket av et høyt volum av samtidige transaksjoner. Debatten om Bitcoins skalérbarhet har lenge delt samfunnet, spesielt under Blocksize-krigen. Siden den episoden er det bredt anerkjent innen Bitcoin-samfunnet at skalérbarhet må sikres gjennom off-chain løsninger, på andre-lags systemer. Blant disse løsningene er sidekjeder, som fortsatt er relativt ukjente og underbrukte sammenlignet med andre systemer som Lightning Network.

En sidekjede er en uavhengig blokkjede som opererer parallelt med hoved-Bitcoin-blokkjeden. Den bruker bitcoin som en enhet gjennom en mekanisme kalt "*two-way peg*". Dette systemet tillater låsing av bitcoins på hovedkjeden for å replikere deres verdi på sidekjeden, hvor de sirkulerer som tokens støttet av de originale bitcoinene. Disse tokenene opprettholder normalt en verdi-paritet med bitcoinene låst på hovedkjeden, og prosessen kan reverseres for å gjenvinne midlene på Bitcoin.

Målet med sidekjeder er å tilby tilleggsfunksjonaliteter eller tekniske forbedringer, som raskere transaksjoner, reduserte gebyrer, eller støtte for smartkontrakter. Disse innovasjonene kan ikke alltid implementeres direkte på Bitcoin-blokkjeden uten å kompromittere dens desentralisering eller sikkerhet. Sidekjeder tillater derfor testing og utforsking av nye løsninger samtidig som integriteten til Bitcoin bevares. Imidlertid krever disse protokollene ofte kompromisser, spesielt når det gjelder desentralisering og sikkerhet, avhengig av den valgte styringsmodellen og konsensusmekanismen.

I dag er den mest kjente sidekjeden sannsynligvis Liquid. I denne veiledningen vil jeg først introdusere deg for hva Liquid er, og deretter veilede deg om hvordan du enkelt kan begynne å bruke det gjennom Blockstream Green-applikasjonen, for å dra nytte av fordelene.

![LIQUID GREEN](assets/fr/01.webp)

## Hva er Liquid Network?

Liquid er en føderert sidekjede bygget på toppen av Bitcoin, utviklet av Blockstream, med mål om å forbedre hastigheten, personvernet, og funksjonalitetene til transaksjoner. Den bruker en bilateral forankringsmekanisme etablert på en føderasjon for å låse bitcoins på hovedkjeden og skape, i retur, Liquid-bitcoins (L-BTC), tokens som sirkulerer på Liquid samtidig som de forblir støttet av de originale bitcoinene.

![LIQUID GREEN](assets/fr/02.webp)
Liquid-nettverket er basert på en føderasjon av deltakere, bestående av anerkjente enheter fra Bitcoin-økosystemet, som validerer blokker og håndterer bilateral forankring. I tillegg til L-BTC, tillater Liquid også utstedelse av andre digitale eiendeler, som stablecoins eller andre kryptovalutaer.
![LIQUID GREEN](assets/fr/03.webp)

## Introduksjon til Blockstream Green

Blockstream Green er en programvarelommebok tilgjengelig på mobil og desktop. Tidligere kjent som *Green Address*, ble denne lommeboken et Blockstream-prosjekt etter oppkjøpet i 2016.

Green er en applikasjon som er spesielt enkel å bruke, noe som gjør den interessant for nybegynnere. Den tilbyr alle de essensielle funksjonene til en god Bitcoin-lommebok, inkludert RBF (*Replace-by-Fee*), en mulighet til å koble til via Tor, evnen til å koble til din egen node, SPV (*Simple Payment Verification*)-alternativet, merking, og myntkontroll.

Blockstream Green støtter også Liquid-nettverket, og det er det vi skal utforske i denne veiledningen. Hvis du ønsker å bruke Green for andre applikasjoner, anbefaler jeg også å konsultere disse andre veiledningene:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Installere og sette opp Blockstream Green-applikasjonen

Det første steget er naturligvis å laste ned Green-applikasjonen. Gå til applikasjonsbutikken din:
- [For Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet) ;
- [For Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

For Android-brukere har du også muligheten til å installere applikasjonen via `.apk`-filen [tilgjengelig på Blockstreams GitHub](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Start applikasjonen, deretter kryss av i boksen "*Jeg aksepterer vilkårene...*".

![LIQUID GREEN](assets/fr/06.webp)

Når du åpner Green for første gang, vises hjemmeskjermen uten noen konfigurerte lommebøker. Senere, hvis du oppretter eller importerer lommebøker, vil de vises i dette grensesnittet. Før du går videre til å opprette en lommebok, anbefaler jeg at du justerer applikasjonsinnstillingene i henhold til dine forventninger. Klikk på "*Applikasjonsinnstillinger*".

![LIQUID GREEN](assets/fr/07.webp)

Alternativet "*Forbedret personvern*", som kun er tilgjengelig på Android, forbedrer personvernet ved å deaktivere skjermbilder og skjule applikasjonsforhåndsvisninger. Det låser også automatisk tilgangen til applikasjonen så snart telefonen din er låst, noe som gjør dataene dine vanskeligere å eksponere.
![LIQUID GREEN](assets/fr/08.webp)
For de som ønsker å forbedre sitt personvern, tilbyr appen muligheten til å rute trafikken din gjennom Tor, et nettverk som krypterer alle tilkoblingene dine og gjør aktivitetene dine vanskelige å spore. Selv om denne muligheten kan senke appens ytelse noe, anbefales den sterkt for å beskytte personvernet ditt, spesielt hvis du ikke bruker din egen fullnode.

![LIQUID GREEN](assets/fr/09.webp)

For brukere som har sin egen fullnode, lar Green Wallet deg koble til den via en Electrum-server, noe som sikrer full kontroll over Bitcoin-nettverksinformasjon og transaksjonssending. Imidlertid er denne funksjonen relevant for tradisjonelle Bitcoin-lommebøker, så du trenger den ikke hvis du bruker Liquid.

![LIQUID GREEN](assets/fr/10.webp)

Et annet alternativt trekk er "*SPV-verifisering*" alternativet, som tillater direkte verifisering av visse blockchain-data, og dermed reduserer behovet for å stole på Blockstreams standardnode, selv om denne metoden ikke gir alle forsikringene til en fullnode. Igjen, dette vil kun angå dine onchain Bitcoin-lommebøker, og ikke Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Når disse innstillingene er justert i henhold til dine behov, klikk på "*Lagre*" knappen og start appen på nytt.

![LIQUID GREEN](assets/fr/12.webp)

## Opprette en Liquid-lommebok på Blockstream Green

Du er nå klar til å opprette en Liquid-lommebok. Klikk på "*Kom i gang*" knappen.

![LIQUID GREEN](assets/fr/13.webp)

Du har valget mellom å opprette en programvarelommebok lokalt eller administrere en kald lommebok via en maskinvarelommebok. For denne veiledningen vil vi fokusere på å opprette en varm lommebok på Liquid, så du må velge alternativet "*På denne enheten*". Du kan også bruke en kompatibel maskinvarelommebok, som Blockstream Jade, for å sikre din Liquid-lommebok.

![LIQUID GREEN](assets/fr/14.webp)
Du kan deretter velge å gjenopprette en eksisterende Bitcoin-lommebok eller opprette en ny. For formålet med denne veiledningen, vil vi opprette en ny lommebok. Men, hvis du trenger å regenerere en eksisterende Liquid-lommebok fra dens mnemoniske frase, for eksempel på grunn av tap av din maskinvarelommebok, må du velge det andre alternativet.
![LIQUID GREEN](assets/fr/15.webp)

Du har deretter valget mellom en 12-ords eller en 24-ords mnemonisk frase. Denne frasen vil tillate deg å gjenopprette tilgangen til lommeboken din fra hvilken som helst kompatibel programvare i tilfelle problemer med telefonen din. For øyeblikket tilbyr ikke valget av en 24-ords frase mer sikkerhet enn en 12-ords frase. Derfor anbefaler jeg å velge en **12-ords** mnemonisk frase.
Green vil deretter gi deg din mnemoniske frase. Før du fortsetter, sørg for at du ikke blir observert. Klikk på "*Vis gjenopprettingsfrase*" for å vise den på skjermen.
![LIQUID GREEN](assets/fr/16.webp)

**Denne mnemoniske frasen gir full og ubegrenset tilgang til alle dine bitcoins.** Enhver som er i besittelse av denne frasen kan stjele midlene dine, selv uten fysisk tilgang til telefonen din.

Den lar deg gjenopprette tilgangen til dine bitcoins i tilfelle tap, tyveri, eller skade på telefonen din. Derfor er det veldig viktig å nøye lagre den **på et fysisk medium (ikke digitalt)** og å oppbevare det på et sikkert sted. Du kan skrive den ned på et stykke papir, eller for mer sikkerhet, hvis denne lommeboken er betydelig, anbefaler jeg å gravere den på et rustfritt stålmedium for å beskytte mot risikoer for branner, flommer eller kollapser (for en varm lommebok ment for å sikre en liten mengde bitcoins, er en enkel papirkopi sannsynligvis tilstrekkelig).

*Selvfølgelig, du bør aldri dele disse ordene på internett, i motsetning til det jeg gjør i denne veiledningen. Denne eksempellommeboken vil kun bli brukt på Liquid Testnet og vil bli slettet ved slutten av veiledningen.*

![LIQUID GREEN](assets/fr/17.webp)

Etter å ha korrekt notert din mnemoniske frase på et fysisk medium, klikk på "*Fortsett*". Green Wallet vil deretter be deg om å bekrefte noen ord fra frasen din for å verifisere at du har registrert dem korrekt. Fyll inn de tomme feltene med de manglende ordene.

![LIQUID GREEN](assets/fr/18.webp)

Velg PIN-koden for enheten din, som vil bli brukt til å låse opp din Green-lommebok. Det er derfor en beskyttelse mot uautorisert fysisk tilgang. Denne PIN-koden spiller ingen rolle i derivasjonen av lommebokens kryptografiske nøkler. Således, selv uten tilgang til denne PIN-koden, vil besittelsen av din 12 eller 24-ords mnemoniske frase tillate deg å gjenopprette tilgangen til dine bitcoins.

Det anbefales å velge en 6-sifret PIN-kode så tilfeldig som mulig. Også, sørg for å lagre denne koden slik at du ikke glemmer den, ellers vil du bli tvunget til å gjenopprette lommeboken din fra den mnemoniske frasen. Senere kan du legge til en biometrisk låseopsjon for å unngå å angi PIN-koden hver gang du bruker den. Generelt sett er biometri mye mindre sikker enn PIN-koden selv. Derfor, som standard, råder jeg mot å sette opp denne låseopsjonen.

![LIQUID GREEN](assets/fr/19.webp)

Skriv inn PIN-koden din en andre gang for å bekrefte den.

![LIQUID GREEN](assets/fr/20.webp)
Vent på at lommeboken din blir opprettet, deretter klikk på "*Opprett en konto*" knappen.
![LIQUID GREEN](assets/fr/21.webp)
I "*Assets*" boksen, velg "*Liquid Bitcoin*". Du har da valget mellom en standard enkeltsignatur-lommebok, som vi vil bruke i denne opplæringen, eller en lommebok beskyttet av tofaktorautentisering (2FA).
![LIQUID GREEN](assets/fr/22.webp)

Og der har du det, din Liquid-lommebok har blitt vellykket opprettet ved bruk av Green-appen!

![LIQUID GREEN](assets/fr/23.webp)

Før du mottar dine første bitcoins på din Liquid-lommebok, **anbefaler jeg på det sterkeste at du utfører en tom gjenopprettingstest**. Noter ned en referanseinformasjon, som din xpub eller den første mottaksadressen, deretter sletter du lommeboken din på Green-appen mens den fortsatt er tom. Prøv deretter å gjenopprette lommeboken din på Green ved hjelp av dine papirbackuper. Sjekk at vitneinformasjonen som genereres etter gjenopprettingen stemmer overens med den du opprinnelig noterte. Hvis så er tilfellet, kan du være sikker på at dine papirbackuper er pålitelige. For å lære mer om hvordan du utfører en gjenopprettingstest, anbefaler jeg at du konsulterer denne andre opplæringen:

https://planb.network/tutorials/wallet/recovery-test

## Sette opp din Liquid-lommebok

Hvis du ønsker å tilpasse lommeboken din, klikk på de tre små prikkene øverst til høyre.

![LIQUID GREEN](assets/fr/24.webp)

"*Rename*" alternativet lar deg tilpasse navnet på lommeboken din, noe som er spesielt nyttig hvis du administrerer flere lommebøker i samme applikasjon.

![LIQUID GREEN](assets/fr/25.webp)

"*Unit*" menyen gir deg muligheten til å endre basisenheten for lommeboken din. For eksempel kan du velge å vise den i satoshis i stedet for i bitcoins.

![LIQUID GREEN](assets/fr/26.webp)

"*Settings*" menyen gir tilgang til de forskjellige alternativene for din Bitcoin-lommebok.

![LIQUID GREEN](assets/fr/27.webp)

Her vil du finne, for eksempel, din *descriptor* som kan være nyttig hvis du planlegger å sette opp en watch-only lommebok fra denne Liquid-lommeboken.

![LIQUID GREEN](assets/fr/28.webp)

Du kan også endre PIN-koden til lommeboken din og aktivere biometrisk innlogging.

![LIQUID GREEN](assets/fr/29.webp)

## Bruke din Liquid-lommebok

Nå som din Liquid-lommebok er satt opp, er du klar til å motta dine første L-sats!
Hvis du ikke allerede eier L-BTC, er det flere alternativer tilgjengelig for deg. Det første er å få det sendt direkte til deg. Hvis noen ønsker å betale deg i bitcoins på Liquid, gi dem bare en mottaksadresse. Den andre løsningen er å bytte dine onchain bitcoins eller de på Lightning-nettverket for L-BTC. For å gjøre dette, kan du bruke [en bro som Boltz](https://boltz.exchange/). Bare skriv inn din Liquid-adresse på nettstedet, og gjør deretter betalingen enten via Lightning-nettverket eller onchain.
![LIQUID GREEN](assets/fr/30.webp)

For å generere en Liquid-adresse, klikk på "*Receive*" knappen.

![LIQUID GREEN](assets/fr/31.webp)

Green vil da vise den første blanke mottaksadressen til lommeboken din. Du kan enten skanne den tilhørende QR-koden eller kopiere adressen direkte for å sende L-BTC til den.

![LIQUID GREEN](assets/fr/32.webp)

Når transaksjonen er kringkastet på nettverket, vil den vises i lommeboken din.

![LIQUID GREEN](assets/fr/33.webp)

Vent til du får nok bekreftelser for å anse transaksjonen som endelig. På Liquid bør bekreftelser være raske, ettersom en blokk publiseres hvert minutt.

![LIQUID GREEN](assets/fr/34.webp)
Med L-sats i din Liquid-lommebok, kan du nå også sende dem. Klikk på "*Send*".
![LIQUID GREEN](assets/fr/35.webp)

På neste side, skriv inn Liquid-adressen til mottakeren. Du kan skrive den inn manuelt eller skanne deres QR-kode.

![LIQUID GREEN](assets/fr/36.webp)

Velg beløpet for betalingen.

![LIQUID GREEN](assets/fr/37.webp)

Klikk på "*Neste*" for å få tilgang til en oppsummeringsskjerm av transaksjonen din. Sjekk at adressen, beløpet, og gebyrene er korrekte.

![LIQUID GREEN](assets/fr/38.webp)

Hvis alt ser bra ut for deg, skyv den grønne knappen nederst på skjermen til høyre for å signere og kringkaste transaksjonen på Bitcoin-nettverket.

![LIQUID GREEN](assets/fr/39.webp)

Transaksjonen din vil nå vises på dashbordet til din Bitcoin-lommebok i påvente av bekreftelse.

![LIQUID GREEN](assets/fr/40.webp)

Og der har du det, du vet nå hvordan du enkelt kan bruke Liquid sidekjeden med Blockstream Green-applikasjonen!

Hvis du fant denne veiledningen nyttig, ville jeg sette pris på en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

Jeg anbefaler også å oppdage denne andre komplette veiledningen om Blockstream Green mobilapp for å sette opp en onchain Bitcoin hot wallet:

https://planb.network/tutorials/wallet/blockstream-green