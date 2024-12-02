---
name: Blockstream Green - Desktop
description: Green Wallet -ohjelmiston käyttö tietokoneella
---
![cover](assets/cover.webp)

Tässä oppaassa tutustumme siihen, miten Blockstream Green -ohjelmistoa käytetään tietokoneella hallitaksesi turvallista lompakkoa laitteistolompakossa. Laitteistolompakkoa käytettäessä on välttämätöntä käyttää tietokoneella ohjelmistoa tämän lompakon hallintaan. Tämä hallintaohjelmisto ei pääse käsiksi yksityisiin avaimiin; sitä käytetään ainoastaan lompakon saldon tarkistamiseen, vastaanotto-osoitteiden luomiseen sekä transaktioiden rakentamiseen ja lähettämiseen, jotka laitteistolompakko allekirjoittaa. Green edustaa yhtä monista saatavilla olevista ratkaisuista Bitcoin-laitteistolompakkosi hallintaan.

Vuonna 2024 Blockstream Green on yhteensopiva vain Ledger Nano S (vanhempi versio), Ledger Nano X, Trezor One, Trezor T ja Blockstream Jade -laitteiden kanssa.

## Johdanto Blockstream Greeniin

Blockstream Green on saatavilla sekä mobiili- että työpöytäversioina. Aiemmin Green Address -nimellä tunnettu lompakko tuli Blockstream-projektiksi sen hankinnan jälkeen vuonna 2016.

Green on erittäin käyttäjäystävällinen sovellus, mikä tekee siitä erityisen sopivan aloittelijoille. Se tarjoaa erilaisia ominaisuuksia, kuten kuumien lompakoiden, laitteistolompakoiden sekä Liquid-sivuketjun lompakoiden hallinnan. Voit myös käyttää sitä vain seurantaan tarkoitetun lompakon perustamiseen.

![GREEN-DESKTOP](assets/fr/01.webp)

Tässä oppaassa keskitymme ainoastaan ohjelmiston käyttöön tietokoneella. Tutustuaksesi Greenin muihin käyttötarkoituksiin, suosittelen tutustumaan muihin omistettuihin oppaisiimme:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Blockstream Green -ohjelmiston asentaminen ja käyttöönotto

Aloita asentamalla Blockstream Green -ohjelmisto tietokoneellesi. Siirry [viralliselle verkkosivustolle](https://blockstream.com/green/) ja napsauta "*Lataa nyt*" -painiketta. Seuraa sitten asennusprosessia käyttöjärjestelmäsi mukaisesti.

![GREEN-DESKTOP](assets/fr/02.webp)

Käynnistä sovellus ja merkitse ruutu "*Hyväksyn ehdot...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Kun avaat Greenin ensimmäistä kertaa, kotinäyttö ilmestyy ilman mitään määritettyä lompakkoa. Myöhemmin, jos luot tai tuot lompakoita, ne ilmestyvät tähän käyttöliittymään. Ennen kuin siirryt lompakon luomiseen, neuvon säätämään sovelluksen asetukset odotustesi mukaisesti. Napsauta asetuskuvaketta vasemmassa alakulmassa.

![GREEN-DESKTOP](assets/fr/04.webp)

"*Yleiset*" -valikossa voit vaihtaa ohjelmiston kieltä ja ottaa käyttöön kokeellisia ominaisuuksia, jos haluat.

![GREEN-DESKTOP](assets/fr/05.webp)
"*Verkko*" -valikossa voit ottaa käyttöön yhteyden Tor-verkon kautta, verkko, joka salaa kaikki yhteytesi ja tekee toiminnastasi vaikeasti jäljitettävää. Vaikka tämä vaihtoehto saattaa hieman hidastaa sovelluksen suorituskykyä, se on erittäin suositeltavaa yksityisyytesi suojaamiseksi, erityisesti jos et käytä omaa täysnodea.
![GREEN-DESKTOP](assets/fr/06.webp)

Käyttäjille, joilla on oma täysnode, Green tarjoaa mahdollisuuden yhdistää siihen Electrum-palvelimen kautta, varmistaen täyden hallinnan Bitcoin-verkon tiedoista ja transaktioiden lähettämisestä. Tehdäksesi tämän, napsauta "*Mukautetut palvelimet ja validointi*" -valikkoa ja syötä Electrum-palvelimesi tiedot.

![GREEN-DESKTOP](assets/fr/07.webp)
Toinen vaihtoehtoinen ominaisuus on "*SPV Varmennus*" -vaihtoehto, joka mahdollistaa tiettyjen lohkoketjutietojen suoran varmentamisen, vähentäen näin tarvetta luottaa Blockstreamin oletusnoodiin, vaikkakaan tämä menetelmä ei tarjoa kaikkia täysnoodin takeita. Tämä vaihtoehto löytyy myös "*Mukautetut palvelimet ja varmennus*" -valikosta.
![GREEN-DESKTOP](assets/fr/08.webp)

Kun nämä asetukset on säädetty tarpeidesi mukaan, voit poistua tästä käyttöliittymästä.

## Bitcoin-lompakon tuominen Blockstream Greeniin

Olet nyt valmis tuomaan Bitcoin-lompakkosi. Klikkaa "**Aloita**" -painiketta.

![GREEN-DESKTOP](assets/fr/09.webp)

Sinulla on valinta luoda paikallinen ohjelmistolompakko tai hallita kylmälompakkoa laitteistolompakon kautta. Tässä oppaassa keskitymme laitteistolompakon hallintaan, joten sinun tulee valita "*Laitteistolompakossa*" -vaihtoehto.

Toisaalta "*Vain katselu*" -vaihtoehto mahdollistaa laajennetun julkisen avaimen (`xpub`) tuonnin lompakon tapahtumien tarkasteluun ilman, että voit käyttää siihen liittyviä varoja.

![GREEN-DESKTOP](assets/fr/10.webp)

Jos käytät Jadea, klikkaa vastaavaa painiketta. Muussa tapauksessa valitse "*Yhdistä eri laitteistolaitteeseen*". Minun tapauksessani käytän Ledger Nano S:ää. Ledgerin käyttäjien tulee varmistaa, että he ovat asentaneet "*Bitcoin Legacy*" -sovelluksen laitteistolompakkoonsa, koska Green tukee vain tätä versiota.

![GREEN-DESKTOP](assets/fr/11.webp)

Yhdistä laitteistolompakkosi tietokoneeseen ja valitse se Greenissä.

![GREEN-DESKTOP](assets/fr/12.webp)

Odota, kun Green tuo tiedot lompakostasi, jonka jälkeen pääset käyttämään sitä.

![GREEN-DESKTOP](assets/fr/13.webp)

Tässä vaiheessa kaksi skenaariota on mahdollista. Jos olit jo käyttänyt laitteistolompakkoasi aiemmin, sinun pitäisi nähdä tilisi ohjelmistossa. Mutta jos, kuten minä, olet juuri alustanut laitteistolompakkosi luomalla muistilauseen käyttämättä sitä vielä, sinun on luotava tili. Klikkaa "*Luo tili*".
![GREEN-DESKTOP](assets/fr/14.webp)
Valitse "*Standardi*", jos haluat käyttää klassista lompakkoa.

![GREEN-DESKTOP](assets/fr/15.webp)

Nyt sinulla on pääsy tilillesi.

![GREEN-DESKTOP](assets/fr/16.webp)

## Laitteistolompakon käyttö Blockstream Greenin kanssa

Nyt kun Bitcoin-lompakkosi on asetettu, olet valmis vastaanottamaan ensimmäiset satsisi! Tee tämä yksinkertaisesti klikkaamalla "*Vastaanota*" -painiketta.

![GREEN-DESKTOP](assets/fr/17.webp)

Klikkaa "*Kopioi osoite*" -painiketta kopioidaksesi osoitteen tai skannataksesi sen QR-koodin.

![GREEN-DESKTOP](assets/fr/18.webp)

Kun transaktio on lähetetty verkossa, se ilmestyy lompakkoosi. Odota saadaksesi tarpeeksi vahvistuksia pitääksesi transaktion muuttumattomana.

![GREEN-DESKTOP](assets/fr/19.webp)

Bitcoineilla lompakossasi, olet nyt valmis lähettämään niitä. Klikkaa "*Lähetä*" -painiketta.

![GREEN-DESKTOP](assets/fr/20.webp)

Seuraavalla sivulla, syötä vastaanottajan osoite. Voit syöttää sen käsin tai skannata QR-koodin web-kamerallasi.

![GREEN-DESKTOP](assets/fr/21.webp)

Valitse maksun määrä.

![GREEN-DESKTOP](assets/fr/22.webp)
Näytön alareunasta voit valita tämän siirron maksutason. Sinulla on mahdollisuus noudattaa sovelluksen suosituksia tai mukauttaa maksujasi. Mitä korkeammat maksut verrattuna muihin odottaviin siirtoihin, sitä nopeammin siirtosi käsitellään. Jos haluat tietää maksutason markkinatilanteen, voit vierailla [Mempool.space](https://mempool.space/) -sivustolla kohdassa "*Siirtomaksut*".
![GREEN-DESKTOP](assets/fr/23.webp)

Jos haluat erityisesti valita, mitä UTXO:ja käytetään siirrossasi, klikkaa "*Manuaalinen kolikkovalinta*" -painiketta.

![GREEN-DESKTOP](assets/fr/24.webp)

Tarkista siirtosi asetukset ja, jos kaikki on odotustesi mukaisesti, klikkaa "*Seuraava*".

![GREEN-DESKTOP](assets/fr/25.webp)

Varmista vielä kerran, että osoite, summa ja maksut ovat oikein, sitten klikkaa "*Vahvista siirto*".

![GREEN-DESKTOP](assets/fr/26.webp)

Varmista, että kaikki siirron parametrit ovat oikein laitteistolompakkosi näytöllä, ja allekirjoita sitten siirto käyttäen sitä.

![GREEN-DESKTOP](assets/fr/27.webp)

Kun siirto on allekirjoitettu laitteistolompakolla, Green lähettää sen automaattisesti Bitcoin-verkkoon. Siirtosi ilmestyy sitten Bitcoin-lompakkosi kojelaudalle odottamaan vahvistusta.

![GREEN-DESKTOP](assets/fr/28.webp)

Ja siinä se, nyt tiedät, miten voit helposti asettaa Blockstream Green -ohjelmiston hallitaksesi Bitcoin-lompakkoasi laitteistolompakolla.
Jos pidit tätä opasta hyödyllisenä, arvostaisin, jos jättäisit peukun ylös alla. Voit vapaasti jakaa tämän artikkelin sosiaalisissa verkostoissasi. Suurkiitokset!
Suosittelen myös tutustumaan tähän kattavaan oppaaseen Blockstream Green -mobiilisovelluksen asettamisesta hot walletiksi:

https://planb.network/tutorials/wallet/blockstream-green