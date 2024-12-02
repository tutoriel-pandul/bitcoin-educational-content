---
name: Blockstream Green - Desktop
description: Bruk av Green Wallet-programvaren på en datamaskin
---
![cover](assets/cover.webp)

I denne veiledningen skal vi utforske hvordan man bruker Blockstream Green-programvaren på en datamaskin for å håndtere en sikker lommebok på en maskinvarelommebok. Når du bruker en maskinvarelommebok, er det essensielt å bruke programvare på datamaskinen din for å håndtere denne lommeboken. Denne styringsprogramvaren har ikke tilgang til de private nøklene; den brukes kun for å sjekke saldoen i lommeboken din, generere mottaksadresser, og konstruere og kringkaste transaksjoner som vil bli signert av maskinvarelommeboken. Green representerer en av de mange løsningene som er tilgjengelige for å håndtere din Bitcoin maskinvarelommebok.

I 2024 er Blockstream Green kun kompatibel med Ledger Nano S (eldre versjon), Ledger Nano X, Trezor One, Trezor T, og Blockstream Jade-enheter.

## Introduksjon til Blockstream Green

Blockstream Green er programvare tilgjengelig på både mobil og desktop. Tidligere kjent som Green Address, ble denne lommeboken et Blockstream-prosjekt etter oppkjøpet i 2016.

Green er en veldig brukervennlig applikasjon, noe som gjør den spesielt egnet for nybegynnere. Den tilbyr ulike funksjoner, som håndtering av hot wallets, maskinvarelommebøker, samt lommebøker på Liquid sidekjeden. Du kan også bruke den til å sette opp en watch-only lommebok.

![GREEN-DESKTOP](assets/fr/01.webp)

I denne veiledningen vil vi fokusere utelukkende på bruk av programvaren på en datamaskin. For å utforske andre bruksområder av Green, inviterer jeg deg til å sjekke ut våre andre dedikerte veiledninger:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Installering og Oppsett av Blockstream Green-programvaren

Start med å installere Blockstream Green-programvaren på datamaskinen din. Gå til [den offisielle nettsiden](https://blockstream.com/green/) og klikk på "*Last ned nå*" knappen. Følg deretter installasjonsprosessen i henhold til ditt operativsystem.

![GREEN-DESKTOP](assets/fr/02.webp)

Start applikasjonen, og kryss av i boksen "*Jeg aksepterer vilkårene...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Når du åpner Green for første gang, vises hjemmeskjermen uten noen konfigurert lommebok. Senere, hvis du oppretter eller importerer lommebøker, vil de vises i dette grensesnittet. Før du går videre til å opprette en lommebok, råder jeg deg til å justere applikasjonens innstillinger i henhold til dine forventninger. Klikk på innstillingsikonet nederst til venstre.

![GREEN-DESKTOP](assets/fr/04.webp)

I "*Generelt*" menyen kan du endre programvarespråket og aktivere eksperimentelle funksjoner hvis du ønsker.

![GREEN-DESKTOP](assets/fr/05.webp)
I "*Nettverk*" menyen kan du aktivere tilkobling via Tor, et nettverk som krypterer alle dine tilkoblinger og gjør dine aktiviteter vanskelige å spore. Selv om dette alternativet kan senke applikasjonens ytelse noe, anbefales det sterkt for å beskytte ditt privatliv, spesielt hvis du ikke bruker din egen full node.
![GREEN-DESKTOP](assets/fr/06.webp)

For brukere som har sin egen full node, tilbyr Green muligheten til å koble til den via en Electrum-server, noe som sikrer full kontroll over Bitcoin-nettverksinformasjon og transaksjonskasting. For å gjøre dette, klikk på "*Egendefinerte servere og validering*" menyen, og skriv inn informasjonen til din Electrum-server.

![GREEN-DESKTOP](assets/fr/07.webp)
Et annet alternativ er "*SPV-verifisering*" som tillater direkte verifisering av visse blockchain-data, og dermed reduserer behovet for å stole på Blockstreams standardnode, selv om denne metoden ikke gir alle garantier som en full node. Dette alternativet finnes også under "*Egendefinerte servere og validering*" menyen.
![GREEN-DESKTOP](assets/fr/08.webp)

Når disse innstillingene er justert i henhold til dine behov, kan du forlate dette grensesnittet.

## Importere en Bitcoin-lommebok til Blockstream Green

Du er nå klar til å importere din Bitcoin-lommebok. Klikk på "**Kom i gang**"-knappen.

![GREEN-DESKTOP](assets/fr/09.webp)

Du har valget mellom å opprette en lokal programvarelommebok eller å håndtere en kald lommebok via en maskinvarelommebok. For denne veiledningen vil vi fokusere på håndtering av en maskinvarelommebok, så du må velge "*På maskinvarelommebok*" alternativet.

"*Kun-visning*" alternativet, på den andre siden, lar deg importere en utvidet offentlig nøkkel (`xpub`) for å se transaksjonene til en lommebok uten å kunne bruke de tilknyttede midlene.

![GREEN-DESKTOP](assets/fr/10.webp)

Hvis du bruker en Jade, klikk på den tilsvarende knappen. Ellers velg "*Koble til en annen maskinvareenhet*". I mitt tilfelle bruker jeg en Ledger Nano S. For Ledger-brukere, sørg for å installere "*Bitcoin Legacy*" applikasjonen på din maskinvarelommebok, ettersom Green kun støtter denne versjonen.

![GREEN-DESKTOP](assets/fr/11.webp)

Koble din maskinvarelommebok til datamaskinen og velg den på Green.

![GREEN-DESKTOP](assets/fr/12.webp)

Vent mens Green importerer informasjonen fra lommeboken din, hvoretter du vil kunne få tilgang til den.

![GREEN-DESKTOP](assets/fr/13.webp)

På dette tidspunktet er to scenarioer mulige. Hvis du allerede hadde brukt maskinvarelommeboken din før, bør du se kontoen din dukke opp i programvaren. Men hvis, som meg, du nettopp har initialisert maskinvarelommeboken din ved å generere en mnemonic frase uten å ha brukt den ennå, må du opprette en konto. Klikk på "*Opprett konto*".
![GREEN-DESKTOP](assets/fr/14.webp)
Velg "*Standard*" hvis du ønsker å bruke en klassisk lommebok.

![GREEN-DESKTOP](assets/fr/15.webp)

Du har nå tilgang til kontoen din.

![GREEN-DESKTOP](assets/fr/16.webp)

## Bruke en maskinvarelommebok med Blockstream Green

Nå som din Bitcoin-lommebok er satt opp, er du klar til å motta dine første sats! For å gjøre dette, klikk bare på "*Motta*" knappen.

![GREEN-DESKTOP](assets/fr/17.webp)

Klikk på "*Kopier adresse*" knappen for å kopiere adressen, eller skann dens QR-kode.

![GREEN-DESKTOP](assets/fr/18.webp)

Når transaksjonen er kringkastet på nettverket, vil den vises i lommeboken din. Vent til du får nok bekreftelser for å anse transaksjonen som uforanderlig.

![GREEN-DESKTOP](assets/fr/19.webp)

Med bitcoins i lommeboken din, er du nå i stand til å sende dem. Klikk på "*Send*" knappen.

![GREEN-DESKTOP](assets/fr/20.webp)

På den følgende siden, skriv inn mottakerens adresse. Du kan skrive den inn manuelt eller skanne en QR-kode med webkameraet ditt.

![GREEN-DESKTOP](assets/fr/21.webp)

Velg betalingsbeløpet.

![GREEN-DESKTOP](assets/fr/22.webp)
Nederst på skjermen kan du velge gebyrsatsen for denne transaksjonen. Du har muligheten til å følge applikasjonens anbefalinger eller tilpasse dine egne gebyrer. Jo høyere gebyrene sammenlignet med andre ventende transaksjoner, desto raskere vil transaksjonen din bli behandlet. For å kjenne til gebyrmarkedet, kan du besøke [Mempool.space](https://mempool.space/) i "*Transaksjonsgebyrer*" seksjonen.
![GREEN-DESKTOP](assets/fr/23.webp)

Hvis du ønsker å spesifikt velge hvilke UTXOer du vil bruke i transaksjonen din, klikk på "*Manuell myntvalg*" knappen.

![GREEN-DESKTOP](assets/fr/24.webp)

Sjekk innstillingene for transaksjonen din og, hvis alt er som du forventer, klikk på "*Neste*".

![GREEN-DESKTOP](assets/fr/25.webp)

Verifiser nok en gang at adressen, beløpet, og gebyrene er korrekte, deretter klikk på "*Bekreft transaksjon*".

![GREEN-DESKTOP](assets/fr/26.webp)

Sørg for at alle transaksjonsparametrene er korrekte på skjermen til din maskinvare-lommebok, deretter signer transaksjonen ved å bruke den.

![GREEN-DESKTOP](assets/fr/27.webp)

Når transaksjonen er signert fra maskinvarelommeboken, sender Green den automatisk ut på Bitcoin-nettverket. Transaksjonen din vil da vises på dashbordet til din Bitcoin-lommebok, i påvente av bekreftelse.

![GREEN-DESKTOP](assets/fr/28.webp)

Og der har du det, du vet nå hvordan du enkelt kan sette opp Blockstream Green-programvaren for å håndtere din Bitcoin-lommebok på en maskinvarelommebok.
Hvis du fant denne veiledningen nyttig, ville jeg sette pris på om du kunne legge igjen en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!
Jeg anbefaler også å sjekke ut denne komplette veiledningen om Blockstream Green mobilapp for å sette opp en hot wallet:

https://planb.network/tutorials/wallet/blockstream-green