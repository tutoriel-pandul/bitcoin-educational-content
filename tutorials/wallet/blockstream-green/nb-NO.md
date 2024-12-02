---
name: Blockstream Green - Mobil
description: Oppsett av en mobil programvarelommebok
---
![cover](assets/cover.webp)

En programvarelommebok er en applikasjon installert på en datamaskin, smarttelefon eller et annet apparat koblet til Internett, som tillater forvaltning og sikring av ens Bitcoin-lommeboknøkler. I motsetning til maskinvarelommebøker, som isolerer private nøkler, opererer "varme" lommebøker dermed i et miljø som potensielt kan være eksponert for cyberangrep, noe som øker risikoen for hacking og tyveri.

Programvarelommebøker er ment for å håndtere rimelige mengder bitcoins, spesielt for daglige transaksjoner. Dette kan også være et interessant alternativ for personer med en begrenset Bitcoin-portefølje, for hvem det å investere i en maskinvarelommebok kan virke uforholdsmessig. Deres konstante eksponering for Internett gjør dem imidlertid mindre sikre for lagring av dine langsiktige sparepenger eller betydelige midler. For disse er det å foretrekke å velge mer sikre løsninger, som maskinvarelommebøker.

I denne veiledningen vil jeg introdusere deg for en av de beste løsningene for mobil programvarelommebok: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Hvis du er interessert i å lære hvordan du bruker Blockstream Green på en datamaskin, vennligst se denne andre veiledningen:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Introduksjon til Blockstream Green

Blockstream Green er en programvarelommebok tilgjengelig både på mobil og datamaskin. Tidligere kjent som *Green Address*, ble denne lommeboken et Blockstream-prosjekt etter oppkjøpet i 2016.

Green er en applikasjon som er spesielt enkel å bruke, noe som gjør den interessant for nybegynnere. Den tilbyr alle de essensielle funksjonene til en god Bitcoin-lommebok, inkludert RBF (*Replace-by-Fee*), en mulighet til å koble til via Tor, evnen til å koble til ens egen node, SPV (*Simple Payment Verification*)-alternativet, merking og myntkontroll.

Blockstream Green støtter også Liquid-nettverket, en Bitcoin-sidekjede utviklet av Blockstream for å utføre raske og konfidensielle transaksjoner utenfor hovedblokkjeden. Denne veiledningen fokuserer utelukkende på Bitcoin, men en fremtidig vil adressere bruken av Liquid.

## Installering og Oppsett av Blockstream Green-appen

Det første steget er naturligvis å laste ned Green-appen. Gå til appbutikken din:
- [For Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [For Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

For Android-brukere har du også muligheten til å installere applikasjonen via `.apk`-filen [tilgjengelig på Blockstreams GitHub](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Start applikasjonen, deretter kryss av i boksen "*Jeg aksepterer vilkårene...*".
![GREEN](assets/fr/04.webp)

Når du åpner Green for første gang, vises hjemmeskjermen uten noen konfigurerte lommebøker. Senere, hvis du oppretter eller importerer lommebøker, vil de vises i dette grensesnittet. Før du går videre til å opprette en lommebok, råder jeg deg til å justere applikasjonsinnstillingene i henhold til dine forventninger. Klikk på "*Applikasjonsinnstillinger*".

![GREEN](assets/fr/05.webp)

"*Forbedret Personvern*" alternativet, tilgjengelig kun på Android, forbedrer personvernet ved å deaktivere skjermbilder og skjule applikasjonsforhåndsvisninger. Det låser også automatisk tilgangen til applikasjonen så snart telefonen din er låst, noe som gjør dataene dine vanskeligere å eksponere.

![GREEN](assets/fr/06.webp)
For de som ønsker å forbedre sitt personvern, tilbyr applikasjonen å rute trafikken din via Tor, et nettverk som krypterer alle dine tilkoblinger og gjør dine aktiviteter vanskelige å spore. Selv om dette alternativet kan senke applikasjonens ytelse noe, er det sterkt anbefalt for å beskytte ditt personvern, spesielt hvis du ikke bruker din egen fullstendige node.
![GREEN](assets/fr/07.webp)

For brukere som har sin egen fullstendige node, tilbyr Green Wallet muligheten til å koble til den via en Electrum-server, noe som sikrer full kontroll over Bitcoin-nettverksinformasjon og transmisjon av transaksjoner.

![GREEN](assets/fr/08.webp)

Et annet alternativt trekk er "*SPV-verifisering*" alternativet, som tillater direkte verifisering av visse blockchain-data, og dermed reduserer behovet for å stole på den standard Blockstream-noden, selv om denne metoden ikke gir alle garantier som en fullstendig node.

![GREEN](assets/fr/09.webp)

Når disse innstillingene er justert i henhold til dine behov, klikk på "*Lagre*" knappen og start applikasjonen på nytt.

![GREEN](assets/fr/10.webp)

## Opprette en Bitcoin-lommebok på Blockstream Green

Du er nå klar til å opprette en Bitcoin-lommebok. Klikk på "*Kom i gang*" knappen.

![GREEN](assets/fr/11.webp)

Du har valget mellom å opprette en programvarelommebok lokalt eller å administrere en kald lommebok via en maskinvarelommebok. For denne veiledningen vil vi fokusere på å opprette en varm lommebok, så du må velge "*På denne enheten*" alternativet. I en fremtidig veiledning vil jeg vise deg hvordan du bruker det andre alternativet.

"*Kun-visning*" alternativet, på den andre siden, lar deg importere en utvidet offentlig nøkkel (`xpub`) for å se transaksjoner av en lommebok uten å kunne bruke de tilknyttede midlene, noe som er praktisk for å overvåke en lommebok på en maskinvarelommebok, for eksempel.

![GREEN](assets/fr/12.webp)
Du kan deretter velge å gjenopprette en eksisterende Bitcoin-lommebok eller opprette en ny. For formålet med denne veiledningen, vil vi opprette en ny lommebok. Men, hvis du trenger å regenerere en allerede eksisterende Bitcoin-lommebok fra dens mnemoniske frase, for eksempel på grunn av tap av din maskinvarelommebok, må du velge det andre alternativet.
![GREEN](assets/fr/13.webp)

Du har deretter valget mellom en 12-ords eller 24-ords mnemonisk frase. Denne frasen vil tillate deg å gjenopprette tilgang til lommeboken din fra hvilken som helst kompatibel programvare i tilfelle problemer med telefonen din. For øyeblikket tilbyr ikke valget av en 24-ords frase mer sikkerhet enn en 12-ords frase. Derfor anbefaler jeg å velge en **12-ords** mnemonisk frase.

Green vil deretter gi deg din mnemoniske frase. Før du fortsetter, sørg for at du ikke blir observert. Klikk på "*Vis gjenopprettingsfrase*" for å vise den på skjermen.

![GREEN](assets/fr/14.webp)

**Denne mnemoniske frasen gir full og ubegrenset tilgang til alle dine bitcoins.** Enhver som er i besittelse av denne frasen kan stjele dine midler, selv uten fysisk tilgang til telefonen din.

Den lar deg gjenopprette tilgang til dine bitcoins i tilfelle tap, tyveri, eller skade på telefonen din. Det er derfor veldig viktig å nøye lagre den **på et fysisk medium (ikke digitalt)** og å oppbevare det på et sikkert sted. Du kan skrive det ned på et stykke papir, eller for mer sikkerhet, hvis denne lommeboken er viktig, anbefaler jeg å gravere den på et rustfritt stålmedium for å beskytte mot risikoer som branner, flommer, eller kollapser (for en varm lommebok ment for å sikre en liten mengde bitcoins, er en enkel papirkopi sannsynligvis tilstrekkelig).
*Åpenbart bør du aldri dele disse ordene på internett, i motsetning til det jeg gjør i denne opplæringen. Denne eksempellommeboken vil kun bli brukt på Testnet og vil bli slettet ved slutten av opplæringen.*
![GREEN](assets/fr/15.webp)

Etter å ha korrekt notert din mnemonic frase på et fysisk medium, klikk på "*Fortsett*". Green Wallet vil deretter be deg om å bekrefte visse ord fra din frase for å verifisere at du har notert dem korrekt. Fyll inn de tomme feltene med de manglende ordene.

![GREEN](assets/fr/16.webp)

Velg PIN-koden for enheten din, som vil bli brukt for å låse opp din Green-lommebok. Dette er derfor en beskyttelse mot uautorisert fysisk tilgang. Denne PIN-koden spiller ikke en rolle i derivasjonen av de kryptografiske nøklene til lommeboken din. Således, selv uten tilgang til denne PIN-koden, vil besittelsen av din 12 eller 24-ords mnemonic frase tillate deg å gjenvinne tilgang til dine bitcoins.
Det anbefales å velge en 6-sifret PIN som er så tilfeldig som mulig. Også, sørg for å sikkerhetskopiere denne koden slik at du ikke glemmer den, ellers vil du bli tvunget til å gjenopprette lommeboken din ved hjelp av mnemonic frasen. Etterfølgende kan du legge til en biometrisk låseopsjon for å unngå å måtte taste inn PIN-koden ved hvert bruk. Generelt sett er biometri mye mindre sikker enn PIN-koden selv. Derfor, som standard, råder jeg mot å sette opp denne låseopsjonen.
![GREEN](assets/fr/17.webp)

Tast inn din PIN en andre gang for å bekrefte den.

![GREEN](assets/fr/18.webp)

Vent på at lommeboken din blir opprettet, deretter klikk på "*Opprett en konto*" knappen.

![GREEN](assets/fr/19.webp)

Du har da valget mellom en standard enkeltsignatur-lommebok, som vi vil bruke i denne opplæringen, eller en lommebok beskyttet av tofaktorautentisering (2FA).

![GREEN](assets/fr/20.webp)

2FA-opsjonen på Green skaper en 2/2 multisignatur-lommebok, hvorav en nøkkel oppbevares av Blockstream. Dette betyr at for å gjøre en transaksjon, kreves begge nøkler: en lokal nøkkel beskyttet av din PIN på telefonen din, og en fjernnøkkel sikret av 2FA på Blockstreams servere. I tilfelle tap av tilgang til 2FA eller utilgjengelighet av Blockstreams tjenester, sikrer gjenopprettingsmekanismer basert på tidsbegrensede skript muligheten for å uavhengig gjenopprette dine midler. Selv om denne oppsettet betydelig reduserer risikoen for at dine bitcoins blir stjålet, er det mer komplekst å håndtere og delvis avhengig av Blockstream. For denne opplæringen vil vi velge en klassisk enkeltsignatur-lommebok, med nøkler lagret lokalt på telefonen.

Og der har du det, din Bitcoin-lommebok har blitt vellykket opprettet ved bruk av Green-appen!

![GREEN](assets/fr/21.webp)

Før du mottar dine første bitcoins i lommeboken din, **råder jeg deg sterkt til å utføre en tørrkjøringsgjenopprettingstest**. Noter en referanseinformasjon, som din xpub eller den første mottaksadressen, deretter slett lommeboken din på Green-appen mens den fortsatt er tom. Prøv deretter å gjenopprette lommeboken din på Green ved hjelp av dine papirbackuper. Sjekk at vitneinformasjonen som genereres etter gjenopprettingen matcher den du opprinnelig noterte. Hvis dette er tilfellet, kan du være sikker på at dine papirbackuper er pålitelige. For å lære mer om hvordan du utfører en gjenopprettingstest, råder jeg deg til å konsultere denne andre opplæringen:

https://planb.network/tutorials/wallet/recovery-test

## Sette opp lommeboken din på Blockstream Green
Hvis du ønsker å tilpasse porteføljen din, klikk på de tre små prikkene øverst til høyre.
![GREEN](assets/fr/22.webp)
"*Gi nytt navn*" alternativet lar deg tilpasse navnet på porteføljen din, noe som er spesielt nyttig hvis du forvalter flere porteføljer i samme app.
![GREEN](assets/fr/23.webp)

"*Enhet*" menyen gir deg muligheten til å endre basisenheten for porteføljen din. For eksempel kan du velge å vise den i satoshis i stedet for i bitcoins.

![GREEN](assets/fr/24.webp)

"*Innstillinger*" menyen gir tilgang til de forskjellige valgene for din Bitcoin-lommebok.

![GREEN](assets/fr/25.webp)

Her vil du for eksempel finne din utvidede offentlige nøkkel og dens *descriptor*, nyttig hvis du planlegger å sette opp en watch-only lommebok fra denne lommeboken.

![GREEN](assets/fr/26.webp)

Du kan også endre PIN-koden til lommeboken din og aktivere biometrisk innlogging.

![GREEN](assets/fr/27.webp)

## Bruke Blockstream Green

Nå som din Bitcoin-lommebok er satt opp, er du klar til å motta dine første sats! For å gjøre dette, klikk ganske enkelt på "*Motta*" knappen.

![GREEN](assets/fr/28.webp)

Green vil da vise den første tomme mottaksadressen til lommeboken din. Du kan enten skanne den tilhørende QR-koden eller kopiere adressen direkte for å sende bitcoins til den. Denne typen adresse spesifiserer ikke beløpet som skal sendes av betaleren. Imidlertid kan du generere en adresse som ber om et spesifikt beløp, ved å klikke på de tre små prikkene øverst til høyre, deretter på "*Be om beløp*", og angi ønsket beløp.

Siden du bruker en Segwit v0 konto (BIP84), vil adressen din starte med `bc1q...`. I mitt eksempel bruker jeg en Testnet-lommebok, så prefikset er litt annerledes.

![GREEN](assets/fr/29.webp)

Når transaksjonen er kringkastet på nettverket, vil den vises i lommeboken din.

![GREEN](assets/fr/30.webp)

Vent til du får nok bekreftelser for å anse transaksjonen som endelig.

![GREEN](assets/fr/31.webp)

Med bitcoins i lommeboken din, kan du nå også sende dem. Klikk på "*Send*".

![GREEN](assets/fr/32.webp)

På neste side, angi mottakerens adresse. Du kan skrive den inn manuelt eller skanne en QR-kode.

![GREEN](assets/fr/33.webp)

Velg betalingsbeløpet.

![GREEN](assets/fr/34.webp)
Nederst på skjermen kan du velge gebyrsatsen for denne transaksjonen. Du har muligheten til å følge applikasjonens anbefalinger eller tilpasse dine egne gebyrer. Jo høyere gebyrene sammenlignet med andre ventende transaksjoner, jo raskere vil transaksjonen din bli behandlet. For å forstå gebyrmarkedet, kan du besøke [Mempool.space](https://mempool.space/) i "*Transaksjonsgebyrer*" seksjonen.
![GREEN](assets/fr/35.webp)

Klikk på "*Neste*" for å få tilgang til en oppsummeringsskjerm av transaksjonen din. Verifiser at adressen, beløpet og gebyrene er korrekte.

![GREEN](assets/fr/36.webp)

Hvis alt er til din tilfredshet, skyv den grønne knappen nederst på skjermen til høyre for å signere og kringkaste transaksjonen på Bitcoin-nettverket.

![GREEN](assets/fr/37.webp)

Transaksjonen din vil nå vises på dashbordet til din Bitcoin-lommebok i påvente av bekreftelse.

![GREEN](assets/fr/38.webp)
*Denne opplæringen er basert på [en original versjon som tilhører Bitstack](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) skrevet av Loïc Morel. Bitstack er en fransk Bitcoin neo-bank som tilbyr muligheten til å spare i bitcoins, enten gjennom DCA (Dollar Cost Averaging) eller via et automatisk avrundingssystem for daglige utgifter.*