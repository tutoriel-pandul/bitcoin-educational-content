---
nimi: Blockstream Green - Liquid
kirjeldus: Rahakoti seadistamine Liquid Network kõrvalahelal
---
![kaas](assets/cover.webp)
Bitcoin'i protokollil on tahtlikud tehnilised piirangud, mis aitavad säilitada võrgu detsentraliseeritust ja tagavad turvalisuse jaotumise kõigi kasutajate vahel. Siiski võivad need piirangud mõnikord kasutajaid frustratsiooni tekitada, eriti ummikute ajal, mida põhjustab suur hulk samaaegseid tehinguid. Vaidlus Bitcoin'i skaleeritavuse üle on kogukonda pikka aega lõhestanud, eriti Blocksize Sõja ajal. Sellest episoodist alates on Bitcoin'i kogukonnas laialdaselt tunnustatud, et skaleeritavust tuleb tagada väljaspool plokiahelat asuvate lahendustega, teise kihi süsteemides. Nende lahenduste hulka kuuluvad kõrvalahelad, mis on endiselt suhteliselt tundmatud ja kasutamata võrreldes teiste süsteemidega nagu Lightning Network.

Kõrvalahel on iseseisev plokiahel, mis töötab paralleelselt peamise Bitcoin'i plokiahelaga. See kasutab bitcoini kui arvestusühikut mehhanismi kaudu, mida nimetatakse "*kahepoolseks sidumiseks*". See süsteem võimaldab lukustada bitcoine peamisel ahelal, et kopeerida nende väärtus kõrvalahelal, kus need ringlevad tokenitena, mida toetavad algsete bitcoinide tagatisel. Need tokenid säilitavad tavaliselt väärtuse pariteedi peamisel ahelal lukustatud bitcoinidega ja protsessi saab pöörata, et taastada vahendid Bitcoin'is.

Kõrvalahelate eesmärk on pakkuda lisafunktsioone või tehnilisi täiustusi, nagu kiiremad tehingud, väiksemad tasud või nutilepingute tugi. Neid uuendusi ei saa alati otse Bitcoin'i plokiahelale rakendada ilma selle detsentraliseeritust või turvalisust ohustamata. Kõrvalahelad võimaldavad seega testida ja uurida uusi lahendusi, säilitades samal ajal Bitcoin'i terviklikkuse. Siiski nõuavad need protokollid sageli kompromisse, eriti detsentraliseerituse ja turvalisuse osas, sõltuvalt valitud valitsemismudelist ja konsensuse mehhanismist.

Täna on kõige tuntum kõrvalahel tõenäoliselt Liquid. Selles õpetuses tutvustan ma esmalt, mis on Liquid, ja seejärel juhendan teid, kuidas seda Blockstream Green rakenduse kaudu lihtsalt kasutama hakata, et kasutada ära selle eeliseid.

![LIQUID GREEN](assets/fr/01.webp)

## Mis on Liquid Network?

Liquid on federatiivne kõrvalahel, mis on ehitatud Bitcoin'i peale, mille on välja töötanud Blockstream, eesmärgiga parandada tehingute kiirust, privaatsust ja funktsionaalsust. See kasutab kahepoolset ankurdamismehhanismi, mis on loodud föderatsiooni alusel, et lukustada bitcoine peamisel ahelal ja luua vastutasuks Liquid-bitcoine (L-BTC), tokeneid, mis ringlevad Liquid'is, jäädes samal ajal toetatud algsete bitcoinide poolt.

![LIQUID GREEN](assets/fr/02.webp)
Liquid võrgustik põhineb föderatsiooni osalejatel, kes koosnevad Bitcoin'i ökosüsteemist tunnustatud üksustest, kes valideerivad blokke ja haldavad kahepoolset ankurdamist. Lisaks L-BTC-le võimaldab Liquid ka teiste digitaalsete varade, nagu stabiilrahad või muud krüptovaluutad, emiteerimist.
![LIQUID GREEN](assets/fr/03.webp)

## Tutvustus Blockstream Green'ile

Blockstream Green on tarkvararahakott, mis on saadaval mobiilil ja lauaarvutil. Varem tuntud kui *Green Address*, sai sellest rahakott Blockstreami projekt pärast selle omandamist 2016. aastal.

Green on rakendus, mis on eriti lihtne kasutada, muutes selle huvitavaks algajatele. See pakub kõiki hea Bitcoin'i rahakoti olulisi omadusi, sealhulgas RBF (*Replace-by-Fee*), võimaluse ühenduda Tori kaudu, võimaluse ühendada oma sõlm, SPV (*Simple Payment Verification*) valiku, märgistamise ja mündikontrolli.

Blockstream Green toetab ka Liquid võrgustikku ja just seda me selles õpetuses uurime. Kui soovite Green'i kasutada muudeks rakendusteks, soovitan teil konsulteerida ka nende teiste õpetustega:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Blockstream Green rakenduse installimine ja seadistamine

Esimene samm on loomulikult Green rakenduse allalaadimine. Mine oma rakenduste poodi:
- [Androidile](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Apple'ile](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Androidi kasutajatel on võimalus rakendus installida ka `.apk` faili kaudu, [mis on saadaval Blockstream'i GitHubis](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Käivita rakendus, seejärel märgi ruut "*Nõustun tingimustega...*".

![LIQUID GREEN](assets/fr/06.webp)

Kui avad Greeni esimest korda, ilmub avakuva ilma seadistatud rahakottideta. Hiljem, kui lood või impordid rahakotte, ilmuvad need sellesse liidesesse. Enne rahakoti loomisele üleminekut soovitan teil rakenduse seadeid oma ootustele vastavalt kohandada. Klõpsa "*Rakenduse seaded*".

![LIQUID GREEN](assets/fr/07.webp)

"*Täiustatud privaatsus*" valik, mis on saadaval ainult Androidil, parandab privaatsust, keelates ekraanipildid ja peites rakenduse eelvaated. See lukustab ka automaatselt juurdepääsu rakendusele kohe, kui telefon lukustub, muutes teie andmed raskemini kättesaadavaks.
![LIQUID GREEN](assets/fr/08.webp)
Neile, kes soovivad oma privaatsust suurendada, pakub rakendus võimalust suunata oma liiklus läbi Tori, võrgu, mis krüpteerib kõik teie ühendused ja muudab teie tegevused raskesti jälgitavaks. Kuigi see valik võib rakenduse jõudlust veidi aeglustada, on see väga soovitatav teie privaatsuse kaitsmiseks, eriti kui te ei kasuta oma täisnoodi.

![LIQUID GREEN](assets/fr/09.webp)

Kasutajatele, kellel on oma täisnood, võimaldab Green Wallet ühendada sellega Electrum serveri kaudu, tagades täieliku kontrolli Bitcoin võrgu informatsiooni ja tehingute edastamise üle. Siiski on see funktsioon oluline traditsiooniliste Bitcoin rahakottide jaoks, seega pole seda vaja, kui kasutate Liquidit.

![LIQUID GREEN](assets/fr/10.webp)

Teine alternatiivne funktsioon on "*SPV kontrollimine*", mis võimaldab teatud plokiahela andmete otsese kontrollimise, vähendades vajadust usaldada Blockstreami vaikimisi noodit, kuigi see meetod ei paku kõiki täisnoodi tagatisi. Jällegi, see puudutab ainult teie onchain Bitcoin rahakotte, mitte Liquidit.

![LIQUID GREEN](assets/fr/11.webp)

Kui need seaded on teie vajadustele vastavalt kohandatud, klõpsa "*Salvesta*" nuppu ja taaskäivita rakendus.

![LIQUID GREEN](assets/fr/12.webp)

## Liquid rahakoti loomine Blockstream Greenis

Nüüd olete valmis Liquid rahakoti looma. Klõpsa "*Alusta*" nuppu.

![LIQUID GREEN](assets/fr/13.webp)

Teil on valik luua tarkvararahakott kohapeal või hallata külma rahakotti riistvara rahakoti kaudu. Selles õpetuses keskendume Liquidis kuumale rahakotile loomisele, seega peate valima valiku "*Sellel seadmel*". Samuti võite kasutada ühilduvat riistvara rahakotti, nagu Blockstream Jade, et turvata oma Liquid rahakotti.

![LIQUID GREEN](assets/fr/14.webp)
Seejärel saate valida olemasoleva Bitcoin'i rahakoti taastamise või uue loomise vahel. Selle õpetuse eesmärgil loome uue rahakoti. Kui aga peate näiteks oma riistvara rahakoti kaotuse tõttu taastama olemasoleva Liquid rahakoti selle mnemoonilise fraasi abil, peate valima teise võimaluse.
![LIQUID GREEN](assets/fr/15.webp)

Seejärel on teil valik 12-sõnalise või 24-sõnalise mnemoonilise fraasi vahel. See fraas võimaldab teil taastada juurdepääsu oma rahakotile mis tahes ühilduvas tarkvaras, kui teie telefoniga peaks tekkima probleeme. Praegu ei paku 24-sõnaline fraas rohkem turvalisust kui 12-sõnaline fraas. Seetõttu soovitan valida **12-sõnalise** mnemoonilise fraasi.
Green annab teile seejärel teie mnemoonilise fraasi. Enne jätkamist veenduge, et teid ei jälgita. Klõpsake nupul "*Näita taastefraasi*", et kuvada see ekraanil.
![LIQUID GREEN](assets/fr/16.webp)

**See mnemooniline fraas annab täieliku ja piiramatu juurdepääsu kõigile teie bitcoinidele.** Igaüks, kes on selle fraasi omandanud, võib teie vahendid varastada, isegi ilma füüsilise juurdepääsuta teie telefonile.

See võimaldab teil taastada juurdepääsu oma bitcoinidele kaotuse, varguse või telefoni kahjustumise korral. Seetõttu on väga oluline see hoolikalt salvestada **füüsilisel kandjal (mitte digitaalsel)** ja hoida seda turvalises kohas. Võite selle kirjutada paberitükile või, kui see rahakott on oluline, soovitan turvalisuse huvides graveerida selle roostevabast terasest kandjale, et kaitsta tulekahju, üleujutuste või kokkuvarisemiste ohtude eest (kuuma rahakoti jaoks, mis on mõeldud väikese hulga bitcoinide turvamiseks, on tõenäoliselt piisav lihtne paberist varukoopia).

*Ilmselgelt ei tohiks te neid sõnu internetis jagada, vastupidiselt sellele, mida ma selles õpetuses teen. See näidisrahakott kasutatakse ainult Liquid Testnetis ja kustutatakse õpetuse lõpus.*

![LIQUID GREEN](assets/fr/17.webp)

Pärast oma mnemoonilise fraasi õiget märkimist füüsilisele kandjale klõpsake nupul "*Jätka*". Green Wallet palub teil kinnitada mõned fraasi sõnad, et kontrollida, kas olete need õigesti üles kirjutanud. Täitke tühjad puuduvate sõnadega.

![LIQUID GREEN](assets/fr/18.webp)

Valige oma seadme PIN-kood, mida kasutatakse teie Green rahakoti avamiseks. Seega on see kaitse volitamata füüsilise juurdepääsu vastu. See PIN-kood ei mängi rolli teie rahakoti krüptograafiliste võtmete tuletamisel. Seega, isegi ilma juurdepääsuta sellele PIN-koodile, võimaldab teie 12 või 24-sõnaline mnemooniline fraas teil taastada juurdepääsu oma bitcoinidele.

Soovitatav on valida võimalikult juhuslik 6-kohaline PIN-kood. Samuti veenduge, et salvestate selle koodi, et te seda ei unustaks, vastasel juhul peate oma rahakoti taastama mnemoonilise fraasi abil. Hiljem võite lisada biomeetrilise lukustamise võimaluse, et vältida PIN-koodi iga kord sisestamist, kui seda kasutate. Üldiselt on biomeetria palju vähem turvaline kui PIN-kood ise. Seetõttu soovitan vaikimisi seda avamisvõimalust mitte seadistada.

![LIQUID GREEN](assets/fr/19.webp)

Sisestage oma PIN-kood teist korda selle kinnitamiseks.

![LIQUID GREEN](assets/fr/20.webp)
Oodake, kuni teie rahakott on loodud, seejärel klõpsake nupul "*Loo konto*".
![LIQUID GREEN](assets/fr/21.webp)
"*Varad*" kastis valige "*Liquid Bitcoin*". Teil on seejärel valik standardse ühe allkirjaga rahakoti ja kahefaktorilise autentimisega (2FA) kaitstud rahakoti vahel, mida me selles õpetuses kasutame.
![LIQUID GREEN](assets/fr/22.webp)

Ja ongi kõik, teie Liquid rahakott on edukalt loodud kasutades Green rakendust!

![LIQUID GREEN](assets/fr/23.webp)

Enne oma esimese bitcoinide vastuvõtmist Liquid rahakotis, **soovitan tungivalt teha tühja taastamise testi**. Pane kirja viiteteave, nagu sinu xpub või esimene vastuvõtu aadress, seejärel kustuta oma rahakott Green rakenduses, kui see on veel tühi. Järgmisena proovi oma rahakotti Greenis taastada kasutades oma paberil varukoopiaid. Kontrolli, et taastamise järel genereeritud tunnistaja info ühtib algsega, mille üles märkisid. Kui see nii on, võid olla kindel, et sinu paberil varukoopiad on usaldusväärsed. Taastamise testi tegemise kohta lisateabe saamiseks soovitan konsulteerida selle teise õpetusega:

https://planb.network/tutorials/wallet/recovery-test

## Seadistades oma Liquid Rahakotti

Kui soovid oma rahakotti kohandada, klõpsa kolmel väikesel punktil üleval paremal.

![LIQUID GREEN](assets/fr/24.webp)

"*Nimeta ümber*" valik võimaldab sul kohandada oma rahakoti nime, mis on eriti kasulik, kui haldad sama rakenduse mitut rahakotti.

![LIQUID GREEN](assets/fr/25.webp)

"*Ühik*" menüü annab sulle võimaluse muuta oma rahakoti baasühikut. Näiteks võid valida selle kuvamise satoshi'des bitcoini asemel.

![LIQUID GREEN](assets/fr/26.webp)

"*Seaded*" menüü pakub juurdepääsu sinu Bitcoin rahakoti erinevatele valikutele.

![LIQUID GREEN](assets/fr/27.webp)

Siit leiad näiteks oma *kirjeldaja*, mis võib olla kasulik, kui plaanid sellest Liquid rahakotist seadistada ainult-vaatamise rahakoti.

![LIQUID GREEN](assets/fr/28.webp)

Samuti võid muuta oma rahakoti PIN-koodi ja lubada biomeetrilist sisselogimist.

![LIQUID GREEN](assets/fr/29.webp)

## Kasutades oma Liquid Rahakotti

Nüüd, kui sinu Liquid rahakott on seadistatud, oled valmis vastu võtma oma esimesed L-satid!
Kui sul veel ei ole L-BTC-d, on sul mitu võimalust. Esimene on lasta see endale otse saata. Kui keegi soovib maksta sulle bitcoinides Liquid peal, anna lihtsalt neile vastuvõtu aadress. Teine lahendus on vahetada oma onchain bitcoinid või need Lightning võrgust L-BTC vastu. Selleks võid kasutada [silda nagu Boltz](https://boltz.exchange/). Sisesta lihtsalt oma Liquid aadress saidil, seejärel tee makse kas Lightning võrgu kaudu või onchain.
![LIQUID GREEN](assets/fr/30.webp)

Liquid aadressi genereerimiseks klõpsa "*Vasta*" nupule.

![LIQUID GREEN](assets/fr/31.webp)

Green kuvab seejärel sinu rahakoti esimese tühja vastuvõtu aadressi. Sa võid kas skannida seotud QR-koodi või kopeerida aadressi otse, et saata sinna L-BTC.

![LIQUID GREEN](assets/fr/32.webp)

Kui tehing on võrgus edastatud, ilmub see sinu rahakotti.

![LIQUID GREEN](assets/fr/33.webp)

Oota piisavalt kinnituste saamist, et pidada tehingut lõplikuks. Liquidis peaksid kinnitused olema kiired, kuna blokk avaldatakse iga minuti järel.

![LIQUID GREEN](assets/fr/34.webp)
L-satsidega oma Liquid rahakotis saate neid nüüd ka saata. Klõpsake nupul "*Saada*".
![LIQUID GREEN](assets/fr/35.webp)

Järgmisel lehel sisestage saaja Liquid aadress. Saate selle sisestada käsitsi või skaneerida nende QR-koodi.

![LIQUID GREEN](assets/fr/36.webp)

Valige makse summa.

![LIQUID GREEN](assets/fr/37.webp)

Klõpsake nupul "*Järgmine*", et pääseda juurde oma tehingu kokkuvõtte ekraanile. Kontrollige, kas aadress, summa ja tasud on õiged.

![LIQUID GREEN](assets/fr/38.webp)

Kui kõik tundub teile korras, libistage ekraani allosas olevat rohelist nuppu paremale, et allkirjastada ja edastada tehing Bitcoin võrgus.

![LIQUID GREEN](assets/fr/39.webp)

Teie tehing ilmub nüüd teie Bitcoin rahakoti armatuurlauale kinnitamist ootama.

![LIQUID GREEN](assets/fr/40.webp)

Ja ongi kõik, nüüd teate, kuidas hõlpsalt kasutada Liquid kõrvalahelat Blockstream Green rakendusega!

Kui leidsite selle õpetuse kasuliku, hindaksin ma allpool pöidla üles. Julgelt jagage seda artiklit oma sotsiaalvõrgustikes. Suur tänu!

Soovitan samuti tutvuda selle teise põhjaliku õpetusega Blockstream Green mobiilirakenduse kohta, et seadistada onchain Bitcoin kuum rahakott:

https://planb.network/tutorials/wallet/blockstream-green