---
name: Blockstream Green - 2FA
description: Nastavení 2/2 multisig na Green Wallet
---
![cover](assets/cover.webp)

Softwarová peněženka je aplikace nainstalovaná na počítači, chytrém telefonu nebo jakémkoli jiném zařízení připojeném k internetu, která umožňuje správu a zabezpečení klíčů Bitcoin peněženky. Na rozdíl od hardwarových peněženek, které izolují privátní klíče, "hot" peněženky tak fungují v prostředí potenciálně vystaveném kybernetickým útokům, což zvyšuje rizika hackování a krádeže.

Softwarové peněženky jsou určeny pro správu rozumných množství bitcoinů, zejména pro denní transakce. Mohou být také zajímavou možností pro lidi s omezeným portfoliem Bitcoinů, pro které může být investice do hardwarové peněženky nepřiměřená. Nicméně jejich neustálá expozice internetu je činí méně bezpečnými pro ukládání vašich dlouhodobých úspor nebo významných fondů. Pro tyto účely je preferováno využití bezpečnějších řešení, jako jsou hardwarové peněženky.

V tomto tutoriálu vám ukážu, jak zvýšit bezpečnost hot peněženky použitím možnosti "2FA" na Blockstream Green.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Úvod do Blockstream Green

Blockstream Green je softwarová peněženka dostupná na mobilních telefonech a desktopu. Původně známá jako *Green Address*, stala se tato peněženka projektem Blockstream po jejím získání v roce 2016.

Green je aplikace, která je obzvláště snadno použitelná, což ji činí zajímavou pro začátečníky. Nabízí všechny základní funkce dobré Bitcoin peněženky, včetně RBF (*Replace-by-Fee*), možnosti připojení přes Tor, schopnosti připojit vlastní uzel, možnost SPV (*Simple Payment Verification*), označování a kontrolu mincí.

Blockstream Green také podporuje Liquid network, Bitcoinovou sidechain vyvinutou Blockstreamem pro provádění rychlých a důvěrných transakcí mimo hlavní blockchain. V tomto tutoriálu se zaměřujeme výhradně na Bitcoin, ale také jsem vytvořil další tutoriál, jak používat Liquid na Green:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## Možnost 2/2 multisig (2FA)

Na Green můžete samozřejmě vytvořit klasickou "singlesig" hot peněženku. Ale máte také možnost "2FA multisig", která vám umožní zlepšit bezpečnost vaší hot peněženky bez zbytečného komplikování jejího každodenního řízení.
Nastavíte tedy 2/2 multisig peněženku, což znamená, že každá transakce bude vyžadovat podpis dvou klíčů. První klíč, odvozený z vaší 12 nebo 24-slovní mnemonické fráze, je zabezpečen lokálně PIN kódem na vašem telefonu. Máte nad tímto klíčem plnou kontrolu. Druhý klíč je držen na serverech Blockstreamu a jeho použití pro podpis vyžaduje autentizaci, která může být dosažena kódem přijatým e-mailem, SMS, telefonním hovorem, nebo, jak uvidíme v tomto tutoriálu, prostřednictvím autentizační aplikace (Authy, Google Authenticator atd.).

Aby byla zajištěna vaše autonomie v případě selhání Blockstreamu (například pokud společnost zbankrotuje nebo servery držící druhý klíč jsou zničeny), je na vaši multisig peněženku aplikován časový zámek. Tento mechanismus transformuje 2/2 multisig na 1/2 multisig po přibližně jednom roce (nebo přesně 51,840 bloků, ale tato hodnota může být změněna), po kterém bude vaše peněženka potřebovat pouze váš lokální klíč k utracení bitcoinů. Takže pokud ztratíte přístup k serverům Blockstreamu nebo k autentizaci 2FA, stačí počkat až rok, abyste mohli své bitcoiny volně používat s vaší aplikací, bez závislosti na Blockstreamu.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
Tato metoda výrazně zvyšuje bezpečnost vaší hot peněženky, zatímco vám umožňuje kontrolovat vaše bitcoiny a usnadňuje jejich každodenní používání. Vyžaduje však pravidelné obnovování časového zámku, aby se udržela bezpečnost 2FA. 360denní odpočet, během kterého jsou vaše prostředky chráněny 2FA, začíná jakmile přijmete bitcoiny. Pokud 360 dní po jejich přijetí neprovedete transakci, která by tyto prostředky utratila, budou vaše bitcoiny chráněny pouze vaším lokálním klíčem, bez 2FA.

Toto omezení činí možnost 2FA vhodnější pro peněženku na výdaje, kde pravidelné transakce automaticky obnovují časové zámky. Pro peněženku na dlouhodobé spoření to může být problematické, protože budete muset myslet na provedení transakce sweep na sebe každý rok před vypršením časového zámku.

Další nevýhodou této bezpečnostní metody je, že budete muset používat minoritní skriptovací vzory. To znamená, že z hlediska soukromí se věci komplikují: velmi málo lidí používá stejný typ skriptu jako vy, což umožňuje vnějšímu pozorovateli snadněji identifikovat stopu vaší peněženky. Navíc tyto skripty budou mít za následek vyšší transakční poplatky kvůli jejich větší velikosti.
Pokud dáváte přednost nevyužívání možnosti 2FA a jednoduše chcete nastavit peněženku "singlesig" na Green, doporučuji se podívat na tento další tutoriál:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Instalace a nastavení softwaru Blockstream Green

Prvním krokem je samozřejmě stáhnout aplikaci Green. Přejděte do obchodu s aplikacemi:
- [Pro Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Pro Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

Uživatelé Androidu mají také možnost nainstalovat aplikaci prostřednictvím souboru `.apk` [dostupného na GitHubu Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Spusťte aplikaci, poté zaškrtněte políčko "*Souhlasím s podmínkami...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Když otevřete Green poprvé, objeví se domovská obrazovka bez nakonfigurované peněženky. Později, pokud vytvoříte nebo importujete peněženky, objeví se v tomto rozhraní. Před přechodem k vytvoření peněženky doporučuji upravit nastavení aplikace podle vašich očekávání. Klikněte na "*Nastavení aplikace*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

Možnost "*Zvýšené soukromí*", dostupná pouze pro Android, zlepšuje soukromí zakázáním snímků obrazovky a skrytím náhledů aplikace. Také automaticky zamyká přístup k aplikaci, jakmile je váš telefon zamčen, což činí vaše data obtížněji přístupná.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

Pro ty, kteří si přejí zvýšit své soukromí, aplikace nabízí možnost směrovat váš provoz přes Tor, síť, která šifruje všechna vaše připojení a činí vaše aktivity obtížně sledovatelnými. Ačkoli tato možnost může mírně zpomalit výkon aplikace, je vysoce doporučena k ochraně vašeho soukromí, zejména pokud nepoužíváte vlastní full node.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

Pro uživatele, kteří mají vlastní full node, nabízí Green Wallet možnost připojení k němu prostřednictvím serveru Electrum, což zajišťuje plnou kontrolu nad informacemi Bitcoinové sítě a vysíláním transakcí.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
Další alternativní funkcí je možnost "*SPV ověření*", která umožňuje přímé ověření určitých dat blockchainu, čímž se snižuje potřeba důvěřovat výchozímu uzlu Blockstream, ačkoli tato metoda neposkytuje všechny záruky plného uzlu.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Jakmile jsou tyto nastavení upravena podle vašich potřeb, klikněte na tlačítko "*Uložit*" a restartujte aplikaci.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Vytvoření Bitcoinové peněženky na Blockstream Green

Nyní jste připraveni vytvořit Bitcoinovou peněženku. Klikněte na tlačítko "*Začít*".

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Máte na výběr mezi vytvořením softwarové peněženky lokálně nebo správou studené peněženky prostřednictvím hardwarové peněženky. V tomto návodu se zaměříme na vytvoření hot peněženky, takže budete muset vybrat možnost "*Na tomto zařízení*".

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Dále můžete vybrat obnovu stávající Bitcoinové peněženky nebo vytvoření nové. Pro účely tohoto návodu vytvoříme novou peněženku. Pokud však potřebujete regenerovat stávající Bitcoinovou peněženku z její mnemonické fráze, například kvůli ztrátě starého telefonu, budete muset vybrat druhou možnost.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Poté máte na výběr mezi 12-slovnou nebo 24-slovnou mnemonickou frází. Tato fráze vám umožní obnovit přístup k vaší peněžence z jakéhokoli kompatibilního softwaru v případě problémů s vaším telefonem. V současné době volba 24-slovné fráze nenabízí větší zabezpečení než 12-slovná fráze. Proto doporučuji vybrat **12-slovnou** mnemonickou frázi.

Green vám poté poskytne vaši mnemonickou frázi. Před pokračováním se ujistěte, že vás nikdo nepozoruje. Klikněte na "*Zobrazit obnovovací frázi*", aby se zobrazila na obrazovce.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**Tato mnemonická fráze dává úplný a neomezený přístup ke všem vašim bitcoinům**. Každý, kdo je v držení této fráze, může vaše prostředky ukrást, i bez fyzického přístupu k vašemu telefonu (za podmínek vypršení časového zámku nebo 2FA v případě 2/2 peněženky na Green).

Umožňuje vám obnovit přístup k vašim lokálním klíčům v případě ztráty, krádeže nebo poškození vašeho telefonu. Je proto velmi důležité ji pečlivě uložit **na fyzickém médiu (nikoli digitálním)** a uložit ji na bezpečném místě. Můžete si ji zapsat na kus papíru, nebo pro větší zabezpečení, pokud je tato peněženka důležitá, doporučuji ji vyryt na nerezovém médiu, aby byla chráněna před riziky požárů, záplav nebo kolapsů (pro hot peněženku určenou k zajištění malého množství bitcoinů je pravděpodobně dostatečná jednoduchá papírová záloha).
*Samozřejmě byste tyto slova nikdy neměli sdílet na internetu, na rozdíl od toho, co dělám v tomto návodu. Tato ukázková peněženka bude použita pouze na Testnetu a na konci návodu bude smazána.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Po správném zaznamenání vaší mnemonické fráze na fyzické médium klikněte na "*Pokračovat*". Green Wallet vás poté požádá o potvrzení některých slov z vaší fráze, aby ověřil, že jste je zaznamenali správně. Doplňte chybějící slova do prázdných míst.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Vyberte si PIN kód pro vaše zařízení, který bude použit k odemčení vaší Green peněženky. Jedná se tedy o ochranu proti neautorizovanému fyzickému přístupu. Tento PIN kód nehraje roli v odvození kryptografických klíčů vaší peněženky. Takže i bez přístupu k tomuto PIN kódu vám vlastnictví vaší 12 nebo 24-slovné mnemonické fráze umožní znovu získat přístup k vašim lokálním klíčům.
Doporučuje se vybrat 6-místný PIN kód co nejvíce náhodně. Také se ujistěte, že si tento kód uložíte, abyste na něj nezapomněli, jinak budete nuceni obnovit vaši peněženku z mnemonické fráze. Později můžete přidat možnost biometrického zámku, abyste nemuseli pokaždé zadávat PIN. Obecně řečeno, biometrie je mnohem méně bezpečná než samotný PIN. Proto ve výchozím nastavení nedoporučuji nastavit tuto možnost odemknutí.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Zadejte svůj PIN podruhé pro jeho potvrzení.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Počkejte, až bude vaše peněženka vytvořena, poté klikněte na tlačítko "*Vytvořit účet*".

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Poté máte na výběr mezi standardní peněženkou s jedním podpisem nebo peněženkou chráněnou dvoufaktorovou autentizací (2FA). V tomto tutoriálu si vybereme druhou možnost.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

A to je vše, váš Bitcoin multisig účet byl úspěšně vytvořen pomocí aplikace Green!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Nastavení 2FA

Klikněte na svůj účet.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Klikněte na zelené tlačítko "*Zvýšit bezpečnost vašeho účtu přidáním 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Poté budete mít možnost vybrat metodu autentizace pro přístup k druhému klíči vašeho 2/2 multisig. V tomto tutoriálu použijeme autentizační aplikaci. Pokud nejste s tímto typem aplikace obeznámeni, doporučuji konzultovat náš tutoriál o Authy:
https://planb.network/tutorials/others/authy

Vyberte "*Aplikace pro autentizaci*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

Green poté zobrazí QR kód a obnovovací klíč. Tento klíč umožňuje obnovit přístup k vašemu 2FA v případě, že ztratíte aplikaci Authy. Doporučuje se udělat bezpečnou zálohu tohoto klíče, i když vždy můžete znovu získat přístup k vašim bitcoinům po vypršení časového zámku, jak bylo vysvětleno dříve.

Ve vaší autentizační aplikaci přidejte nový kód, poté naskenujte QR kód poskytnutý Green.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Samozřejmě byste nikdy neměli sdílet tento klíč a QR kód na internetu, na rozdíl od toho, co dělám v tomto tutoriálu. Tento příkladový účet bude použit pouze na Testnetu a na konci tutoriálu bude smazán.*

Klikněte na tlačítko "*Pokračovat*".

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Zadejte dynamický 6-místný kód, který se zobrazuje ve vaší autentizační aplikaci.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

Dvoufaktorová autentizace je nyní povolena.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Procházením tohoto menu můžete také upravit dobu trvání časového zámku. Tento odpočet začíná po přijetí bitcoinů a jakmile časový zámek vyprší, vaše prostředky lze utratit pouze s vaším lokálním klíčem, bez nutnosti 2FA. Výchozí doba trvání je nastavena na 12 měsíců, ale pro spořicí peněženku může být rozumné zvolit 15 měsíců, aby se minimalizovala frekvence obnov časového zámku. Naopak pro peněženku na výdaje může být preferován časový zámek 6 měsíců, protože bude často obnovován s vašimi denními transakcemi a kratší časový zámek snižuje čekání v případě problémů s 2FA. Je na vás, abyste určili dobu trvání časového zámku, která vám nejlépe vyhovuje.
![GREEN 2FA MULTISIG](assets/fr/30.webp)

Nyní můžete toto menu opustit. Vaše multisig peněženka je připravena!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Nastavení vaší peněženky na Blockstream Green

Pokud si přejete přizpůsobit svou peněženku, klikněte na tři malé tečky v pravém horním rohu.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
Možnost "*Přejmenovat*" vám umožní přizpůsobit název vaší peněženky, což je obzvláště užitečné, pokud spravujete více peněženek ve stejné aplikaci.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

Menu "*Jednotka*" vám dává možnost změnit základní jednotku vaší peněženky. Například si můžete zvolit zobrazení v satoshi místo v bitcoinech.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

Menu "*Nastavení*" poskytuje přístup k různým možnostem vaší Bitcoinové peněženky.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Zde například najdete váš rozšířený veřejný klíč a jeho *descriptor*, což je užitečné, pokud plánujete nastavit sledovací peněženku z této peněženky.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

Můžete také změnit PIN kód vaší peněženky a povolit biometrické přihlášení.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Používání Blockstream Green

Nyní, když je vaše Bitcoinová peněženka nastavena, jste připraveni přijmout své první satoshi! Stačí kliknout na tlačítko "*Přijmout*".

![GREEN 2FA MULTISIG](assets/fr/38.webp)

Green poté zobrazí první prázdnou přijímací adresu vaší peněženky. Můžete buď naskenovat přidružený QR kód, nebo adresu přímo zkopírovat, abyste na ni poslali bitcoiny. Tento typ adresy nespecifikuje částku, která má být odesílatelem zaslána. Nicméně můžete vygenerovat adresu, která požaduje konkrétní částku, kliknutím na tři malé tečky v pravém horním rohu, poté na "*Požádat o částku*", a zadáním požadované částky.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Když je transakce vysílána do sítě, objeví se ve vaší peněžence.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Počkejte, až dostanete dostatečný počet potvrzení, abyste mohli transakci považovat za konečnou.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

S bitcoiny ve vaší peněžence nyní můžete také posílat. Klikněte na "*Poslat*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

Na následující stránce zadejte adresu příjemce. Můžete ji zadat ručně nebo naskenovat QR kód.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Vyberte částku platby.
![GREEN 2FA MULTISIG](assets/fr/44.webp) Na spodní části obrazovky můžete vybrat sazbu poplatku za tuto transakci. Máte možnost řídit se doporučeními aplikace nebo si poplatky přizpůsobit. Čím vyšší jsou poplatky ve srovnání s ostatními čekajícími transakcemi, tím rychleji bude vaše transakce zpracována. Pro pochopení trhu s poplatky můžete navštívit [Mempool.space](https://mempool.space/) v sekci "*Poplatky za transakce*".
![GREEN 2FA MULTISIG](assets/fr/45.webp)

Klikněte na "*Další*", abyste přistoupili k souhrnné obrazovce vaší transakce. Ověřte, že adresa, částka a poplatky jsou správné.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Pokud je vše v pořádku, posuňte zelené tlačítko na spodní části obrazovky doprava, abyste transakci podepsali a vysílali na síť Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

V tomto okamžiku musíte zadat svůj ověřovací kód, abyste odemkli druhý klíč multisigu držený Blockstreamem. Zadejte 6místný kód zobrazený ve vaší ověřovací aplikaci.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Vaše transakce se nyní objeví na palubní desce vaší Bitcoin peněženky a čeká na potvrzení.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

A to je vše, nyní víte, jak snadno nastavit 2/2 multisig peněženku s využitím možnosti 2FA od Blockstream Green!

Pokud se vám tento návod zdál užitečný, ocenil bych, kdybyste níže zanechali zelený palec. Neváhejte tento článek sdílet na svých sociálních sítích. Velmi vám děkuji!

Doporučuji také zkontrolovat tento další úplný návod na mobilní aplikaci Blockstream Green pro nastavení Liquid peněženky:

https://planb.network/tutorials/wallet/blockstream-green-liquid