---
nimi: Blockstream Green - Vaatlusrežiimis
kirjeldus: Vaatlusrežiimis rahakoti seadistamine
---
![kaas](assets/cover.webp)

Selles õpetuses saate teada, kuidas mobiilis hõlpsalt seadistada vaatlusrežiimis rahakotti, kasutades Blockstream Green rakendust.

## Mis on Vaatlusrežiimis Rahakott?

Vaatlusrežiimis rahakott, ehk "watch-only wallet," on tarkvara tüüp, mis on loodud selleks, et võimaldada kasutajal jälgida tehinguid, mis on seotud ühe või mitme kindla Bitcoin avaliku võtmega, ilma et tal oleks juurdepääsu vastavatele privaatvõtmetele.

Selline rakendus säilitab ainult andmeid, mis on vajalikud Bitcoin rahakoti jälgimiseks, sealhulgas selle saldo ja tehingute ajaloo vaatamiseks, kuid tal puudub juurdepääs privaatvõtmetele. Seetõttu on võimatu kulutada vaatlusrežiimis rakenduses hoitavaid bitcoine.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Vaatlusrežiimis kasutamine on üldiselt lisaks riistvara rahakotile. Viimane võimaldab rahakoti privaatvõtmete turvalist säilitamist internetiühenduseta seadmes, millel on minimaalne rünnaku pind, isoleerides privaatvõtmed potentsiaalselt haavatavatest keskkondadest. Vaatlusrežiimis rakendus seevastu säilitab ainult Bitcoin rahakoti laiendatud avaliku võtme (`xpub`, `zpub` jne). See vanemvõti ei võimalda seotud privaatvõtmete avastamist ja seega ei luba bitcoine kulutada. Siiski võimaldab see tuletada alamavalikud võtmed ja vastuvõtu aadresse. Tundes riistvara rahakoti poolt kaitstud rahakoti aadresse, saab vaatlusrežiimis rakendus jälgida neid tehinguid Bitcoin võrgus, pakkudes kasutajale võimalust jälgida oma saldo ja genereerida uusi vastuvõtu aadresse, ilma et peaks iga kord oma riistvara rahakotti ühendama.

Selles õpetuses pakun avastada ühte populaarsemat vaatlusrežiimis rahakoti lahendust mobiilis: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Tutvustus Blockstream Green'ile

Blockstream Green on tarkvara, mis on saadaval nii mobiilil kui ka arvutil. Varem tuntud kui Green Address, sai sellest rahakott Blockstreami projekt pärast selle omandamist 2016. aastal.

Green on väga lihtsasti kasutatav rakendus, muutes selle eriti sobivaks algajatele. See pakub mitmesuguseid funktsioone, nagu kuumade rahakottide, riistvara rahakottide, samuti Liquid kõrvalahela rahakottide haldamine.

Selles õpetuses keskendume ainult vaatlusrežiimis rahakoti loomisele. Greeni teiste kasutusviiside uurimiseks kutsume teid tutvuma meie teiste pühendatud õpetustega:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Blockstream Green Rakenduse Allalaadimine ja Seadistamine
Esimene samm on loomulikult Green rakenduse allalaadimine. Minge oma rakenduste poodi:
- [Androidile](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Apple'ile](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Androidi kasutajatel on võimalus rakendus installida ka `.apk` faili kaudu [saadaval Blockstreami GitHubis](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Käivitage rakendus, seejärel märkige ruut "*Nõustun tingimustega...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Kui avate esimest korda Greeni, ilmub avakuva ilma seadistatud rahakotita. Hiljem, kui loote või impordite rahakotte, ilmuvad need sellesse liidesesse. Enne rahakoti loomise juurde liikumist soovitan teil rakenduse seadeid oma ootustele vastavalt kohandada. Klõpsake nupul "*Rakenduse Seaded*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

Valik "*Täiustatud Privaatsus*", mis on saadaval ainult Androidil, parandab privaatsust, keelates ekraanipildid ja peites rakenduse eelvaated. See lukustab ka automaatselt rakendusele juurdepääsu kohe, kui teie telefon lukustub, muutes teie andmed raskemini paljastatavaks.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Neile, kes soovivad oma privaatsust suurendada, pakub rakendus võimalust suunata teie liiklus läbi Tori, võrgu, mis krüpteerib kõik teie ühendused ja muudab teie tegevused raskesti jälgitavaks. Kuigi see valik võib rakenduse jõudlust veidi aeglustada, on see väga soovitatav teie privaatsuse kaitsmiseks, eriti kui te ei kasuta oma täisnoodi.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Kasutajatele, kellel on oma täisnood, pakub Green Wallet võimalust ühendada sellega Electrum serveri kaudu, tagades täieliku kontrolli Bitcoin võrgu informatsiooni ja tehingute edastamise üle.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Teine alternatiivne funktsioon on valik "*SPV Kontroll*", mis võimaldab teatud plokiahela andmete otsest kontrollimist, vähendades vajadust usaldada Blockstreami vaikenoodi, kuigi see meetod ei paku kõiki täisnoodi garantiisid.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Kui need seaded on teie vajadustele vastavalt kohandatud, klõpsake nupul "*Salvesta*" ja taaskäivitage rakendus.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Blockstream Greenis vaatlus-ainult rahakoti loomine
Nüüd olete valmis looma vaatlus-ainult rahakoti. Klõpsake nupul "*Alusta*".
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Teil on valik mitme eri tüüpi rahakottide vahel. Selle õpetuse jaoks soovime luua vaatlus-ainult rahakoti, seega klõpsake vastaval nupul.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Valige valik "*Üksik Allkiri*".

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Seejärel valige "*Bitcoin*". Minu poolt viiakse see õpetus läbi testneti rahakotiga, kuid protseduur jääb samaks põhivõrgus.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Teilt palutakse esitada kas laiendatud avalik võti (`xpub`, `zpub` jne) või väljundi skripti kirjeldus.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Peate selle teabe hankima rahakotist, mida soovite oma vaatlus-ainult rahakoti kaudu jälgida. Laiendatud avalik võti ei ole turvalisuse seisukohast tundlik, kuna see ei võimalda juurdepääsu privaatvõtmetele, kuid see on tundlik teie privaatsuse jaoks, kuna see paljastab kõik teie avalikud võtmed ja seega kõik teie Bitcoin tehingud.

Kujutage ette, et kasutate Sparrow Walletit oma rahakoti haldamiseks riistvaralises rahakotis, leiate selle teabe jaotisest "*Seaded*". Selle teabe leidmine sõltub teie kasutatavast rahakoti haldamise tarkvarast, kuid see asub tavaliselt seadetes.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Kopeerige oma laiendatud avalik võti ja sisestage see Greeni rakendusse, seejärel klõpsake nupul "*Ühenda*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Seejärel saate näha selle võtmega seotud saldo ning tehingute ajalugu.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Klõpsates nupul "*Receive*", saate genereerida vastuvõtu aadressi, et vastu võtta bitcoine oma riistvara rahakotis. Siiski soovitan selle võimaluse kasutamist vältida enne, kui olete riistvara rahakoti ekraanil kontrollinud, et see hoiab genereeritud aadressiga seotud privaatvõtit, enne selle kasutamist bitcoinide lukustamiseks. See on hea tava, mida järgida.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

Valik "*Sweep*" võimaldab teil käsitsi sisestada privaatvõtme, et kulutada vahendeid otse oma Green rakendusest. Väga spetsiifilistel juhtudel välja arvatud, soovitan seda funktsiooni mitte kasutada, kuna see nõuab teie privaatvõtme avalikustamist telefonis, mis on küberattackidele palju haavatavam kui teie riistvara rahakott.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
Ja ongi kõik, nüüd teate, kuidas hõlpsalt seadistada oma nutitelefonis vaatlus-ainult rahakotti! See on väga käepärane tööriist riistvara rahakoti jälgimiseks ilma iga kord seda ühendamata ja avamata.

Kui leidsite selle õpetuse kasuliku, oleksin tänulik, kui jätaksite allpool pöidla üles. Julgelt jagage seda artiklit oma sotsiaalvõrgustikes. Suur tänu!

Soovitan samuti tutvuda selle täieliku õpetusega Blockstream Green rakenduse kohta, et seadistada kuum rahakott:

https://planb.network/tutorials/wallet/blockstream-green