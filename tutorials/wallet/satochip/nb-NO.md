---
name: Satochip
description: Oppsett og bruk av et Satochip smartkort
---

![cover](assets/cover.webp)

En maskinvarelommebok er en elektronisk enhet dedikert til å håndtere og sikre de private nøklene til en Bitcoin-lommebok. I motsetning til programvarelommebøker (eller varme lommebøker) installert på generelle maskiner ofte koblet til internett, tillater maskinvarelommebøker fysisk isolasjon av private nøkler, noe som reduserer risikoen for hacking og tyveri.

Hovedmålet med en maskinvarelommebok er å minimere enhetens funksjonaliteter for å redusere dens angrepsflate. En mindre angrepsflate betyr også færre potensielle angrepsvektorer, dvs. færre svakheter i systemet som angripere kunne utnytte for å få tilgang til bitcoinene.

Det anbefales å bruke en maskinvarelommebok for å sikre dine bitcoins, spesielt hvis du holder betydelige mengder, enten i absolutt verdi eller som en andel av dine totale eiendeler.

Maskinvarelommebøker brukes i kombinasjon med lommebokforvaltningsprogramvare på en datamaskin eller smarttelefon. Denne programvaren håndterer opprettelsen av transaksjoner, men den kryptografiske signaturen som er nødvendig for å validere disse transaksjonene, gjøres utelukkende innenfor maskinvarelommeboken. Dette betyr at de private nøklene aldri blir eksponert for et potensielt sårbart miljø.

Maskinvarelommebøker tilbyr dobbel beskyttelse for brukeren: på den ene siden sikrer de dine bitcoins mot fjernangrep ved å holde de private nøklene frakoblet, og på den andre siden tilbyr de generelt bedre fysisk motstand mot forsøk på å ekstrahere nøklene. Og det er nettopp på disse 2 sikkerhetskriteriene man kan bedømme og rangere de forskjellige modellene som er tilgjengelige på markedet.

I denne veiledningen foreslår jeg å oppdage en av disse løsningene: Satochip.

## Introduksjon til Satochip

Satochip er en maskinvarelommebok i form av et kort med en _EAL6+_ sertifisert brikke, som er en veldig høy sikkerhetsstandard (_NXP JCOP_). Den produseres av et belgisk selskap.

![SATOCHIP](assets/notext/01.webp)

Dette smartkortet selges for €25, noe som er veldig rimelig sammenlignet med andre maskinvarelommebøker på markedet. Brikken er et sikkert element som sikrer veldig god motstand mot fysiske angrep. I tillegg er koden åpen kildekode (_AGPLv3_).
Imidlertid, på grunn av formatet, tilbyr ikke Satochip like mange alternativer som andre maskinvare. Det er åpenbart ingen batteri, ingen kamera, eller en mikro SD-kortleser, ettersom det er et kort. Den største ulempen, etter min mening, er mangelen på en skjerm på maskinvarelommeboken, noe som gjør den mer sårbar for visse typer fjernangrep. Dette tvinger brukeren til å signere blindt og stole på det de ser på dataskjermen sin.

Til tross for sine begrensninger, forblir Satochip interessant på grunn av sin reduserte pris. Denne lommeboken kan spesielt brukes til å forbedre sikkerheten til en utgiftslommebok i tillegg til en sparelommebok beskyttet av en maskinvarelommebok utstyrt med en skjerm. Den utgjør også en god løsning for de som holder små mengder bitcoins og ikke ønsker å investere hundre euro i en mer sofistikert enhet. I tillegg kan bruken av Satochips i multisig-konfigurasjoner, eller potensielt i lommeboksystemer med tidsbegrensning i fremtiden, tilby interessante fordeler.

Satochip-selskapet tilbyr også 2 andre produkter. Det er Satodime, som er et bærerkort designet for å lagre bitcoins frakoblet, men tillater ikke transaksjoner. Det er en slags papirlommebok som er mye sikrere, som kan brukes, for eksempel, til å lage en gave. Til slutt er det Seedkeeper, som er en mnemonic frase manager. Den kan brukes til å sikkert lagre vår frø uten at den er direkte notert på et stykke papir.

## Hvordan kjøpe en Satochip?

Satochip er tilgjengelig for salg [på den offisielle nettsiden](https://satochip.io/product/satochip/). For å kjøpe den i en fysisk butikk, kan du også finne [listen over sertifiserte forhandlere](https://satochip.io/resellers/) på Satochip-nettsiden.
For å samhandle med programvaren for lommebokstyring, tilbyr Satochip to muligheter: gjennom NFC-kommunikasjon eller via en smartkortleser. For NFC-alternativet, sørg for at maskinen din er kompatibel med denne teknologien eller skaff en ekstern NFC-leser. Satochip opererer på den standard frekvensen på 13,56 MHz. Ellers kan du også kjøpe en smartkortleser. Du kan finne en på Satochip-nettsiden eller andre steder.

![SATOCHIP](assets/notext/02.webp)

## Hvordan sette opp en Satochip med Sparrow?

Når du har mottatt din Satochip, er det første steget å undersøke emballasjen for å sikre at den ikke har blitt åpnet. Satochips emballasje skal inkludere et forseglingsetikett. Hvis denne etiketten mangler eller er skadet, kan det indikere at smartkortet har blitt kompromittert og kanskje ikke er autentisk.
![SATOCHIP](assets/notext/03.webp)
Du vil finne Satochip inni.

![SATOCHIP](assets/notext/04.webp)

For å administrere lommeboken, i denne veiledningen, foreslår jeg å bruke Sparrow. Hvis du ikke allerede har programvaren, [besøk den offisielle nettsiden for å laste den ned](https://sparrowwallet.com/download/). Du kan også sjekke ut vår veiledning om Sparrow Wallet (kommer snart).

![SATOCHIP](assets/notext/05.webp)

Sett din Satochip inn i smartkortleseren eller plasser den på NFC-leseren, og koble leseren til datamaskinen din der Sparrow er åpen.

![SATOCHIP](assets/notext/06.webp)

Åpne Sparrow Wallet og sørg for at du er ordentlig koblet til en Bitcoin-node. For å gjøre dette, sjekk merket nederst til høyre: det bør være gult hvis du er koblet til en offentlig node, grønt for en tilkobling til Bitcoin Core, eller blått for Electrum.

![SATOCHIP](assets/notext/07.webp)

På Sparrow Wallet, klikk på "_File_" fanen.

![SATOCHIP](assets/notext/08.webp)

Deretter på "_New Wallet_" menyen.

![SATOCHIP](assets/notext/09.webp)

Velg et navn for lommeboken din og klikk deretter på "_Create Wallet_".

![SATOCHIP](assets/notext/10.webp)

Klikk på "_Connected Hardware Wallet_" knappen.

![SATOCHIP](assets/notext/11.webp)

Klikk på "_Scan..._" knappen.

![SATOCHIP](assets/notext/12.webp)

Din Satochip bør dukke opp. Klikk på "_Import Keystore_".

![SATOCHIP](assets/notext/13.webp)

Deretter må du sette opp en PIN-kode for å låse opp din Satochip. Velg et sterkt passord, mellom 4 og 16 tegn. Lag en sikkerhetskopi av dette passordet.

Vær oppmerksom på at dette passordet ikke er en passfrase. Dette betyr at selv uten dette passordet, vil din mnemoniske frase tillate deg å re-importere lommeboken din til programvaren om nødvendig. Passordet brukes kun til å sikre tilgangen til Satochip selv. Det er tilsvarende PIN-koden som finnes på andre maskinvarelommebøker.

Når passordet er angitt, klikk igjen på "_Import Keystore_" knappen.

![SATOCHIP](assets/notext/14.webp)

Noter passordet igjen, deretter klikk på "_Initialize_" knappen.
![SATOCHIP](assets/notext/15.webp)
Du kommer deretter til vinduet for å generere din mnemoniske frase. Klikk på "_Generer Ny_" knappen.

![SATOCHIP](assets/notext/16.webp)
Lag en eller flere fysiske kopier av din gjenopprettingsfrase ved å skrive den ned på et papir- eller metallmedium. Vær oppmerksom på at denne frasen gir full tilgang til dine bitcoins uten noen ytterligere beskyttelse. Derfor, hvis noen skulle oppdage den, kunne de umiddelbart stjele dine bitcoins, selv uten tilgang til din Satochip eller dens PIN-kode. Det er derfor viktig å sikre disse sikkerhetskopiene. Videre tillater denne frasen deg å gjenopprette tilgangen til dine bitcoins i tilfelle tap, skade på Satochip, eller hvis du glemmer din PIN-kode.
![SATOCHIP](assets/notext/17.webp)

Din Bitcoin-lommebok har blitt vellykket opprettet.

![SATOCHIP](assets/notext/18.webp)

Klikk igjen på "_Importer Keystore_" knappen.

![SATOCHIP](assets/notext/19.webp)

Din lommebok er nå opprettet. Dine private nøkler er nå lagret på smartkortet til din Satochip. Klikk på "_Bruk_" knappen for å fortsette.

![SATOCHIP](assets/notext/20.webp)

Det anbefales å sette opp et ekstra passord for å sikre den offentlige informasjonen som håndteres av Sparrow Wallet, i tillegg til PIN-koden til din Satochip. Dette passordet vil sikre tilgangssikkerheten til Sparrow Wallet, som hjelper til med å beskytte dine offentlige nøkler, adresser og transaksjonshistorikk mot uautorisert tilgang.

![SATOCHIP](assets/notext/21.webp)

Skriv inn passordet ditt i de to feltene, og klikk deretter på "_Sett Passord_" knappen.

![SATOCHIP](assets/notext/22.webp)

Og der har du det, din Satochip er nå konfigurert på Sparrow Wallet.

![SATOCHIP](assets/notext/23.webp)

Nå som din lommebok er opprettet, kan du koble fra din Satochip. Oppbevar den på et sikkert sted!

## Hvordan motta bitcoins med Satochip?

Når du er i lommeboken din, klikk på "_Motta_" fanen.

![SATOCHIP](assets/notext/24.webp)

Sparrow Wallet genererer en adresse for lommeboken din. Vanligvis, for andre maskinvarelommebøker, anbefales det å klikke på "_Vis Adresse_" for å verifisere adressen direkte på enhetens skjerm. Dessverre er ikke denne muligheten tilgjengelig med Satochip, men sørg for å bruke den for dine andre lommebøker.

![SATOCHIP](assets/notext/25.webp)

Du kan legge til en "_Etikett_" for å beskrive kilden til bitcoins som vil bli sikret med denne adressen. Dette er en god praksis som hjelper deg å bedre håndtere dine UTXOs.

![SATOCHIP](assets/notext/26.webp)

For mer informasjon om etikettering, anbefaler jeg også å sjekke ut denne andre opplæringen:

https://planb.network/tutorials/privacy/utxo-labelling

Du kan deretter bruke denne adressen til å motta bitcoins.

![SATOCHIP](assets/notext/27.webp)

## Hvordan sende Bitcoins med Satochip?

Nå som du har mottatt dine første sats i din sikre lommebok med Satochip, kan du også bruke dem! Koble din Satochip til datamaskinen, start Sparrow Wallet, og gå deretter til "_Send_" fanen for å konstruere en ny transaksjon.

![SATOCHIP](assets/notext/28.webp)
Hvis du ønsker å utføre myntkontroll, det vil si, spesifikt velge hvilke UTXOer du vil bruke i transaksjonen, gå til "_UTXOer_" fanen. Velg UTXOene du ønsker å bruke, og klikk deretter på "_Send valgte_". Du vil bli omdirigert til samme skjerm som "_Send_" fanen, men med dine UTXOer allerede valgt for transaksjonen.
![SATOCHIP](assets/notext/29.webp)

Skriv inn mottakeradressen. Du kan også legge til flere adresser ved å klikke på "_+ Legg til_" knappen.

![SATOCHIP](assets/notext/30.webp)

Noter en "_Etikett_" for å huske formålet med denne utgiften.

![SATOCHIP](assets/notext/31.webp)

Velg beløpet som skal sendes til denne adressen.

![SATOCHIP](assets/notext/32.webp)

Justér transaksjonsgebyrets rate i henhold til det nåværende markedet.

![SATOCHIP](assets/notext/33.webp)

Sørg for at alle parametrene for transaksjonen din er korrekte, og klikk deretter på "_Opprett transaksjon_".

![SATOCHIP](assets/notext/34.webp)

Hvis alt er til din tilfredshet, klikk på "_Fullfør transaksjon for signering_".

![SATOCHIP](assets/notext/35.webp)

Klikk på "_Signer_".

![SATOCHIP](assets/notext/36.webp)

Klikk på "_Signer_" igjen ved siden av din Satochip.

![SATOCHIP](assets/notext/37.webp)

Skriv inn PIN-koden til din Satochip, og klikk deretter på "_Signer_" igjen for å signere transaksjonen din.

![SATOCHIP](assets/notext/38.webp)

Transaksjonen din er nå signert. Klikk på "_Kringkast transaksjon_" for å sende den ut på Bitcoin-nettverket.

![SATOCHIP](assets/notext/39.webp)

Du kan finne den i "_Transaksjoner_" fanen i Sparrow Wallet.

![SATOCHIP](assets/notext/40.webp)

Gratulerer, du er nå kunnskapsrik om bruk av Satochip! Hvis du fant denne veiledningen nyttig, ville jeg sette pris på en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

