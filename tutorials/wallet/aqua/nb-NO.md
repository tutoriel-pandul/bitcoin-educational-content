---
name: Aqua
description: Bitcoin, Lightning og Liquid i en enkelt lommebok
---
![cover](assets/cover.webp)

Aqua er en mobilapplikasjon som gjør det enkelt å opprette en hot wallet for Bitcoin og Liquid, og tilbyr også muligheten til å bruke Lightning uten kompleksiteten ved å administrere en node, takket være integrerte bytter. Den støtter også administrasjon av USDT stablecoins på tvers av ulike nettverk.

Utviklet av selskapet JAN3 under ledelse av Samson Mow, ble Aqua-applikasjonen opprinnelig designet spesifikt for brukernes behov i Latin-Amerika, selv om den er egnet for enhver bruker over hele verden. Den er spesielt interessant for nybegynnere og de som bruker Bitcoin daglig for betalingene sine.

I denne veiledningen vil vi utforske hvordan man bruker de mange funksjonene til Aqua. Men før det, la oss ta et øyeblikk for å forstå hva en sidechain på Bitcoin er og hvordan Liquid fungerer, noe som vil tillate oss å fullt ut forstå interessen av Aqua.

![AQUA](assets/fr/01.webp)

## Hva er en sidechain?

Bitcoin-protokollen har bevisste tekniske begrensninger som hjelper med å opprettholde nettverkets desentralisering og sikre en fordeling av sikkerhet blant alle brukere. Imidlertid kan disse grensene noen ganger frustrere brukere, spesielt under trengsel forårsaket av et høyt volum av samtidige transaksjoner. Debatten om Bitcoins skalérbarhet har lenge delt samfunnet, spesielt under Blocksize-krigen. Siden den episoden er det bredt anerkjent innenfor Bitcoin-samfunnet at skalérbarhet må sikres av off-chain løsninger, på andre-lags systemer. Blant disse løsningene er sidechains, som fortsatt er relativt ukjente og underbrukte sammenlignet med andre systemer som Lightning Network.

En sidechain er en uavhengig blokkjede som opererer parallelt med hoved-Bitcoin-blokkjeden. Den bruker bitcoin som en enhet av konto gjennom en mekanisme kalt "*two-way peg*". Dette systemet tillater låsing av bitcoins på hovedkjeden for å replikere deres verdi på sidekjeden, hvor de sirkulerer som tokens støttet av de originale bitcoins. Disse tokenene opprettholder normalt en verdi-paritet med de låste bitcoins på hovedkjeden, og prosessen kan reverseres for å hente midlene på Bitcoin.
Målet med sidechains er å tilby tilleggsfunksjonaliteter eller tekniske forbedringer, som raskere transaksjoner, reduserte gebyrer eller støtte for smartkontrakter. Disse innovasjonene kan ikke alltid implementeres direkte på Bitcoin-blokkjeden uten å kompromittere dens desentralisering eller sikkerhet. Sidechains tillater derfor testing og utforsking av nye løsninger samtidig som integriteten til Bitcoin bevares. Imidlertid krever disse protokollene ofte kompromisser, spesielt når det gjelder desentralisering og sikkerhet, avhengig av det valgte styringsmodellen og konsensusmekanismen.
## Hva er Liquid?

Liquid er en føderert sidechain bygget på toppen av Bitcoin, utviklet av Blockstream, med mål om å forbedre hastigheten, personvernet og funksjonalitetene til transaksjoner. Den bruker en bilateral forankringsmekanisme etablert på en føderasjon for å låse bitcoins på hovedkjeden og skape i retur Liquid-bitcoins (L-BTC), tokens som sirkulerer på Liquid samtidig som de forblir støttet av de originale bitcoins.

![AQUA](assets/fr/02.webp)

Liquid-nettverket er basert på en føderasjon av deltakere, sammensatt av anerkjente enheter fra Bitcoin-økosystemet, som validerer blokkene og administrerer den bilaterale forankringen. I tillegg til L-BTC, tillater Liquid også utstedelse av andre digitale eiendeler, som stablecoinen USDT eller andre kryptovalutaer.

![AQUA](assets/fr/03.webp)

## Installere Aqua-appen

Det første steget er naturligvis å laste ned Aqua-appen. Gå til appbutikken din:
- [For Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [For Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
For Android-brukere har du også muligheten til å installere appen via `.apk`-filen [tilgjengelig på deres GitHub](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Start appen, og kryss av for "*Jeg har lest og godtar Vilkårene for bruk & Personvernpolicy*".

![AQUA](assets/fr/06.webp)

## Opprette din lommebok på Aqua

Klikk på "*Opprett lommebok*" knappen.

![AQUA](assets/fr/07.webp)

Og der har du det, lommeboken din er allerede opprettet!

![AQUA](assets/fr/08.webp)

Men før noe annet, siden dette er en selvforvaltet lommebok, er det avgjørende å lage en fysisk sikkerhetskopi av din mnemonic frase. **Denne mnemonic frasen gir full og ubegrenset tilgang til alle dine bitcoins**. Enhver som er i besittelse av denne frasen kan stjele dine midler, selv uten fysisk tilgang til telefonen din.
Den lar deg gjenopprette tilgangen til dine bitcoins i tilfelle tap, tyveri, eller skade på telefonen din. Det er derfor veldig viktig å sikkerhetskopiere den nøye på et fysisk medium (ikke digitalt) og oppbevare det på et sikkert sted. Du kan skrive den ned på et stykke papir, eller for mer sikkerhet, hvis denne lommeboken er betydelig, anbefaler jeg å gravere den på et rustfritt stålmedium for å beskytte mot risikoer som branner, flommer, eller kollapser (for en varm lommebok ment for å sikre en liten mengde bitcoins, er en enkel papirsikkerhetskopi sannsynligvis tilstrekkelig).
For å gjøre dette, klikk på innstillingsmenyen.

![AQUA](assets/fr/09.webp)

Deretter klikker du på "*Vis Seed Phrase*". Lag en fysisk sikkerhetskopi av denne 12-ords frasen.

![AQUA](assets/fr/10.webp)

I denne samme innstillingsmenyen kan du også endre språket på applikasjonen samt den fiatvalutaen som brukes.

![AQUA](assets/fr/11.webp)

Før du mottar dine første bitcoins i lommeboken din, **anbefaler jeg sterkt at du utfører en tørrkjøringsgjenopprettingstest**. Noter en referanseinformasjon, som din xpub eller den første mottaksadressen, deretter sletter du lommeboken din på Aqua-appen mens den fortsatt er tom. Prøv deretter å gjenopprette lommeboken din på Aqua ved hjelp av dine papirsikkerhetskopier. Sjekk at vitneinformasjonen som genereres etter gjenopprettingen stemmer overens med den du opprinnelig noterte. Hvis dette er tilfellet, kan du være sikker på at dine papirsikkerhetskopier er pålitelige. For å lære mer om hvordan du utfører en gjenopprettingstest, anbefaler jeg at du konsulterer denne andre opplæringen:

https://planb.network/tutorials/wallet/recovery-test

## Motta bitcoins på Aqua

Nå som lommeboken din er satt opp, er du klar til å motta dine første sats! Klikk bare på "*Motta*" knappen i "*Lommebok*" menyen.

![AQUA](assets/fr/12.webp)

Du kan velge å motta bitcoins onchain, på Liquid, eller via Lightning.

![AQUA](assets/fr/13.webp)

For onchain-transaksjoner vil Aqua generere en spesifikk mottaksadresse hvor du kan motta dine sats.

![AQUA](assets/fr/14.webp)

På samme måte, ved å velge Liquid, vil Aqua gi deg en Liquid-adresse.

![AQUA](assets/fr/15.webp)

Hvis du foretrekker å motta midler via Lightning, må du først spesifisere ønsket beløp.

![AQUA](assets/fr/16.webp)

Deretter klikker du på "*Generer faktura*".

![AQUA](assets/fr/17.webp)
Aqua vil opprette en faktura for å motta midler fra en Lightning-lommebok. Det er viktig å merke seg at, i motsetning til onchain og Liquid-alternativer, vil midler mottatt via Lightning automatisk bli konvertert til L-BTC på Liquid ved bruk av Boltz-verktøyet, siden Aqua ikke er en Lightning-node. Denne prosessen lar deg motta og sende midler via Lightning, men uten å noen gang holde dine bitcoins på Lightning. ![AQUA](assets/fr/18.webp)

Personlig vil jeg starte med å sende bitcoins via Lightning til Aqua. Når transaksjonen er fullført med den oppgitte fakturaen, mottas en bekreftelse.

![AQUA](assets/fr/19.webp)

For å følge fremgangen til byttet, gå tilbake til hjemmesiden til lommeboken din og klikk på "*L2 Bitcoin*" kontoen, som lister opp Lightning (via bytte) og Liquid-transaksjoner.

![AQUA](assets/fr/20.webp)

Her kan du se transaksjonen din samt saldoen din i L-BTC.

![AQUA](assets/fr/21.webp)

## Bytte bitcoins med Aqua

Nå som du har midler i Aqua-lommeboken din, har du muligheten til å bytte dem direkte fra appen, enten for å overføre dem til hoved-Bitcoin-blockchainen eller til Liquid. Du kan også konvertere dine bitcoins til stablecoinen USDT (eller andre). For å gjøre dette, gå til "*Marketplace*" menyen.

![AQUA](assets/fr/22.webp)

Klikk på "*Swaps*".

![AQUA](assets/fr/23.webp)

I "*Transfer from*" boksen, velg eiendelen du ønsker å bytte. For øyeblikket har jeg bare L-BTC, så det er det jeg velger.

![AQUA](assets/fr/24.webp)

I "*Transfer to*" boksen, velg mål-eiendelen for byttet ditt. For min del valgte jeg USDT på Liquid-nettverket.

![AQUA](assets/fr/25.webp)

Skriv inn beløpet du ønsker å konvertere.

![AQUA](assets/fr/26.webp)

Bekreft ved å klikke på "*Continue*".

![AQUA](assets/fr/27.webp)

Sørg for at bytteinnstillingene er etter din smak, og bekreft deretter ved å skyve "*Swap*" knappen nederst på skjermen.

![AQUA](assets/fr/28.webp)

Byttet ditt er nå bekreftet.

![AQUA](assets/fr/29.webp)

Hvis vi går tilbake til lommeboken vår, kan vi se at vi nå har USDT på Liquid.

![AQUA](assets/fr/30.webp)

## Sende bitcoins med Aqua

Nå som du har bitcoins i Aqua-lommeboken din, har du muligheten til å sende dem. Klikk på "*Send*" knappen.

![AQUA](assets/fr/31.webp)

Velg eiendelen du ønsker å sende eller velg nettverket for å utføre transaksjonen. For min del vil jeg sende bitcoins via Lightning.

![AQUA](assets/fr/32.webp)
Deretter, skriv inn nødvendig informasjon for å sende betalingen: for Bitcoin onchain eller Liquid, trenger du å oppgi en mottaksadresse; for Lightning, kreves en faktura. Du kan lime inn denne informasjonen direkte i det angitte feltet eller bruke QR-kodeikonet for å åpne kameraet ditt og skanne adressen eller fakturaen. Klikk deretter på "*Continue*".
![AQUA](assets/fr/33.webp)

Klikk på "*Continue*" igjen hvis all informasjonen ser korrekt ut.

![AQUA](assets/fr/34.webp)
Aqua presenterer deg deretter for et sammendrag av transaksjonen. Sørg for at all informasjon er korrekt, spesielt destinasjonsadressen, gebyrene og beløpet. For å bekrefte transaksjonen, skyv "*Skyv for å sende*" knappen som er plassert nederst på skjermen.
![AQUA](assets/fr/35.webp)

En bekreftelse på sendingen blir deretter gitt til deg.

![AQUA](assets/fr/36.webp)

Og der har du det, du vet nå hvordan du bruker Aqua-appen til å motta og bruke midler på Bitcoin, Lightning og Liquid, alt fra ett enkelt grensesnitt.

Hvis du fant denne veiledningen nyttig, ville jeg sette pris på om du kunne legge igjen en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

Jeg råder deg også til å sjekke ut denne andre komplette veiledningen om Blockstream Green mobilappen, som er en annen interessant løsning for å sette opp din Liquid-lommebok:

https://planb.network/tutorials/wallet/blockstream-green-liquid