---
name: Aqua
description: Bitcoin, Lightning a Liquid v jedné peněžence
---
![cover](assets/cover.webp)

Aqua je mobilní aplikace, která umožňuje snadné vytvoření hot peněženky pro Bitcoin a Liquid, a také nabízí možnost používat Lightning bez složitosti správy uzlu, díky integrovaným swapům. Podporuje také správu stablecoinů USDT v různých sítích.

Vyvinutá společností JAN3 pod vedením Samsona Mowa, byla aplikace Aqua původně navržena speciálně pro potřeby uživatelů v Latinské Americe, ačkoliv je vhodná pro jakéhokoli uživatele na světě. Je zvláště zajímavá pro začátečníky a ty, kteří používají Bitcoin denně pro své platby.

V tomto tutoriálu prozkoumáme, jak používat mnoho funkcí Aqua. Ale předtím si vezměme chvíli na pochopení, co je to sidechain na Bitcoinu a jak funguje Liquid, což nám umožní plně pochopit význam Aqua.

![AQUA](assets/fr/01.webp)

## Co je to sidechain?

Protokol Bitcoinu má záměrné technické omezení, které pomáhá udržovat decentralizaci sítě a zajišťuje rozdělení bezpečnosti mezi všechny uživatele. Nicméně, tato omezení mohou někdy uživatele frustrovat, zejména během zácpy způsobené vysokým objemem současných transakcí. Debata o škálovatelnosti Bitcoinu dlouho rozdělovala komunitu, zejména během Blocksize War. Od té doby je v komunitě Bitcoinu široce uznáváno, že škálovatelnost musí být zajištěna off-chain řešeními, na systémech druhé vrstvy. Mezi tato řešení patří sidechainy, které jsou stále relativně neznámé a málo využívané ve srovnání s jinými systémy jako je Lightning Network.

Sidechain je nezávislý blockchain, který funguje paralelně s hlavním blockchainem Bitcoinu. Používá bitcoin jako jednotku účtu prostřednictvím mechanismu nazývaného "*two-way peg*". Tento systém umožňuje uzamknout bitcoiny na hlavním řetězci, aby se jejich hodnota replikovala na sidechainu, kde cirkulují jako tokeny podložené původními bitcoiny. Tyto tokeny obvykle udržují hodnotovou paritu s uzamčenými bitcoiny na hlavním řetězci, a proces lze obrátit pro získání prostředků na Bitcoinu.
Cílem sidechainů je nabídnout dodatečné funkce nebo technické vylepšení, jako jsou rychlejší transakce, snížené poplatky nebo podpora pro smart kontrakty. Tyto inovace nemohou být vždy přímo implementovány na blockchainu Bitcoinu bez ohrožení jeho decentralizace nebo bezpečnosti. Sidechainy tak umožňují testování a prozkoumávání nových řešení při zachování integrity Bitcoinu. Nicméně, tyto protokoly často vyžadují kompromisy, zejména z hlediska decentralizace a bezpečnosti, v závislosti na zvoleném modelu správy a mechanismu konsensu.
## Co je Liquid?

Liquid je federovaný sidechain postavený na Bitcoinu, vyvinutý společností Blockstream, s cílem zlepšit rychlost, soukromí a funkčnosti transakcí. Používá bilaterální mechanismus ukotvení založený na federaci pro uzamčení bitcoinů na hlavním řetězci a vytvoření Liquid-bitcoinů (L-BTC), tokenů cirkulujících na Liquidu, zatímco zůstávají podložené původními bitcoiny.

![AQUA](assets/fr/02.webp)

Síť Liquid je založena na federaci účastníků, složené z uznávaných entit z ekosystému Bitcoinu, kteří validují bloky a spravují bilaterální ukotvení. Kromě L-BTC, Liquid také umožňuje vydávání dalších digitálních aktiv, jako je stablecoin USDT nebo jiné kryptoměny.

![AQUA](assets/fr/03.webp)

## Instalace aplikace Aqua

Prvním krokem je samozřejmě stáhnout aplikaci Aqua. Přejděte do svého obchodu s aplikacemi:
- [Pro Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Pro Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
Pro uživatele Androidu máte také možnost nainstalovat aplikaci prostřednictvím souboru `.apk` [dostupného na jejich GitHubu](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Spusťte aplikaci, poté zaškrtněte políčko "*Přečetl(a) jsem a souhlasím s Podmínkami služby & Zásadami ochrany osobních údajů*".

![AQUA](assets/fr/06.webp)

## Vytvoření vaší peněženky na Aqua

Klikněte na tlačítko "*Vytvořit peněženku*".

![AQUA](assets/fr/07.webp)

A máte to, vaše peněženka je již vytvořena!

![AQUA](assets/fr/08.webp)

Ale především, jelikož se jedná o peněženku s vlastní správou, je nezbytné udělat fyzickou zálohu vaší mnemonické fráze. **Tato mnemonická fráze poskytuje úplný a neomezený přístup ke všem vašim bitcoinům**. Kdokoli, kdo je v držení této fráze, může ukrást vaše prostředky, i bez fyzického přístupu k vašemu telefonu.
Umožňuje vám obnovit přístup k vašim bitcoinům v případě ztráty, krádeže nebo poškození vašeho telefonu. Je proto velmi důležité pečlivě ji zálohovat na fyzickém médiu (nikoli digitálním) a uložit ji na bezpečném místě. Můžete si ji zapsat na kus papíru, nebo pro větší bezpečnost, pokud je tato peněženka významná, doporučuji vyrytí na nerezovém médiu, aby byla chráněna před riziky požárů, záplav nebo zřícení (pro hot peněženku určenou k zabezpečení malého množství bitcoinů, pravděpodobně postačí jednoduchá papírová záloha).
K tomu klikněte na menu nastavení.

![AQUA](assets/fr/09.webp)

Poté klikněte na "*Zobrazit Seed Frázi*". Udělejte fyzickou zálohu této 12-slovné fráze.

![AQUA](assets/fr/10.webp)

V tomto stejném menu nastavení můžete také změnit jazyk aplikace a používanou fiat měnu.

![AQUA](assets/fr/11.webp)

Před přijetím vašich prvních bitcoinů do vaší peněženky **vřele doporučuji provést test suchého běhu obnovy**. Poznamenejte si referenční informaci, jako je váš xpub nebo první přijímací adresa, poté smažte vaši peněženku v aplikaci Aqua, zatímco je ještě prázdná. Poté se pokuste obnovit vaši peněženku na Aqua pomocí vašich papírových záloh. Zkontrolujte, zda informace svědka vygenerované po obnově odpovídají té, kterou jste původně poznamenali. Pokud tomu tak je, můžete být ujištěni, že vaše papírové zálohy jsou spolehlivé. Chcete-li se dozvědět více o tom, jak provést test obnovy, doporučuji vám konzultovat tento další návod:

https://planb.network/tutorials/wallet/recovery-test

## Přijímání bitcoinů na Aqua

Nyní, když je vaše peněženka nastavena, jste připraveni přijmout vaše první satoshi! Stačí kliknout na tlačítko "*Přijmout*" v menu "*Peněženka*".

![AQUA](assets/fr/12.webp)

Můžete si vybrat, zda chcete přijímat bitcoiny onchain, na Liquid, nebo přes Lightning.

![AQUA](assets/fr/13.webp)

Pro onchain transakce Aqua vygeneruje specifickou přijímací adresu, na kterou můžete přijímat vaše satoshi.

![AQUA](assets/fr/14.webp)

Podobně, pokud si vyberete Liquid, Aqua vám poskytne Liquid adresu.

![AQUA](assets/fr/15.webp)

Pokud dáváte přednost přijímání prostředků přes Lightning, nejprve budete muset určit požadovanou částku.

![AQUA](assets/fr/16.webp)

Poté klikněte na "*Generovat fakturu*".

![AQUA](assets/fr/17.webp)
Aqua vytvoří fakturu pro přijetí prostředků z Lightning peněženky. Je důležité si uvědomit, že na rozdíl od onchain a Liquid možností, prostředky přijaté přes Lightning budou automaticky převedeny na L-BTC na Liquid pomocí nástroje Boltz, protože Aqua není Lightning uzlem. Tento proces vám umožní přijímat a odesílat prostředky přes Lightning, ale nikdy neuchovávat vaše bitcoiny na Lightning. ![AQUA](assets/fr/18.webp)

Osobně začnu tím, že pošlu bitcoiny přes Lightning do Aqua. Jakmile je transakce s poskytnutou fakturou dokončena, je přijato potvrzení.

![AQUA](assets/fr/19.webp)

Pro sledování průběhu výměny se vraťte na domovskou stránku vaší peněženky a klikněte na účet "*L2 Bitcoin*", který zobrazuje transakce Lightning (přes swap) a Liquid.

![AQUA](assets/fr/20.webp)

Zde můžete zobrazit vaši transakci i váš zůstatek v L-BTC.

![AQUA](assets/fr/21.webp)

## Výměna bitcoinů s Aqua

Nyní, když máte prostředky ve vaší peněžence Aqua, máte možnost je přímo v aplikaci vyměnit, buď pro převod na hlavní blockchain Bitcoinu nebo na Liquid. Můžete také převést vaše bitcoiny na stablecoin USDT (nebo jiné). K tomu přistupte přes menu "*Marketplace*".

![AQUA](assets/fr/22.webp)

Klikněte na "*Swaps*".

![AQUA](assets/fr/23.webp)

V poli "*Transfer from*" vyberte aktivum, které chcete vyměnit. V současné době mám pouze L-BTC, takže to vyberu.

![AQUA](assets/fr/24.webp)

V poli "*Transfer to*" vyberte cílové aktivum vaší výměny. Z mé strany jsem si vybral USDT na síti Liquid.

![AQUA](assets/fr/25.webp)

Zadejte částku, kterou chcete převést.

![AQUA](assets/fr/26.webp)

Potvrďte kliknutím na "*Continue*".

![AQUA](assets/fr/27.webp)

Ujistěte se, že nastavení výměny jsou podle vašich představ, a poté potvrďte posunutím tlačítka "*Swap*" na spodku obrazovky.

![AQUA](assets/fr/28.webp)

Vaše výměna je nyní potvrzena.

![AQUA](assets/fr/29.webp)

Pokud se vrátíme do naší peněženky, můžeme vidět, že nyní máme USDT na Liquid.

![AQUA](assets/fr/30.webp)

## Odesílání bitcoinů s Aqua

Nyní, když máte bitcoiny ve vaší peněžence Aqua, máte možnost je odeslat. Klikněte na tlačítko "*Send*".

![AQUA](assets/fr/31.webp)

Vyberte aktivum, které chcete odeslat, nebo vyberte síť pro provedení transakce. Z mé strany pošlu bitcoiny přes Lightning.

![AQUA](assets/fr/32.webp)
Dále zadejte potřebné informace pro odeslání platby: pro Bitcoin onchain nebo Liquid potřebujete zadat přijímací adresu; pro Lightning je vyžadována faktura. Tyto informace můžete přímo vložit do určeného pole nebo použít ikonu QR kódu pro otevření kamery a naskenování adresy nebo faktury. Poté klikněte na "*Continue*".
![AQUA](assets/fr/33.webp)

Klikněte znovu na "*Continue*", pokud všechny informace vypadají správně.

![AQUA](assets/fr/34.webp)
Aqua vám poté představí souhrn transakce. Ujistěte se, že jsou všechny informace správné, zejména cílová adresa, poplatky a částka. Pro potvrzení transakce posuňte tlačítko "*Slide to send*" umístěné na spodní části obrazovky.
![AQUA](assets/fr/35.webp)

Poté vám bude poskytnuto potvrzení o odeslání.

![AQUA](assets/fr/36.webp)

A to je vše, nyní víte, jak používat aplikaci Aqua pro přijímání a utrácení prostředků na Bitcoinu, Lightning a Liquid, vše z jednoho rozhraní.

Pokud se vám tento návod líbil, byl bych vděčný, kdybyste mohl nechat palce nahoru níže. Neváhejte tento článek sdílet na svých sociálních sítích. Velmi vám děkuji!

Doporučuji vám také prohlédnout si tento další úplný návod na mobilní aplikaci Blockstream Green, která je dalším zajímavým řešením pro nastavení vaší Liquid peněženky:

https://planb.network/tutorials/wallet/blockstream-green-liquid