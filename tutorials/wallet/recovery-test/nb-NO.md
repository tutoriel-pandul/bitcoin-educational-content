---
name: Recovery Test
description: Hvordan teste sikkerhetskopiene dine for å sikre at du ikke mister bitcoinene dine?
---
![cover](assets/cover.webp)

Når du oppretter en Bitcoin-lommebok, blir du bedt om å notere en mnemonic frase, som vanligvis består av 12 eller 24 ord. Denne frasen lar deg gjenopprette tilgangen til dine bitcoins i tilfelle tap, skade eller tyveri av enheten som huser lommeboken din. Før du begynner å bruke din nye Bitcoin-lommebok, er det veldig viktig å verifisere gyldigheten av denne mnemonic frasen. Den beste måten å gjøre dette på er ved å utføre en tørrkjøring av gjenopprettingstest.

Denne testen innebærer å simulere en lommebokgjenoppretting før du setter inn noen bitcoins i den. Så lenge lommeboken er tom, simulerer vi en situasjon hvor enheten som huser nøklene våre er tapt, og alt vi har igjen er vår mnemonic frase for å forsøke å gjenopprette våre bitcoins.

![RECOVERY TEST](assets/notext/01.webp)

## Hva er formålet?

Denne testprosessen lar deg verifisere at den fysiske sikkerhetskopien av din mnemonic frase, enten på papir eller metall, er funksjonell. En feil under denne gjenopprettingstesten signaliserer en feil i sikkerhetskopien av frasen, og setter dermed dine bitcoins i fare. På den annen side, hvis testen er vellykket, bekrefter den at din mnemonic frase er fullt operasjonell, og du kan deretter trygt sikre bitcoins med ro i sinnet ved å bruke denne lommeboken.

Å utføre en tørrkjøring av gjenopprettingstest har en dobbel fordel. Ikke bare lar det deg sjekke nøyaktigheten av din mnemonic frase, men det gir deg også muligheten til å gjøre deg kjent med gjenopprettingsprosessen til lommeboken. På denne måten vil du oppdage potensielle vanskeligheter før en reell situasjon presenterer seg for deg. Den dagen du faktisk trenger å gjenopprette lommeboken din, vil du være mindre stresset, ettersom du allerede kjenner prosessen, noe som reduserer risikoen for feil. Derfor er det viktig å ikke forsømme dette testtrinnet og å ta nødvendig tid til å gjøre det riktig.

## Hva er en gjenopprettingstest?

Prosessen med testen er ganske enkel:
- Etter å ha opprettet din nye Bitcoin-lommebok, og før du setter inn dine første satoshier, noter ned et vitneinformasjon som en xpub, den første mottaksadressen, eller til og med master key fingerprint;
- Slett deretter den fortsatt tomme lommeboken med vilje, for eksempel ved å tilbakestille din hardware wallet til fabrikkinnstillinger;
- Simuler deretter en gjenoppretting av lommeboken din ved å bruke kun papirsikkerhetskopiene av din mnemonic frase og din passfrase hvis du bruker en;
- Til slutt, sjekk om vitneinformasjonen stemmer overens med den av det regenererte porteføljet. Hvis informasjonen stemmer, kan du være trygg på påliteligheten av din fysiske sikkerhetskopiering, og du kan deretter sende dine første bitcoins til denne lommeboken.
Vær forsiktig, under en gjenopprettingstest, **må du bruke samme enhet som er ment for din endelige lommebok**, for ikke å øke angrepsflaten til lommeboken din. For eksempel, hvis du oppretter en lommebok på en Trezor Safe 5, sørg for å utføre gjenopprettingstesten på denne samme Trezor Safe 5. Det er viktig å ikke skrive inn din gjenopprettingsfrase i noen annen programvare, da dette ville kompromittere sikkerheten som tilbys av din hardware wallet, selv om lommeboken fortsatt er tom.

## Hvordan utføre en gjenopprettingstest?

I denne veiledningen vil jeg forklare hvordan du utfører en gjenopprettingstest på en Bitcoin software wallet, ved å bruke Sparrow Wallet (for en hot wallet). Imidlertid, prosessen forblir den samme for enhver annen type enhet. Igjen, **hvis du bruker en hardware wallet, ikke utfør gjenopprettingstesten på Sparrow Wallet** (se forrige seksjon).
Jeg har nettopp opprettet en ny hot wallet på Sparrow Wallet. For øyeblikket har jeg ikke sendt noen bitcoins til den. Den er tom.
![RECOVERY TEST](assets/notext/02.webp)

Jeg har nøye notert min 12-ords mnemonic frase på et stykke papir. Og siden jeg ønsker å forbedre sikkerheten til denne lommeboken, har jeg også satt opp en BIP39-passfrase som jeg har lagret på et annet stykke papir:

```txt
1. shield
2. brass
3. sentence
4. cube
5. marble
6. glad
7. satoshi
8. door
9. project
10. panic
11. prepare
12. general
```

```text
Passfrase: YfaicGzXH9t5C#g&47Kzbc$JL
```

***Åpenbart bør du aldri dele din mnemonic frase og din passfrase på internett, i motsetning til det jeg gjør i denne opplæringen. Denne eksempellommeboken vil ikke bli brukt og vil bli slettet ved slutten av opplæringen.***

Jeg vil nå notere ned på et utkast et vitnesbyrd om informasjon fra min lommebok. Du kan velge forskjellige informasjonsbiter, som den første mottaksadressen, xpub, eller hovednøkkelfingeravtrykket. Personlig anbefaler jeg å velge den første mottaksadressen. Dette lar deg verifisere at du er i stand til å finne den komplette første derivasjonsbanen som leder til denne adressen.

På Sparrow, klikk på "*Addresses*" fanen.

![RECOVERY TEST](assets/notext/03.webp)

Noter deretter ned på et stykke papir den aller første mottaksadressen til lommeboken din. I mitt eksempel er adressen:

```txt
Etter å ha notert informasjonen, gå til "*File*" menyen, deretter velg "*Delete Wallet*". Jeg minner deg nok en gang om at din Bitcoin-lommebok må være tom før du fortsetter med denne operasjonen.

![RECOVERY TEST](assets/notext/04.webp)

Hvis lommeboken din faktisk er tom, bekreft slettingen av lommeboken din.

![RECOVERY TEST](assets/notext/05.webp)

Nå må du gjenta prosessen med å opprette lommebok, men ved å bruke våre papirkopier. Klikk på "*File*" menyen og deretter på "*New Wallet*".

![RECOVERY TEST](assets/notext/06.webp)

Skriv inn navnet på lommeboken din igjen.

![RECOVERY TEST](assets/notext/07.webp)

I "*Script Type*" menyen, må du velge samme skripttype som lommeboken du tidligere slettet.

![RECOVERY TEST](assets/notext/08.webp)

Deretter klikker du på "*New or Imported Software Wallet*" knappen.

![RECOVERY TEST](assets/notext/09.webp)

Velg det korrekte antallet ord for din seed.

![RECOVERY TEST](assets/notext/10.webp)

Skriv inn din mnemonic frase i programvaren. Hvis en "*Invalid Checksum*" melding vises, indikerer dette at backupen av din mnemonic frase er feil. Du må da starte opprettelsen av lommeboken din fra bunnen av, ettersom din gjenopprettingstest har mislyktes.

![RECOVERY TEST](assets/notext/11.webp)

Hvis du har en passfrase, som i mitt tilfelle, skriv også inn den.

![RECOVERY TEST](assets/notext/12.webp)

Klikk på "*Create Keystore*", deretter på "*Import Keystore*".

![RECOVERY TEST](assets/notext/13.webp)

Og til slutt, klikk på "*Apply*" knappen.

![RECOVERY TEST](assets/notext/14.webp)

Du kan nå returnere til "*Addresses*" fanen.

![RECOVERY TEST](assets/notext/15.webp)
Til slutt, verifiser at den første mottaksadressen stemmer overens med den du hadde notert som et vitne på utkastet ditt.
![RECOVERY TEST](assets/notext/16.webp)

Hvis mottaksadressene stemmer overens, er din gjenopprettingstest vellykket, og du kan bruke din nye Bitcoin-lommebok. Hvis de ikke stemmer overens, kan dette indikere enten en feil i valget av skripttype, som gjør avledningsveien feil, eller et problem med sikkerhetskopien av din mnemoniske frase eller ditt passord. I begge tilfeller anbefaler jeg sterkt å starte på nytt og opprette en ny Bitcoin-lommebok fra begynnelsen for å unngå enhver risiko. Denne gangen, vær nøye med å notere den mnemoniske frasen uten feil.
Gratulerer, du er nå oppdatert på hvordan du gjennomfører en gjenopprettingstest! Jeg råder deg til å generalisere denne prosessen for opprettelsen av alle dine Bitcoin-lommebøker. Hvis du fant denne veiledningen nyttig, ville jeg sette pris på om du kunne legge igjen en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!