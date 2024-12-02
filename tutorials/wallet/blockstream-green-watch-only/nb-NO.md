---
name: Blockstream Green - Kun Visning
description: Oppsett av en lommebok kun for visning
---
![cover](assets/cover.webp)

I denne veiledningen vil du lære hvordan du enkelt kan sette opp en lommebok kun for visning på mobil ved hjelp av Blockstream Green-appen.

## Hva er en Lommebok Kun for Visning?

En lommebok kun for visning, eller "watch-only wallet," er en type programvare designet for å tillate brukeren å observere transaksjoner knyttet til en eller flere spesifikke Bitcoin offentlige nøkler, uten å ha tilgang til de tilsvarende private nøklene.

Denne typen applikasjon beholder kun dataene som er nødvendige for å overvåke en Bitcoin-lommebok, inkludert å se saldoen og transaksjonshistorikken, men den har ikke tilgang til de private nøklene. Derfor er det umulig å bruke bitcoins som er holdt i lommeboken på watch-only-appen.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Watch-only brukes generelt i tillegg til en maskinvarelommebok. Sistnevnte tillater sikker lagring av lommebokens private nøkler på en enhet som ikke er koblet til internett, som har en minimal angrepsflate, og isolerer dermed de private nøklene fra potensielt sårbare miljøer. Watch-only-appen, på den andre siden, lagrer utelukkende den utvidede offentlige nøkkelen (`xpub`, `zpub`, osv.) til Bitcoin-lommeboken. Denne overordnede nøkkelen tillater ikke oppdagelsen av de tilhørende private nøklene og, følgelig, tillater ikke bruk av bitcoins. Imidlertid tillater den derivasjon av barne offentlige nøkler og mottaksadresser. Med kunnskap om adressene til lommeboken sikret av maskinvarelommeboken, kan watch-only-appen spore disse transaksjonene på Bitcoin-nettverket, og tilby brukeren muligheten til å overvåke sin saldo og generere nye mottaksadresser, uten å måtte koble til sin maskinvarelommebok hver gang.

I denne veiledningen foreslår jeg å oppdage en av de mest populære løsningene for lommebok kun for visning på mobil: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Introduksjon til Blockstream Green

Blockstream Green er programvare tilgjengelig på mobil og datamaskin. Tidligere kjent som Green Address, ble denne lommeboken et Blockstream-prosjekt etter oppkjøpet i 2016.

Green er en veldig brukervennlig applikasjon, noe som gjør den spesielt egnet for nybegynnere. Den tilbyr ulike funksjoner, som forvaltning av hot wallets, maskinvarelommebøker, samt lommebøker på Liquid sidekjeden.

I denne veiledningen vil vi fokusere utelukkende på å opprette en lommebok kun for visning. For å utforske andre bruksområder av Green, inviterer jeg deg til å konsultere våre andre dedikerte veiledninger:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Installering og Oppsett av Blockstream Green-appen
Det første steget er naturligvis å laste ned Green-appen. Gå til appbutikken din:
- [For Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [For Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

For Android-brukere har du også muligheten til å installere appen via `.apk`-filen [tilgjengelig på Blockstreams GitHub](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Start appen, deretter kryss av i boksen "*Jeg aksepterer vilkårene...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Når du åpner Green for første gang, vises hjemskjermen uten en konfigurert lommebok. Senere, hvis du oppretter eller importerer lommebøker, vil de vises i dette grensesnittet. Før du går videre til å opprette en lommebok, råder jeg deg til å justere appens innstillinger i henhold til dine forventninger. Klikk på "*Applikasjonsinnstillinger*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

Alternativet "*Forbedret Personvern*", som kun er tilgjengelig på Android, forbedrer personvernet ved å deaktivere skjermbilder og skjule appforhåndsvisninger. Det låser også automatisk tilgangen til appen så snart telefonen din er låst, noe som gjør dataene dine vanskeligere å eksponere.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

For de som ønsker å forbedre sitt personvern, tilbyr appen å rute trafikken din gjennom Tor, et nettverk som krypterer alle dine tilkoblinger og gjør dine aktiviteter vanskelige å spore. Selv om dette alternativet kan senke appens ytelse noe, anbefales det sterkt for å beskytte ditt personvern, spesielt hvis du ikke bruker din egen fullnode.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

For brukere som har sin egen fullnode, tilbyr Green Wallet muligheten til å koble til den via en Electrum-server, noe som sikrer full kontroll over Bitcoin-nettverksinformasjon og transaksjonskringkasting.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Et annet alternativt trekk er "*SPV-verifisering*" alternativet, som tillater direkte verifisering av visse blockchain-data, og dermed reduserer behovet for å stole på Blockstreams standardnode, selv om denne metoden ikke gir alle garantier som en fullnode.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Når disse innstillingene er justert i henhold til dine behov, klikk på "*Lagre*" knappen og start appen på nytt.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Opprette en watch-only lommebok på Blockstream Green
Du er nå klar til å opprette en watch-only lommebok. Klikk på "*Kom i gang*" knappen.
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Du vil ha valget mellom flere typer lommebøker. For denne veiledningen ønsker vi å opprette en watch-only lommebok, så klikk på den tilsvarende knappen.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Velg "*Enkel Signatur*" alternativet.

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Velg deretter "*Bitcoin*". For min del gjennomfører jeg denne veiledningen på en testnet-lommebok, men prosedyren forblir den samme på hovednettet.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Du vil bli bedt om å oppgi enten en utvidet offentlig nøkkel (`xpub`, `zpub`, osv.), eller en output script descriptor.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Du må hente denne informasjonen fra lommeboken du ønsker å følge via din watch-only lommebok. Den utvidede offentlige nøkkelen er ikke sensitiv med tanke på sikkerhet, da den ikke gir tilgang til private nøkler, men den er sensitiv for ditt personvern, siden den avslører alle dine offentlige nøkler og derfor alle dine Bitcoin-transaksjoner.

Forestil deg at du bruker Sparrow Wallet for å håndtere lommeboken din på en maskinvarelommebok, vil du finne denne informasjonen i "*Innstillinger*" seksjonen. Å finne denne informasjonen vil avhenge av lommebokforvaltningsprogramvaren du bruker, men den finnes generelt i innstillingene.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Kopier din utvidede offentlige nøkkel og skriv den inn i Green-appen, deretter klikk på "*Koble til*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Du vil da kunne se saldoen knyttet til denne nøkkelen samt transaksjonshistorikken.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Ved å klikke på "*Motta*", kan du generere en mottaksadresse for å motta bitcoins på din maskinvarelommebok. Jeg råder imidlertid mot å bruke denne muligheten uten først å verifisere på skjermen til maskinvarelommeboken at den inneholder den private nøkkelen som er assosiert med den genererte adressen, før du bruker den til å låse bitcoins. Dette er en god praksis å følge.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

"*Sveip*" alternativet lar deg manuelt angi en privat nøkkel for å bruke midler direkte fra din Green-applikasjon. Bortsett fra i veldig spesifikke tilfeller, anbefaler jeg ikke å bruke denne funksjonen, da den krever at du avslører din private nøkkel på en telefon, som er mye mer sårbar for cyberangrep enn din maskinvarelommebok.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
Og der har du det, du vet nå hvordan du enkelt kan sette opp en watch-only lommebok på smarttelefonen din! Det er et veldig praktisk verktøy for å overvåke en lommebok på en maskinvarelommebok uten å måtte koble til og låse den opp hver gang.

Hvis du fant denne veiledningen nyttig, ville jeg sette pris på om du kunne legge igjen en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

Jeg anbefaler også å sjekke ut denne komplette veiledningen om Blockstream Green-applikasjonen for å sette opp en hot wallet:

https://planb.network/tutorials/wallet/blockstream-green