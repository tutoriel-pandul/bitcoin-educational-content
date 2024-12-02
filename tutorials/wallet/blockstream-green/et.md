---
name: Blockstream Green - Mobiil
description: Mobiilse tarkvarakoti seadistamine
---
![kaas](assets/cover.webp)

Tarkvarakott on rakendus, mis on paigaldatud arvutisse, nutitelefoni või mõnda muusse Internetiga ühendatud seadmesse, võimaldades hallata ja kaitsta oma Bitcoin'i kotti võtmeid. Erinevalt riistvarakottidest, mis isoleerivad privaatvõtmeid, töötavad "kuumad" kotid keskkonnas, mis võib olla avatud küberrünnakutele, suurendades häkkimise ja varguse riske.

Tarkvarakotte kasutatakse mõistlike bitcoinide koguste haldamiseks, eriti igapäevaste tehingute jaoks. See võib olla huvitav valik ka inimestele, kellel on piiratud Bitcoin'i portfell, kelle jaoks riistvarakoti investeering võib tunduda ebaproportsionaalne. Siiski, nende pidev Interneti-ühendus muudab need vähem turvaliseks teie pikaajaliste säästude või oluliste fondide hoidmiseks. Nende jaoks on eelistatav valida turvalisemad lahendused, nagu riistvarakotid.

Selles õpetuses tutvustan teile ühte parimat mobiilse tarkvarakoti lahendust: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Kui olete huvitatud õppimisest, kuidas kasutada Blockstream Green'i arvutis, palun vaadake seda teist õpetust:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Sissejuhatus Blockstream Green'i

Blockstream Green on tarkvarakott, mis on saadaval nii mobiilil kui ka arvutis. Varem tuntud kui *Green Address*, sai see kott Blockstreami projektiks pärast selle omandamist 2016. aastal.

Green on rakendus, mis on eriti lihtne kasutada, muutes selle huvitavaks algajatele. See pakub kõiki hea Bitcoin'i kotti olulisi omadusi, sealhulgas RBF (*Replace-by-Fee*), võimaluse ühenduda Tori kaudu, võimaluse ühendada oma sõlm, SPV (*Simple Payment Verification*) valiku, märgistamise ja mündikontrolli.

Blockstream Green toetab ka Liquid võrku, Bitcoin'i kõrvalahelat, mille on välja töötanud Blockstream kiirete ja konfidentsiaalsete tehingute sooritamiseks peamisest plokiahelast väljaspool. See õpetus keskendub ainult Bitcoin'ile, kuid tulevikus käsitletakse Liquid'i kasutamist.

## Blockstream Green'i rakenduse allalaadimine ja seadistamine

Esimene samm on loomulikult Green'i rakenduse allalaadimine. Minge oma rakenduste poodi:
- [Androidile](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Apple'ile](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Androidi kasutajatel on võimalus paigaldada rakendus ka `.apk` faili kaudu [saadaval Blockstream'i GitHub'is](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Käivitage rakendus, seejärel märkige ruut "*Nõustun tingimustega...*".
![GREEN](assets/fr/04.webp)

Kui avate Green'i esimest korda, ilmub avakuva ilma seadistatud rahakottideta. Hiljem, kui loote või impordite rahakotte, ilmuvad need sellesse liidesesse. Enne rahakoti loomisele üleminekut soovitan teil rakenduse seadeid oma ootustele vastavalt kohandada. Klõpsake "*Rakenduse seaded*".

![GREEN](assets/fr/05.webp)

"*Täiustatud privaatsus*" valik, mis on saadaval ainult Androidil, parandab privaatsust, keelates ekraanipildid ja peites rakenduse eelvaated. See lukustab ka automaatselt rakendusele juurdepääsu kohe, kui teie telefon lukustub, muutes teie andmed raskemini paljastatavaks.

![GREEN](assets/fr/06.webp)
Neile, kes soovivad oma privaatsust suurendada, pakub rakendus võimalust suunata teie liiklus läbi Tori, võrgu, mis krüpteerib kõik teie ühendused ja muudab teie tegevused jälitamiseks raskeks. Kuigi see valik võib rakenduse jõudlust veidi aeglustada, on see väga soovitatav teie privaatsuse kaitsmiseks, eriti kui te ei kasuta oma täisnoodi.
![GREEN](assets/fr/07.webp)

Kasutajatele, kellel on oma täisnood, pakub Green Wallet võimalust ühenduda sellega läbi Electrum serveri, tagades täieliku kontrolli Bitcoin võrgu informatsiooni ja tehingute edastamise üle.

![GREEN](assets/fr/08.webp)

Teine alternatiivne funktsioon on "*SPV kontrollimine*" valik, mis võimaldab teatud plokiahela andmete otsekontrolli, vähendades vajadust usaldada vaikimisi Blockstreami noodit, kuigi see meetod ei paku kõiki täisnoodi garantiisid.

![GREEN](assets/fr/09.webp)

Kui need seaded on teie vajadustele vastavalt kohandatud, klõpsake nuppu "*Salvesta*" ja taaskäivitage rakendus.

![GREEN](assets/fr/10.webp)

## Bitcoin rahakoti loomine Blockstream Greenis

Nüüd olete valmis looma Bitcoin rahakoti. Klõpsake nupul "*Alusta*".

![GREEN](assets/fr/11.webp)

Teil on valik luua tarkvararahakott kohapeal või hallata külma rahakotti riistvararahakoti kaudu. Selle õpetuse jaoks keskendume kuumale rahakotile loomisele, seega peate valima valiku "*Sellel seadmel*". Tulevases õpetuses näitan teile, kuidas kasutada teist valikut.

Teisest küljest võimaldab "*Ainult-vaatamise*" valik teil importida laiendatud avaliku võtme (`xpub`), et vaadata rahakoti tehinguid ilma seotud vahendite kulutamise võimaluseta, mis on mugav näiteks riistvararahakoti jälgimiseks.

![GREEN](assets/fr/12.webp)
Seejärel saate valida olemasoleva Bitcoin rahakoti taastamise või uue loomise vahel. Selle õpetuse eesmärgil loome uue rahakoti. Kui aga peate taastama juba olemasoleva Bitcoin rahakoti selle mnemoonilisest fraasist, näiteks oma riistvararahakoti kaotuse tõttu, peate valima teise valiku.
![GREEN](assets/fr/13.webp)

Seejärel on teil valik 12-sõnalise või 24-sõnalise mnemoonilise fraasi vahel. See fraas võimaldab teil taastada juurdepääsu oma rahakotile mis tahes ühilduvas tarkvaras, kui teil on probleeme oma telefoniga. Praegu ei paku 24-sõnaline fraas rohkem turvalisust kui 12-sõnaline fraas. Seetõttu soovitan valida **12-sõnalise** mnemoonilise fraasi.

Green annab teile seejärel teie mnemoonilise fraasi. Enne jätkamist veenduge, et teid ei jälgitaks. Klõpsake nupul "*Näita taastefraasi*", et kuvada see ekraanil.

![GREEN](assets/fr/14.webp)

**See mnemooniline fraas annab täieliku ja piiramatu juurdepääsu kõigile teie bitcoinidele.** Igaüks, kes on selle fraasi valduses, võib teie vahendid varastada, isegi ilma füüsilise juurdepääsuta teie telefonile.

See võimaldab teil taastada juurdepääsu oma bitcoinidele kaotuse, varguse või telefoni kahjustumise korral. Seetõttu on väga oluline hoolikalt salvestada see **füüsilisel kandjal (mitte digitaalsel)** ja hoida seda turvalises kohas. Võite selle kirjutada paberitükile või suurema turvalisuse tagamiseks, kui see rahakott on oluline, soovitan graveerida selle roostevabast terasest kandjale, et kaitsta tulekahju, üleujutuste või kokkuvarisemise ohtude eest (kuuma rahakoti jaoks, mis on mõeldud väikese hulga bitcoinide turvamiseks, on tõenäoliselt piisav lihtne paberist varukoopia).
*Ilmselgelt ei tohiks te kunagi neid sõnu internetis jagada, vastupidiselt sellele, mida ma selles õpetuses teen. See näidisrahakott kasutatakse ainult Testnetis ja kustutatakse õpetuse lõpus.*
![GREEN](assets/fr/15.webp)

Pärast oma mnemoonilise fraasi õiget ülesmärkimist füüsilisele kandjale klõpsake nupul "*Jätka*". Green Wallet palub teil kinnitada teatud sõnu oma fraasist, et kontrollida, kas olete need õigesti üles märkinud. Täitke tühjad puuduvate sõnadega.

![GREEN](assets/fr/16.webp)

Valige oma seadme PIN-kood, mida kasutatakse teie Green rahakoti avamiseks. See on seega kaitse volitamata füüsilise juurdepääsu vastu. See PIN-kood ei mängi rolli teie rahakoti krüptograafiliste võtmete tuletamisel. Seega, isegi ilma sellele PIN-koodile juurdepääsuta, võimaldab teie 12 või 24-sõnaline mnemooniline fraas teil oma bitcoine uuesti kätte saada.
Soovitatav on valida võimalikult juhuslik 6-kohaline PIN-kood. Samuti veenduge, et varundate selle koodi, et te seda ei unustaks, vastasel juhul peate oma rahakoti taastama mnemoonilise fraasi abil. Hiljem võite lisada biomeetrilise lukustamise võimaluse, et vältida PIN-koodi iga kasutuskorra sisestamist. Üldiselt on biomeetria palju vähem turvaline kui PIN-kood ise. Seetõttu soovitan vaikimisi seda avamisvõimalust mitte seadistada.
![GREEN](assets/fr/17.webp)

Sisestage oma PIN-kood teist korda selle kinnitamiseks.

![GREEN](assets/fr/18.webp)

Oodake, kuni teie rahakott on loodud, seejärel klõpsake nupul "*Loo konto*".

![GREEN](assets/fr/19.webp)

Seejärel on teil valik standardse ühe allkirjaga rahakoti ja kahefaktorilise autentimisega (2FA) kaitstud rahakoti vahel, mida me selles õpetuses kasutame.

![GREEN](assets/fr/20.webp)

2FA valik Greenis loob 2/2 multisignatuuriga rahakoti, millest ühe võtme hoiab Blockstream. See tähendab, et tehingu tegemiseks on vajalikud mõlemad võtmed: kohalik võti, mida kaitseb teie PIN teie telefonis, ja kaugvõti, mida kaitseb 2FA Blockstreami serverites. Juurdepääsu kaotamise või Blockstreami teenuste kättesaamatuse korral tagavad ajalukkudega skriptidel põhinevad taastamismehhanismid fondide iseseisva taastamise võimaluse. Kuigi see seadistus vähendab oluliselt teie bitcoinide varastamise riski, on see keerulisem hallata ja osaliselt sõltub Blockstreamist. Selle õpetuse jaoks valime klassikalise ühe allkirjaga rahakoti, mille võtmed on salvestatud kohalikult telefonis.

Ja ongi kõik, teie Bitcoin rahakott on edukalt loodud kasutades Green rakendust!

![GREEN](assets/fr/21.webp)

Enne oma esimeste bitcoinide vastuvõtmist oma rahakotti, **soovitan tungivalt teha kuiva taastamise testi**. Märkige üles viiteteave, näiteks teie xpub või esimene vastuvõtu aadress, seejärel kustutage oma rahakott Green rakenduses, kui see on veel tühi. Seejärel proovige oma rahakotti Greenis taastada oma paberil varukoopiate abil. Kontrollige, kas taastamise järel genereeritud tunnistusinfo vastab algselt märgitule. Kui see nii on, võite olla kindel, et teie paberil varukoopiad on usaldusväärsed. Taastamistesti tegemise kohta lisateabe saamiseks soovitan konsulteerida selle teise õpetusega:

https://planb.network/tutorials/wallet/recovery-test

## Oma rahakoti seadistamine Blockstream Greenis
Kui soovite oma portfelli kohandada, klõpsake paremas ülanurgas kolmel väikesel punktil.
![GREEN](assets/fr/22.webp)
"*Nimeta ümber*" valik võimaldab teil kohandada oma portfelli nime, mis on eriti kasulik, kui haldate sama rakenduse peal mitut portfelli.
![GREEN](assets/fr/23.webp)

"*Ühik*" menüü annab teile võimaluse muuta oma portfelli baasühikut. Näiteks võite valida selle kuvamise satoshi'des bitcoini asemel.

![GREEN](assets/fr/24.webp)

"*Seaded*" menüü pakub juurdepääsu teie Bitcoin'i rahakoti erinevatele valikutele.

![GREEN](assets/fr/25.webp)

Siin, näiteks, leiate oma laiendatud avaliku võtme ja selle *kirjeldaja*, mis on kasulik, kui plaanite seadistada sellest rahakotist vaatlus-ainult rahakoti.

![GREEN](assets/fr/26.webp)

Samuti võite muuta oma rahakoti PIN-koodi ja lubada biomeetrilise sisselogimise.

![GREEN](assets/fr/27.webp)

## Blockstream Green'i kasutamine

Nüüd, kui teie Bitcoin'i rahakott on seadistatud, olete valmis vastu võtma oma esimesed satid! Selleks klõpsake lihtsalt "*Vasta*" nupule.

![GREEN](assets/fr/28.webp)

Green kuvab seejärel teie rahakoti esimese tühja vastuvõtu aadressi. Võite kas skannida seotud QR-koodi või kopeerida aadressi otse, et saata sinna bitcoine. Selline aadress ei määra saatja poolt saadetava summa suurust. Siiski võite genereerida aadressi, mis nõuab kindlat summat, klõpsates paremal üleval asuvatel kolmel väikesel punktil, seejärel "*Nõua summat*" ja sisestades soovitud summa.

Kuna kasutate Segwit v0 kontot (BIP84), algab teie aadress `bc1q...`. Minu näites kasutan Testnet'i rahakotti, seega eesliide on veidi erinev.

![GREEN](assets/fr/29.webp)

Kui tehing on võrgus edastatud, ilmub see teie rahakotti.

![GREEN](assets/fr/30.webp)

Oodake piisavalt kinnituste saamist, et pidada tehingut lõplikuks.

![GREEN](assets/fr/31.webp)

Bitcoine oma rahakotis omades, võite neid nüüd ka saata. Klõpsake "*Saada*".

![GREEN](assets/fr/32.webp)

Järgmisel lehel sisestage saaja aadress. Võite selle sisestada käsitsi või skannida QR-koodi.

![GREEN](assets/fr/33.webp)

Valige makse summa.

![GREEN](assets/fr/34.webp)
Ekraani allosas saate valida selle tehingu tasu määra. Teil on võimalus järgida rakenduse soovitusi või kohandada oma tasusid. Mida kõrgemad on tasud võrreldes teiste ootel olevate tehingutega, seda kiiremini teie tehing töödeldakse. Tasuturu mõistmiseks võite külastada [Mempool.space](https://mempool.space/) jaotises "*Transaction Fees*".
![GREEN](assets/fr/35.webp)

Klõpsake "*Järgmine*", et pääseda juurde oma tehingu kokkuvõtte ekraanile. Kontrollige, kas aadress, summa ja tasud on õiged.

![GREEN](assets/fr/36.webp)

Kui kõik on teie rahuloluks, libistage ekraani allosas olevat rohelist nuppu paremale, et allkirjastada ja edastada tehing Bitcoin'i võrgus.

![GREEN](assets/fr/37.webp)

Teie tehing ilmub nüüd teie Bitcoin'i rahakoti armatuurlauale, oodates kinnitust.

![GREEN](assets/fr/38.webp)
See õpetus põhineb [Bitstackile kuuluval originaalversioonil](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet), mille autoriks on Loïc Morel. Bitstack on Prantsuse Bitcoin neo-pank, mis pakub võimalust säästa bitcoine'ides, kasutades kas DCA-d (Dollar Cost Averaging) või automaatset igapäevaste kulutuste ümardamise süsteemi.