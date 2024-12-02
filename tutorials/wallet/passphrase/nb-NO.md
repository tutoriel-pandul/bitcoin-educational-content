---
name: BIP39 Passphrase
description: Forstå hvordan et passord fungerer
---
![cover](assets/cover.webp)

## Hva er en BIP39-passordfrase?

HD-lommebøker genereres vanligvis fra en mnemonisk frase bestående av 12 eller 24 ord. Denne frasen er svært viktig fordi den muliggjør gjenopprettingen av alle nøklene til en lommebok i tilfelle det fysiske mediet (som en maskinvarelommebok, for eksempel) går tapt. Imidlertid utgjør den et enkelt feilpunkt fordi hvis den blir kompromittert, kan en angriper stjele alle bitcoinene.

![PASSPHRASE BIP39](assets/notext/01.webp)

Dette er hvor passordfrasen kommer inn. Det er et valgfritt passord som du fritt kan velge, som legges til den mnemoniske frasen i nøkkelavledningsprosessen for å forbedre lommebokens sikkerhet.

![PASSPHRASE BIP39](assets/notext/02.webp)

Vær forsiktig så du ikke forveksler passordfrasen med PIN-koden til din maskinvarelommebok eller passordet som brukes for å låse opp tilgangen til lommeboken din på datamaskinen. I motsetning til alle disse elementene, spiller passordfrasen en rolle i avledningen av lommebokens nøkler. **Dette betyr at uten den, vil du aldri kunne gjenopprette dine bitcoins.**

Passordfrasen fungerer i tandem med den mnemoniske frasen, og endrer frøet som nøklene genereres fra. Så selv om noen får tak i din 12 eller 24-ords frase, uten passordfrasen, kan de ikke få tilgang til midlene dine. **Å bruke en passordfrase skaper i prinsippet en ny lommebok med distinkte nøkler. Å endre (selv litt) på passordfrasen vil generere en annen lommebok.**

## Hvorfor bør du bruke en passordfrase?

Passordfrasen er vilkårlig og kan være hvilken som helst kombinasjon av tegn valgt av brukeren. Å bruke en passordfrase tilbyr derfor flere fordeler. Først reduserer det alle risikoer forbundet med kompromittering av den mnemoniske frasen ved å kreve en sekundær faktor for å få tilgang til midlene (innbrudd, tilgang til hjemmet ditt, osv.).

Videre kan den brukes strategisk for å skape en avledningslommebok, for å håndtere fysiske begrensninger for å stjele midlene dine som det beryktede "*$5 skiftenøkkelangrepet*". I dette scenarioet er ideen å ha en lommebok uten passordfrase som inneholder bare en liten mengde bitcoins, nok til å tilfredsstille en potensiell angriper, mens du har en skjult lommebok. Denne sistnevnte bruker den samme mnemoniske frasen, men er sikret med en ekstra passordfrase.

Til slutt er bruk av passordfrase interessant når man ønsker å kontrollere tilfeldigheten av HD-lommebokens frøgenerering.

## Hvordan velge en god passordfrase?
For at passordfrasen skal være effektiv, må den være tilstrekkelig lang og tilfeldig. Akkurat som med et sterkt passord, anbefaler jeg å velge en passordfrase som er så lang og tilfeldig som mulig, med en variasjon av bokstaver, tall og symboler for å gjøre ethvert brute force-angrep umulig.

Det er også viktig å skikkelig lagre denne passordfrasen, på samme måte som den mnemoniske frasen. **Å miste den betyr å miste tilgangen til dine bitcoins**. Jeg fraråder sterkt å kun huske den i hodet ditt, da dette urimelig øker risikoen for tap. Det ideelle er å skrive den ned på et fysisk medium (papir eller metall) separat fra den mnemoniske frasen. Denne sikkerhetskopien må åpenbart oppbevares på et annet sted enn hvor din mnemoniske frase er oppbevart for å forhindre at begge blir kompromittert samtidig.

## Veiledninger

For å sette opp en passordfrase på en Ledger-enhet (Stax, Flex, eller Nano), kan du konsultere denne veiledningen:

https://planb.network/tutorials/wallet/passphrase-ledger