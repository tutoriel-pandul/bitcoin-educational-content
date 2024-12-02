---
name: Blockstream Green - Liquid
description: Liquid-verkkosivuketjun lompakon asettaminen
---
![cover](assets/cover.webp)
Bitcoin-protokollalla on tarkoituksellisia teknisiä rajoituksia, jotka auttavat ylläpitämään verkon hajautusta ja varmistamaan turvallisuuden jakautumisen kaikkien käyttäjien kesken. Kuitenkin nämä rajoitukset voivat joskus aiheuttaa käyttäjille turhautumista, erityisesti ruuhkautumisen aikana, joka johtuu suuresta määrästä samanaikaisia siirtoja. Keskustelu Bitcoinin skaalautuvuudesta on pitkään jakauttanut yhteisön, erityisesti Blocksize War -kiistan aikana. Tämän episodin jälkeen Bitcoin-yhteisössä tunnustetaan laajalti, että skaalautuvuus on varmistettava off-chain-ratkaisuilla, toisen kerroksen järjestelmissä. Näihin ratkaisuihin kuuluvat sivuketjut, jotka ovat edelleen suhteellisen tuntemattomia ja vähän käytettyjä verrattuna muihin järjestelmiin, kuten Lightning Networkiin.

Sivuketju on itsenäinen lohkoketju, joka toimii rinnakkain pääasiallisen Bitcoin-lohkoketjun kanssa. Se käyttää bitcoinia laskentayksikkönä mekanismin kautta, jota kutsutaan "*kahden suunnan kiinnitykseksi*". Tämä järjestelmä mahdollistaa bitcoinien lukitsemisen pääketjussa toistaakseen niiden arvon sivuketjussa, jossa ne kiertävät tokeneina, jotka ovat tuettu alkuperäisillä bitcoineilla. Nämä tokenit yleensä säilyttävät arvopariteetin pääketjussa lukittujen bitcoinien kanssa, ja prosessi voidaan kääntää varojen palauttamiseksi Bitcoinissa.

Sivuketjujen tavoitteena on tarjota lisätoimintoja tai teknisiä parannuksia, kuten nopeampia siirtoja, pienempiä maksuja tai älykkäiden sopimusten tuki. Näitä innovaatioita ei aina voida toteuttaa suoraan Bitcoin-lohkoketjussa vaarantamatta sen hajautusta tai turvallisuutta. Sivuketjut mahdollistavat uusien ratkaisujen testaamisen ja tutkimisen säilyttäen samalla Bitcoinin eheyden. Kuitenkin nämä protokollat vaativat usein kompromisseja, erityisesti hajautuksen ja turvallisuuden suhteen, riippuen valitusta hallintomallista ja konsensusmekanismista.

Tänään tunnetuin sivuketju on todennäköisesti Liquid. Tässä oppaassa esittelen ensin, mikä Liquid on, ja sitten opastan sinua, kuinka aloittaa sen käyttö helposti Blockstream Green -sovelluksen kautta, hyödyntääksesi sen etuja.

![LIQUID GREEN](assets/fr/01.webp)

## Mikä on Liquid Network?

Liquid on federatiivinen sivuketju, joka on rakennettu Bitcoinin päälle, ja sen on kehittänyt Blockstream. Se pyrkii parantamaan siirtojen nopeutta, yksityisyyttä ja toiminnallisuuksia. Se käyttää kahdenvälistä ankkurointimekanismia, joka perustuu federaatioon lukitakseen bitcoineja pääketjussa ja luomaan vastineeksi Liquid-bitcoineja (L-BTC), tokeneita, jotka kiertävät Liquidissa samalla kun ne pysyvät tuettuina alkuperäisillä bitcoineilla.

![LIQUID GREEN](assets/fr/02.webp)
Liquid-verkko perustuu federaation osallistujiin, joihin kuuluu tunnustettuja tahoja Bitcoin-ekosysteemistä, jotka validioivat lohkoja ja hallinnoivat kahdenvälistä ankkurointia. L-BTC:n lisäksi Liquid mahdollistaa myös muiden digitaalisten varojen, kuten stablecoinien tai muiden kryptovaluuttojen, liikkeeseenlaskun.
![LIQUID GREEN](assets/fr/03.webp)

## Johdatus Blockstream Greeniin

Blockstream Green on ohjelmistolompakko, joka on saatavilla mobiililaitteille ja tietokoneille. Aiemmin tunnettu nimellä *Green Address*, tämä lompakko tuli Blockstream-projektiksi sen hankinnan jälkeen vuonna 2016.

Green on sovellus, joka on erityisen helppokäyttöinen, mikä tekee siitä mielenkiintoisen aloittelijoille. Se tarjoaa kaikki hyvän Bitcoin-lompakon olennaiset ominaisuudet, mukaan lukien RBF (*Replace-by-Fee*), vaihtoehdon yhdistää Torin kautta, mahdollisuuden yhdistää omaan nodeen, SPV (*Simple Payment Verification*) -vaihtoehdon, merkinnät ja kolikoiden hallinnan.

Blockstream Green tukee myös Liquid-verkkoa, ja sitä tulemme tutkimaan tässä oppaassa. Jos haluat käyttää Greeniä muihin sovelluksiin, suosittelen myös näiden muiden oppaiden tutkimista:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Blockstream Green -sovelluksen asentaminen ja käyttöönotto

Ensimmäinen askel on luonnollisesti Green-sovelluksen lataaminen. Siirry sovelluskauppaasi:
- [Androidille](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet) ;
- [Applelle](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Android-käyttäjillä on myös mahdollisuus asentaa sovellus `.apk`-tiedoston kautta, [joka on saatavilla Blockstreamin GitHubissa](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Käynnistä sovellus ja merkitse ruutu "*Hyväksyn ehdot...*".

![LIQUID GREEN](assets/fr/06.webp)

Kun avaat Greenin ensimmäistä kertaa, kotinäyttö ilmestyy ilman määritettyjä lompakoita. Myöhemmin, jos luot tai tuot lompakoita, ne ilmestyvät tähän käyttöliittymään. Ennen kuin siirryt lompakon luomiseen, suosittelen, että säädät sovelluksen asetuksia odotustesi mukaisesti. Klikkaa "*Sovelluksen asetukset*".

![LIQUID GREEN](assets/fr/07.webp)

"*Parannettu yksityisyys*" -vaihtoehto, joka on saatavilla vain Androidilla, parantaa yksityisyyttä poistamalla kuvakaappaukset käytöstä ja piilottamalla sovelluksen esikatselut. Se myös lukitsee automaattisesti pääsyn sovellukseen heti, kun puhelimesi lukittuu, tehden tietojesi paljastumisen vaikeammaksi.
![LIQUID GREEN](assets/fr/08.webp)
Yksityisyytensä parantamisesta kiinnostuneille sovellus tarjoaa mahdollisuuden reitittää liikenteen Tor-verkon kautta, verkko, joka salaa kaikki yhteytesi ja tekee toimintasi jäljittämisen vaikeaksi. Vaikka tämä vaihtoehto saattaa hieman hidastaa sovelluksen suorituskykyä, sitä suositellaan erittäin yksityisyyden suojaamiseen, erityisesti jos et käytä omaa täysnodea.

![LIQUID GREEN](assets/fr/09.webp)

Käyttäjille, joilla on oma täysnode, Green Wallet mahdollistaa yhteyden muodostamisen siihen Electrum-palvelimen kautta, varmistaen täyden hallinnan Bitcoin-verkon tiedoista ja transaktioiden lähettämisestä. Tämä ominaisuus on kuitenkin relevantti perinteisille Bitcoin-lompakoille, joten et tarvitse sitä, jos käytät Liquidia.

![LIQUID GREEN](assets/fr/10.webp)

Toinen vaihtoehtoinen ominaisuus on "*SPV-tarkistus*" -vaihtoehto, joka mahdollistaa tiettyjen lohkoketjun tietojen suoran tarkistamisen, vähentäen tarvetta luottaa Blockstreamin oletusnodeen, vaikka tämä menetelmä ei tarjoakaan kaikkia täysnoden vakuuksia. Jälleen, tämä koskee vain onchain Bitcoin-lompakoitasi, ei Liquidia.

![LIQUID GREEN](assets/fr/11.webp)

Kun olet säätänyt nämä asetukset tarpeidesi mukaisesti, klikkaa "*Tallenna*" -painiketta ja käynnistä sovellus uudelleen.

![LIQUID GREEN](assets/fr/12.webp)

## Liquid-lompakon luominen Blockstream Greenissä

Olet nyt valmis luomaan Liquid-lompakon. Klikkaa "*Aloita*" -painiketta.

![LIQUID GREEN](assets/fr/13.webp)

Sinulla on valinta luoda ohjelmistopohjainen lompakko paikallisesti tai hallita kylmälompakkoa laitteistolompakon kautta. Tässä oppaassa keskitymme Liquidin kuumalompakon luomiseen, joten sinun tulee valita "*Tällä laitteella*" -vaihtoehto. Voit myös käyttää yhteensopivaa laitteistolompakkoa, kuten Blockstream Jadea, Liquid-lompakkosi turvaamiseen.

![LIQUID GREEN](assets/fr/14.webp)
Voit sen jälkeen valita, haluatko palauttaa olemassa olevan Bitcoin-lompakon vai luoda uuden. Tämän oppaan tarkoituksessa luomme uuden lompakon. Jos kuitenkin tarvitset uudelleenluoda olemassa olevan Liquid-lompakon sen mnemonisen lauseen avulla, esimerkiksi laitteistolompakkosi kadottua, sinun tulee valita toinen vaihtoehto.
![LIQUID GREEN](assets/fr/15.webp)

Sinulla on sitten valinta 12 sanan tai 24 sanan mnemonisen lauseen välillä. Tämä lause mahdollistaa pääsyn palauttamisen lompakkoosi mistä tahansa yhteensopivasta ohjelmistosta, jos puhelimesi kanssa ilmenee ongelmia. Tällä hetkellä 24 sanan lauseen valitseminen ei tarjoa enemmän turvallisuutta kuin 12 sanan lause. Siksi suosittelen valitsemaan **12 sanan** mnemonisen lauseen.
Green antaa sinulle sitten mnemonisen lauseesi. Ennen jatkamista, varmista, että kukaan ei tarkkaile sinua. Klikkaa "*Näytä palautuslause*" näyttääksesi sen näytöllä.
![LIQUID GREEN](assets/fr/16.webp)

**Tämä mnemoninen lause antaa täyden ja rajoittamattoman pääsyn kaikkiin bitcoineihisi.** Kuka tahansa, jolla on tämä lause, voi varastaa varasi, vaikka hänellä ei olisi fyysistä pääsyä puhelimeesi.

Se mahdollistaa pääsyn palauttamisen bitcoineihisi tapauksissa, kuten menetys, varkaus tai puhelimen vahingoittuminen. Siksi on erittäin tärkeää tallentaa se huolellisesti **fyysiselle välineelle (ei digitaalisesti)** ja säilyttää se turvallisessa paikassa. Voit kirjoittaa sen paperille, tai lisäturvallisuuden vuoksi, jos tämä lompakko on merkittävä, suosittelen kaivertamaan sen ruostumattomasta teräksestä valmistetulle välineelle suojautuaksesi tulipalojen, tulvien tai sortumien riskeiltä (pienen määrän bitcoineja turvaavaan hot walletiin yksinkertainen paperivarmuuskopio on todennäköisesti riittävä).

*Ilmeisesti, sinun ei pitäisi koskaan jakaa näitä sanoja internetissä, päinvastoin kuin teen tässä oppaassa. Tämä esimerkkilompakko käytetään vain Liquid Testnetissä ja se poistetaan oppaan lopussa.*

![LIQUID GREEN](assets/fr/17.webp)

Kun olet oikein merkinnyt mnemonisen lauseesi fyysiselle välineelle, klikkaa "*Jatka*". Green Wallet pyytää sinua sitten vahvistamaan joitakin lauseesi sanoja varmistaakseen, että olet kirjannut ne oikein. Täytä puuttuvat sanat.

![LIQUID GREEN](assets/fr/18.webp)

Valitse PIN-koodi laitteellesi, jota käytetään Green-lompakkosi avaamiseen. Se on siis suoja luvattomalta fyysiseltä pääsyltä. Tämä PIN-koodi ei vaikuta lompakkosi kryptografisten avainten johdannaisuuteen. Näin ollen, vaikka sinulla ei olisi pääsyä tähän PIN-koodiin, 12 tai 24 sanan mnemonisen lauseen hallussapito mahdollistaa pääsyn palauttamisen bitcoineihisi.

On suositeltavaa valita mahdollisimman satunnainen 6-numeroinen PIN-koodi. Varmista myös, että tallennat tämän koodin, jotta et unohda sitä, muuten sinun on pakko palauttaa lompakkosi mnemonisen lauseen avulla. Myöhemmin voit lisätä biometrisen lukitusvaihtoehdon välttääksesi PIN-koodin syöttämisen joka kerta, kun sitä käytät. Yleisesti ottaen biometriikka on paljon vähemmän turvallinen kuin itse PIN-koodi. Siksi oletuksena neuvon olemaan asettamatta tätä lukitusvaihtoehtoa.

![LIQUID GREEN](assets/fr/19.webp)

Syötä PIN-koodisi toisen kerran vahvistaaksesi sen.

![LIQUID GREEN](assets/fr/20.webp)
Odota, että lompakkosi luodaan, ja klikkaa sitten "*Luo tili*" -painiketta.
![LIQUID GREEN](assets/fr/21.webp)
Valitse "*Assets*" -laatikosta "*Liquid Bitcoin*". Tämän jälkeen voit valita joko perinteisen yksittäisen allekirjoituksen lompakon, jota käytämme tässä oppaassa, tai kaksivaiheisen tunnistautumisen (2FA) suojan lompakon.
![LIQUID GREEN](assets/fr/22.webp)

Ja siinä se on, Liquid-lompakkosi on onnistuneesti luotu käyttäen Green-sovellusta!

![LIQUID GREEN](assets/fr/23.webp)

Ennen ensimmäisten bitcoiniesi vastaanottamista Liquid-lompakkoosi, **suosittelen vahvasti suorittamaan tyhjän palautustestin**. Kirjaa ylös viitetieto, kuten xpubisi tai ensimmäinen vastaanotto-osoitteesi, poista sitten lompakkosi Green-sovelluksesta, kun se on vielä tyhjä. Yritä sen jälkeen palauttaa lompakkosi Greeniin käyttäen paperivarmuuskopioitasi. Tarkista, että palautuksen jälkeen luotu todistetieto vastaa alun perin kirjaamaasi. Jos näin on, voit olla varma, että paperivarmuuskopiosi ovat luotettavia. Jos haluat oppia lisää palautustestin suorittamisesta, suosittelen tutustumaan tähän toiseen oppaaseen:

https://planb.network/tutorials/wallet/recovery-test

## Liquid-lompakkosi asettaminen

Jos haluat mukauttaa lompakkoasi, klikkaa kolmea pientä pistettä oikeassa yläkulmassa.

![LIQUID GREEN](assets/fr/24.webp)

"*Rename*" -vaihtoehto antaa sinun mukauttaa lompakkosi nimeä, mikä on erityisen hyödyllistä, jos hallinnoit useita lompakoita samassa sovelluksessa.

![LIQUID GREEN](assets/fr/25.webp)

"*Unit*" -valikko antaa sinulle mahdollisuuden vaihtaa lompakkosi perusyksikköä. Voit esimerkiksi valita näyttämään sen satosheina bitcoinien sijaan.

![LIQUID GREEN](assets/fr/26.webp)

"*Settings*" -valikko tarjoaa pääsyn lompakkosi eri asetuksiin.

![LIQUID GREEN](assets/fr/27.webp)

Täältä löydät esimerkiksi *descriptorisi*, joka voi olla hyödyllinen, jos aiot perustaa vain seurantalompakon tästä Liquid-lompakosta.

![LIQUID GREEN](assets/fr/28.webp)

Voit myös vaihtaa lompakkosi PIN-koodin ja ottaa käyttöön biometrisen kirjautumisen.

![LIQUID GREEN](assets/fr/29.webp)

## Liquid-lompakkosi käyttäminen

Nyt kun Liquid-lompakkosi on asetettu, olet valmis vastaanottamaan ensimmäiset L-satoshisi!
Jos sinulla ei vielä ole L-BTC:tä, käytössäsi on useita vaihtoehtoja. Ensimmäinen on saada se suoraan lähetettynä sinulle. Jos joku haluaa maksaa sinulle bitcoineilla Liquidissa, anna heille vain vastaanotto-osoite. Toinen ratkaisu on vaihtaa onchain-bitcoinit tai Lightning-verkon bitcoinit L-BTC:ksi. Tätä varten voit käyttää [siltaa, kuten Boltz](https://boltz.exchange/). Syötä vain Liquid-osoitteesi sivustolle, tee sitten maksu joko Lightning-verkon kautta tai onchain.
![LIQUID GREEN](assets/fr/30.webp)

Liquid-osoitteen luomiseksi klikkaa "*Receive*" -nappia.

![LIQUID GREEN](assets/fr/31.webp)

Green näyttää sitten lompakkosi ensimmäisen tyhjän vastaanotto-osoitteen. Voit joko skannata liitetyn QR-koodin tai kopioida osoitteen suoraan lähettääksesi L-BTC:tä siihen.

![LIQUID GREEN](assets/fr/32.webp)

Kun transaktio on lähetetty verkossa, se ilmestyy lompakkoosi.

![LIQUID GREEN](assets/fr/33.webp)

Odota, että saat tarpeeksi vahvistuksia pitääksesi transaktion lopullisena. Liquidissa vahvistusten pitäisi olla nopeita, koska lohko julkaistaan joka minuutti.

![LIQUID GREEN](assets/fr/34.webp)
L-sateilla Liquid-lompakossasi voit nyt myös lähettää niitä. Klikkaa "*Lähetä*".
![LIQUID GREEN](assets/fr/35.webp)

Seuraavalla sivulla, syötä vastaanottajan Liquid-osoite. Voit syöttää sen käsin tai skannata heidän QR-koodinsa.

![LIQUID GREEN](assets/fr/36.webp)

Valitse maksun määrä.

![LIQUID GREEN](assets/fr/37.webp)

Klikkaa "*Seuraava*" päästäksesi yhteenvedon näyttöön transaktiostasi. Tarkista, että osoite, määrä ja maksut ovat oikein.

![LIQUID GREEN](assets/fr/38.webp)

Jos kaikki näyttää hyvältä, liu'uta vihreää nappia näytön alareunassa oikealle allekirjoittaaksesi ja lähettääksesi transaktion Bitcoin-verkkoon.

![LIQUID GREEN](assets/fr/39.webp)

Transaktiosi ilmestyy nyt Bitcoin-lompakkosi kojelaudalle odottamaan vahvistusta.

![LIQUID GREEN](assets/fr/40.webp)

Ja siinä se on, nyt tiedät kuinka käyttää Liquid-sivuketjua Blockstream Green -sovelluksen kanssa helposti!

Jos pidit tätä opasta hyödyllisenä, arvostaisin peukkua ylös alla. Voit vapaasti jakaa tämän artikkelin sosiaalisissa verkostoissasi. Suurkiitokset!

Suosittelen myös tutustumaan tähän toiseen kattavaan oppaaseen Blockstream Green -mobiilisovelluksesta, jotta voit perustaa onchain Bitcoin hot walletin:

https://planb.network/tutorials/wallet/blockstream-green