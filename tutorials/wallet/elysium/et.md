---
nimi: Elysium Wallet
kirjeldus: Elysium Wallet'i seadistamine ja kasutamine
---

![cover-elysium](assets/cover.webp)

Elysium Wallet on esimene mittehoidlateenusega tarkvarakott Šveitsi idufirmalt Elysium Labs.

Tänu innovaatilisele võtmete haldamise süsteemile saate oma digitaalsetele varadele ligi pääseda igapäevaelus kasutatavate elementide abil: teie kasutajanimi, passkey, parool või pääsukood.
Just nii: Seed Phrase'i kasutamine oma digitaalsetele varadele juurdepääsu taastamiseks ei ole enam rangelt vajalik.
See lihtsustus võib kiirendada Bitcoini levikut üle maailma.

## Kuidas avada kontot?

Laadige alla Elysium Wallet'i rakendus Apple Store'ist või Google Play'st.
Avage oma seadmes allalaaditud Elysium Wallet'i rakendus.
Puudutage "Loo uus rahakott".
Ilmub kasutustingimuste ekraan.
Nõustumiseks ja konto loomise jätkamiseks puudutage "Alusta seadistamist".
Sisestage oma kasutajanimi.
Profiilipilt on kohandatav: valige pakutavate valikute hulgast, tehke foto või laadige pilt oma seadmest üles.
Kui olete valinud, puudutage "Jätka".

![Open](assets/open.webp)

Elysium paistab silma oma innovaatilise mitmefaktorilise algoritmi poolest, mis ühendab Passkey, PassCode ja PassWord.
PassKeys on kohustuslikud.
Need võimaldavad teil kiiresti ja turvaliselt autentida, kasutades seadme sisseehitatud turvafunktsioone, nagu Face ID või sõrmejälje skaneerimine.
Need on teie peamine kaitsekiht, tagades kiire ja turvalise juurdepääsu.

![Passkey](assets/passkey.webp)

Valige oma teine tase: PassCode või PassWord
Järgmisena peate valima teise turvatase:

- PassCode: 6-kohaline kood, mis on lihtne meelde jätta. Ideaalne lisakaitsekihi lisamiseks.
- Parool: Looge vähemalt 8 tähemärgist koosnev tugev parool, lisades veelgi turvalisust.

Peate kasutama Passkey'd koos PassCode või PassWord'iga.

![secondfactor](assets/secondfactor.webp)
Märkus: Konto seadistamiseks vajate vähemalt kahte faktorit, millest üks peab olema Passkey.

Turvalisuse suurendamiseks võite lisada kolmanda kaitsekihi (Passkey + PassCode + PassWord).

Kihtide kombinatsioon maksimaalseks turvalisuseks
Te kasutate alati Passkey'd kui peamist faktorit. Teise kihi jaoks valige PassCode või PassWord.
Kui olete valinud PassCode kui teise faktori, võite lisada PassWord kui kolmanda kihi või vastupidi. See paindlik lähenemine tagab, et teie varad on kaitstud vastavalt teie eelistustele.
Kolmanda turvafaktori saate lisada seadistamise faasis (vt pilte) või hiljem, minnes jaotisse Seaded > Paranda turvalisust.

![thirdfactor](assets/thirdfactor.webp)

Kui aga unustate ühe faktoritest, pange tähele, et:

Kui olete seadistanud kõik kolm faktorit, saate neid alati seadetest muuta või lähtestada.
Kahjuks, kui olete seadistanud ainult kaks faktorit ja unustate ühe, siis taastamisvõimalust ei ole.

Soovitame tungivalt seadistada algusest peale kõik kolm faktorit maksimaalse turvalisuse ja paindlikkuse tagamiseks.

## Kuidas vastu võtta tehingut?

1. samm: Avage Elysiumi rakendus ja minge põhimenüüsse. Puudutage 'Võta vastu'.

![receive1](assets/receive1.webp)

Nüüd valige kett, millel soovite makset vastu võtta (Bitcoin või Polygon) ja saate lihtsalt jagada oma Elysiumi rahakoti QR-koodi inimesega, kes peab teile maksma, nad hoolitsevad ülejäänu eest.

## Kuidas vastu võtta tehingut Lightning Network'is?
SAMM 1: Puudutades nuppu "Request Payment", taotlete Bitcoin'i makset läbi Lightning Network'i.
![requestpayment1](asset/requestpayment1)

Samm 2: Sisestage soovitud summa, valige valuuta, mida soovite saada, ja lisage vajadusel kirjeldus.

![requestpayment2](asset/requestpayment2)

Märkus: Esimese Lightning Network (LN) makse tegemisel avamaks LN kanalit, tuleb tasuda väike tasu. Pärast seda on kõik järgnevad maksed tasuta.

## Kuidas saata tehingut?

SAMM 1: Minge põhimenüüsse ja puudutage "Send".
![send1](assets/send1.webp)

SAMM 2: Skaneerige saaja QR-kood nende Elysium Wallet'ist, et salvestada automaatselt nende kontakt teie aadressiraamatusse.
Või kopeerige käsitsi nende aadress ja kleepige see saaja väljale.
Pärast saaja valimist või nende lisamist teie aadressiraamatusse puudutage "Send Payment".

![payment1](assets/payment1.webp)

Kas kontakt on juba olemas? Valige see otse aadressiraamatust.

![addressbook1](assets/addressbook1.webp)

SAMM 3: Sisestage summa, mida soovite saata, ja valige vara, mida soovite üle kanda.
BTC tehingute puhul saate valida eelistatud võrgukiiruse ja tasud (nagu on näidatud kolmandal pildil)

![payment2](assets/payment2.webp)

Teie tehing on esitatud! Saate hõlpsalt kontrollida oma Elysium Wallet'i uuendatud saldot ja tehingu staatust.

## Kuidas saata tehingut Lightning Network'is (LN)?

SAMM 1: Puudutage "Scan", et avada skanner.
SAMM 2: Skaneerige LN QR-kood makse jaoks.
SAMM 3: Vaadake üle makse üksikasjad ja kinnitage, et kõik on õige.
SAMM 4: Puudutage "Confirm", et tehing lõpule viia.

![paymentLN1](assets/paymentLN1.webp)

## Kuidas näha Seed Phrase'i?

Minge põhimenüüsse ja puudutage "Hub". Valige Settings ja puudutage "Extract private key".

![extract1](assets/extract1.webp)

Logige sisse oma passkey'ga ja sisestage oma parool ja/või pääsukood.
Seed phrase kuvatakse 24-sõnalises formaadis.

![seed1](assets/seed1.webp)

Ärge jagage seda kellegagi!

## Kuidas võtta ühendust toega?

Vajate abi Elysium Wallet'iga? Oleme siin, et aidata!

Laadige alla rakendus.
Siin on, kuidas võite meie klienditoe meeskonnaga rakendusest otse ühendust võtta:

1. Minge Hub'i
2. Puudutage Settings
3. Valige Help

![help1](assets/help1.webp)

Ilmub vorm, kus saate kirjeldada kogetavat probleemi.

Esitamise järel vastab meie meeskond esimesel võimalusel lahendusega!

Vea raporteerimiseks või tagasiside andmiseks klõpsake avalehel vidinal:

[help2](assets/help2.webp)