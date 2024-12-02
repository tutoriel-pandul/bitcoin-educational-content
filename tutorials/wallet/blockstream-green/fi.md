---
nimi: Blockstream Green - Mobiili
kuvaus: Mobiilin ohjelmistolompakon asettaminen
---
![kansi](assets/cover.webp)

Ohjelmistolompakko on sovellus, joka asennetaan tietokoneelle, älypuhelimeen tai mihin tahansa muuhun Internetiin yhdistettyyn laitteeseen, mahdollistaen Bitcoin-lompakon avainten hallinnan ja turvallisuuden. Toisin kuin laitteistolompakot, jotka eristävät yksityiset avaimet, "kuumat" lompakot toimivat ympäristössä, joka voi olla alttiina kyberhyökkäyksille, lisäten hakkeroinnin ja varkauden riskejä.

Ohjelmistolompakoita käytetään kohtuullisten bitcoin-määrien hallintaan, erityisesti päivittäisissä transaktioissa. Tämä voi olla myös mielenkiintoinen vaihtoehto ihmisille, joilla on rajoitettu Bitcoin-portfolio, ja joille laitteistolompakon hankkiminen saattaa tuntua suhteettomalta. Kuitenkin niiden jatkuva altistuminen Internetille tekee niistä vähemmän turvallisia pitkäaikaisten säästöjen tai merkittävien varojen säilyttämiseen. Näissä tapauksissa on suositeltavaa valita turvallisempia ratkaisuja, kuten laitteistolompakot.

Tässä oppaassa esittelen sinulle yhden parhaista mobiilin ohjelmistolompakon ratkaisuista: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Jos olet kiinnostunut oppimaan, kuinka käyttää Blockstream Greeniä tietokoneella, tutustu tähän toiseen oppaaseen:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Johdanto Blockstream Greeniin

Blockstream Green on ohjelmistolompakko, joka on saatavilla sekä mobiililaitteille että tietokoneille. Aiemmin nimellä *Green Address* tunnettu lompakko tuli Blockstream-projektiksi sen hankittua sen vuonna 2016.

Green on sovellus, joka on erityisen helppokäyttöinen, tehden siitä mielenkiintoisen aloittelijoille. Se tarjoaa kaikki hyvän Bitcoin-lompakon olennaiset ominaisuudet, mukaan lukien RBF (*Replace-by-Fee*), mahdollisuuden yhdistää Torin kautta, kyvyn yhdistää omaan nodeen, SPV (*Simple Payment Verification*) -vaihtoehdon, merkinnät ja kolikoiden hallinnan.

Blockstream Green tukee myös Liquid-verkkoa, Bitcoinin sivuketjua, jonka Blockstream on kehittänyt nopeiden ja luottamuksellisten transaktioiden suorittamiseen päälohkoketjun ulkopuolella. Tämä opas keskittyy yksinomaan Bitcoiniin, mutta tulevaisuudessa käsitellään myös Liquidin käyttöä.

## Blockstream Green -sovelluksen asentaminen ja asetusten määrittäminen

Ensimmäinen askel on luonnollisesti Green-sovelluksen lataaminen. Siirry sovelluskauppaasi:
- [Androidille](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Applelle](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Android-käyttäjillä on myös mahdollisuus asentaa sovellus `.apk`-tiedoston kautta [saatavilla Blockstreamin GitHubissa](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Käynnistä sovellus, sitten rastita ruutu "*Hyväksyn ehdot...*".
![GREEN](assets/fr/04.webp)

Kun avaat Greenin ensimmäistä kertaa, kotinäyttö ilmestyy ilman mitään määritettyjä lompakoita. Myöhemmin, jos luot tai tuot lompakoita, ne ilmestyvät tähän käyttöliittymään. Ennen kuin siirryt luomaan lompakkoa, neuvon sinua säätämään sovelluksen asetuksia odotustesi mukaisesti. Klikkaa "*Sovelluksen Asetukset*".

![GREEN](assets/fr/05.webp)

"*Parannettu Yksityisyys*" -vaihtoehto, joka on saatavilla vain Androidilla, parantaa yksityisyyttä poistamalla kuvakaappaukset käytöstä ja piilottamalla sovelluksen esikatselut. Se myös automaattisesti lukitsee pääsyn sovellukseen heti, kun puhelimesi lukittuu, tehden tietojesi paljastumisen vaikeammaksi.

![GREEN](assets/fr/06.webp)
Niille, jotka haluavat parantaa yksityisyyttään, sovellus tarjoaa mahdollisuuden reitittää liikenteesi Tor-verkon kautta, joka salaa kaikki yhteytesi ja tekee toimintasi jäljittämisen vaikeaksi. Vaikka tämä vaihtoehto saattaa hieman hidastaa sovelluksen suorituskykyä, sitä suositellaan erittäin lämpimästi yksityisyytesi suojaamiseen, erityisesti jos et käytä omaa täysnodea.
![GREEN](assets/fr/07.webp)

Käyttäjille, joilla on oma täysnode, Green Wallet tarjoaa mahdollisuuden yhdistää siihen Electrum-palvelimen kautta, varmistaen täyden kontrollin Bitcoin-verkon tiedon ja transaktioiden lähettämisen yli.

![GREEN](assets/fr/08.webp)

Toinen vaihtoehtoinen ominaisuus on "*SPV Varmennus*" -vaihtoehto, joka mahdollistaa tiettyjen lohkoketjun tietojen suoran varmentamisen, vähentäen tarvetta luottaa oletusarvoiseen Blockstream-nodeen, vaikka tämä menetelmä ei tarjoakaan kaikkia täysnoden takeita.

![GREEN](assets/fr/09.webp)

Kun olet säätänyt nämä asetukset tarpeidesi mukaan, klikkaa "*Tallenna*" -painiketta ja käynnistä sovellus uudelleen.

![GREEN](assets/fr/10.webp)

## Bitcoin-lompakon luominen Blockstream Greenissä

Olet nyt valmis luomaan Bitcoin-lompakon. Klikkaa "*Aloita*" -painiketta.

![GREEN](assets/fr/11.webp)

Voit valita luovasi ohjelmistolompakon paikallisesti tai hallitsevasi kylmälompakkoa laitteistolompakon kautta. Tässä oppaassa keskitymme kuumalompakon luomiseen, joten sinun tulee valita "*Tällä laitteella*" -vaihtoehto. Tulevaisuuden oppaassa näytän, miten käyttää toista vaihtoehtoa.

Toisaalta "*Vain katselu*" -vaihtoehto mahdollistaa laajennetun julkisen avaimen (`xpub`) tuonnin, jotta voit tarkastella lompakon transaktioita pystymättä käyttämään siihen liittyviä varoja, mikä on kätevää esimerkiksi laitteistolompakon lompakon seurantaan.

![GREEN](assets/fr/12.webp)
Voit sitten valita palauttaaksesi olemassa olevan Bitcoin-lompakon tai luodaksesi uuden. Tämän oppaan tarkoituksena me luomme uuden lompakon. Jos kuitenkin tarvitset uudelleengeneroida jo olemassa olevan Bitcoin-lompakon sen mnemonisen fraasin avulla, esimerkiksi laitteistolompakkosi kadotessa, sinun tulee valita toinen vaihtoehto.
![GREEN](assets/fr/13.webp)

Sinulla on sitten valinta 12-sanan tai 24-sanan mnemonisen fraasin välillä. Tämä fraasi mahdollistaa pääsyn palauttamisen lompakkoosi mistä tahansa yhteensopivasta ohjelmistosta, jos kohtaat ongelmia puhelimesi kanssa. Tällä hetkellä 24-sanan fraasin valitseminen ei tarjoa enempää turvallisuutta kuin 12-sanan fraasi. Siksi suosittelen valitsemaan **12-sanan** mnemonisen fraasin.

Green tarjoaa sinulle sitten mnemonisen fraasisi. Ennen jatkamista, varmista, ettei kukaan tarkkaile sinua. Klikkaa "*Näytä palautusfraasi*" näyttääksesi sen ruudulla.

![GREEN](assets/fr/14.webp)

**Tämä mnemoninen fraasi antaa täyden ja rajoittamattoman pääsyn kaikkiin bitcoineihisi.** Kuka tahansa, jolla on tämä fraasi, voi varastaa varasi, vaikka hänellä ei olisi fyysistä pääsyä puhelimeesi.

Se mahdollistaa pääsyn palauttamisen bitcoineihisi tapauksissa, kuten menetys, varkaus tai puhelimen vahingoittuminen. On siis erittäin tärkeää tallentaa se huolellisesti **fyysiselle välineelle (ei digitaalisesti)** ja säilyttää se turvallisessa paikassa. Voit kirjoittaa sen paperille, tai lisäturvallisuuden vuoksi, jos tämä lompakko on tärkeä, suosittelen kaivertamaan sen ruostumattomasta teräksestä valmistetulle välineelle suojautuaksesi tulipalojen, tulvien tai sortumien riskeiltä (pienen bitcoin-määrän turvaamiseen tarkoitetulle kuumalompakolle yksinkertainen paperivarmuuskopio on todennäköisesti riittävä).
*Ilmiselvästi, sinun ei koskaan pitäisi jakaa näitä sanoja internetissä, päinvastoin kuin mitä teen tässä opetusohjelmassa. Tätä esimerkkilompakkoa käytetään vain Testnetissä ja se poistetaan opetusohjelman lopussa.*
![GREEN](assets/fr/15.webp)

Kun olet oikein merkinnyt muistilauseesi fyysiseen välineeseen, klikkaa "*Jatka*". Green Wallet pyytää sinua sen jälkeen vahvistamaan tiettyjä sanoja lauseestasi varmistaakseen, että olet kirjannut ne oikein. Täytä puuttuvat sanat.

![GREEN](assets/fr/16.webp)

Valitse PIN-koodi laitteellesi, jota käytetään Green-lompakkosi avaamiseen. Tämä on siis suoja luvattomalta fyysiseltä pääsyltä. Tämä PIN-koodi ei vaikuta lompakkosi kryptografisten avainten johdannaisuuteen. Näin ollen, vaikka sinulla ei olisi pääsyä tähän PIN-koodiin, 12 tai 24 sanan muistilauseesi avulla voit palauttaa pääsyn bitcoineihisi.
On suositeltavaa valita mahdollisimman satunnainen 6-numeroinen PIN-koodi. Varmista myös, että varmuuskopioit tämän koodin, jotta et unohda sitä, muuten sinun on pakko palauttaa lompakkosi käyttäen muistilausetta. Myöhemmin voit lisätä biometrisen lukitusvaihtoehdon välttääksesi PIN-koodin syöttämisen joka käytöllä. Yleisesti ottaen biometriikka on paljon vähemmän turvallinen kuin itse PIN-koodi. Siksi oletuksena neuvon olemaan asettamatta tätä lukitusvaihtoehtoa.
![GREEN](assets/fr/17.webp)

Syötä PIN-koodisi toisen kerran vahvistaaksesi sen.

![GREEN](assets/fr/18.webp)

Odota, että lompakkosi luodaan, ja klikkaa sitten "*Luo tili*" -painiketta.

![GREEN](assets/fr/19.webp)

Sinulla on sitten valinta tavallisen yksiallekirjoituksen lompakon ja kaksivaiheisen tunnistautumisen (2FA) suojan lompakon välillä.

![GREEN](assets/fr/20.webp)

2FA-vaihtoehto Greenissä luo 2/2 multisignature-lompakon, jonka yhden avaimen pitää Blockstream. Tämä tarkoittaa, että transaktion tekemiseen tarvitaan molemmat avaimet: paikallinen avain, joka on suojattu PIN-koodillasi puhelimessasi, ja etäavain, joka on suojattu 2FA:lla Blockstreamin palvelimilla. Jos menetät pääsyn 2FA:han tai Blockstreamin palvelut eivät ole käytettävissä, aikalukkoskriptien perustuvat palautusmekanismit takaavat mahdollisuuden palauttaa varasi itsenäisesti. Vaikka tämä asetus merkittävästi vähentää bitcoinejesi varastamisen riskiä, se on monimutkaisempi hallita ja osittain riippuvainen Blockstreamista. Tässä opetusohjelmassa valitsemme klassisen yksiallekirjoituksen lompakon, jonka avaimet säilytetään paikallisesti puhelimessa.

Ja siinä se on, Bitcoin-lompakkosi on onnistuneesti luotu käyttäen Green-sovellusta!

![GREEN](assets/fr/21.webp)

Ennen ensimmäisten bitcoiniesi vastaanottamista lompakkoosi, **suosittelen vahvasti suorittamaan kuivan harjoituksen palautustestin**. Kirjaa ylös viitetieto, kuten xpubisi tai ensimmäinen vastaanotto-osoitteesi, sitten poista lompakkosi Green-sovelluksessa, kun se on vielä tyhjä. Yritä sen jälkeen palauttaa lompakkosi Greenissä käyttäen paperivarmuuskopioitasi. Tarkista, että palautuksen jälkeen luotu todistetieto vastaa alun perin merkitseämääsi. Jos näin on, voit olla varma, että paperivarmuuskopiosi ovat luotettavia. Lisätietoja palautustestin suorittamisesta suosittelen konsultoimaan tätä toista opetusohjelmaa:

https://planb.network/tutorials/wallet/recovery-test

## Lompakkosi asettaminen Blockstream Greenissä
Jos haluat mukauttaa salkkuasi, klikkaa kolmea pientä pistettä oikeassa yläkulmassa.
![GREEN](assets/fr/22.webp)
"*Nimeä uudelleen*" -vaihtoehto mahdollistaa portfolion nimen mukauttamisen, mikä on erityisen hyödyllistä, jos hallinnoit useita portfolioita samassa sovelluksessa.
![GREEN](assets/fr/23.webp)

"*Yksikkö*" -valikko antaa sinulle mahdollisuuden vaihtaa portfolion perusyksikköä. Voit esimerkiksi valita näyttämään sen satosheina bitcoinien sijaan.

![GREEN](assets/fr/24.webp)

"*Asetukset*" -valikko tarjoaa pääsyn eri vaihtoehtoihin Bitcoin-lompakossasi.

![GREEN](assets/fr/25.webp)

Täältä löydät esimerkiksi laajennetun julkisen avaimen ja sen *kuvaajan*, mikä on hyödyllistä, jos aiot perustaa vain seurantaan tarkoitetun lompakon tästä lompakosta.

![GREEN](assets/fr/26.webp)

Voit myös vaihtaa lompakkosi PIN-koodin ja ottaa käyttöön biometrisen kirjautumisen.

![GREEN](assets/fr/27.webp)

## Blockstream Greenin käyttö

Nyt kun Bitcoin-lompakkosi on asetettu, olet valmis vastaanottamaan ensimmäiset satsisi! Tee tämä yksinkertaisesti napsauttamalla "*Vastaanota*" -painiketta.

![GREEN](assets/fr/28.webp)

Green näyttää sitten lompakkosi ensimmäisen tyhjän vastaanotto-osoitteen. Voit joko skannata liitetyn QR-koodin tai kopioida osoitteen suoraan lähettääksesi bitcoineja siihen. Tämäntyyppinen osoite ei määritä maksajan lähettämää summaa. Voit kuitenkin luoda osoitteen, joka pyytää tiettyä summaa, napsauttamalla kolmea pientä pistettä oikeassa yläkulmassa, sitten "*Pyydä summaa*" ja syöttämällä halutun summan.

Koska käytät Segwit v0 -tiliä (BIP84), osoitteesi alkaa `bc1q...`. Esimerkissäni käytän Testnet-lompakkoa, joten etuliite on hieman erilainen.

![GREEN](assets/fr/29.webp)

Kun transaktio on lähetetty verkossa, se ilmestyy lompakkoosi.

![GREEN](assets/fr/30.webp)

Odota, että saat tarpeeksi vahvistuksia pitääksesi transaktion lopullisena.

![GREEN](assets/fr/31.webp)

Bitcoineilla lompakossasi voit nyt myös lähettää niitä. Napsauta "*Lähetä*".

![GREEN](assets/fr/32.webp)

Seuraavalla sivulla syötä vastaanottajan osoite. Voit syöttää sen manuaalisesti tai skannata QR-koodin.

![GREEN](assets/fr/33.webp)

Valitse maksun summa.

![GREEN](assets/fr/34.webp)
Näytön alareunassa voit valita tämän transaktion maksunopeuden. Voit noudattaa sovelluksen suosituksia tai mukauttaa maksujasi. Mitä korkeammat maksut verrattuna muihin odottaviin transaktioihin, sitä nopeammin transaktiosi käsitellään. Ymmärtääksesi maksujen markkinat, voit vierailla [Mempool.space](https://mempool.space/) -sivustolla kohdassa "*Transaction Fees*".
![GREEN](assets/fr/35.webp)

Napsauta "*Seuraava*" päästäksesi transaktiosi yhteenvetonäyttöön. Varmista, että osoite, summa ja maksut ovat oikein.

![GREEN](assets/fr/36.webp)

Jos kaikki on mielestäsi kunnossa, liu'uta vihreää painiketta näytön alareunassa oikealle allekirjoittaaksesi ja lähettääksesi transaktion Bitcoin-verkkoon.

![GREEN](assets/fr/37.webp)

Transaktiosi ilmestyy nyt Bitcoin-lompakkosi kojelaudalle odottamaan vahvistusta.

![GREEN](assets/fr/38.webp)
*Tämä opas perustuu [alkuperäiseen versioon, joka kuuluu Bitstackille](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) ja jonka on kirjoittanut Loïc Morel. Bitstack on ranskalainen Bitcoin-neopankki, joka tarjoaa mahdollisuuden säästää bitcoineissa joko DCA:n (Dollar Cost Averaging) kautta tai automaattisen päivittäisten menojen pyöristysjärjestelmän avulla.*