---
name: GnuPG
description: Hvordan verifisere integriteten og autentisiteten til programvare?
---
![cover](assets/cover.webp)

Når du laster ned programvare, er det veldig viktig å forsikre seg om at den ikke har blitt endret og at den faktisk kommer fra den offisielle kilden. Dette er spesielt sant for programvare relatert til Bitcoin, som lommebokprogramvare, som lar deg sikre nøklene som gir tilgang til dine midler. I denne opplæringen vil vi se hvordan vi kan verifisere integriteten og autentisiteten til programvare før vi installerer den. Vi vil bruke Sparrow Wallet som et eksempel, en favoritt lommebokprogramvare blant bitcoinere, men prosedyren vil være den samme for hvilken som helst annen programvare.

Å verifisere integritet innebærer å forsikre seg om at den nedlastede filen ikke har blitt modifisert ved å sammenligne dens digitale fingeravtrykk (dvs. dens hash) med den som er oppgitt av den offisielle utvikleren. Hvis de to matcher, betyr det at filen er identisk med originalen og ikke har blitt korrupt eller modifisert av en angriper.

Å verifisere autentisitet, på den andre siden, sikrer at filen faktisk kommer fra den offisielle utvikleren og ikke en bedrager. Dette gjøres ved å verifisere en digital signatur. Denne signaturen beviser at programvaren ble signert med den legitime utviklerens private nøkkel.

Hvis disse sjekkene ikke utføres, er det en risiko for å installere skadelig programvare som kan inneholde modifisert kode. Denne koden kan enten stjele informasjon som dine private nøkler eller blokkere tilgang til filene dine. Denne typen angrep er ganske vanlig, spesielt i konteksten av åpen kildekode-programvare hvor forfalskede versjoner kan distribueres.

For å utføre denne verifiseringen, vil vi bruke to verktøy: hashing-funksjoner for å verifisere integritet, og GnuPG, et åpen kildekode-verktøy som implementerer PGP-protokollen, for å verifisere autentisitet.

## Forutsetninger

Hvis du er på **Linux**, er GPG forhåndsinstallert på de fleste distribusjoner. Hvis ikke, kan du installere det med følgende kommando:

```bash
sudo apt install gnupg
```

For **macOS**, hvis du ikke allerede har installert Homebrew pakkebehandler, gjør det med følgende kommandoer:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
```

```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Deretter installerer du GPG med denne kommandoen:

```bash
brew install gnupg
```
For **Windows**, hvis du ikke har GPG, kan du installere [Gpg4win](https://www.gpg4win.org/) programvaren.
![GnuPG](assets/notext/01.webp)

## Nedlasting av dokumenter

For å starte, trenger vi ulike dokumenter. Besøk den offisielle siden til [Sparrow Wallet i "*Download*" seksjonen](https://sparrowwallet.com/download/). Hvis du ønsker å verifisere en annen programvare, gå til den programvarens nettsted.

![GnuPG](assets/notext/02.webp)

Du kan også gå [til GitHub-repositoriet til prosjektet](https://github.com/sparrowwallet/sparrow/releases).

![GnuPG](assets/notext/03.webp)

Last ned installasjonsprogrammet for programvaren som tilsvarer ditt operativsystem.

![GnuPG](assets/notext/04.webp)

Du trenger også filens hash, ofte kalt "*SHA256SUMS*" eller "*MANIFEST*".

![GnuPG](assets/notext/05.webp)

Last ned PGP-signaturen til filen også. Dette er dokumentet i `.asc` format.

![GnuPG](assets/notext/06.webp)
Sørg for å plassere alle disse filene i samme mappe for de følgende stegene.
Til slutt vil du trenge utviklerens offentlige nøkkel, som vi vil bruke til å verifisere PGP-signaturen. Denne nøkkelen er ofte tilgjengelig enten på programmets nettsted, på GitHub-repositoriet til prosjektet, noen ganger på utviklerens sosiale medier, eller på spesialiserte sider som Keybase. I tilfellet Sparrow Wallet, kan du finne utvikler Craig Raws offentlige nøkkel [på Keybase](https://keybase.io/craigraw). For å laste den ned direkte fra terminalen, utfør kommandoen:

```bash
curl https://keybase.io/craigraw/pgp_keys.asc | gpg --import
```

![GnuPG](assets/notext/07.webp)

## Verifisering av Signaturen

Prosessen med å verifisere signaturen er den samme på **Windows**, **macOS**, og **Linux**. Normalt har du allerede importert den offentlige nøkkelen i det forrige steget, men hvis ikke, gjør det med kommandoen:

```bash
gpg --import [nøkkelsti]
```

Erstatt `[nøkkelsti]` med plasseringen av utviklerens offentlige nøkkelfil.

![GnuPG](assets/notext/08.webp)

Verifiser signaturen med følgende kommando:

```bash
gpg --verify [fil.asc]
```

Erstatt `[fil.asc]` med stien til signaturfilen. I tilfellet Sparrow, kalles denne filen "*sparrow-2.0.0-manifest.txt.asc*" for versjon 2.0.0.

![GnuPG](assets/notext/09.webp)

Hvis signaturen er gyldig, vil GPG indikere dette til deg. Du kan da gå videre til neste steg, da dette bekrefter filens autentisitet.

![GnuPG](assets/notext/10.webp)

## Verifisering av Hash
Nå som programmets autentisitet er bekreftet, er det også nødvendig å verifisere dets integritet. Vi vil sammenligne programmets hash med hashen som er oppgitt av utvikleren. Hvis de to matcher, garanterer det at programkoden ikke har blitt endret.

På **Windows**, åpne en terminal og utfør følgende kommando:

```bash
CertUtil -hashfile [filsti] SHA256 | findstr /v "hash"
```

Erstatt `[filsti]` med plasseringen av installasjonsfilen.

![GnuPG](assets/notext/11.webp)

Terminalen vil returnere hashen av den nedlastede programvaren.

![GnuPG](assets/notext/12.webp)

Vær oppmerksom på at for noen programmer, kan det være nødvendig å bruke en annen hashfunksjon enn SHA256. I så fall, erstatt bare navnet på hashfunksjonen i kommandoen.

Sammenlign deretter resultatet med den tilsvarende verdien i filen "*sparrow-2.0.0-manifest.txt*".

![GnuPG](assets/notext/13.webp)

I mitt tilfelle ser vi at de to hashene matcher perfekt.

På **macOS** og **Linux**, er hashverifiseringsprosessen automatisert. Det er ikke nødvendig å manuelt sjekke om de to hashene matcher som på Windows.

Utfør ganske enkelt denne kommandoen på **macOS**:

```bash
shasum --check [filnavn] --ignore-missing
```

Erstatt `[filnavn]` med navnet på installasjonsfilen. For eksempel, for Sparrow Wallet:

```bash
shasum --check sparrow-2.0.0-manifest.txt --ignore-missing
```

Hvis hashene matcher, bør du se følgende utdata:

```bash
Sparrow-2.0.0.dmg: OK
```
På **Linux** er kommandoen lignende:
```bash
sha256sum --check [filnavn] --ignore-missing
```

Og hvis hashene stemmer overens, bør du se følgende utskrift:

```bash
sparrow_2.0.0-1_amd64.deb: OK
```

Du kan nå være sikker på at programvaren du har lastet ned er både autentisk og intakt. Du kan fortsette med installasjonen på maskinen din.

Hvis du fant denne veiledningen nyttig, setter jeg pris på en tommel opp nedenfor. Føl deg fri til å dele denne artikkelen på dine sosiale nettverk. Tusen takk!

Jeg anbefaler også å sjekke ut denne andre veiledningen om VeraCrypt, en programvare som lar deg kryptere og dekryptere lagringsenheter.

https://planb.network/tutorials/others/veracrypt