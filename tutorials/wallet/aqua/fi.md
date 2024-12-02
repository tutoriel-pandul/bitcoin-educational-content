---
name: Aqua
description: Bitcoin, Lightning ja Liquid yhdessä lompakossa
---

![cover](assets/cover.webp)

Aqua on mobiilisovellus, joka mahdollistaa helposti "hot walletin" luomisen Bitcoinille ja Liquidille, ja tarjoaa myös mahdollisuuden käyttää Lightningia ilman solmun hallinnan monimutkaisuutta integroitujen vaihtojen ansiosta. Se tukee myös USDT-stablecoinien hallintaa eri verkostoissa.

Yhtiö JAN3:n, Samson Mow'n johdolla kehittämä Aqua-sovellus suunniteltiin alun perin erityisesti Latinalaisen Amerikan käyttäjien tarpeisiin, vaikkakin se soveltuu mille tahansa käyttäjälle maailmanlaajuisesti. Se on erityisen mielenkiintoinen aloittelijoille ja niille, jotka käyttävät Bitcoinia päivittäin maksuihinsa.

Tässä oppaassa tutustumme Aquan moniin ominaisuuksiin. Mutta ennen sitä, käydään hetki ymmärtämään, mikä on sivuketju Bitcoinissa ja miten Liquid toimii, mikä antaa meille täyden käsityksen Aquan eduista.

![AQUA](assets/fr/01.webp)

## Mikä on sivuketju?

Bitcoin-protokollalla on tarkoituksellisia teknisiä rajoituksia, jotka auttavat ylläpitämään verkon hajautusta ja varmistamaan turvallisuuden jakautumisen kaikkien käyttäjien kesken. Kuitenkin nämä rajoitukset voivat joskus turhauttaa käyttäjiä, erityisesti ruuhkan aikana, joka johtuu suuresta määrästä samanaikaisia transaktioita. Bitcoinin skaalautuvuudesta käyty keskustelu on pitkään jakanut yhteisöä, erityisesti Blocksize Warin aikana. Tuon episodin jälkeen Bitcoin-yhteisössä on laajalti tunnustettu, että skaalautuvuus on varmistettava off-chain ratkaisuilla, toisen kerroksen järjestelmissä. Näihin ratkaisuihin kuuluvat sivuketjut, jotka ovat edelleen suhteellisen tuntemattomia ja vähän käytettyjä verrattuna muihin järjestelmiin, kuten Lightning Networkiin.

Sivuketju on itsenäinen lohkoketju, joka toimii rinnakkain pääasiallisen Bitcoin-lohkoketjun kanssa. Se käyttää bitcoinia tilikauden yksikkönä mekanismin kautta, jota kutsutaan "*kahden suunnan kiinnitykseksi*". Tämä järjestelmä mahdollistaa bitcoinien lukitsemisen pääketjussa toistaakseen niiden arvon sivuketjussa, jossa ne kiertävät alkuperäisiä bitcoineja tukevina tokenina. Nämä tokenit yleensä säilyttävät arvoyhteyden pääketjussa lukittuihin bitcoineihin, ja prosessi voidaan kääntää varojen palauttamiseksi Bitcoinissa.
Sivuketjujen tavoitteena on tarjota lisätoimintoja tai teknisiä parannuksia, kuten nopeampia transaktioita, pienempiä maksuja tai älykkäiden sopimusten tuki. Näitä innovaatioita ei aina voida toteuttaa suoraan Bitcoin-lohkoketjussa vaarantamatta sen hajautusta tai turvallisuutta. Sivuketjut mahdollistavat uusien ratkaisujen testaamisen ja tutkimisen säilyttäen samalla Bitcoinin eheyden. Kuitenkin nämä protokollat vaativat usein kompromisseja, erityisesti hajautuksen ja turvallisuuden suhteen, riippuen valitusta hallintomallista ja konsensusmekanismista.
## Mikä on Liquid?

Liquid on Bitcoinin päälle rakennettu federoitu sivuketju, jonka on kehittänyt Blockstream, tavoitteenaan parantaa transaktioiden nopeutta, yksityisyyttä ja toiminnallisuuksia. Se käyttää kahdenvälistä ankkurointimekanismia, joka perustuu federaatioon lukitakseen bitcoineja pääketjussa ja luodakseen vastineeksi Liquid-bitcoineja (L-BTC), tokeneita, jotka kiertävät Liquidissa samalla kun ne pysyvät alkuperäisten bitcoinien tukemina.

![AQUA](assets/fr/02.webp)

Liquid-verkko perustuu federaatioon osallistujista, joka koostuu Bitcoin-ekosysteemin tunnustetuista tahoista, jotka validioivat lohkot ja hallinnoivat kahdenvälistä ankkurointia. L-BTC:n lisäksi Liquid mahdollistaa myös muiden digitaalisten varojen, kuten stablecoin USDT:n tai muiden kryptovaluuttojen, liikkeeseenlaskun.

![AQUA](assets/fr/03.webp)

## Aquan sovelluksen asentaminen

Ensimmäinen askel on luonnollisesti Aquan sovelluksen lataaminen. Siirry sovelluskauppaasi:
- [Androidille](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Applelle](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
Android-käyttäjillä on myös mahdollisuus asentaa sovellus `.apk`-tiedoston kautta, [joka on saatavilla heidän GitHubissa](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Käynnistä sovellus, sitten rastita ruutu "*Olen lukenut ja hyväksynyt Käyttöehdot & Tietosuojakäytännön*".

![AQUA](assets/fr/06.webp)

## Lompakon luominen Aquassa

Napsauta "*Luo Lompakko*" -painiketta.

![AQUA](assets/fr/07.webp)

Ja siinä se on, lompakkosi on jo luotu!

![AQUA](assets/fr/08.webp)

Mutta ennen kaikkea, koska tämä on itse hallinnoitu lompakko, on välttämätöntä tehdä fyysinen varmuuskopio mnemonic-lauseestasi. **Tämä mnemonic-lause tarjoaa täydellisen ja rajoittamattoman pääsyn kaikkiin bitcoineihisi**. Kuka tahansa, jolla on tämä lause, voi varastaa varasi, vaikka hänellä ei olisi fyysistä pääsyä puhelimeesi.
Se mahdollistaa pääsyn palauttamisen bitcoineihisi tapauksessa, jos menetät, varastetaan tai puhelimesi vahingoittuu. On siis erittäin tärkeää varmuuskopioida se huolellisesti fyysiselle välineelle (ei digitaaliselle) ja säilyttää se turvallisessa paikassa. Voit kirjoittaa sen paperille, tai lisäturvallisuuden vuoksi, jos tämä lompakko on merkittävä, suosittelen kaivertamaan sen ruostumattomasta teräksestä valmistetulle välineelle suojautuaksesi tulipalojen, tulvien tai sortumien riskeiltä (pienen bitcoin-määrän turvaamiseen tarkoitetulle hot walletille yksinkertainen paperivarmuuskopio on todennäköisesti riittävä).
Tehdäksesi tämän, napsauta asetusvalikkoa.

![AQUA](assets/fr/09.webp)

Sitten napsauta "*Näytä Siemenlause*". Tee fyysinen varmuuskopio tästä 12 sanan lauseesta.

![AQUA](assets/fr/10.webp)

Samassa asetusvalikossa voit myös vaihtaa sovelluksen kielen sekä käytetyn fiat-valuutan.

![AQUA](assets/fr/11.webp)

Ennen ensimmäisten bitcoiniesi vastaanottamista lompakkoosi, **suosittelen vahvasti suorittamaan kuivan harjoituksen palautustestin**. Kirjaa ylös viitetieto, kuten xpubisi tai ensimmäinen vastaanotto-osoitteesi, sitten poista lompakkosi Aqua-sovelluksesta, kun se on vielä tyhjä. Yritä sen jälkeen palauttaa lompakkosi Aquassa käyttäen paperivarmuuskopioitasi. Tarkista, että palautuksen jälkeen generoitu todistetieto vastaa alun perin kirjaamaasi. Jos näin on, voit olla varma, että paperivarmuuskopiosi ovat luotettavia. Lisätietoja palautustestin suorittamisesta, suosittelen konsultoimaan tätä toista opasta:

https://planb.network/tutorials/wallet/recovery-test

## Bitcoinien vastaanottaminen Aquassa

Nyt kun lompakkosi on pystytetty, olet valmis vastaanottamaan ensimmäiset satsisi! Napsauta vain "*Vastaanota*" -painiketta "*Lompakko*" -valikossa.

![AQUA](assets/fr/12.webp)

Voit valita vastaanottavasi bitcoineja onchain, Liquidissa tai Lightningin kautta.

![AQUA](assets/fr/13.webp)

Onchain-siirtoja varten Aqua luo erityisen vastaanotto-osoitteen, jossa voit vastaanottaa satsisi.

![AQUA](assets/fr/14.webp)

Samoin, valitsemalla Liquidin, Aqua tarjoaa sinulle Liquid-osoitteen.

![AQUA](assets/fr/15.webp)

Jos haluat vastaanottaa varoja Lightningin kautta, sinun on ensin määriteltävä haluttu määrä.

![AQUA](assets/fr/16.webp)

Sitten, napsauta "*Luo Lasku*".

![AQUA](assets/fr/17.webp)
Aqua luo laskun vastaanottaakseen varoja Lightning-lompakosta. On tärkeää huomata, että toisin kuin onchain- ja Liquid-vaihtoehdoissa, Lightningin kautta vastaanotetut varat muunnetaan automaattisesti L-BTC:ksi Liquidissa käyttäen Boltz-työkalua, koska Aqua ei ole Lightning-solmu. Tämä prosessi mahdollistaa varojen vastaanottamisen ja lähettämisen Lightningin kautta, mutta ilman, että pitäisit bitcoinejasi koskaan Lightning-verkossa.![AQUA](assets/fr/18.webp)

Henkilökohtaisesti aloitan lähettämällä bitcoineja Lightningin kautta Aquaan. Kun transaktio on suoritettu annetulla laskulla, vastaanotetaan vahvistus.

![AQUA](assets/fr/19.webp)

Vaihdon etenemisen seuraamiseksi palaa lompakkosi kotisivulle ja klikkaa "*L2 Bitcoin*" -tiliä, joka listaa Lightning (vaihdon kautta) ja Liquid -transaktiot.

![AQUA](assets/fr/20.webp)

Täällä voit tarkastella transaktiotasi sekä saldoasi L-BTC:ssä.

![AQUA](assets/fr/21.webp)

## Bitcoinien vaihtaminen Aquassa

Nyt kun sinulla on varoja Aqua-lompakossasi, sinulla on mahdollisuus vaihtaa niitä suoraan sovelluksessa, joko siirtääksesi ne pääasialliseen Bitcoin-lohkoketjuun tai Liquidiin. Voit myös muuntaa bitcoinejasi stablecoiniin USDT (tai muihin). Tee tämä siirtymällä "*Marketplace*" -valikkoon.

![AQUA](assets/fr/22.webp)

Klikkaa "*Swaps*".

![AQUA](assets/fr/23.webp)

"*Transfer from*" -laatikossa valitse vaihdettava omaisuuserä. Tällä hetkellä minulla on vain L-BTC, joten valitsen sen.

![AQUA](assets/fr/24.webp)

"*Transfer to*" -laatikossa valitse vaihdon kohde-omaisuuserä. Omalta osaltani valitsin USDT:n Liquid-verkossa.

![AQUA](assets/fr/25.webp)

Syötä haluamasi muunnettava määrä.

![AQUA](assets/fr/26.webp)

Vahvista klikkaamalla "*Continue*".

![AQUA](assets/fr/27.webp)

Varmista, että vaihdon asetukset ovat mieleisesi, ja vahvista sitten liu'uttamalla "*Swap*" -painiketta näytön alareunassa.

![AQUA](assets/fr/28.webp)

Vaihtosi on nyt vahvistettu.

![AQUA](assets/fr/29.webp)

Jos palaamme lompakkoosamme, voimme nähdä, että meillä on nyt USDT:tä Liquidissa.

![AQUA](assets/fr/30.webp)

## Bitcoinien lähettäminen Aquassa

Nyt kun sinulla on bitcoineja Aqua-lompakossasi, sinulla on mahdollisuus lähettää niitä. Klikkaa "*Send*" -painiketta.

![AQUA](assets/fr/31.webp)

Valitse lähetettävä omaisuuserä tai valitse verkko suorittaaksesi transaktion. Omalta osaltani lähetän bitcoineja Lightningin kautta.

![AQUA](assets/fr/32.webp)
Seuraavaksi, syötä tarvittavat tiedot maksun lähettämiseksi: Bitcoin onchainille tai Liquidille tarvitset vastaanotto-osoitteen; Lightningille tarvitaan lasku. Voit liittää nämä tiedot suoraan määrättyyn kenttään tai käyttää QR-koodi -ikonia avataksesi kameran ja skannataksesi osoitteen tai laskun. Klikkaa sitten "*Continue*".
![AQUA](assets/fr/33.webp)

Klikkaa "*Continue*" uudelleen, jos kaikki tiedot näyttävät oikeilta.

![AQUA](assets/fr/34.webp)
Aqua esittelee sinulle yhteenvedon tapahtumasta. Varmista, että kaikki tiedot ovat oikein, erityisesti kohdeosoite, maksut ja summa. Vahvistaaksesi tapahtuman, liu'uta "*Liu'uta lähettääksesi*" -painiketta, joka sijaitsee näytön alareunassa.
![AQUA](assets/fr/35.webp)

Tämän jälkeen sinulle annetaan vahvistus lähetyksestä.

![AQUA](assets/fr/36.webp)

Ja siinä se on, nyt tiedät kuinka käyttää Aqua-sovellusta vastaanottaaksesi ja käyttääksesi varoja Bitcoinissa, Lightningissa ja Liquidissa, kaikki yhden käyttöliittymän kautta.

Jos pidit tätä opasta hyödyllisenä, arvostaisin, jos voisit jättää peukun ylös alla. Voit vapaasti jakaa tämän artikkelin sosiaalisissa verkostoissasi. Suurkiitokset!

Suosittelen myös tutustumaan tähän toiseen kattavaan oppaaseen Blockstream Green mobiilisovelluksesta, joka on toinen mielenkiintoinen ratkaisu Liquid-lompakkosi pystyttämiseen:

https://planb.network/tutorials/wallet/blockstream-green-liquid