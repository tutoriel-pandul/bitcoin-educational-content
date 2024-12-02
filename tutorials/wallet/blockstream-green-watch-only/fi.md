---
name: Blockstream Green - Vain seuranta
description: Vain seurantaa varten tarkoitetun lompakon asettaminen
---
![cover](assets/cover.webp)

Tässä oppaassa opit, kuinka voit helposti asettaa vain seurantaa varten tarkoitetun lompakon mobiililaitteella käyttäen Blockstream Green -sovellusta.

## Mikä on Vain seurantaa varten tarkoitettu lompakko?

Vain seurantaa varten tarkoitettu lompakko, tai "watch-only wallet", on ohjelmistotyyppi, joka on suunniteltu mahdollistamaan käyttäjälle yhden tai useamman tietyn Bitcoinin julkisen avaimen liittyvien transaktioiden tarkkailun, ilman että käyttäjällä on pääsy vastaaviin yksityisiin avaimiin.

Tämän tyyppinen sovellus säilyttää vain Bitcoin-lompakon seurantaan tarvittavat tiedot, mukaan lukien sen saldon ja transaktiohistorian tarkastelun, mutta sillä ei ole pääsyä yksityisiin avaimiin. Siksi on mahdotonta käyttää lompakossa olevia bitcoineja vain seurantaa varten tarkoitetussa sovelluksessa.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Vain seurantaa varten tarkoitettua lompakkoa käytetään yleensä yhdessä laitteistolompakon kanssa. Jälkimmäinen mahdollistaa lompakon yksityisten avainten turvallisen säilytyksen laitteessa, joka ei ole yhteydessä internetiin, mikä minimoi hyökkäyspinnan, eristäen yksityiset avaimet mahdollisesti haavoittuvilta ympäristöiltä. Toisaalta vain seurantaa varten tarkoitettu sovellus säilyttää yksinomaan Bitcoin-lompakon laajennetun julkisen avaimen (`xpub`, `zpub` jne.). Tämä vanhempi avain ei mahdollista yhdistettyjen yksityisten avainten löytämistä ja siten ei salli bitcoinien käyttöä. Se kuitenkin mahdollistaa lasten julkisten avainten ja vastaanotto-osoitteiden johdannaisen. Tietäen laitteistolompakon turvaamien osoitteiden tiedot, vain seurantaa varten tarkoitettu sovellus voi seurata näitä transaktioita Bitcoin-verkossa, tarjoten käyttäjälle mahdollisuuden tarkkailla saldoaan ja luoda uusia vastaanotto-osoitteita, ilman että tarvitsee yhdistää laitteistolompakkoaan joka kerta.

Tässä oppaassa ehdotan, että tutustumme yhteen suosituimmista vain seurantaa varten tarkoitetuista lompakkoratkaisuista mobiililaitteilla: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Johdanto Blockstream Greeniin

Blockstream Green on ohjelmisto, joka on saatavilla mobiililaitteille ja tietokoneille. Aiemmin Green Address -nimellä tunnettu lompakko tuli Blockstream-projektiksi sen hankittua sen vuonna 2016.

Green on erittäin helppokäyttöinen sovellus, mikä tekee siitä erityisen sopivan aloittelijoille. Se tarjoaa erilaisia ominaisuuksia, kuten kuumien lompakoiden, laitteistolompakoiden sekä Liquid-sivuketjun lompakoiden hallinnan.

Tässä oppaassa keskitymme ainoastaan vain seurantaa varten tarkoitetun lompakon luomiseen. Tutustuaksesi Greenin muihin käyttötarkoituksiin, kutsun sinut tutustumaan muihin omistettuihin oppaisiimme:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Blockstream Green -sovelluksen asentaminen ja asettaminen
Ensimmäinen askel on luonnollisesti Green-sovelluksen lataaminen. Siirry sovelluskauppaasi:
- [Androidille](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Applelle](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Android-käyttäjillä on myös mahdollisuus asentaa sovellus `.apk` tiedoston kautta [saatavilla Blockstreamin GitHubissa](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Käynnistä sovellus, sitten rastita ruutu "*Hyväksyn ehdot...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Kun avaat Green-sovelluksen ensimmäistä kertaa, kotinäyttö ilmestyy ilman määritettyä lompakkoa. Myöhemmin, jos luot tai tuot lompakoita, ne ilmestyvät tähän käyttöliittymään. Ennen kuin siirryt lompakon luomiseen, suosittelen sinua säätämään sovelluksen asetukset odotustesi mukaisiksi. Klikkaa "*Sovelluksen Asetukset*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

"*Parannettu Yksityisyys*" -vaihtoehto, joka on saatavilla vain Androidilla, parantaa yksityisyyttä poistamalla käytöstä kuvakaappaukset ja piilottamalla sovelluksen esikatselut. Se myös automaattisesti lukitsee pääsyn sovellukseen heti, kun puhelimesi lukittuu, tehden tietojesi paljastamisen vaikeammaksi.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Niille, jotka haluavat parantaa yksityisyyttään, sovellus tarjoaa mahdollisuuden reitittää liikenteesi Tor-verkon kautta, verkko, joka salaa kaikki yhteytesi ja tekee toimintasi jäljittämisen vaikeaksi. Vaikka tämä vaihtoehto saattaa hieman hidastaa sovelluksen suorituskykyä, sitä suositellaan erittäin vahvasti yksityisyytesi suojaamiseen, erityisesti jos et käytä omaa täysnodea.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Käyttäjille, joilla on oma täysnode, Green Wallet tarjoaa mahdollisuuden yhdistää siihen Electrum-palvelimen kautta, varmistaen täyden kontrollin Bitcoin-verkon tiedoista ja transaktioiden lähettämisestä.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Toinen vaihtoehtoinen ominaisuus on "*SPV Varmennus*" -vaihtoehto, joka mahdollistaa tiettyjen lohkoketjun tietojen suoran varmentamisen, vähentäen tarvetta luottaa Blockstreamin oletusnodeen, vaikka tämä menetelmä ei tarjoakaan kaikkia täysnoden takeita.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Kun olet säätänyt nämä asetukset tarpeidesi mukaisiksi, klikkaa "*Tallenna*" -painiketta ja käynnistä sovellus uudelleen.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Vain seurantaan tarkoitetun lompakon luominen Blockstream Greenissä
Olet nyt valmis luomaan vain seurantaan tarkoitetun lompakon. Klikkaa "*Aloita*" -painiketta.
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Sinulla on valittavana useita erityyppisiä lompakoita. Tässä oppaassa haluamme luoda vain seurantaan tarkoitetun lompakon, joten klikkaa vastaavaa painiketta.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Valitse "*Yksittäinen Allekirjoitus*" -vaihtoehto.

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Valitse sitten "*Bitcoin*". Osaan tästä oppaasta testnet-lompakolla, mutta menettely on sama pääverkossa.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Sinua pyydetään antamaan joko laajennettu julkinen avain (`xpub`, `zpub` jne.) tai tulostusskriptin kuvaus.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Sinun täytyy hankkia tämä tieto lompakosta, jota haluat seurata vain seurantaan tarkoitetun lompakkosi kautta. Laajennettu julkinen avain ei ole turvallisuuden kannalta arkaluonteinen, sillä se ei salli pääsyä yksityisiin avaimiin, mutta se on yksityisyyden kannalta arkaluonteinen, sillä se paljastaa kaikki julkiset avaimesi ja siten kaikki Bitcoin-siirtosi.

Kuvittele, että käytät Sparrow Walletia hallitaksesi lompakkoasi laitteistolompakolla, löydät tämän tiedon "*Asetukset*" -osiosta. Tämän tiedon löytäminen riippuu käyttämästäsi lompakonhallintaohjelmistosta, mutta se löytyy yleensä asetuksista.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Kopioi laajennettu julkinen avain ja syötä se Green-sovellukseen, sitten klikkaa "*Yhdistä*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Tämän jälkeen voit nähdä kyseisen avaimen liittyvän saldon sekä tapahtumahistorian.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Napsauttamalla "*Receive*" voit luoda vastaanotto-osoitteen bitcoineja varten hardware-lompakkoosi. Suosittelen kuitenkin välttämään tämän vaihtoehdon käyttöä ennen kuin olet varmistanut hardware-lompakon näytöltä, että se hallitsee yksityistä avainta, joka on liitetty luotuun osoitteeseen, ennen kuin käytät sitä bitcoinien lukitsemiseen. Tämä on hyvä käytäntö noudattaa.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

"*Sweep*" -vaihtoehto mahdollistaa yksityisen avaimen manuaalisen syöttämisen varojen käyttämiseksi suoraan Green-sovelluksestasi. Paitsi erittäin spesifeissä tapauksissa, suosittelen välttämään tämän toiminnon käyttöä, koska se vaatii yksityisen avaimen paljastamisen puhelimessa, joka on paljon alttiimpi kyberhyökkäyksille kuin hardware-lompakkosi.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
Siinä se on, nyt tiedät, miten voit helposti perustaa watch-only -lompakon älypuhelimeesi! Se on erittäin kätevä työkalu lompakon seurantaan hardware-lompakossa ilman, että sinun tarvitsee yhdistää ja avata sitä joka kerta.

Jos pidit tätä opasta hyödyllisenä, arvostaisin, jos voisit jättää peukun ylös alla. Voit vapaasti jakaa tämän artikkelin sosiaalisissa verkostoissasi. Suurkiitokset!

Suosittelen myös tutustumaan tähän kattavaan oppaaseen Blockstream Green -sovelluksen käyttöön hot walletin perustamiseksi:

https://planb.network/tutorials/wallet/blockstream-green