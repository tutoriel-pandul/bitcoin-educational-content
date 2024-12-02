---
name: Blockstream Green - Töölaud
description: Green Wallet tarkvara kasutamine arvutis
---
![kaas](assets/cover.webp)

Selles õpetuses uurime, kuidas kasutada Blockstream Green tarkvara arvutis, et hallata turvalist rahakotti riistvaralises rahakotis. Riistvaralise rahakoti kasutamisel on hädavajalik kasutada arvutis tarkvara selle rahakoti haldamiseks. See haldustarkvara ei oma juurdepääsu privaatvõtmetele; seda kasutatakse ainult rahakoti saldo kontrollimiseks, vastuvõtu aadresside genereerimiseks ja tehingute koostamiseks ning edastamiseks, mille allkirjastab riistvaraline rahakott. Green esindab üht paljudest lahendustest oma Bitcoin riistvaralise rahakoti haldamiseks.

Aastal 2024 on Blockstream Green ühilduv ainult Ledger Nano S (vanem versioon), Ledger Nano X, Trezor One, Trezor T ja Blockstream Jade seadmetega.

## Sissejuhatus Blockstream Green'i

Blockstream Green on tarkvara, mis on saadaval nii mobiilil kui ka töölaual. Varem tuntud kui Green Address, sai sellest rahakott Blockstreami projekt pärast selle omandamist 2016. aastal.

Green on väga kasutajasõbralik rakendus, muutes selle eriti sobivaks algajatele. See pakub mitmesuguseid funktsioone, nagu kuumade rahakottide, riistvaraliste rahakottide, samuti Liquid kõrvalahela rahakottide haldamine. Saate seda kasutada ka vaatlusainult rahakoti seadistamiseks.

![GREEN-DESKTOP](assets/fr/01.webp)

Selles õpetuses keskendume ainult tarkvara kasutamisele arvutis. Greeni muude kasutusviiside uurimiseks kutsun teid tutvuma meie teiste pühendatud õpetustega:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Blockstream Green tarkvara installimine ja seadistamine

Alustage Blockstream Green tarkvara installimisega oma arvutisse. Minge [ametlikule veebilehele](https://blockstream.com/green/) ja klõpsake nupul "*Laadi kohe alla*". Seejärel järgige installiprotsessi vastavalt oma operatsioonisüsteemile.

![GREEN-DESKTOP](assets/fr/02.webp)

Käivitage rakendus, seejärel märkige ruut "*Nõustun tingimustega...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Kui avate Greeni esimest korda, ilmub avakuva ilma ühegi seadistatud rahakotita. Hiljem, kui loote või impordite rahakotte, ilmuvad need sellesse liidesesse. Enne rahakoti loomisele üleminekut soovitan teil rakenduse seadeid oma ootustele vastavalt kohandada. Klõpsake seadete ikoonil vasakul all.

![GREEN-DESKTOP](assets/fr/04.webp)

"*Üldine*" menüüs saate muuta tarkvara keelt ja lubada eksperimentaalseid funktsioone, kui soovite.

![GREEN-DESKTOP](assets/fr/05.webp)
"*Võrk*" menüüs saate lubada ühenduse Tori kaudu, võrk, mis krüpteerib kõik teie ühendused ja muudab teie tegevused raskesti jälgitavaks. Kuigi see võimalus võib rakenduse jõudlust veidi aeglustada, on see eriti soovitatav teie privaatsuse kaitsmiseks, eriti kui te ei kasuta oma täisnoodi.
![GREEN-DESKTOP](assets/fr/06.webp)

Kasutajatele, kellel on oma täisnood, pakub Green võimalust sellega ühenduda Electrum serveri kaudu, tagades täieliku kontrolli Bitcoin võrgu informatsiooni ja tehingute edastamise üle. Selleks klõpsake menüül "*Kohandatud serverid ja valideerimine*", seejärel sisestage oma Electrum serveri teave.

![GREEN-DESKTOP](assets/fr/07.webp)
Teine alternatiivne funktsioon on "*SPV kontrollimine*" valik, mis võimaldab otsest kontrollimist teatud plokiahela andmete üle, vähendades seeläbi vajadust usaldada Blockstreami vaikimisi sõlme, kuigi see meetod ei paku kõiki täissõlme garantiisid. See valik asub ka "*Kohandatud serverid ja valideerimine*" menüüs.
![GREEN-DESKTOP](assets/fr/08.webp)

Kui need seaded on teie vajadustele vastavalt kohandatud, võite sellest liidesest väljuda.

## Bitcoini rahakoti importimine Blockstream Greeni

Nüüd olete valmis importima oma Bitcoini rahakoti. Klõpsake nupul "**Alusta**".

![GREEN-DESKTOP](assets/fr/09.webp)

Teil on valik luua kohalik tarkvararahakott või hallata külma rahakotti riistvara rahakoti kaudu. Selle õpetuse jaoks keskendume riistvara rahakoti haldamisele, seega peate valima "*Riistvara rahakotil*" valiku.

Teisest küljest võimaldab "*Ainult-vaatamise*" valik importida laiendatud avaliku võtme (`xpub`), et vaadata rahakoti tehinguid ilma seotud vahendite kulutamise võimaluseta.

![GREEN-DESKTOP](assets/fr/10.webp)

Kui kasutate Jade'i, klõpsake vastaval nupul. Vastasel juhul valige "*Ühenda erinev riistvara seade*". Minu puhul kasutan Ledger Nano S-i. Ledgeri kasutajatele, veenduge, et olete installinud "*Bitcoin Legacy*" rakenduse oma riistvara rahakotile, kuna Green toetab ainult seda versiooni.

![GREEN-DESKTOP](assets/fr/11.webp)

Ühendage oma riistvara rahakott arvutiga ja valige see Greenis.

![GREEN-DESKTOP](assets/fr/12.webp)

Oodake, kuni Green impordib teie rahakoti andmed, pärast mida pääsete sellele juurde.

![GREEN-DESKTOP](assets/fr/13.webp)

Sel hetkel on võimalikud kaks stsenaariumi. Kui olete oma riistvara rahakotti juba varem kasutanud, peaksite nägema oma kontot tarkvaras. Kuid kui, nagu mina, olete just oma riistvara rahakoti initsialiseerinud, genereerides mnemoonilise fraasi ilma seda veel kasutamata, peate looma konto. Klõpsake "*Loo konto*".
![GREEN-DESKTOP](assets/fr/14.webp)
Valige "*Standard*", kui soovite kasutada klassikalist rahakotti.

![GREEN-DESKTOP](assets/fr/15.webp)

Nüüd on teil juurdepääs oma kontole.

![GREEN-DESKTOP](assets/fr/16.webp)

## Riistvara rahakoti kasutamine Blockstream Greeniga

Nüüd, kui teie Bitcoini rahakott on seadistatud, olete valmis vastu võtma oma esimesed satoshid! Selleks klõpsake lihtsalt nupul "*Võta vastu*".

![GREEN-DESKTOP](assets/fr/17.webp)

Klõpsake nupul "*Kopeeri aadress*", et aadress kopeerida, või skaneerige selle QR-kood.

![GREEN-DESKTOP](assets/fr/18.webp)

Kui tehing on võrgus edastatud, ilmub see teie rahakotti. Oodake piisavalt kinnitusi, et pidada tehingut muutumatuks.

![GREEN-DESKTOP](assets/fr/19.webp)

Bitcoine oma rahakotis olles olete nüüd võimeline neid saatma. Klõpsake nupul "*Saada*".

![GREEN-DESKTOP](assets/fr/20.webp)

Järgmisel lehel sisestage saaja aadress. Võite selle sisestada käsitsi või skaneerida QR-koodi oma veebikaameraga.

![GREEN-DESKTOP](assets/fr/21.webp)

Valige makse summa.

![GREEN-DESKTOP](assets/fr/22.webp)
Ekraani allosas saate valida selle tehingu tasumäära. Teil on võimalus järgida rakenduse soovitusi või kohandada oma tasusid. Mida kõrgemad on tasud võrreldes teiste ootel olevate tehingutega, seda kiiremini teie tehing töödeldakse. Tasuturu kohta teabe saamiseks võite külastada [Mempool.space](https://mempool.space/) lehel jaotist "*Transaction Fees*".
![GREEN-DESKTOP](assets/fr/23.webp)

Kui soovite spetsiifiliselt valida, milliseid UTXO-sid oma tehingus kasutada, klõpsake nupul "*Manual coin selection*".

![GREEN-DESKTOP](assets/fr/24.webp)

Kontrollige oma tehingu seadeid ja kui kõik on ootuspärane, klõpsake nupul "*Next*".

![GREEN-DESKTOP](assets/fr/25.webp)

Kontrollige veel kord, et aadress, summa ja tasud on õiged, seejärel klõpsake nupul "*Confirm transaction*".

![GREEN-DESKTOP](assets/fr/26.webp)

Veenduge, et kõik tehingu parameetrid on teie riistvara rahakoti ekraanil õiged, seejärel allkirjastage tehing selle abil.

![GREEN-DESKTOP](assets/fr/27.webp)

Kui tehing on riistvara rahakotist allkirjastatud, edastab Green selle automaatselt Bitcoin'i võrku. Teie tehing ilmub seejärel teie Bitcoin'i rahakoti armatuurlauale, oodates kinnitust.

![GREEN-DESKTOP](assets/fr/28.webp)

Ja ongi kõik, nüüd teate, kuidas hõlpsalt seadistada Blockstream Green tarkvara, et hallata oma Bitcoin'i rahakotti riistvara rahakotis.
Kui leidsite selle õpetuse kasuliku, oleksin tänulik, kui jätaksite allapoole pöidla üles. Julgelt jagage seda artiklit oma sotsiaalvõrgustikes. Suur tänu!
Soovitan samuti tutvuda selle põhjaliku õpetusega Blockstream Green mobiilirakenduse kohta, et seadistada kuum rahakott:

https://planb.network/tutorials/wallet/blockstream-green