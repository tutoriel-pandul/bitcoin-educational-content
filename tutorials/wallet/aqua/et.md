---
nimi: Aqua
kirjeldus: Bitcoin, Lightning ja Liquid ühes rahakotis
---
![kaas](assets/cover.webp)

Aqua on mobiilirakendus, mis võimaldab hõlpsasti luua kuumat rahakotti Bitcoinile ja Liquidile ning pakub ka võimalust kasutada Lightningut ilma sõlme haldamise keerukuseta tänu integreeritud vahetustele. See toetab ka USDT stabiilmüntide haldamist erinevatel võrkudel.

Ettevõtte JAN3 poolt Samson Mow juhtimisel välja töötatud Aqua rakendus oli algselt spetsiaalselt kavandatud Ladina-Ameerika kasutajate vajadustele, kuigi see sobib igale kasutajale üle maailma. See on eriti huvitav algajatele ja neile, kes kasutavad Bitcoini igapäevaselt oma maksete jaoks.

Selles õpetuses uurime, kuidas kasutada Aqua paljusid funktsioone. Enne seda võtame hetke, et mõista, mis on Bitcoinil kõrvalahel ja kuidas Liquid töötab, mis võimaldab meil täielikult mõista Aqua huvi.

![AQUA](assets/fr/01.webp)

## Mis on kõrvalahel?

Bitcoin protokollil on tahtlikud tehnilised piirangud, mis aitavad säilitada võrgu detsentraliseeritust ja tagada turvalisuse jaotumise kõigi kasutajate vahel. Siiski võivad need piirangud mõnikord kasutajaid frustratsiooni tekitada, eriti ummikute ajal, mida põhjustab suur hulk samaaegseid tehinguid. Bitcoin'i skaleeritavuse üle peetud debatt on kogukonda pikka aega lõhestanud, eriti Blocksize War'i ajal. Sellest episoodist alates on Bitcoin'i kogukonnas laialdaselt tunnustatud, et skaleeritavust tuleb tagada väljaspool ahelat asuvate lahendustega, teise kihi süsteemides. Nende lahenduste hulka kuuluvad kõrvalahelad, mis on võrreldes teiste süsteemidega nagu Lightning Network veel suhteliselt tundmatud ja alakasutatud.

Kõrvalahel on iseseisev plokiahel, mis töötab paralleelselt peamise Bitcoin plokiahelaga. See kasutab bitcoini kui arvestusühikut mehhanismi kaudu, mida nimetatakse "*kahepoolseks sidumiseks*". See süsteem võimaldab lukustada bitcoine peamisel ahelal, et kopeerida nende väärtus kõrvalahelal, kus need ringlevad algsete bitcoinidega tagatud tokenitena. Need tokenid säilitavad tavaliselt väärtuse pariteedi peamisel ahelal lukustatud bitcoinidega ja protsessi saab pöörata, et vahendid Bitcoinis tagasi saada.
Kõrvalahelate eesmärk on pakkuda lisafunktsioone või tehnilisi täiustusi, nagu kiiremad tehingud, väiksemad tasud või nutilepingute tugi. Neid uuendusi ei saa alati otse Bitcoin plokiahelale rakendada ilma selle detsentraliseeritust või turvalisust ohustamata. Kõrvalahelad võimaldavad seega uute lahenduste katsetamist ja uurimist, säilitades samal ajal Bitcoin'i terviklikkuse. Siiski nõuavad need protokollid sageli kompromisse, eriti detsentraliseerituse ja turvalisuse osas, sõltuvalt valitud valitsemismudelist ja konsensuse mehhanismist.
## Mis on Liquid?

Liquid on Bitcoin'i peale ehitatud föderaalne kõrvalahel, mille on välja töötanud Blockstream, eesmärgiga parandada tehingute kiirust, privaatsust ja funktsionaalsust. See kasutab kahepoolset ankurdusmehhanismi, mis on loodud föderatsiooni põhjal, et lukustada bitcoine peamisel ahelal ja luua vastutasuks Liquid-bitcoine (L-BTC), tokeneid, mis ringlevad Liquidis, olles samal ajal tagatud algsete bitcoinidega.

![AQUA](assets/fr/02.webp)

Liquid võrgustik põhineb föderatsiooni osalejatel, kes koosnevad Bitcoin ökosüsteemist tunnustatud üksustest, kes valideerivad plokke ja haldavad kahepoolset ankurdust. Lisaks L-BTC-le võimaldab Liquid ka teiste digitaalvarade, nagu stabiilmünt USDT või muude krüptovaluutade, emiteerimist.

![AQUA](assets/fr/03.webp)

## Aqua rakenduse installimine

Esimene samm on loomulikult Aqua rakenduse allalaadimine. Minge oma rakenduste poodi:
- [Androidile](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Apple'ile](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
Androidi kasutajatel on võimalus rakendus installida ka `.apk` faili kaudu, [mis on saadaval nende GitHubis](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Käivitage rakendus, seejärel märkige ruut "*Olen lugenud ja nõustunud Kasutustingimuste & Privaatsuspoliitikaga*".

![AQUA](assets/fr/06.webp)

## Oma rahakoti loomine Aquas

Vajutage nupule "*Loo Rahakott*".

![AQUA](assets/fr/07.webp)

Ja ongi kõik, teie rahakott on juba loodud!

![AQUA](assets/fr/08.webp)

Kuid enne kõike muud, kuna tegemist on isehoitud rahakotiga, on hädavajalik teha oma mnemoonilisest fraasist füüsiline varukoopia. **See mnemooniline fraas annab täieliku ja piiramatu juurdepääsu kõigile teie bitcoinidele**. Igaüks, kes on selle fraasi omandanud, võib teie vahendid varastada, isegi ilma füüsilise juurdepääsuta teie telefonile.
See võimaldab teil taastada juurdepääsu oma bitcoinidele kaotuse, varguse või telefoni kahjustumise korral. Seetõttu on väga oluline see hoolikalt füüsilisel kandjal (mitte digitaalselt) varundada ja hoida turvalises kohas. Võite selle üles kirjutada paberitükile või suurema turvalisuse tagamiseks, kui see rahakott on oluline, soovitan ma graveerida selle roostevabast terasest kandjale, et kaitsta tulekahju, üleujutuste või kokkuvarisemise ohtude eest (kuuma rahakoti puhul, mille eesmärk on väikese hulga bitcoinide turvamine, on tõenäoliselt piisav lihtne paberist varukoopia).
Selleks vajutage seadete menüüle.

![AQUA](assets/fr/09.webp)

Seejärel vajutage "*Vaata Seemnefraasi*". Tehke sellest 12-sõnalisest fraasist füüsiline varukoopia.

![AQUA](assets/fr/10.webp)

Selles samas seadete menüüs saate muuta ka rakenduse keelt ning kasutatavat fiat valuutat.

![AQUA](assets/fr/11.webp)

Enne oma esimeste bitcoinide rahakotti vastuvõtmist **soovitan tungivalt teha kuiva taastamise testi**. Märkige üles viiteteave, näiteks teie xpub või esimene vastuvõtu aadress, seejärel kustutage oma rahakott Aqua rakenduses, kui see on veel tühi. Seejärel proovige oma rahakotti Aquas taastada, kasutades oma paberist varukoopiaid. Kontrollige, kas taastamise järel genereeritud tunnistusinfo ühtib algsega. Kui see nii on, võite olla kindel, et teie paberist varukoopiad on usaldusväärsed. Taastamistesti tegemise kohta lisateabe saamiseks soovitan konsulteerida selle teise õpetusega:

https://planb.network/tutorials/wallet/recovery-test

## Bitcoinide vastuvõtmine Aquas

Nüüd, kui teie rahakott on seadistatud, olete valmis vastu võtma oma esimesed satoshid! Lihtsalt vajutage "*Vasta*" nupule "*Rahakott*" menüüs.

![AQUA](assets/fr/12.webp)

Võite valida bitcoinide vastuvõtmise onchain, Liquid või Lightning kaudu.

![AQUA](assets/fr/13.webp)

Onchain tehingute puhul genereerib Aqua spetsiifilise vastuvõtu aadressi, kuhu saate oma satoshid vastu võtta.

![AQUA](assets/fr/14.webp)

Sarnaselt, kui valite Liquid, pakub Aqua teile Liquid aadressi.

![AQUA](assets/fr/15.webp)

Kui eelistate vahendeid vastu võtta Lightningu kaudu, peate esmalt määrama soovitud summa.

![AQUA](assets/fr/16.webp)

Seejärel vajutage "*Genereeri Arve*".

![AQUA](assets/fr/17.webp)
Aqua loob arve, et saada vahendeid Lightning rahakotist. On oluline märkida, et erinevalt onchain ja Liquid valikutest, vahendid, mis on saadud Lightning'i kaudu, konverteeritakse automaatselt L-BTC-ks Liquid'il kasutades Boltz tööriista, kuna Aqua ei ole Lightning sõlm. See protsess võimaldab teil vastu võtta ja saata vahendeid Lightning'i kaudu, kuid hoidmata kunagi oma bitcoine Lightning'il. ![AQUA](assets/fr/18.webp)

Isiklikult alustan ma bitcoine saates Lightning'i kaudu Aquasse. Kui tehing on esitatud arvega lõpule viidud, saadakse kinnitus.

![AQUA](assets/fr/19.webp)

Vahetuse edenemise jälgimiseks naaske oma rahakoti avalehele ja klõpsake "*L2 Bitcoin*" kontol, mis loetleb Lightning (vahetuse kaudu) ja Liquid tehingud.

![AQUA](assets/fr/20.webp)

Siin saate vaadata oma tehingut ja oma saldo L-BTC-s.

![AQUA](assets/fr/21.webp)

## Bitcoine vahetamine Aquas

Nüüd, kui teil on varasid oma Aqua rahakotis, on teil võimalus neid otse rakendusest vahetada, kas siis üle kanda peamisele Bitcoin'i plokiahelale või Liquid'ile. Samuti võite oma bitcoine konverteerida stabiilrahasse USDT (või teistesse). Selleks pääsege ligi "*Marketplace*" menüüle.

![AQUA](assets/fr/22.webp)

Klõpsake "*Swaps*".

![AQUA](assets/fr/23.webp)

"*Transfer from*" kastis valige vara, mida soovite vahetada. Praegu on mul ainult L-BTC, seega valin selle.

![AQUA](assets/fr/24.webp)

"*Transfer to*" kastis valige oma vahetuse sihtvara. Minu osa, ma valisin USDT Liquid võrgus.

![AQUA](assets/fr/25.webp)

Sisestage summa, mida soovite konverteerida.

![AQUA](assets/fr/26.webp)

Kinnitage, klõpsates "*Continue*".

![AQUA](assets/fr/27.webp)

Veenduge, et vahetuse seaded on teile meelepärased, seejärel kinnitage, libistades ekraani allosas olevat "*Swap*" nuppu.

![AQUA](assets/fr/28.webp)

Teie vahetus on nüüd kinnitatud.

![AQUA](assets/fr/29.webp)

Kui läheme tagasi oma rahakotti, näeme, et meil on nüüd USDT Liquid'il.

![AQUA](assets/fr/30.webp)

## Bitcoine saatmine Aquaga

Nüüd, kui teil on bitcoine oma Aqua rahakotis, on teil võimalus neid saata. Klõpsake "*Send*" nupul.

![AQUA](assets/fr/31.webp)

Valige vara, mida soovite saata, või valige võrk tehingu sooritamiseks. Minu osa, ma saadan bitcoine Lightning'i kaudu.

![AQUA](assets/fr/32.webp)
Seejärel sisestage makse saatmiseks vajalik teave: Bitcoin onchain või Liquid jaoks peate sisestama vastuvõtva aadressi; Lightning'i jaoks on vajalik arve. Saate selle teabe otse määratud väljale kleepida või kasutada QR-koodi ikooni, et avada oma kaamera ja skannida aadress või arve. Seejärel klõpsake "*Continue*".
![AQUA](assets/fr/33.webp)

Klõpsake uuesti "*Continue*", kui kogu teave tundub õige.

![AQUA](assets/fr/34.webp)
Aqua esitleb teile seejärel tehingu kokkuvõtet. Veenduge, et kogu teave on õige, eriti sihtkoha aadress, tasud ja summa. Tehingu kinnitamiseks libistage ekraani allosas asuvat nuppu "*Libista saatmiseks*".
![AQUA](assets/fr/35.webp)

Seejärel antakse teile saatmise kinnitus.

![AQUA](assets/fr/36.webp)

Ja ongi kõik, nüüd teate, kuidas kasutada Aqua rakendust Bitcoin'i, Lightning'i ja Liquid'i vahendite vastuvõtmiseks ja kulutamiseks, kõik ühest liidesest.

Kui leidsite selle õpetuse kasuliku, oleksin tänulik, kui jätaksite allapoole pöidla üles. Julgelt jagage seda artiklit oma sotsiaalvõrgustikes. Suur tänu!

Soovitan teil samuti tutvuda selle teise põhjaliku õpetusega Blockstream Green mobiilirakenduse kohta, mis on teine huvitav lahendus oma Liquid rahakoti seadistamiseks:

https://planb.network/tutorials/wallet/blockstream-green-liquid