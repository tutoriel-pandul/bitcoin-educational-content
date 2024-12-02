---
name: Blockstream Green - 2FA
description: 2/2 multisig -asetuksen käyttöönotto Green Walletissa
---
![cover](assets/cover.webp)

Ohjelmistopohjainen lompakko on sovellus, joka on asennettu tietokoneelle, älypuhelimelle tai mille tahansa muulle Internetiin yhdistetylle laitteelle, mahdollistaen Bitcoin-lompakon avainten hallinnan ja turvallisuuden. Toisin kuin laitteistopohjaiset lompakot, jotka eristävät yksityiset avaimet, "kuumat" lompakot toimivat ympäristössä, joka voi altistua kyberhyökkäyksille, lisäten hakkeroinnin ja varkauden riskejä.

Ohjelmistopohjaisia lompakoita tulisi käyttää kohtuullisten bitcoin-määrien hallintaan, erityisesti päivittäisissä transaktioissa. Tämä voi olla myös mielenkiintoinen vaihtoehto ihmisille, joilla on rajallinen Bitcoin-portfolio, ja joille laitteistopohjaisen lompakon hankkiminen saattaa tuntua suhteettomalta. Kuitenkin niiden jatkuva altistuminen Internetille tekee niistä vähemmän turvallisia pitkäaikaissäästöjen tai merkittävien varojen säilyttämiseen. Näissä tapauksissa on suositeltavaa valita turvallisempia ratkaisuja, kuten laitteistopohjaiset lompakot.

Tässä oppaassa näytän, kuinka voit parantaa kuuman lompakon turvallisuutta käyttämällä "2FA" -vaihtoehtoa Blockstream Greenissä.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Johdanto Blockstream Greeniin

Blockstream Green on ohjelmistopohjainen lompakko, joka on saatavilla mobiililaitteille ja tietokoneille. Aiemmin *Green Address* -nimellä tunnettu lompakko tuli Blockstreamin projektiksi sen hankittua sen vuonna 2016.

Green on erityisen helppokäyttöinen sovellus, mikä tekee siitä mielenkiintoisen vaihtoehdon aloittelijoille. Se tarjoaa kaikki hyvän Bitcoin-lompakon olennaiset ominaisuudet, mukaan lukien RBF (*Replace-by-Fee*), mahdollisuuden yhdistää Tor-verkon kautta, mahdollisuuden yhdistää omaan solmuun, SPV (*Simple Payment Verification*) -vaihtoehdon, merkinnät ja kolikoiden hallinnan.

Blockstream Green tukee myös Liquid-verkkoa, Blockstreamin kehittämää Bitcoin-sivuketjua, joka mahdollistaa nopeat ja luottamukselliset transaktiot päälohkoketjun ulkopuolella. Tässä oppaassa keskitymme yksinomaan Bitcoiniin, mutta olen myös tehnyt toisen oppaan, jossa opetetaan käyttämään Liquidia Greenissä:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## 2/2 multisig (2FA) -vaihtoehto

Greenissä voit luoda perinteisen "singlesig" kuuman lompakon. Mutta sinulla on myös "2FA multisig" -vaihtoehto, joka mahdollistaa kuuman lompakon turvallisuuden parantamisen ilman, että sen päivittäinen hallinta monimutkaistuu liikaa.
Asetat siis käyttöön 2/2 multisig-lompakon, mikä tarkoittaa, että jokainen transaktio vaatii kahden avaimen allekirjoituksen. Ensimmäinen avain, joka on johdettu 12 tai 24 sanan muistilauseestasi, on suojattu paikallisesti PIN-koodilla puhelimessasi. Sinulla on täysi hallinta tästä avaimesta. Toinen avain on Blockstreamin palvelimilla, ja sen käyttö allekirjoitukseen vaatii todennuksen, joka voidaan saavuttaa koodilla, jonka saat sähköpostitse, SMS-viestillä, puhelimitse tai, kuten tässä oppaassa näemme, todennussovelluksen kautta (Authy, Google Authenticator jne.).

Varmistaaksesi itsenäisyytesi Blockstreamin mahdollisen epäonnistumisen sattuessa (esimerkiksi, jos yritys menee konkurssiin tai palvelimet, jotka pitävät toista avainta, tuhoutuvat), multisigiisi sovelletaan aikalukkomekanismia. Tämä mekanismi muuttaa 2/2 multisigin 1/2 multisigiksi noin vuoden kuluttua (tai tarkalleen 51,840 lohkon jälkeen, mutta tätä arvoa voidaan muuttaa), jonka jälkeen lompakkosi tarvitsee vain paikallisen avaimen bitcoinejesi käyttämiseen. Näin ollen, jos menetät pääsyn Blockstreamin palvelimiin tai 2FA-todennukseen, sinun tarvitsee vain odottaa enintään vuosi voidaksesi käyttää bitcoinejasi vapaasti sovelluksellasi, riippumatta Blockstreamista.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
Tämä menetelmä lisää merkittävästi kuumien lompakoidesi turvallisuutta, samalla kun se antaa sinun hallita bitcoinejasi ja helpottaa niiden päivittäistä käyttöä. Se kuitenkin vaatii säännöllistä aikalukon päivittämistä, jotta 2FA:n turvallisuus säilyy. 360 päivän laskenta, jonka aikana varasi ovat suojattu 2FA:lla, alkaa heti, kun vastaanotat bitcoineja. Jos et ole tehnyt transaktiota näiden varojen käyttämiseksi 360 päivän kuluessa niiden vastaanottamisesta, bitcoinejasi suojaa enää vain paikallinen avaimesi ilman 2FA:ta.

Tämä rajoitus tekee 2FA-vaihtoehdosta paremmin sopivan kulutuslompakolle, jossa säännölliset transaktiot automaattisesti uusivat aikalukkoja. Pitkäaikaiselle säästölompakolle tämä voi olla ongelmallista, sillä sinun täytyy muistaa suorittaa haravointitransaktio itsellesi joka vuosi ennen kuin aikakatkaisu vanhenee.

Toinen tämän turvallisuusmenetelmän haittapuoli on, että sinun täytyy käyttää vähemmistön skriptimalleja. Tämä tarkoittaa, että yksityisyyden kannalta asiat monimutkaistuvat: hyvin harvat ihmiset käyttävät samaa skriptityyppiä kuin sinä, mikä mahdollistaa ulkopuolisen tarkkailijan lompakkosi jäljen helpomman tunnistamisen. Lisäksi nämä skriptit johtavat korkeampiin transaktiomaksuihin niiden suuremman koon vuoksi.
Jos et halua käyttää 2FA-vaihtoehtoa ja haluat vain perustaa "singlesig"-lompakon Greenissä, suosittelen tutustumaan tähän toiseen opastukseen:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Blockstream Green -ohjelmiston asentaminen ja asetusten määrittäminen

Ensimmäinen askel on luonnollisesti Green-sovelluksen lataaminen. Mene sovelluskauppaasi:
- [Androidille](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Applelle](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

Android-käyttäjillä on myös mahdollisuus asentaa sovellus `.apk`-tiedoston kautta [saatavilla Blockstreamin GitHubissa](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Käynnistä sovellus ja valitse ruutu "*Hyväksyn ehdot...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Kun avaat Greenin ensimmäistä kertaa, kotinäyttö ilmestyy ilman määritettyjä lompakoita. Myöhemmin, jos luot tai tuot lompakoita, ne ilmestyvät tähän käyttöliittymään. Ennen kuin siirryt lompakon luomiseen, neuvon sinua säätämään sovelluksen asetuksia odotustesi mukaisesti. Klikkaa "*Sovellusasetukset*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

"*Parannettu yksityisyys*" -vaihtoehto, joka on saatavilla vain Androidilla, parantaa yksityisyyttä poistamalla käytöstä kuvakaappaukset ja piilottamalla sovelluksen esikatselut. Se myös automaattisesti lukitsee pääsyn sovellukseen heti, kun puhelimesi lukittuu, tehden tietojesi paljastumisen vaikeammaksi.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

Niille, jotka haluavat parantaa yksityisyyttään, sovellus tarjoaa mahdollisuuden reitittää liikenteesi Tor-verkon kautta, joka salaa kaikki yhteytesi ja tekee toimintasi jäljittämisen vaikeaksi. Vaikka tämä vaihtoehto saattaa hieman hidastaa sovelluksen suorituskykyä, se on erittäin suositeltavaa yksityisyytesi suojaamiseksi, erityisesti jos et käytä omaa täysnodea.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

Käyttäjille, joilla on oma täysnode, Green Wallet tarjoaa mahdollisuuden yhdistää siihen Electrum-palvelimen kautta, varmistaen täyden hallinnan Bitcoin-verkon tiedoista ja transaktioiden lähettämisestä.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
Toinen vaihtoehtoinen ominaisuus on "*SPV Vahvistus*" -vaihtoehto, joka mahdollistaa tiettyjen lohkoketjutietojen suoran vahvistamisen, vähentäen tarvetta luottaa Blockstreamin oletusnoodiin, vaikkakaan tämä menetelmä ei tarjoa kaikkia täysnoodin takeita.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Kun nämä asetukset on säädetty tarpeidesi mukaan, klikkaa "*Tallenna*" -painiketta ja käynnistä sovellus uudelleen.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Bitcoin-lompakon luominen Blockstream Greenissä

Olet nyt valmis luomaan Bitcoin-lompakon. Klikkaa "*Aloita*" -painiketta.

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Sinulla on valinta luoda ohjelmistolompakko paikallisesti tai hallita kylmälompakkoa laitteistolompakon kautta. Tässä oppaassa keskitymme kuumalompakon luomiseen, joten sinun tulee valita "*Tällä Laitteella*" -vaihtoehto.

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Seuraavaksi voit valita palauttaa olemassa olevan Bitcoin-lompakon tai luoda uuden. Tämän oppaan tarkoituksessa luomme uuden lompakon. Jos kuitenkin tarvitset uudelleengeneroida olemassa olevan Bitcoin-lompakon sen mnemonisen lauseen avulla, esimerkiksi vanhan puhelimesi katoamisen vuoksi, sinun tulee valita toinen vaihtoehto.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Sinulla on sitten valinta 12-sanan tai 24-sanan mnemonisen lauseen välillä. Tämä lause mahdollistaa pääsyn palauttamisen lompakkoosi mistä tahansa yhteensopivasta ohjelmistosta, jos puhelimesi kanssa ilmenee ongelmia. Tällä hetkellä 24-sanan lauseen valitseminen ei tarjoa enemmän turvallisuutta kuin 12-sanan lause. Siksi suosittelen valitsemaan **12-sanan** mnemonisen lauseen.

Green tarjoaa sinulle mnemonisen lauseesi. Ennen jatkamista, varmista, että kukaan ei tarkkaile sinua. Klikkaa "*Näytä palautuslause*" näyttääksesi sen näytöllä.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**Tämä mnemoninen lause antaa täydellisen ja rajoittamattoman pääsyn kaikkiin bitcoineihisi**. Kuka tahansa, jolla on tämä lause, voi varastaa varasi, jopa ilman fyysistä pääsyä puhelimeesi (vanhentuneen aikalukon tai 2FA:n tapauksessa, jos kyseessä on 2/2 lompakko Greenissä).

Se mahdollistaa pääsyn palauttamisen paikallisiin avaimiisi tapauksessa, jos puhelimesi katoaa, varastetaan tai vahingoittuu. Siksi on erittäin tärkeää tallentaa se huolellisesti **fyysiselle välineelle (ei digitaaliselle)** ja säilyttää se turvallisessa paikassa. Voit kirjoittaa sen paperille, tai lisäturvallisuuden vuoksi, jos tämä lompakko on tärkeä, suosittelen kaivertamaan sen ruostumattomasta teräksestä valmistetulle välineelle suojautuaksesi tulipalojen, tulvien tai sortumien riskeiltä (kuumalompakolle, joka on tarkoitettu pienen määrän bitcoinien turvaamiseen, yksinkertainen paperivarmuuskopio on todennäköisesti riittävä).
*Ilmeisesti, sinun ei pitäisi koskaan jakaa näitä sanoja internetissä, toisin kuin teen tässä oppaassa. Tämä esimerkkilompakko käytetään vain Testnetissä ja se poistetaan oppaan lopussa.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Kun olet oikein merkinnyt mnemonisen lauseesi fyysiselle välineelle, klikkaa "*Jatka*". Green Wallet pyytää sinua vahvistamaan joitakin sanoja lauseestasi varmistaakseen, että olet kirjannut ne oikein. Täytä puuttuvat sanat tyhjiin kohtiin.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Valitse PIN-koodi laitteellesi, jota käytetään Green-lompakkosi avaamiseen. Se on siis suoja luvattomalta fyysiseltä pääsyltä. Tämä PIN-koodi ei vaikuta lompakkosi kryptografisten avainten johdannaisuuteen. Näin ollen, vaikka sinulla ei olisi pääsyä tähän PIN-koodiin, 12 tai 24 sanan muistilauseen hallussapito mahdollistaa pääsyn paikallisiin avaimiisi uudelleen.

On suositeltavaa valita mahdollisimman satunnainen 6-numeroinen PIN-koodi. Varmista myös, että tallennat tämän koodin, jotta et unohda sitä, muuten sinun on pakko palauttaa lompakkosi muistilauseen avulla. Voit myöhemmin lisätä vaihtoehdon biometriseen lukitukseen välttääksesi PIN-koodin syöttämisen joka kerta. Yleisesti ottaen biometria on paljon vähemmän turvallinen kuin itse PIN-koodi. Siksi oletuksena neuvon olemaan asettamatta tätä lukitusvaihtoehtoa.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Syötä PIN-koodisi toisen kerran vahvistaaksesi sen.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Odota, kun lompakkoasi luodaan, ja klikkaa sitten "*Luo tili*" -painiketta.

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Sinulla on sitten valinta tavallisen yksiallekirjoituslompakon ja kaksivaiheisen tunnistautumisen (2FA) suojan lompakon välillä. Tässä oppaassa valitsemme jälkimmäisen vaihtoehdon.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

Ja siinä se on, Bitcoin multisig-lompakkosi on onnistuneesti luotu käyttäen Green-sovellusta!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## 2FA:n asettaminen

Klikkaa tiliäsi.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Klikkaa vihreää painiketta "*Lisää tilisi turvallisuutta lisäämällä 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Sinulla on sitten mahdollisuus valita todennusmenetelmä pääsyyn toiseen avaimistasi 2/2 multisigissa. Tässä oppaassa käytämme todennussovellusta. Jos et ole tuttu tämän tyyppisen sovelluksen kanssa, suosittelen konsultoimaan opastamme Authy-sovelluksesta:
https://planb.network/tutorials/others/authy

Valitse "*Authenticator Application*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green näyttää sitten QR-koodin ja palautusavaimen. Tämä avain mahdollistaa pääsyn 2FA:han palauttamisen, jos menetät Authy-sovelluksesi. On suositeltavaa tehdä turvallinen varmuuskopio tästä avaimesta, vaikka voit aina palauttaa pääsyn bitcoineihisi timelockin päättymisen jälkeen, kuten aiemmin selitettiin.

Lisää uusi koodi todennussovellukseesi, sitten skannaa Greenin tarjoama QR-koodi.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Ilmeisesti, sinun ei pitäisi koskaan jakaa tätä avainta ja QR-koodia internetissä, päinvastoin kuin teen tässä oppaassa. Tämä esimerkkilompakko käytetään vain Testnetissä ja se poistetaan oppaan lopussa.*

Klikkaa "*Jatka*" -painiketta.

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Syötä todennussovelluksessasi oleva dynaaminen 6-numeroinen koodi.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

Kaksivaiheinen tunnistautuminen on nyt käytössä.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Selatessasi tätä valikkoa, voit myös säätää aikalukon kestoa. Tämä laskuri alkaa, kun olet vastaanottanut bitcoineja, ja kun aikalukko vanhenee, varojasi voidaan käyttää vain paikallisella avaimellasi ilman, että tarvitaan 2FA:ta. Oletuskestoaika on asetettu 12 kuukauteen, mutta säästölompakolle 15 kuukauden valitseminen voi olla järkevää aikalukon uusimistiheyden minimoimiseksi. Päinvastoin, kulutuslompakolle kuuden kuukauden aikalukko voi olla suositeltava, koska se uusitaan usein päivittäisten transaktioidesi yhteydessä, ja lyhyempi aikalukko vähentää odotusaikaa ongelmatilanteissa 2FA:n kanssa. Sinun tehtäväsi on määrittää itsellesi parhaiten sopiva aikalukon kesto.
![GREEN 2FA MULTISIG](assets/fr/30.webp)

Voit nyt poistua tästä valikosta. Moniallekirjoituslompakkosi on valmis!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Lompakkosi asettaminen Blockstream Greenissä

Jos haluat mukauttaa lompakkoasi, klikkaa kolmea pientä pistettä oikeassa yläkulmassa.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
"*Rename*" -vaihtoehto antaa sinun mukauttaa lompakkosi nimeä, mikä on erityisen hyödyllistä, jos hallinnoit useita lompakoita samassa sovelluksessa.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

"*Unit*" -valikko antaa sinulle mahdollisuuden vaihtaa lompakkosi perusyksikköä. Voit esimerkiksi valita sen näyttämisen satosheina bitcoinejen sijaan.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

"*Settings*" -valikko tarjoaa pääsyn lompakkosi eri asetuksiin.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Täältä löydät esimerkiksi laajennetun julkisen avaimesi ja sen *descriptorin*, mikä on hyödyllistä, jos aiot perustaa vain seurattavan lompakon tästä lompakosta.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

Voit myös vaihtaa lompakkosi PIN-koodin ja ottaa käyttöön biometrisen kirjautumisen.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Blockstream Greenin käyttö

Nyt kun Bitcoin-lompakkosi on asetettu, olet valmis vastaanottamaan ensimmäiset satsisi! Tee tämä yksinkertaisesti klikkaamalla "*Receive*" -painiketta.

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green näyttää sitten lompakkosi ensimmäisen tyhjän vastaanotto-osoitteen. Voit joko skannata liitetyn QR-koodin tai kopioida osoitteen suoraan lähettääksesi bitcoineja siihen. Tämäntyyppinen osoite ei määritä lähetettävän summan määrää. Voit kuitenkin luoda osoitteen, joka pyytää tiettyä summaa, klikkaamalla kolmea pientä pistettä oikeassa yläkulmassa, sitten "*Request Amount*" ja syöttämällä halutun summan.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Kun transaktio on lähetetty verkossa, se ilmestyy lompakkoosi.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Odota, että saat tarpeeksi vahvistuksia pitääksesi transaktion lopullisena.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

Bitcoineilla lompakossasi voit nyt myös lähettää niitä. Klikkaa "*Send*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

Seuraavalla sivulla syötä vastaanottajan osoite. Voit syöttää sen manuaalisesti tai skannata QR-koodin.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Valitse maksun määrä.
![GREEN 2FA MULTISIG](assets/fr/44.webp) Näytön alareunasta voit valita maksutason tälle siirrolle. Voit joko noudattaa sovelluksen suosituksia tai mukauttaa maksujasi. Mitä korkeammat maksut verrattuna muihin odottaviin siirtoihin, sitä nopeammin siirtosi käsitellään. Jos haluat ymmärtää maksutason markkinat, voit vierailla [Mempool.space](https://mempool.space/) -sivustolla kohdassa "*Transaction Fees*".
![GREEN 2FA MULTISIG](assets/fr/45.webp)

Napsauta "*Next*" päästäksesi siirtosi yhteenvetonäyttöön. Varmista, että osoite, summa ja maksut ovat oikein.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Jos kaikki näyttää hyvältä, liu'uta vihreää painiketta näytön alareunassa oikealle allekirjoittaaksesi ja lähettääksesi siirron Bitcoin-verkkoon.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

Tässä vaiheessa sinun on syötettävä todennuskoodisi avataksesi toisen avaimen multisigistä, jota Blockstream hallitsee. Syötä autentikointisovelluksessasi näkyvä 6-numeroinen koodi.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Siirtosi näkyy nyt Bitcoin-lompakkosi kojelaudalla odottamassa vahvistusta.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

Ja siinä se on, nyt tiedät miten helposti voit perustaa 2/2 multisig-lompakon käyttäen Blockstream Greenin 2FA-vaihtoehtoa!

Jos pidit tätä opasta hyödyllisenä, arvostaisin, jos jättäisit vihreän peukun alla. Voit vapaasti jakaa tämän artikkelin sosiaalisissa verkostoissasi. Suurkiitokset!

Suosittelen myös tutustumaan tähän toiseen kattavaan oppaaseen Blockstream Green mobiilisovelluksen käyttöön Liquid-lompakon perustamiseksi:

https://planb.network/tutorials/wallet/blockstream-green-liquid