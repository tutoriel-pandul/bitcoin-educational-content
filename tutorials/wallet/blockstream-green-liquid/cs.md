---
name: Blockstream Green - Liquid
description: Nastavení peněženky na vedlejším řetězci Liquid Network
---
![cover](assets/cover.webp)
Protokol Bitcoinu má záměrné technické omezení, které pomáhá udržovat decentralizaci sítě a zajišťuje rozdělení bezpečnosti mezi všechny uživatele. Nicméně, tato omezení mohou někdy uživatele frustrovat, zejména během přetížení způsobeného vysokým objemem současných transakcí. Debata o škálovatelnosti Bitcoinu dlouho rozdělovala komunitu, zejména během tzv. Blocksize War. Od té doby je v komunitě Bitcoinu široce uznáváno, že škálovatelnost musí být zajištěna pomocí řešení mimo hlavní řetěz, na systémech druhé vrstvy. Mezi tato řešení patří vedlejší řetězce, které jsou stále relativně neznámé a málo využívané ve srovnání s jinými systémy, jako je Lightning Network.

Vedlejší řetězec je nezávislý blockchain, který funguje paralelně s hlavním blockchainem Bitcoinu. Používá bitcoin jako jednotku účtu prostřednictvím mechanismu nazývaného "*two-way peg*". Tento systém umožňuje uzamknout bitcoiny na hlavním řetězci a replikovat jejich hodnotu na vedlejším řetězci, kde cirkulují jako tokeny podložené původními bitcoiny. Tyto tokeny obvykle udržují hodnotovou paritu s bitcoiny uzamčenými na hlavním řetězci, a proces lze obrátit pro získání prostředků zpět na Bitcoin.

Cílem vedlejších řetězců je nabídnout dodatečné funkcionality nebo technická vylepšení, jako jsou rychlejší transakce, snížené poplatky nebo podpora pro smart kontrakty. Tyto inovace nemohou být vždy přímo implementovány na blockchainu Bitcoinu bez ohrožení jeho decentralizace nebo bezpečnosti. Vedlejší řetězce tak umožňují testování a prozkoumávání nových řešení při zachování integrity Bitcoinu. Nicméně, tyto protokoly často vyžadují kompromisy, zejména z hlediska decentralizace a bezpečnosti, v závislosti na zvoleném modelu správy a mechanismu konsensu.

Dnes je pravděpodobně nejznámějším vedlejším řetězcem Liquid. V tomto tutoriálu vás nejprve seznámím s tím, co je Liquid, a poté vás provedu, jak jej snadno začít používat prostřednictvím aplikace Blockstream Green, abyste mohli využít jeho výhod.

![LIQUID GREEN](assets/fr/01.webp)

## Co je Liquid Network?

Liquid je federovaný vedlejší řetězec postavený na Bitcoinu, vyvinutý společností Blockstream, s cílem zlepšit rychlost, soukromí a funkcionality transakcí. Používá bilaterální mechanismus ukotvení založený na federaci pro uzamčení bitcoinů na hlavním řetězci a vytvoření, v návratu, Liquid-bitcoinů (L-BTC), tokenů cirkulujících na Liquidu, zatímco zůstávají podložené původními bitcoiny.

![LIQUID GREEN](assets/fr/02.webp)
Síť Liquid je založena na federaci účastníků, která se skládá z uznávaných entit z ekosystému Bitcoinu, kteří validují bloky a spravují bilaterální ukotvení. Kromě L-BTC umožňuje Liquid také vydávání dalších digitálních aktiv, jako jsou stablecoiny nebo jiné kryptoměny.
![LIQUID GREEN](assets/fr/03.webp)

## Úvod do Blockstream Green

Blockstream Green je softwarová peněženka dostupná na mobilních telefonech a desktopu. Dříve známá jako *Green Address*, tato peněženka se stala projektem Blockstream po jejím akvizici v roce 2016.

Green je aplikace, která je obzvláště snadno použitelná, což ji činí zajímavou pro začátečníky. Nabízí všechny základní funkce dobré Bitcoin peněženky, včetně RBF (*Replace-by-Fee*), možnosti připojení přes Tor, schopnosti připojit vlastní uzel, možnosti SPV (*Simple Payment Verification*), označování a kontrolu mincí.

Blockstream Green také podporuje síť Liquid, a to je to, co budeme v tomto tutoriálu prozkoumávat. Pokud si přejete používat Green pro jiné aplikace, doporučuji také konzultovat tyto další tutoriály:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Instalace a nastavení aplikace Blockstream Green

Prvním krokem je samozřejmě stáhnout aplikaci Green. Přejděte do obchodu s aplikacemi:
- [Pro Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Pro Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Uživatelé Androidu mají také možnost nainstalovat aplikaci prostřednictvím souboru `.apk` [dostupného na GitHubu Blockstream](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Spusťte aplikaci a zaškrtněte políčko "*Souhlasím s podmínkami...*".

![LIQUID GREEN](assets/fr/06.webp)

Když otevřete Green poprvé, objeví se úvodní obrazovka bez nakonfigurovaných peněženek. Později, pokud vytvoříte nebo importujete peněženky, objeví se v tomto rozhraní. Než přejdete k vytvoření peněženky, doporučuji upravit nastavení aplikace podle vašich očekávání. Klikněte na "*Nastavení aplikace*".

![LIQUID GREEN](assets/fr/07.webp)

Možnost "*Vylepšené soukromí*", dostupná pouze pro Android, zlepšuje soukromí zakázáním snímků obrazovky a skrytím náhledů aplikace. Také automaticky zamyká přístup k aplikaci, jakmile je váš telefon zamčen, což vaše data činí obtížněji přístupná.
![LIQUID GREEN](assets/fr/08.webp)
Pro ty, kteří chtějí zvýšit své soukromí, aplikace nabízí možnost směrovat váš provoz přes Tor, síť, která šifruje všechna vaše připojení a činí vaše aktivity obtížně sledovatelnými. Ačkoli tato možnost může mírně zpomalit výkon aplikace, je vysoce doporučena pro ochranu vašeho soukromí, zejména pokud nepoužíváte vlastní full node.

![LIQUID GREEN](assets/fr/09.webp)

Pro uživatele, kteří mají vlastní full node, Green Wallet umožňuje připojení k němu prostřednictvím serveru Electrum, čímž zajišťuje plnou kontrolu nad informacemi Bitcoinové sítě a vysíláním transakcí. Tato funkce je však relevantní pro tradiční Bitcoinové peněženky, takže ji nepotřebujete, pokud používáte Liquid.

![LIQUID GREEN](assets/fr/10.webp)

Další alternativní funkcí je možnost "*SPV ověření*", která umožňuje přímé ověření určitých dat blockchainu, čímž se snižuje potřeba důvěřovat výchozímu uzlu Blockstream, ačkoli tato metoda neposkytuje všechna zajištění full node. Opět se to týká pouze vašich onchain Bitcoinových peněženek, nikoli Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Jakmile jsou tyto nastavení upravena podle vašich potřeb, klikněte na tlačítko "*Uložit*" a restartujte aplikaci.

![LIQUID GREEN](assets/fr/12.webp)

## Vytvoření Liquid peněženky na Blockstream Green

Nyní jste připraveni vytvořit Liquid peněženku. Klikněte na tlačítko "*Začít*".

![LIQUID GREEN](assets/fr/13.webp)

Máte na výběr mezi vytvořením softwarové peněženky lokálně nebo správou cold peněženky prostřednictvím hardwarové peněženky. V tomto návodu se zaměříme na vytvoření hot peněženky na Liquid, takže budete muset vybrat možnost "*Na tomto zařízení*". Můžete také použít kompatibilní hardwarovou peněženku, jako je Blockstream Jade, pro zabezpečení vaší Liquid peněženky.

![LIQUID GREEN](assets/fr/14.webp)
Poté můžete zvolit obnovu stávající Bitcoinové peněženky nebo vytvoření nové. Pro účely tohoto návodu vytvoříme novou peněženku. Pokud však potřebujete regenerovat existující Liquid peněženku z její mnemonické fráze, například kvůli ztrátě vaší hardwarové peněženky, budete muset zvolit druhou možnost.
![LIQUID GREEN](assets/fr/15.webp)

Poté máte na výběr mezi 12-slovnou nebo 24-slovnou mnemonickou frází. Tato fráze vám umožní obnovit přístup k vaší peněžence z jakéhokoli kompatibilního softwaru v případě problémů s vaším telefonem. V současné době volba 24-slovné fráze nenabízí větší zabezpečení než 12-slovná fráze. Proto doporučuji zvolit **12-slovnou** mnemonickou frázi.
Green vám poté poskytne vaši mnemonickou frázi. Před pokračováním se ujistěte, že vás nikdo nepozoruje. Klikněte na "*Zobrazit obnovovací frázi*", aby se zobrazila na obrazovce.
![LIQUID GREEN](assets/fr/16.webp)

**Tato mnemonická fráze dává plný a neomezený přístup ke všem vašim bitcoinům.** Každý, kdo je v držení této fráze, může vaše prostředky ukrást, i bez fyzického přístupu k vašemu telefonu.

Umožňuje vám obnovit přístup k vašim bitcoinům v případě ztráty, krádeže nebo poškození vašeho telefonu. Proto je velmi důležité ji pečlivě uložit **na fyzickém médiu (nikoli digitálním)** a uchovávat ji na bezpečném místě. Můžete si ji zapsat na kus papíru, nebo pro větší zabezpečení, pokud je tato peněženka významná, doporučuji vyrytí na nerezovém médiu, aby byla chráněna před riziky požárů, záplav nebo zřícení (pro hot peněženku určenou k zabezpečení malého množství bitcoinů je pravděpodobně dostatečná jednoduchá papírová záloha).

*Samozřejmě byste tyto slova nikdy neměli sdílet na internetu, na rozdíl od toho, co dělám v tomto návodu. Tato ukázková peněženka bude použita pouze na Liquid Testnetu a na konci návodu bude smazána.*

![LIQUID GREEN](assets/fr/17.webp)

Po správném zaznamenání vaší mnemonické fráze na fyzické médium klikněte na "*Pokračovat*". Green Wallet vás poté požádá o potvrzení některých slov z vaší fráze, aby ověřil, že jste je zaznamenali správně. Doplňte chybějící slova.

![LIQUID GREEN](assets/fr/18.webp)

Zvolte PIN kód pro vaše zařízení, který bude použit k odemčení vaší Green peněženky. Jedná se tedy o ochranu proti neoprávněnému fyzickému přístupu. Tento PIN kód nehraje roli v derivaci kryptografických klíčů vaší peněženky. Tedy i bez přístupu k tomuto PIN kódu umožní držení vaší 12 nebo 24-slovné mnemonické fráze znovu získat přístup k vašim bitcoinům.

Doporučuje se zvolit 6-místný PIN kód co nejvíce náhodný. Také se ujistěte, že si tento kód uložíte, abyste na něj nezapomněli, jinak budete nuceni obnovit vaši peněženku z mnemonické fráze. Později můžete přidat možnost biometrického zámku, abyste nemuseli PIN zadávat pokaždé, když jej používáte. Obecně platí, že biometrie je mnohem méně bezpečná než samotný PIN. Proto ve výchozím nastavení nedoporučuji nastavit tuto možnost odemykání.

![LIQUID GREEN](assets/fr/19.webp)

Zadejte svůj PIN podruhé pro jeho potvrzení.

![LIQUID GREEN](assets/fr/20.webp)
Počkejte, až bude vaše peněženka vytvořena, a poté klikněte na tlačítko "*Vytvořit účet*".
![LIQUID GREEN](assets/fr/21.webp)
V poli "*Assets*" vyberte "*Liquid Bitcoin*". Poté máte na výběr mezi standardní peněženkou s jedním podpisem, kterou v tomto tutoriálu použijeme, nebo peněženkou chráněnou dvoufaktorovou autentizací (2FA).
![LIQUID GREEN](assets/fr/22.webp)

A máte to, váš Liquid peněženka byla úspěšně vytvořena pomocí aplikace Green!

![LIQUID GREEN](assets/fr/23.webp)

Před přijetím vašich prvních bitcoinů na vaší Liquid peněžence, **důrazně vám doporučuji provést test prázdné obnovy**. Zapište si referenční informaci, jako je váš xpub nebo první přijímací adresa, poté smažte vaši peněženku v aplikaci Green, zatímco je ještě prázdná. Poté zkuste obnovit vaši peněženku v Green pomocí vašich papírových záloh. Zkontrolujte, že informace svědka vygenerované po obnově odpovídají té, kterou jste si původně zapsali. Pokud ano, můžete být ujištěni, že vaše papírové zálohy jsou spolehlivé. Chcete-li se dozvědět více o tom, jak provést test obnovy, doporučuji vám konzultovat tento další tutoriál:

https://planb.network/tutorials/wallet/recovery-test

## Nastavení vaší Liquid peněženky

Pokud si přejete přizpůsobit vaši peněženku, klikněte na tři malé tečky v pravém horním rohu.

![LIQUID GREEN](assets/fr/24.webp)

Možnost "*Rename*" vám umožňuje přizpůsobit název vaší peněženky, což je obzvláště užitečné, pokud spravujete více peněženek ve stejné aplikaci.

![LIQUID GREEN](assets/fr/25.webp)

Menu "*Unit*" vám dává možnost změnit základní jednotku vaší peněženky. Například si můžete vybrat zobrazení v satoshi místo v bitcoinech.

![LIQUID GREEN](assets/fr/26.webp)

Menu "*Settings*" poskytuje přístup k různým možnostem vaší Bitcoin peněženky.

![LIQUID GREEN](assets/fr/27.webp)

Zde například najdete váš *descriptor*, který může být užitečný, pokud plánujete nastavit sledovací peněženku z této Liquid peněženky.

![LIQUID GREEN](assets/fr/28.webp)

Můžete také změnit PIN kód vaší peněženky a povolit biometrické přihlášení.

![LIQUID GREEN](assets/fr/29.webp)

## Používání vaší Liquid peněženky

Nyní, když je vaše Liquid peněženka nastavena, jste připraveni přijmout vaše první L-saty!
Pokud ještě nevlastníte L-BTC, máte k dispozici několik možností. První je nechat si je přímo poslat. Pokud vám někdo chce zaplatit v bitcoinech na Liquid, jednoduše mu dejte přijímací adresu. Další možností je vyměnit vaše onchain bitcoiny nebo ty na síti Lightning za L-BTC. K tomu můžete použít [most jako je Boltz](https://boltz.exchange/). Stačí zadat vaši Liquid adresu na webu, a poté provést platbu buď přes síť Lightning nebo onchain.
![LIQUID GREEN](assets/fr/30.webp)

Pro generování Liquid adresy klikněte na tlačítko "*Receive*".

![LIQUID GREEN](assets/fr/31.webp)

Green poté zobrazí první prázdnou přijímací adresu vaší peněženky. Můžete buď naskenovat přidružený QR kód nebo přímo zkopírovat adresu, aby na ni bylo možné poslat L-BTC.

![LIQUID GREEN](assets/fr/32.webp)

Když je transakce vysílána do sítě, objeví se ve vaší peněžence.

![LIQUID GREEN](assets/fr/33.webp)

Počkejte, až dostanete dostatečný počet potvrzení, abyste mohli transakci považovat za konečnou. Na Liquid by potvrzení měla být rychlá, protože blok je publikován každou minutu.

![LIQUID GREEN](assets/fr/34.webp)
S L-saty ve vaší Liquid peněžence je nyní můžete také posílat. Klikněte na "*Odeslat*".
![LIQUID GREEN](assets/fr/35.webp)

Na další stránce zadejte Liquid adresu příjemce. Můžete ji zadat ručně nebo naskenovat jejich QR kód.

![LIQUID GREEN](assets/fr/36.webp)

Vyberte částku platby.

![LIQUID GREEN](assets/fr/37.webp)

Klikněte na "*Další*", abyste přistoupili k souhrnné obrazovce vaší transakce. Zkontrolujte, zda jsou adresa, částka a poplatky správné.

![LIQUID GREEN](assets/fr/38.webp)

Pokud vám všechno připadá v pořádku, posuňte zelené tlačítko na spodku obrazovky doprava, abyste transakci podepsali a vysílali na Bitcoinovou síť.

![LIQUID GREEN](assets/fr/39.webp)

Vaše transakce se nyní zobrazí na přehledové stránce vaší Bitcoinové peněženky a čeká na potvrzení.

![LIQUID GREEN](assets/fr/40.webp)

A to je vše, nyní víte, jak snadno používat Liquid sidechain s aplikací Blockstream Green!

Pokud se vám tento návod líbil, ocenil bych, kdybyste níže dali palec nahoru. Neváhejte tento článek sdílet na svých sociálních sítích. Moc vám děkuji!

Doporučuji také objevit tento další úplný návod na mobilní aplikaci Blockstream Green pro nastavení onchain Bitcoinové hot peněženky:

https://planb.network/tutorials/wallet/blockstream-green