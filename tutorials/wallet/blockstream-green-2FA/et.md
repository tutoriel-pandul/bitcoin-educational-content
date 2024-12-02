---
name: Blockstream Green - 2FA
description: 2/2 multisig seadistamine Green Wallet'is
---
![cover](assets/cover.webp)

Tarkvaraline rahakott on rakendus, mis on paigaldatud arvutisse, nutitelefoni või mõnda muusse Internetiga ühendatud seadmesse, võimaldades hallata ja kaitsta oma Bitcoin'i rahakoti võtmeid. Erinevalt riistvaralistest rahakottidest, mis isoleerivad privaatvõtmeid, töötavad "kuumad" rahakotid keskkonnas, mis võib olla avatud küberrünnakutele, suurendades häkkimise ja varguse riske.

Tarkvaralisi rahakotte kasutatakse mõistlike Bitcoin'i summade haldamiseks, eriti igapäevaste tehingute jaoks. See võib olla huvitav valik inimestele, kellel on piiratud Bitcoin'i portfell, kelle jaoks riistvaralise rahakoti investeering võib tunduda ebaproportsionaalne. Siiski muudab nende pidev Interneti-ühendus neid vähem turvaliseks teie pikaajaliste säästude või oluliste fondide hoidmiseks. Nende jaoks on eelistatav valida turvalisemad lahendused, nagu riistvaralised rahakotid.

Selles õpetuses näitan teile, kuidas suurendada kuumale rahakotile turvalisust, kasutades Blockstream Green'is "2FA" valikut.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Sissejuhatus Blockstream Green'i

Blockstream Green on tarkvaraline rahakott, mis on saadaval mobiilil ja lauaarvutil. Varem tuntud kui *Green Address*, sai see rahakott Blockstreami projektiks pärast selle omandamist 2016. aastal.

Green on rakendus, mis on eriti lihtne kasutada, muutes selle huvitavaks algajatele. See pakub kõiki hea Bitcoin'i rahakoti olulisi omadusi, sealhulgas RBF (*Replace-by-Fee*), võimalust ühenduda Tor'i kaudu, võimalust ühendada oma sõlm, SPV (*Simple Payment Verification*) valikut, märgistamist ja mündikontrolli.

Blockstream Green toetab ka Liquid võrku, Bitcoin'i kõrvalahelat, mille on välja töötanud Blockstream kiirete ja konfidentsiaalsete tehingute sooritamiseks peamisest plokiahelast väljaspool. Selles õpetuses keskendume ainult Bitcoin'ile, kuid olen teinud ka teise õpetuse, et õppida, kuidas kasutada Liquid'i Green'is:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## 2/2 multisig (2FA) valik

Green'is saate kindlasti luua klassikalise "singlesig" kuum rahakott. Kuid teil on ka "2FA multisig" valik, mis võimaldab parandada teie kuum rahakott turvalisust ilma selle igapäevast haldamist liigselt keerukaks muutmata.
Seega seadistate 2/2 multisig rahakoti, mis tähendab, et iga tehing nõuab kahe võtme allkirja. Esimene võti, mis on tuletatud teie 12 või 24-sõnalise mnemoonilise fraasist, on kohapeal turvatud PIN-koodiga teie telefonis. Teil on selle võtme üle täielik kontroll. Teine võti hoitakse Blockstream'i serverites ja selle kasutamine allkirjastamiseks nõuab autentimist, mida saab saavutada koodi saamisega e-posti, SMS-i, telefonikõne kaudu või, nagu me selles õpetuses näeme, autentimisrakenduse kaudu (Authy, Google Authenticator jne).

Teie autonoomia tagamiseks Blockstream'i rikke korral (näiteks kui ettevõte läheb pankrotti või teise võtit hoidevad serverid hävitatakse), rakendatakse teie multisig'ile ajalukumehhanismi. See mehhanism muudab 2/2 multisig'i 1/2 multisig'iks umbes aasta pärast (või täpselt 51,840 ploki järel, kuid seda väärtust saab muuta), pärast mida vajab teie rahakott teie kohalikku võtit ainult bitcoinide kulutamiseks. Seega, kui kaotate juurdepääsu Blockstream'i serveritele või 2FA autentimisele, peate lihtsalt ootama kuni aasta, et saaksite oma bitcoine oma rakendusega vabalt kasutada, sõltumata Blockstream'ist.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
See meetod suurendab oluliselt teie kuum rahakoti turvalisust, jättes teile kontrolli oma bitcoinide üle ja hõlbustades nende igapäevast kasutamist. Siiski nõuab see regulaarselt ajaluku lukustuse värskendamist, et säilitada 2FA turvalisus. 360-päevane loendus, mille jooksul teie vahendid on kaitstud 2FA-ga, algab kohe, kui saate bitcoine. Kui 360 päeva pärast nende saamist pole te tehingut teinud, mis kulutaks neid vahendeid, on teie bitcoinid kaitstud ainult teie kohaliku võtmega, ilma 2FA-ta.

See piirang muudab 2FA valiku rohkem sobivaks kulutamise rahakotiks, kus regulaarsed tehingud uuendavad automaatselt ajaluku lukustusi. Pikaajalise säästu rahakoti jaoks võib see olla problemaatiline, kuna peate mõtlema iga aasta enne ajaluku lukustuse aegumist endale pühkimistehingu tegemisele.

Teine selle turvameetodi puudus on see, et peate kasutama vähemuslikke skriptimustreid. See tähendab, et privaatsuse seisukohast muutuvad asjad keeruliseks: väga vähesed inimesed kasutavad sama tüüpi skripti nagu teie, võimaldades välisel vaatlejal teie rahakoti jalajälge kergemini tuvastada. Lisaks toovad need skriptid kaasa suuremad tehingutasud nende suurema suuruse tõttu.
Kui eelistate mitte kasutada 2FA valikut ja soovite lihtsalt seadistada "singlesig" rahakoti Greenis, siis soovitan teil vaadata seda teist õpetust:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Blockstream Green tarkvara installimine ja seadistamine

Esimene samm on loomulikult Greeni rakenduse allalaadimine. Minge oma rakenduste poodi:
- [Androidile](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Apple'ile](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

Androidi kasutajatel on võimalus rakendus installida ka `.apk` faili kaudu [saadaval Blockstreami GitHubis](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Käivitage rakendus, seejärel märkige ruut "*Nõustun tingimustega...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Kui avate Greeni esimest korda, ilmub avakuva ilma seadistatud rahakottideta. Hiljem, kui loote või impordite rahakotte, ilmuvad need sellesse liidesesse. Enne rahakoti loomisele üleminekut soovitan teil rakenduse seadeid oma ootustele vastavalt kohandada. Klõpsake "*Rakenduse seaded*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

"*Täiustatud privaatsus*" valik, mis on saadaval ainult Androidis, parandab privaatsust, keelates ekraanipildid ja peites rakenduse eelvaated. See lukustab ka automaatselt juurdepääsu rakendusele kohe, kui teie telefon lukustub, muutes teie andmed raskemini paljastatavaks.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

Need, kes soovivad oma privaatsust suurendada, pakub rakendus võimalust suunata teie liiklus läbi Tori, võrgu, mis krüpteerib kõik teie ühendused ja muudab teie tegevused raskesti jälgitavaks. Kuigi see valik võib rakenduse jõudlust veidi aeglustada, on see väga soovitatav teie privaatsuse kaitsmiseks, eriti kui te ei kasuta oma täisnodi.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

Kasutajatele, kellel on oma täisnodi, pakub Green Wallet võimalust sellega ühenduda Electrumi serveri kaudu, tagades täieliku kontrolli Bitcoin võrgu teabe ja tehingute edastamise üle.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
Teine alternatiivne funktsioon on "*SPV kontrollimine*", mis võimaldab teatud plokiahela andmete otsekontrolli, vähendades vajadust usaldada Blockstreami vaikimisi sõlme, kuigi see meetod ei paku kõiki täissõlme garantiisid.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Kui need seaded on teie vajadustele vastavalt kohandatud, klõpsake nupul "*Salvesta*" ja taaskäivitage rakendus.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Bitcoini rahakoti loomine Blockstream Greenis

Nüüd olete valmis looma Bitcoini rahakoti. Klõpsake nupul "*Alusta*".

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Teil on valik luua tarkvararahakott kohapeal või hallata külma rahakotti riistvararahakoti kaudu. Selle õpetuse jaoks keskendume kuumale rahakotile, seega peate valima valiku "*Sellel seadmel*".

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Järgmisena võite valida olemasoleva Bitcoini rahakoti taastamise või uue loomise vahel. Selle õpetuse eesmärgil loome uue rahakoti. Kui aga peate taastama olemasoleva Bitcoini rahakoti selle mnemoonilisest fraasist, näiteks oma vana telefoni kaotuse tõttu, peate valima teise võimaluse.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Seejärel on teil valik 12-sõnalise või 24-sõnalise mnemoonilise fraasi vahel. See fraas võimaldab teil taastada juurdepääsu oma rahakotile mis tahes ühilduvas tarkvaras, kui teie telefoniga peaks midagi juhtuma. Praegu ei paku 24-sõnaline fraas rohkem turvalisust kui 12-sõnaline fraas. Seetõttu soovitan valida **12-sõnalise** mnemoonilise fraasi.

Green annab teile seejärel teie mnemoonilise fraasi. Enne jätkamist veenduge, et teid ei jälgitaks. Klõpsake nupul "*Näita taastefraasi*", et kuvada see ekraanil.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**See mnemooniline fraas annab täieliku ja piiramatu juurdepääsu kõigile teie bitcoinidele**. Igaüks, kes on selle fraasi valduses, võib teie vahendid varastada, isegi ilma füüsilise juurdepääsuta teie telefonile (tingimustel, kui ajalukk on aegunud või 2FA puhul 2/2 rahakoti korral Greenis).

See võimaldab teil taastada juurdepääsu oma kohalikele võtmetele juhul, kui kaotate telefoni, see varastatakse või saab kahjustada. Seetõttu on väga oluline hoolikalt salvestada see **füüsilisel kandjal (mitte digitaalselt)** ja hoida seda turvalises kohas. Võite selle üles kirjutada paberitükile või suurema turvalisuse huvides, kui see rahakott on oluline, soovitan graveerida selle roostevabast terasest kandjale, et kaitsta tulekahju, üleujutuste või kokkuvarisemiste eest (kuuma rahakoti puhul, mis on mõeldud väikese hulga bitcoinide turvamiseks, on tõenäoliselt piisav lihtne paberist varukoopia).
*Ilmselgelt ei tohiks te neid sõnu kunagi internetis jagada, erinevalt sellest, mida ma teen selles õpetuses. See näidisrahakott kasutatakse ainult Testnetis ja kustutatakse õpetuse lõpus.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Pärast oma mnemoonilise fraasi õiget märkimist füüsilisele kandjale klõpsake nupul "*Jätka*". Green Wallet palub teil kinnitada mõned fraasi sõnad, et kontrollida, kas olete need õigesti üles kirjutanud. Täitke tühjad puuduvate sõnadega.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Valige oma seadme PIN-kood, mida kasutatakse teie Green rahakoti avamiseks. Seega on see kaitse volitamata füüsilise juurdepääsu vastu. See PIN-kood ei mängi rolli teie rahakoti krüptograafiliste võtmete tuletamisel. Seega isegi ilma sellele PIN-koodile juurdepääsuta võimaldab teie 12 või 24-sõnaline mnemooniline fraas teil taastada juurdepääsu oma kohalikele võtmetele.
Soovitatav on valida võimalikult juhuslik 6-kohaline PIN-kood. Samuti veenduge, et salvestate selle koodi, et te seda ei unustaks, vastasel juhul peate oma rahakoti taastama mnemoonilise fraasi abil. Hiljem võite lisada võimaluse biomeetriliseks lukustamiseks, et vältida iga kord PIN-koodi sisestamist. Üldiselt on biomeetria palju vähem turvaline kui PIN-kood ise. Seetõttu soovitan vaikimisi seda avamisvõimalust mitte seadistada.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Sisestage oma PIN-kood teist korda, et seda kinnitada.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Oodake, kuni teie rahakott luuakse, seejärel klõpsake nupul "*Loo konto*".

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Seejärel on teil valik standardse ühe allkirjaga rahakoti ja kahefaktorilise autentimisega (2FA) kaitstud rahakoti vahel. Selles õpetuses valime teise võimaluse.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

Ja ongi kõik, teie Bitcoin multisig rahakott on edukalt loodud kasutades Green rakendust!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## 2FA seadistamine

Klõpsake oma kontol.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Klõpsake rohelisel nupul "*Suurenda oma konto turvalisust, lisades 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Seejärel on teil võimalus valida autentimismeetod, et pääseda juurde oma 2/2 multisigi teisele võtmele. Selle õpetuse jaoks kasutame autentimisrakendust. Kui te pole sellise tüüpi rakendusega tuttav, soovitan meie õpetust Authy kohta konsulteerida:
https://planb.network/tutorials/others/authy

Valige "*Autentimisrakendus*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green kuvab seejärel QR-koodi ja taastamisvõtme. See võti võimaldab teil taastada juurdepääsu oma 2FA-le, kui kaotate oma Authy rakenduse. Soovitatav on teha sellest võtmest turvaline varukoopia, kuigi nagu varem selgitatud, saate alati oma bitcoinidele juurdepääsu taastada pärast ajaluku aegumist.

Oma autentimisrakenduses lisage uus kood, seejärel skannige Greeni poolt pakutud QR-kood.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Ilmselgelt ei tohiks te seda võtit ja QR-koodi internetis jagada, vastupidiselt sellele, mida ma selles õpetuses teen. See näidisrahakott kasutatakse ainult Testnetis ja kustutatakse õpetuse lõpus.*

Klõpsake nupul "*Jätka*".

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Sisestage oma autentimisrakenduses olev dünaamiline 6-kohaline kood.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

Kahefaktoriline autentimine on nüüd lubatud.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Selle menüü sirvimisel saate samuti kohandada ajaluku kestust. See loendur käivitub bitcoinide vastuvõtmisel ja kui ajalukk aegub, saab teie vahendeid kulutada ainult teie kohaliku võtmega, ilma et oleks vaja 2FA-d. Vaikimisi kestus on määratud 12 kuuks, kuid säästukonto puhul võib olla mõistlik valida 15 kuud, et minimeerida ajaluku uuendamise sagedust. Vastupidiselt, kulutamise rahakoti puhul võib eelistada 6 kuu pikkust ajalukku, kuna see uuendatakse sageli teie igapäevaste tehingutega ja lühem ajalukk vähendab ooteaega probleemide korral 2FA-ga. Teie otsustada on, milline ajaluku kestus teile kõige paremini sobib.
![GREEN 2FA MULTISIG](assets/fr/30.webp)

Nüüd võite sellest menüüst väljuda. Teie multisig rahakott on valmis!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Oma rahakoti seadistamine Blockstream Greenis

Kui soovite oma rahakotti kohandada, klõpsake paremas ülanurgas kolmel väikesel punktil.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
"*Rename*" valik võimaldab teil kohandada oma rahakoti nime, mis on eriti kasulik, kui haldate sama rakenduse peal mitut rahakotti.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

"*Unit*" menüü annab teile võimaluse muuta oma rahakoti baasühikut. Näiteks võite valida selle kuvamise satoshi'des bitcoini asemel.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

"*Settings*" menüü pakub juurdepääsu teie Bitcoin rahakoti erinevatele valikutele.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Siin leiate näiteks oma laiendatud avaliku võtme ja selle *descriptori*, mis on kasulik, kui plaanite sellest rahakotist seadistada ainult-vaatamise rahakoti.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

Samuti saate muuta oma rahakoti PIN-koodi ja lubada biomeetrilist sisselogimist.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Blockstream Greeni kasutamine

Nüüd, kui teie Bitcoin rahakott on seadistatud, olete valmis vastu võtma oma esimesed satid! Selleks klõpsake lihtsalt "*Receive*" nupul.

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green kuvab seejärel teie rahakoti esimese tühja vastuvõtu aadressi. Saate kas skannida seotud QR-koodi või kopeerida aadressi otse, et saata sinna bitcoine. Selline aadress ei määra saatja poolt saadetava summa suurust. Siiski saate genereerida aadressi, mis nõuab konkreetset summat, klõpsates paremas ülanurgas kolmel väikesel punktil, seejärel "*Request Amount*" ja sisestades soovitud summa.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Kui tehing on võrgus edastatud, ilmub see teie rahakotti.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Oodake piisavalt kinnituste saamist, et pidada tehingut lõplikuks.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

Bitcoine oma rahakotis, saate neid nüüd ka saata. Klõpsake "*Send*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

Järgmisel lehel sisestage saaja aadress. Saate selle sisestada käsitsi või skannida QR-koodi.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Valige makse summa.
![GREEN 2FA MULTISIG](assets/fr/44.webp) Ekraani allosas saate valida selle tehingu tasumäära. Teil on võimalus järgida rakenduse soovitusi või kohandada oma tasusid. Mida kõrgemad on tasud võrreldes teiste ootel olevate tehingutega, seda kiiremini teie tehing töödeldakse. Tasuturu mõistmiseks võite külastada [Mempool.space](https://mempool.space/) lehel jaotist "*Transaction Fees*".

![GREEN 2FA MULTISIG](assets/fr/45.webp)

Klõpsake nuppu "*Next*", et pääseda juurde oma tehingu kokkuvõtte ekraanile. Kontrollige, kas aadress, summa ja tasud on õiged.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Kui kõik tundub teile korras, libistage ekraani allosas olevat rohelist nuppu paremale, et allkirjastada ja edastada tehing Bitcoin'i võrgus.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

See on hetk, mil peate sisestama oma autentimiskoodi, et avada Blockstreami poolt hoitava multisigi teine võti. Sisestage oma autentimisrakenduses kuvatav 6-kohaline kood.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Teie tehing ilmub nüüd teie Bitcoin'i rahakoti armatuurlauale ootel kinnitust.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

Ja ongi kõik, nüüd teate, kuidas hõlpsalt seadistada 2/2 multisigi rahakotti, kasutades Blockstream Green'i 2FA valikut!

Kui leidsite selle õpetuse kasuliku, oleksin tänulik, kui jätaksite allapoole rohelise pöidla. Julgelt jagage seda artiklit oma sotsiaalvõrgustikes. Suur tänu!

Soovitan samuti tutvuda selle teise põhjaliku õpetusega Blockstream Green'i mobiilirakenduse kohta Liquid rahakoti seadistamiseks:

https://planb.network/tutorials/wallet/blockstream-green-liquid