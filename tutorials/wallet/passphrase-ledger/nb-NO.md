---
name: BIP39 Passphrase Ledger
description: Hvordan legge til en passordfrase på din Ledger-lommebok?
---
![cover](assets/cover.webp)

En BIP39 passordfrase er et valgfritt passord som, når det kombineres med din mnemoniske frase, gir et ekstra sikkerhetslag for deterministiske og hierarkiske Bitcoin-lommebøker. I denne opplæringen skal vi sammen se på hvordan du setter opp en passordfrase på din sikre Bitcoin-lommebok på en Ledger (uavhengig av modellen).

Før du starter denne opplæringen, hvis du ikke er kjent med konseptet av en passordfrase, hvordan det fungerer, og dets implikasjoner for din Bitcoin-lommebok, anbefaler jeg sterkt å konsultere denne andre teoretiske artikkelen hvor jeg forklarer alt:

https://planb.network/tutorials/wallet/passphrase

## Hvordan fungerer passordfrasen på en Ledger?

Med Ledger-enheter har du to forskjellige alternativer for å konfigurere en passordfrase på lommeboken din: "*PIN-bundet*" alternativet og "*midlertidig*" alternativet.

Med "*PIN-bundet*" alternativet, assosierer du en passordfrase med en sekundær PIN på din Ledger. Dette betyr at du vil ha 2 PIN-koder: en for å få tilgang til din vanlige lommebok uten en passordfrase, og den andre for å få tilgang til din andre lommebok beskyttet av passordfrasen.

![PASSPHRASE BIP39](assets/notext/03.webp)

Grunnleggende sett, selv med dette passordfrasealternativet bundet til den sekundære PIN-koden, forblir din passordfrase din passordfrase. Dette betyr at hvis du mister din Ledger og ønsker å gjenopprette dine bitcoins på en annen enhet eller programvare, vil du absolutt trenge din 24-ords frase og din **komplette passordfrase**. PIN-koden assosiert med passordfrasen brukes kun for å få tilgang til den på din nåværende Ledger, men den fungerer ikke på andre Ledgers eller annen programvare. Det er derfor viktig å fullstendig sikkerhetskopiere din passordfrase på et fysisk medium. **Å kjenne den sekundære PIN-koden alene er ikke nok til å gjenopprette tilgang til lommeboken din**; det er rett og slett en bekvemmelighetsfunksjon på din Ledger.

Dette andre PIN-alternativet er spesielt interessant for å håndtere fysiske angrep. For eksempel, hvis en angriper tvinger deg til å låse opp enheten din for å stjele dine midler, kan du bruke den første PIN-koden for å få tilgang til en lokkelommebok som inneholder en liten mengde bitcoins, mens du holder dine hovedmidler sikre bak den andre PIN-koden.

I tillegg tilbyr dette alternativet alle sikkerhetsfordelene til BIP39 passordfrasen uten begrensningen av å måtte skrive den inn manuelt hver gang du bruker signeringsenheten din. Dette lar deg bruke en lang og tilfeldig passordfrase, og dermed styrke beskyttelsen mot brute force-angrep, samtidig som du unngår vanskeligheten med å måtte skrive den inn manuelt hver gang på enhetens små knapper.
Alternativet for "midlertidig passordfrase" lagrer ikke passordfrasen på enheten. Hver gang du ønsker å få tilgang til din beskyttede lommebok, må du manuelt skrive inn passordfrasen på Ledgeren. Dette gjør bruken mer tungvint, men øker også sikkerheten noe ved å ikke etterlate noen spor av passordfrasen på enheten. Så snart du slår av enheten, går den tilbake til sin standardtilstand og krever en ny inntasting av den komplette passordfrasen for å få tilgang til de skjulte kontoene. Dette "midlertidige passordfrase"-alternativet er dermed likt operasjonen av andre maskinvarelommebøker.
I denne opplæringen vil jeg bruke Ledger Flex som et eksempel. Men, hvis du bruker en annen Ledger-modell, forblir prosessen den samme. For Ledger Stax er grensesnittet det samme som for Ledger Flex. Når det gjelder Nano S, Nano S Plus og Nano X-modellene, selv om grensesnittet er forskjellig, forblir prosessen og navnene på menyene de samme.
**Oppmerksomhet:** Hvis du allerede har mottatt bitcoins på din Ledger før du aktiverte passfrasen, må du overføre dem via en Bitcoin-transaksjon. Passfrasen genererer et sett med nye nøkler, og skaper dermed en lommebok som er helt uavhengig av din opprinnelige lommebok. Når du legger til passfrasen, vil du ha en ny lommebok som vil være tom. Dette sletter imidlertid ikke din første lommebok uten passfrase. Du kan fortsatt få tilgang til den, enten direkte via din Ledger uten å angi passfrasen eller gjennom et annet programvare ved å bruke din 24-ords frase.
Før du starter denne veiledningen, sørg for at du allerede har initialisert din Ledger og generert din mnemoniske frase. Hvis dette ikke er tilfellet og din Ledger er ny, følg den spesifikke veiledningen for din modell tilgjengelig på PlanB Network. Når dette trinnet er fullført, kan du returnere til denne veiledningen.

https://planb.network/tutorials/wallet/ledger-flex
https://planb.network/tutorials/wallet/ledger-nano-s-plus
https://planb.network/tutorials/wallet/ledger

## Hvordan sette opp en midlertidig passfrase med en Ledger?

På hjemmesiden til din Ledger, klikk på tannhjulet for innstillinger.

![PASSPHRASE BIP39](assets/notext/04.webp)

Velg "Advanced"-menyen, deretter "Set passphrase".

![PASSPHRASE BIP39](assets/notext/05.webp)

Dette er trinnet hvor du kan velge mellom alternativet "linked to PIN" eller "temporary" som vi snakket om i den forrige delen. Her vil jeg forklare hvordan du setter opp en midlertidig passfrase, så klikk på "Set temporary passphrase".

![PASSPHRASE BIP39](assets/notext/06.webp)
Du blir deretter bedt om å angi din passfrase. Velg en sterk passfrase og fortsett umiddelbart til en fysisk sikkerhetskopi, på et medium som papir eller metall. I dette eksemplet valgte jeg passfrasen: `fH3&kL@9mP#2sD5qR!82`. Etter å ha angitt din passfrase, klikk på "*Continue*" knappen.
![PASSPHRASE BIP39](assets/notext/07.webp)

Verifiser at din passfrase stemmer overens med det du har notert på din fysiske sikkerhetskopi, deretter klikk på "*Yes, it's correct*" knappen for å bekrefte.

![PASSPHRASE BIP39](assets/notext/08.webp)

For å fullføre opprettelsen av din passfrase, angi PIN-koden til din Ledger. Fra nå av, hver gang du ønsker å få tilgang til din lommebok med en passfrase på Ledger, må du følge nøyaktig de samme trinnene som beskrevet her.

![PASSPHRASE BIP39](assets/notext/09.webp)

Du kan nå importere ditt sett med offentlige nøkler på Sparrow Wallet for å administrere din lommebok. På Sparrow vil dette tilsvare en annen lommebok fra din opprinnelige lommebok uten passfrase.

Åpne Sparrow Wallet. Sørg for at programvaren er koblet til en node, deretter klikk på "*File*" fanen og velg "*New Wallet*".

![PASSPHRASE BIP39](assets/notext/10.webp)

Velg et navn for din lommebok beskyttet av en passfrase. For dette eksemplet valgte jeg et navn som eksplisitt inkluderer termen "*passfrase*". Men hvis du foretrekker å holde diskresjonen av denne lommeboken på datamaskinen din, kan du velge et mindre beskrivende navn.

![PASSPHRASE BIP39](assets/notext/11.webp)

Velg typen skript for din lommebok. Jeg råder deg til å velge "*Taproot*" eller alternativt "*Native SegWit*".

![PASSPHRASE BIP39](assets/notext/12.webp)
Koble Ledgeren din til datamaskinen, og klikk deretter på "*Connected Hardware Wallet*". Sørg for at du allerede har tastet inn din passfrase på Ledgeren din. Hvis ikke, vennligst gå tilbake til de forrige stegene for å taste inn din passfrase. Før du fortsetter til skanningen, husk også å åpne "*Bitcoin*" applikasjonen på Ledgeren din.
![PASSPHRASE BIP39](assets/notext/13.webp)

Klikk på "*Scan...*" knappen.

![PASSPHRASE BIP39](assets/notext/14.webp)

Klikk på "*Import Keystore*" ved siden av din Ledger.

![PASSPHRASE BIP39](assets/notext/15.webp)

Din lommebok beskyttet av passfrasen er nå opprettet på Sparrow. For å bekrefte, klikk på "*Apply*" knappen.

![PASSPHRASE BIP39](assets/notext/16.webp)
Velg et sterkt passord for å sikre tilgangen til Sparrow Wallet. Dette passordet vil sikre tilgangssikkerheten til dine lommebokdata på Sparrow, som hjelper med å beskytte dine offentlige nøkler, adresser, etiketter og transaksjonshistorikk mot uautorisert tilgang.
Jeg råder deg til å lagre dette passordet i en passordbehandler slik at du ikke glemmer det.

![PASSPHRASE BIP39](assets/notext/17.webp)

Og der har du det, din lommebok er nå opprettet! I "*Settings*" menyen, vil Sparrow gi deg din "*Master fingerprint*". Dette representerer fingeravtrykket av din hovednøkkel, brukt som basis for å utlede din lommebok. Jeg anbefaler sterkt å beholde en kopi av dette fingeravtrykket. I mitt eksempel, tilsvarer det: `281ee33a`.

![PASSPHRASE BIP39](assets/notext/18.webp)

Husk det vi nevnte i de tidligere delene: en feil, selv en liten en, i inntastingen av din passfrase vil generere en helt ny lommebok med forskjellige nøkler. Hver gang du trenger å forsikre deg om at du får tilgang til riktig lommebok med riktig passfrase, sjekk at fingeravtrykket av din hovednøkkel matcher det du noterte ned. Denne informasjonen, i seg selv, utgjør ingen risiko for sikkerheten til dine midler eller ditt privatliv.

Før du bruker lommeboken din med en passfrase, råder jeg deg sterkt til å utføre en tørrkjøringsgjenopprettingstest. Noter ned et referansestykket informasjon som din xpub eller fingeravtrykket av din hovednøkkel, deretter nullstill din Ledger mens lommeboken fortsatt er tom. Prøv deretter å gjenopprette lommeboken din på Ledgeren ved hjelp av dine papirkopier av den 24-ords frasen og passfrasen. Sjekk at informasjonen generert etter gjenopprettingen matcher det du opprinnelig noterte. Hvis det er tilfellet, kan du være sikker på at dine papirkopier er pålitelige.

## Hvordan sette opp en passfrase knyttet til en PIN med en Ledger?

På hjemmesiden til din Ledger, klikk på tannhjulinnstillingene.

![PASSPHRASE BIP39](assets/notext/19.webp)

Velg "*Advanced*" menyen, deretter "*Set passphrase*".

![PASSPHRASE BIP39](assets/notext/20.webp)

Dette er stegene hvor du kan velge mellom "*linked to PIN*" eller "*temporary*" alternativet vi snakket om i den forrige delen. Her vil jeg forklare hvordan du setter opp en passfrase knyttet til en ny PIN, så klikk på "*Set passphrase and attach it to a new PIN*".

![PASSPHRASE BIP39](assets/notext/21.webp)
Du må deretter velge PIN-koden som vil bli assosiert med din passfrase. Akkurat som med hoved-PIN-koden, anbefales det å velge en 8-sifret PIN-kode, så tilfeldig som mulig. Også, sørg for å lagre denne koden på et annet sted enn der din Ledger Flex er lagret.
I mitt tilfelle er hoved-PIN-koden `58293647` og jeg valgte `71425839` som den sekundære PIN-koden knyttet til passfrasen.
![PASSPHRASE BIP39](assets/notext/22.webp)

Du blir deretter bedt om å angi din passfrase. Velg en sterk passfrase og gå umiddelbart videre til en fysisk sikkerhetskopi, på et medium som papir eller metall. I dette eksemplet valgte jeg passfrasen: `fH3&kL@9mP#2sD5qR!82`. Etter å ha angitt passfrasen din, klikk på "*Fortsett*" knappen.

![PASSPHRASE BIP39](assets/notext/23.webp)

Verifiser at passfrasen din stemmer overens med det du har notert på din fysiske sikkerhetskopi, og klikk deretter på "*Ja, det er korrekt*" knappen for å bekrefte.

![PASSPHRASE BIP39](assets/notext/24.webp)

For å fullføre opprettelsen av passfrasen din, angi hoved-PIN-koden til din Ledger (ikke den som er knyttet til passfrasen).

![PASSPHRASE BIP39](assets/notext/25.webp)

Fra nå av, når du vil få tilgang til lommeboken din med en passfrase på Ledger, må du angi ikke hoved-PIN-koden, men den sekundære PIN-koden:
- Hoved-PIN-kode (`58293647`) > lommebok uten passfrase.
- Sekundær PIN-kode (`71425839`) > lommebok med passfrase.

Du kan nå importere ditt sett med offentlige nøkler på Sparrow Wallet for å administrere lommeboken din. På Sparrow vil dette tilsvare en annen lommebok fra din opprinnelige lommebok uten passfrase.

Åpne Sparrow Wallet. Sørg for at programvaren er koblet til en node, og klikk deretter på "*Fil*" fanen og velg "*Ny Lommebok*".

![PASSPHRASE BIP39](assets/notext/26.webp)

Velg et navn for lommeboken din beskyttet av en passfrase. For dette eksemplet valgte jeg et navn som eksplisitt inkluderer termen "*passfrase*". Men hvis du foretrekker å holde diskresjonen av denne lommeboken på datamaskinen din, kan du velge et mindre beskrivende navn.

![PASSPHRASE BIP39](assets/notext/27.webp)

Velg skripttypen for lommeboken din. Jeg råder deg til å velge "*Taproot*" eller, hvis ikke, "*Native SegWit*".

![PASSPHRASE BIP39](assets/notext/28.webp)
Koble din Ledger til datamaskinen din, og klikk deretter på "*Tilkoblet Maskinvarelommebok*". Sørg for at du allerede har passfrasen din på din Ledger ved å låse den opp med den sekundære PIN-koden. Hvis ikke, start din Ledger på nytt og angi PIN-koden knyttet til passfrasen. Husk også å åpne "*Bitcoin*" applikasjonen på din Ledger før du fortsetter til skanning.

![PASSPHRASE BIP39](assets/notext/29.webp)

Klikk på "*Skann...*" knappen.

![PASSPHRASE BIP39](assets/notext/30.webp)

Klikk på "*Importer Keystore*".

![PASSPHRASE BIP39](assets/notext/31.webp)

Din lommebok beskyttet av passfrasen er nå opprettet på Sparrow. For å bekrefte, klikk på "*Bruk*" knappen.

![PASSPHRASE BIP39](assets/notext/32.webp)

Velg et sterkt passord for å sikre tilgangen til Sparrow Wallet. Dette passordet vil sikre sikkerheten til tilgangen til dine lommebokdata på Sparrow, noe som hjelper til med å beskytte dine offentlige nøkler, adresser, etiketter og transaksjonshistorikk mot uautorisert tilgang.

Jeg råder deg til å lagre dette passordet i en passordbehandler slik at du ikke glemmer det.
Og der har du det, lommeboken din er nå opprettet! I "*Innstillinger*" menyen, vil Sparrow gi deg ditt "*Master fingerprint*". Dette representerer fingeravtrykket av din hovednøkkel, brukt som grunnlag for din lommeboks derivasjon. Jeg anbefaler sterkt å beholde en kopi av dette fingeravtrykket. I mitt eksempel, tilsvarer det: `281ee33a`.

Husk det vi nevnte i de tidligere delene: en feil, selv en liten en, i inntastingen av din passfrase vil generere en helt ny lommebok med forskjellige nøkler. Hver gang du trenger å sikre tilgang til den korrekte lommeboken med riktig passfrase, verifiser at fingeravtrykket av din hovednøkkel matcher det du noterte. Denne informasjonen, i seg selv, utgjør ingen risiko for sikkerheten til dine midler eller ditt privatliv.
Før du bruker lommeboken din med en passfrase, anbefaler jeg sterkt at du utfører en tørrkjøringsgjenopprettingstest. Noter ned et referansestykke informasjon som din xpub eller fingeravtrykket av din hovednøkkel, deretter nullstill din Ledger mens lommeboken fortsatt er tom. Prøv deretter å gjenopprette lommeboken din på Ledger ved hjelp av dine papirkopier av den 24-ords frasen og passfrasen. Sjekk at informasjonen generert etter gjenopprettingen matcher det du opprinnelig noterte. Hvis dette er tilfellet, kan du være sikker på at dine papirkopier er pålitelige.

Gratulerer, din Bitcoin-lommebok er nå sikret med en passfrase! Hvis du fant denne veiledningen nyttig, ville jeg sette pris på om du kunne legge igjen en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

Jeg anbefaler også at du sjekker ut denne andre komplette veiledningen om hvordan du bruker din Ledger Flex:

https://planb.network/tutorials/wallet/ledger-flex