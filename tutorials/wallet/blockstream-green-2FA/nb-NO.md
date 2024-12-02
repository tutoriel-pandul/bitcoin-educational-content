---
name: Blockstream Green - 2FA
description: Oppsett av en 2/2 multisig på Green Wallet
---
![cover](assets/cover.webp)

En programvarelommebok er en applikasjon installert på en datamaskin, smarttelefon eller et annet enhet koblet til Internett, som tillater forvaltning og sikkerhet av ens Bitcoin-lommeboknøkler. I motsetning til maskinvarelommebøker, som isolerer private nøkler, opererer "varme" lommebøker dermed i et miljø potensielt eksponert for cyberangrep, noe som øker risikoen for hacking og tyveri.

Programvarelommebøker bør brukes til å håndtere rimelige mengder bitcoins, spesielt for daglige transaksjoner. Dette kan også være et interessant alternativ for personer med en begrenset Bitcoin-portefølje, for hvem det å investere i en maskinvarelommebok kan virke uforholdsmessig. Deres konstante eksponering for Internett gjør dem imidlertid mindre sikre for lagring av dine langsiktige sparepenger eller betydelige midler. For disse er det å foretrekke å velge sikrere løsninger, som maskinvarelommebøker.

I denne veiledningen vil jeg vise deg hvordan du kan forbedre sikkerheten til en varm lommebok ved å bruke "2FA"-alternativet på Blockstream Green.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Introduksjon til Blockstream Green

Blockstream Green er en programvarelommebok tilgjengelig på mobil og skrivebord. Tidligere kjent som *Green Address*, ble denne lommeboken et Blockstream-prosjekt etter oppkjøpet i 2016.

Green er en applikasjon som er spesielt enkel å bruke, noe som gjør den interessant for nybegynnere. Den tilbyr alle de essensielle funksjonene til en god Bitcoin-lommebok, inkludert RBF (*Replace-by-Fee*), et alternativ for å koble til via Tor, muligheten til å koble til sin egen node, SPV (*Simple Payment Verification*)-alternativet, merking og myntkontroll.

Blockstream Green støtter også Liquid-nettverket, en Bitcoin-sidekjede utviklet av Blockstream for å utføre raske og konfidensielle transaksjoner utenfor hovedblokkjeden. I denne veiledningen fokuserer vi utelukkende på Bitcoin, men jeg har også laget en annen veiledning for å lære hvordan du bruker Liquid på Green:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## 2/2 multisig (2FA)-alternativet

På Green kan du selvfølgelig opprette en klassisk "singlesig" varm lommebok. Men du har også "2FA multisig"-alternativet, som lar deg forbedre sikkerheten til din varme lommebok uten å overkomplisere dens daglige håndtering.
Du vil derfor sette opp en 2/2 multisig-lommebok, noe som betyr at hver transaksjon vil kreve signaturen til to nøkler. Den første nøkkelen, avledet fra din 12 eller 24-ords mnemonic-frase, er sikret lokalt med en PIN-kode på telefonen din. Du har full kontroll over denne nøkkelen. Den andre nøkkelen holdes av Blockstreams servere, og bruken av den for signering krever autentisering, som kan oppnås via en kode mottatt på e-post, SMS, telefonsamtale, eller, som vi vil se i denne veiledningen, via en autentiseringsapp (Authy, Google Authenticator, osv.).

For å sikre din autonomi i tilfelle en Blockstream-svikt (for eksempel, hvis selskapet går konkurs eller serverne som holder den andre nøkkelen blir ødelagt), anvendes en tidsbegrensningsmekanisme på din multisig. Denne mekanismen transformerer 2/2 multisig til en 1/2 multisig etter omtrent ett år (eller nøyaktig 51,840 blokker, men denne verdien kan endres), hvoretter lommeboken din bare vil trenge din lokale nøkkel for å bruke bitcoins. Så, hvis du mister tilgangen til Blockstreams servere eller til 2FA-autentisering, trenger du bare å vente opptil et år for å kunne fritt bruke dine bitcoins med appen din, uten å være avhengig av Blockstream.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
Denne metoden øker betydelig sikkerheten til din varme lommebok, samtidig som du beholder kontrollen over dine bitcoins og letter daglig bruk. Det krever imidlertid regelmessig oppdatering av tidsbegrensningen for å opprettholde sikkerheten til 2FA. Den 360-dagers nedtellingen, hvor dine midler er beskyttet av 2FA, starter så snart du mottar bitcoins. Hvis du, 360 dager etter å ha mottatt dem, ikke har gjort en transaksjon som bruker disse midlene, vil dine bitcoins kun være beskyttet av din lokale nøkkel, uten 2FA.

Denne begrensningen gjør 2FA-alternativet mer egnet for en utgiftslommebok, hvor regelmessige transaksjoner automatisk fornyer tidsbegrensningene. For en langsiktig sparelommebok kan dette være problematisk, da du må tenke på å utføre en feiingstransaksjon til deg selv hvert år før tidsbegrensningen utløper.

En annen ulempe med denne sikkerhetsmetoden er at du må bruke minoritets skriptmønstre. Dette betyr at, fra et personvernperspektiv, blir ting kompliserte: veldig få personer bruker samme type skript som deg, noe som gjør det lettere for en ekstern observatør å identifisere fotavtrykket til lommeboken din. I tillegg vil disse skriptene resultere i høyere transaksjonsgebyrer på grunn av deres større størrelse.
Hvis du foretrekker å ikke bruke 2FA-alternativet og bare ønsker å sette opp en "singlesig" lommebok på Green, inviterer jeg deg til å sjekke ut denne andre opplæringen:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Installere og sette opp Blockstream Green-programvare

Det første steget er naturligvis å laste ned Green-appen. Gå til appbutikken din:
- [For Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [For Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

For Android-brukere har du også muligheten til å installere appen via `.apk`-filen [tilgjengelig på Blockstreams GitHub](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Start appen, og kryss av i boksen "*Jeg aksepterer vilkårene...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Når du åpner Green for første gang, vises hjemmeskjermen uten noen konfigurert lommebok. Senere, hvis du oppretter eller importerer lommebøker, vil de vises i dette grensesnittet. Før du går videre til å opprette en lommebok, råder jeg deg til å justere appinnstillingene i henhold til dine forventninger. Klikk på "*Applikasjonsinnstillinger*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

"*Forbedret personvern*" alternativet, tilgjengelig kun på Android, forbedrer personvernet ved å deaktivere skjermbilder og skjule appforhåndsvisninger. Det låser også automatisk tilgangen til appen så snart telefonen din er låst, noe som gjør dataene dine vanskeligere å eksponere.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

For de som ønsker å forbedre sitt personvern, tilbyr appen å rute trafikken din gjennom Tor, et nettverk som krypterer alle dine tilkoblinger og gjør dine aktiviteter vanskelige å spore. Selv om dette alternativet kan bremse appens ytelse noe, er det sterkt anbefalt for å beskytte ditt personvern, spesielt hvis du ikke bruker din egen fullnode.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

For brukere som har sin egen fullnode, tilbyr Green Wallet muligheten til å koble til den via en Electrum-server, noe som sikrer full kontroll over Bitcoin-nettverksinformasjon og transaksjonssending.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
En annen alternativ funksjon er "*SPV-verifisering*" alternativet, som tillater direkte verifisering av visse blockchain-data, og dermed reduserer behovet for å stole på Blockstreams standard node, selv om denne metoden ikke gir alle garantier som en full node.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Når disse innstillingene er justert i henhold til dine behov, klikk på "*Lagre*" knappen og start applikasjonen på nytt.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Opprette en Bitcoin-lommebok på Blockstream Green

Du er nå klar til å opprette en Bitcoin-lommebok. Klikk på "*Kom i gang*" knappen.

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Du har valget mellom å opprette en programvarelommebok lokalt eller å administrere en kald lommebok via en maskinvarelommebok. For denne veiledningen vil vi fokusere på å opprette en varm lommebok, så du må velge "*På denne enheten*" alternativet.

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Deretter kan du velge å gjenopprette en eksisterende Bitcoin-lommebok eller opprette en ny. For formålet med denne veiledningen, vil vi opprette en ny lommebok. Men, hvis du trenger å regenerere en eksisterende Bitcoin-lommebok fra dens mnemoniske frase, for eksempel på grunn av tap av din gamle telefon, må du velge det andre alternativet.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Du har deretter valget mellom en 12-ords eller 24-ords mnemonisk frase. Denne frasen vil tillate deg å gjenopprette tilgang til lommeboken din fra hvilken som helst kompatibel programvare i tilfelle problemer med telefonen din. For øyeblikket tilbyr ikke valget av en 24-ords frase mer sikkerhet enn en 12-ords frase. Derfor anbefaler jeg å velge en **12-ords** mnemonisk frase.

Green vil deretter gi deg din mnemoniske frase. Før du fortsetter, sørg for at du ikke blir observert. Klikk på "*Vis gjenopprettingsfrase*" for å vise den på skjermen.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**Denne mnemoniske frasen gir fullstendig og ubegrenset tilgang til alle dine bitcoins**. Enhver som er i besittelse av denne frasen kan stjele dine midler, selv uten fysisk tilgang til telefonen din (under forutsetning av utløpt tidsbegrensning eller 2FA i tilfellet av en 2/2 lommebok på Green).

Den lar deg gjenopprette tilgang til dine lokale nøkler i tilfelle tap, tyveri eller skade på telefonen din. Det er derfor veldig viktig å nøye lagre den **på et fysisk medium (ikke digitalt)** og å oppbevare det på et sikkert sted. Du kan skrive det ned på et stykke papir, eller for mer sikkerhet, hvis denne lommeboken er viktig, anbefaler jeg å gravere den på et rustfritt stålmedium for å beskytte mot risikoer som branner, flommer eller kollapser (for en varm lommebok ment for å sikre en liten mengde bitcoins, er en enkel papirbackup sannsynligvis tilstrekkelig).
*Selvfølgelig, du bør aldri dele disse ordene på internett, i motsetning til det jeg gjør i denne veiledningen. Denne eksempellommeboken vil kun bli brukt på Testnet og vil bli slettet ved slutten av veiledningen.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Etter å ha korrekt notert din mnemoniske frase på et fysisk medium, klikk på "*Fortsett*". Green Wallet vil deretter be deg om å bekrefte noen ord fra frasen din for å verifisere at du har registrert dem korrekt. Fyll inn de tomme feltene med de manglende ordene.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Velg PIN-koden for enheten din, som vil bli brukt til å låse opp din Green-lommebok. Det er derfor en beskyttelse mot uautorisert fysisk tilgang. Denne PIN-koden spiller ikke en rolle i utledningen av lommebokens kryptografiske nøkler. Således, selv uten tilgang til denne PIN-koden, vil besittelsen av din 12 eller 24-ords mnemonic frase tillate deg å gjenopprette tilgang til dine lokale nøkler.
Det anbefales å velge en 6-sifret PIN-kode så tilfeldig som mulig. Også, sørg for å lagre denne koden slik at du ikke glemmer den, ellers vil du bli tvunget til å gjenopprette lommeboken din fra mnemonic frasen. Du kan senere legge til en mulighet for biometrisk låsing for å unngå å måtte angi PIN-koden hver gang. Generelt sett er biometri mye mindre sikkert enn PIN-koden i seg selv. Derfor råder jeg som standard mot å sette opp denne låseopsjonen.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Skriv inn PIN-koden din en andre gang for å bekrefte den.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Vent mens lommeboken din blir opprettet, deretter klikk på "*Opprett en konto*" knappen.

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Du har da valget mellom en standard enkeltsignatur-lommebok eller en lommebok beskyttet av tofaktorautentisering (2FA). I denne veiledningen vil vi velge det andre alternativet.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

Og der har du det, din Bitcoin multisig-lommebok har blitt vellykket opprettet ved bruk av Green-appen!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Sette opp 2FA

Klikk på kontoen din.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Klikk på den grønne knappen "*Øk sikkerheten til kontoen din ved å legge til 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Du vil da ha muligheten til å velge autentiseringsmetoden for å få tilgang til den andre nøkkelen i din 2/2 multisig. For denne veiledningen vil vi bruke en autentiseringsapp. Hvis du ikke er kjent med denne typen app, anbefaler jeg å konsultere vår veiledning om Authy:
https://planb.network/tutorials/others/authy

Velg "*Autentiseringsapplikasjon*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green vil deretter vise en QR-kode og en gjenopprettingsnøkkel. Denne nøkkelen lar deg gjenopprette tilgang til din 2FA i tilfelle du mister Authy-appen din. Det anbefales å lage en sikker sikkerhetskopi av denne nøkkelen, selv om du alltid kan gjenopprette tilgang til dine bitcoins etter utløpet av tidslåsen, som forklart tidligere.

I autentiseringsappen din, legg til en ny kode, deretter skann QR-koden som Green har gitt.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Selvfølgelig, du bør aldri dele denne nøkkelen og QR-koden på internett, i motsetning til hva jeg gjør i denne veiledningen. Denne eksempellommeboken vil kun bli brukt på Testnet og vil bli slettet ved slutten av veiledningen.*

Klikk på "*Fortsett*" knappen.

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Skriv inn den dynamiske 6-sifrede koden som er til stede på autentiseringsappen din.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

Tofaktorautentisering er nå aktivert.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Ved å bla gjennom denne menyen kan du også justere varigheten på tidslåsen. Denne nedtellingen starter når du mottar bitcoins, og når tidslåsen utløper, kan midlene dine kun brukes med din lokale nøkkel, uten å kreve 2FA. Standard varighet er satt til 12 måneder, men for en sparelommebok kan det være lurt å velge 15 måneder for å minimere frekvensen av fornyelser av tidslåsen. På den annen side, for en brukslommebok, kan en tidslås på 6 måneder være å foretrekke, da den vil bli ofte fornyet med dine daglige transaksjoner, og en kortere tidslås reduserer ventetiden i tilfelle problemer med 2FA. Det er opp til deg å bestemme varigheten av tidslåsen som passer deg best.
![GREEN 2FA MULTISIG](assets/fr/30.webp)

Du kan nå forlate denne menyen. Din multisig-lommebok er klar!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Sette opp lommeboken din på Blockstream Green

Hvis du ønsker å tilpasse lommeboken din, klikk på de tre små prikkene øverst til høyre.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
"*Rename*" alternativet lar deg tilpasse navnet på lommeboken din, noe som er spesielt nyttig hvis du administrerer flere lommebøker i samme applikasjon.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

"*Unit*" menyen gir deg muligheten til å endre basisenheten for lommeboken din. For eksempel kan du velge å vise den i satoshis i stedet for i bitcoins.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

"*Settings*" menyen gir tilgang til de forskjellige alternativene for din Bitcoin-lommebok.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Her vil du for eksempel finne din utvidede offentlige nøkkel og dens *descriptor*, nyttig hvis du planlegger å sette opp en watch-only lommebok fra denne lommeboken.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

Du kan også endre PIN-koden til lommeboken din og aktivere biometrisk innlogging.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Bruke Blockstream Green

Nå som din Bitcoin-lommebok er satt opp, er du klar til å motta dine første sats! For å gjøre dette, klikk bare på "*Receive*" knappen.

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green vil da vise den første blanke mottaksadressen til lommeboken din. Du kan enten skanne den tilknyttede QR-koden eller kopiere adressen direkte for å sende bitcoins til den. Denne typen adresse spesifiserer ikke beløpet som skal sendes av betaleren. Imidlertid kan du generere en adresse som ber om et spesifikt beløp, ved å klikke på de tre små prikkene øverst til høyre, deretter på "*Request Amount*", og angi ønsket beløp.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Når transaksjonen er kringkastet på nettverket, vil den vises i lommeboken din.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Vent til du får nok bekreftelser for å anse transaksjonen som endelig.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

Med bitcoins i lommeboken din, kan du nå også sende dem. Klikk på "*Send*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

På den følgende siden, angi mottakerens adresse. Du kan angi den manuelt eller skanne en QR-kode.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Velg betalingsbeløpet.
![GREEN 2FA MULTISIG](assets/fr/44.webp)Nederst på skjermen kan du velge gebyrsatsen for denne transaksjonen. Du har muligheten til å følge applikasjonens anbefalinger eller tilpasse dine egne gebyrer. Jo høyere gebyrene sammenlignet med andre ventende transaksjoner, desto raskere vil transaksjonen din bli behandlet. For å forstå gebyrmarkedet, kan du besøke [Mempool.space](https://mempool.space/) i "*Transaction Fees*" seksjonen.
![GREEN 2FA MULTISIG](assets/fr/45.webp)

Klikk på "*Neste*" for å få tilgang til en oppsummeringsskjerm for transaksjonen din. Verifiser at adressen, beløpet, og gebyrene er korrekte.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Hvis alt ser bra ut for deg, skyv den grønne knappen nederst på skjermen til høyre for å signere og kringkaste transaksjonen på Bitcoin-nettverket.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

Dette er øyeblikket når du må angi din autentiseringskode for å låse opp den andre nøkkelen av multisig som holdes av Blockstream. Skriv inn den 6-sifrede koden som vises på din autentiseringsapp.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Transaksjonen din vil nå vises på dashbordet til din Bitcoin-lommebok i påvente av bekreftelse.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

Og der har du det, nå vet du hvordan du enkelt kan sette opp en 2/2 multisig-lommebok ved å bruke Blockstream Greens 2FA-alternativ!

Hvis du fant denne veiledningen nyttig, ville jeg sette pris på det hvis du kunne legge igjen en grønn tommel nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

Jeg anbefaler også å sjekke ut denne andre komplette veiledningen om Blockstream Green mobilapp for å sette opp en Liquid-lommebok:

https://planb.network/tutorials/wallet/blockstream-green-liquid