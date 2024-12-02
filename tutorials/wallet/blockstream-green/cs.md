---
name: Blockstream Green - Mobilní
description: Nastavení mobilní softwarové peněženky
---
![cover](assets/cover.webp)

Softwarová peněženka je aplikace instalovaná na počítači, chytrém telefonu nebo jakémkoli jiném zařízení připojeném k internetu, která umožňuje správu a zabezpečení klíčů Bitcoin peněženky. Na rozdíl od hardwarových peněženek, které izolují soukromé klíče, "hot" peněženky tak fungují v prostředí potenciálně vystaveném kybernetickým útokům, což zvyšuje rizika hackování a krádeže.

Softwarové peněženky jsou určeny pro správu rozumných množství bitcoinů, zejména pro denní transakce. To může být také zajímavá možnost pro lidi s omezeným portfoliem Bitcoinů, pro které může být investice do hardwarové peněženky nepřiměřená. Nicméně jejich neustálé vystavení internetu je činí méně bezpečnými pro ukládání vašich dlouhodobých úspor nebo významných fondů. Pro tyto účely je vhodnější volit bezpečnější řešení, jako jsou hardwarové peněženky.

V tomto tutoriálu vám představím jedno z nejlepších řešení mobilní softwarové peněženky: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Pokud máte zájem dozvědět se, jak používat Blockstream Green na počítači, prosím, odkazujte na tento další tutoriál:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Úvod do Blockstream Green

Blockstream Green je softwarová peněženka dostupná jak na mobilních zařízeních, tak na počítači. Původně známá jako *Green Address*, tato peněženka se stala projektem Blockstream po jejím akvizici v roce 2016.

Green je aplikace, která je obzvláště snadno použitelná, což ji činí zajímavou pro začátečníky. Nabízí všechny základní funkce dobré Bitcoin peněženky, včetně RBF (*Replace-by-Fee*), možnosti připojení přes Tor, schopnosti připojit vlastní uzel, možnosti SPV (*Simple Payment Verification*), označování a kontroly mincí.

Blockstream Green také podporuje síť Liquid, Bitcoinovou sidechain vyvinutou Blockstreamem pro provádění rychlých a důvěrných transakcí mimo hlavní blockchain. Tento tutoriál se zaměřuje výhradně na Bitcoin, ale budoucí se bude zabývat používáním Liquid.

## Instalace a nastavení aplikace Blockstream Green

Prvním krokem je samozřejmě stáhnout aplikaci Green. Přejděte do svého obchodu s aplikacemi:
- [Pro Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Pro Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Uživatelé Androidu mají také možnost instalovat aplikaci prostřednictvím souboru `.apk` [dostupného na GitHubu Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Spusťte aplikaci, poté zaškrtněte políčko "*Souhlasím s podmínkami...*".
![GREEN](assets/fr/04.webp)

Když otevřete Green poprvé, objeví se domovská obrazovka bez jakýchkoli nakonfigurovaných peněženek. Později, pokud vytvoříte nebo importujete peněženky, objeví se v tomto rozhraní. Než přejdete k vytvoření peněženky, doporučuji vám upravit nastavení aplikace podle vašich očekávání. Klikněte na "*Nastavení aplikace*".

![GREEN](assets/fr/05.webp)

Možnost "*Vylepšené soukromí*", dostupná pouze na Androidu, zlepšuje soukromí zakázáním snímání obrazovky a skrytím náhledů aplikace. Také automaticky zablokuje přístup k aplikaci, jakmile je váš telefon zamčen, což činí vaše data obtížněji přístupná.

![GREEN](assets/fr/06.webp)
Pro ty, kteří si přejí zvýšit své soukromí, aplikace nabízí možnost směrovat váš provoz přes Tor, síť, která šifruje všechna vaše připojení a činí vaše aktivity obtížně sledovatelnými. Ačkoli tato možnost může mírně zpomalit výkon aplikace, je vysoce doporučeno chránit vaše soukromí, zejména pokud nepoužíváte vlastní úplný uzel.
![GREEN](assets/fr/07.webp)

Pro uživatele, kteří mají svůj vlastní úplný uzel, Green Wallet nabízí možnost připojit se k němu přes Electrum server, čímž zajišťuje plnou kontrolu nad informacemi Bitcoinové sítě a vysíláním transakcí.

![GREEN](assets/fr/08.webp)

Další alternativní funkcí je možnost "*SPV ověření*", která umožňuje přímé ověření určitých dat blockchainu, čímž se snižuje potřeba důvěřovat výchozímu uzlu Blockstream, ačkoli tato metoda neposkytuje všechny záruky úplného uzlu.

![GREEN](assets/fr/09.webp)

Jakmile jsou tyto nastavení upravena podle vašich potřeb, klikněte na tlačítko "*Uložit*" a restartujte aplikaci.

![GREEN](assets/fr/10.webp)

## Vytvoření Bitcoinové peněženky na Blockstream Green

Nyní jste připraveni vytvořit Bitcoinovou peněženku. Klikněte na tlačítko "*Začít*".

![GREEN](assets/fr/11.webp)

Máte na výběr mezi vytvořením softwarové peněženky lokálně nebo správou studené peněženky prostřednictvím hardwarové peněženky. V tomto tutoriálu se zaměříme na vytvoření hot peněženky, takže budete muset vybrat možnost "*Na tomto zařízení*". V budoucím tutoriálu vám ukážu, jak použít druhou možnost.

Možnost "*Pouze pro sledování*", na druhou stranu, vám umožňuje importovat rozšířený veřejný klíč (`xpub`) pro zobrazení transakcí peněženky bez možnosti utrácet přidružené prostředky, což je vhodné pro sledování peněženky na hardwarové peněžence, například.

![GREEN](assets/fr/12.webp)
Poté můžete zvolit obnovu stávající Bitcoinové peněženky nebo vytvoření nové. Pro účely tohoto tutoriálu vytvoříme novou peněženku. Pokud však potřebujete znovu vygenerovat již existující Bitcoinovou peněženku z její mnemonické fráze, například kvůli ztrátě vaší hardwarové peněženky, budete muset vybrat druhou možnost.
![GREEN](assets/fr/13.webp)

Poté máte na výběr mezi 12-slovnou nebo 24-slovnou mnemonickou frází. Tato fráze vám umožní obnovit přístup k vaší peněžence z jakéhokoli kompatibilního softwaru v případě problémů s vaším telefonem. V současné době volba 24-slovné fráze nenabízí více zabezpečení než 12-slovná fráze. Proto doporučuji zvolit **12-slovnou** mnemonickou frázi.

Green vám poté poskytne vaši mnemonickou frázi. Před pokračováním se ujistěte, že vás nikdo nepozoruje. Klikněte na "*Zobrazit obnovovací frázi*", aby se zobrazila na obrazovce.

![GREEN](assets/fr/14.webp)

**Tato mnemonická fráze poskytuje plný a neomezený přístup ke všem vašim bitcoinům.** Každý, kdo je v držení této fráze, může ukrást vaše prostředky, i bez fyzického přístupu k vašemu telefonu.

Umožňuje vám obnovit přístup k vašim bitcoinům v případě ztráty, krádeže nebo poškození vašeho telefonu. Je proto velmi důležité pečlivě ji uložit **na fyzickém médiu (nikoli digitálním)** a uložit ji na bezpečném místě. Můžete si ji zapsat na kus papíru, nebo pro větší bezpečnost, pokud je tato peněženka důležitá, doporučuji ji vyryt na nerezové médium, aby byla chráněna před riziky požárů, záplav nebo zřícení (pro hot peněženku určenou k zajištění malého množství bitcoinů, pravděpodobně postačí jednoduchá papírová záloha).
*Samozřejmě byste nikdy neměli sdílet tyto slova na internetu, na rozdíl od toho, co dělám v tomto tutoriálu. Tato ukázková peněženka bude použita pouze na Testnetu a na konci tutoriálu bude smazána.*
![GREEN](assets/fr/15.webp)

Po správném zaznamenání vaší mnemonické fráze na fyzické médium klikněte na "*Pokračovat*". Green Wallet vás poté požádá o potvrzení určitých slov z vaší fráze, aby ověřil, že jste je zaznamenali správně. Doplňte chybějící slova do prázdných polí.

![GREEN](assets/fr/16.webp)

Vyberte si PIN kód pro vaše zařízení, který bude použit k odemčení vaší Green peněženky. Jedná se tedy o ochranu proti neautorizovanému fyzickému přístupu. Tento PIN kód nehraje roli v odvození kryptografických klíčů vaší peněženky. Tedy, i bez přístupu k tomuto PIN kódu, vlastnictví vaší 12 nebo 24-slovní mnemonické fráze vám umožní znovu získat přístup k vašim bitcoinům.
Doporučuje se vybrat 6-místný PIN, který je co nejvíce náhodný. Také se ujistěte, že si tento kód zazálohujete, abyste na něj nezapomněli, jinak budete nuceni obnovit vaši peněženku pomocí mnemonické fráze. Následně můžete přidat možnost biometrického zámku, aby se předešlo zadávání PINu při každém použití. Obecně platí, že biometrie je mnohem méně bezpečná než samotný PIN. Proto ve výchozím nastavení nedoporučuji nastavit tuto možnost odemknutí.
![GREEN](assets/fr/17.webp)

Zadejte svůj PIN podruhé pro jeho potvrzení.

![GREEN](assets/fr/18.webp)

Počkejte, až bude vaše peněženka vytvořena, a poté klikněte na tlačítko "*Vytvořit účet*".

![GREEN](assets/fr/19.webp)

Poté máte na výběr mezi standardní peněženkou s jedním podpisem, kterou budeme v tomto tutoriálu používat, nebo peněženkou chráněnou dvoufaktorovým ověřením (2FA).

![GREEN](assets/fr/20.webp)

Možnost 2FA na Green vytváří peněženku s více podpisy 2/2, přičemž jeden klíč je uchováván společností Blockstream. To znamená, že pro provedení transakce jsou vyžadovány oba klíče: lokální klíč chráněný vaším PINem na telefonu a vzdálený klíč zabezpečený 2FA na serverech Blockstream. V případě ztráty přístupu k 2FA nebo nedostupnosti služeb Blockstream, mechanismy obnovy založené na skriptech s časovým zámkem zajišťují možnost samostatné obnovy vašich prostředků. Ačkoli toto nastavení výrazně snižuje riziko krádeže vašich bitcoinů, je složitější na správu a částečně závisí na Blockstream. Pro tento tutoriál si vybereme klasickou peněženku s jedním podpisem, s klíči uloženými lokálně na telefonu.

A máte to, vaše Bitcoin peněženka byla úspěšně vytvořena pomocí aplikace Green!

![GREEN](assets/fr/21.webp)

Před přijetím vašich prvních bitcoinů do vaší peněženky, **důrazně doporučuji provést test suchého běhu obnovy**. Zapište si referenční informaci, jako je váš xpub nebo první přijímací adresa, poté smažte vaši peněženku v aplikaci Green, zatímco je ještě prázdná. Poté se pokuste obnovit vaši peněženku na Green pomocí vašich papírových záloh. Zkontrolujte, zda informace svědka vygenerované po obnově odpovídají té, kterou jste si původně zaznamenali. Pokud tomu tak je, můžete být ujištěni, že vaše papírové zálohy jsou spolehlivé. Chcete-li se dozvědět více o tom, jak provést test obnovy, doporučuji vám konzultovat tento další tutoriál:

https://planb.network/tutorials/wallet/recovery-test

## Nastavení vaší peněženky na Blockstream Green
Pokud chcete přizpůsobit své portfolio, klikněte na tři malé tečky v pravém horním rohu.
![GREEN](assets/fr/22.webp)
Možnost "*Přejmenovat*" vám umožňuje přizpůsobit název vašeho portfolia, což je obzvláště užitečné, pokud spravujete více portfolií ve stejné aplikaci.
![GREEN](assets/fr/23.webp)

Menu "*Jednotka*" vám dává možnost změnit základní jednotku vašeho portfolia. Například si můžete vybrat zobrazení v satoshi místo v bitcoinech.

![GREEN](assets/fr/24.webp)

Menu "*Nastavení*" poskytuje přístup k různým možnostem vaší Bitcoinové peněženky.

![GREEN](assets/fr/25.webp)

Zde například najdete váš rozšířený veřejný klíč a jeho *descriptor*, což je užitečné, pokud plánujete nastavit sledovací peněženku z této peněženky.

![GREEN](assets/fr/26.webp)

Můžete také změnit PIN kód vaší peněženky a povolit biometrické přihlášení.

![GREEN](assets/fr/27.webp)

## Používání Blockstream Green

Nyní, když je vaše Bitcoinová peněženka nastavena, jste připraveni přijmout své první satoshi! Stačí kliknout na tlačítko "*Přijmout*".

![GREEN](assets/fr/28.webp)

Green poté zobrazí první prázdnou přijímací adresu vaší peněženky. Můžete buď naskenovat přidružený QR kód, nebo adresu přímo zkopírovat, abyste na ni poslali bitcoiny. Tento typ adresy nespecifikuje částku, která má být odesílatelem zaslána. Nicméně, můžete vygenerovat adresu, která požaduje konkrétní částku, kliknutím na tři malé tečky v pravém horním rohu, poté na "*Požádat o částku*", a zadáním požadované částky.

Protože používáte účet Segwit v0 (BIP84), vaše adresa začne s `bc1q...`. V mém příkladu používám peněženku Testnet, takže prefix je mírně odlišný.

![GREEN](assets/fr/29.webp)

Když je transakce vysílána do sítě, objeví se ve vaší peněžence.

![GREEN](assets/fr/30.webp)

Počkejte, až dostanete dostatečný počet potvrzení, abyste mohli transakci považovat za konečnou.

![GREEN](assets/fr/31.webp)

S bitcoiny ve vaší peněžence nyní můžete také posílat. Klikněte na "*Poslat*".

![GREEN](assets/fr/32.webp)

Na další stránce zadejte adresu příjemce. Můžete ji zadat ručně nebo naskenovat QR kód.

![GREEN](assets/fr/33.webp)

Vyberte částku platby.

![GREEN](assets/fr/34.webp)
V dolní části obrazovky můžete vybrat sazbu poplatku za tuto transakci. Máte možnost následovat doporučení aplikace nebo si poplatky přizpůsobit. Čím vyšší jsou poplatky ve srovnání s ostatními čekajícími transakcemi, tím rychleji bude vaše transakce zpracována. Pro pochopení trhu s poplatky můžete navštívit [Mempool.space](https://mempool.space/) v sekci "*Poplatky za transakce*".
![GREEN](assets/fr/35.webp)

Klikněte na "*Další*", abyste přistoupili k souhrnné obrazovce vaší transakce. Ověřte, že adresa, částka a poplatky jsou správné.

![GREEN](assets/fr/36.webp)

Pokud je vše podle vašich představ, posuňte zelené tlačítko v dolní části obrazovky doprava, abyste transakci podepsali a vysílali do Bitcoinové sítě.

![GREEN](assets/fr/37.webp)

Vaše transakce se nyní objeví na palubní desce vaší Bitcoinové peněženky čekající na potvrzení.

![GREEN](assets/fr/38.webp)
*Tento tutoriál je založen na [původní verzi od Bitstack](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) napsané Loïcem Morelem. Bitstack je francouzská Bitcoin neo-banka, která nabízí možnost spoření v bitcoinech, a to buď prostřednictvím DCA (Dollar Cost Averaging) nebo prostřednictvím automatického zaokrouhlování denních výdajů.*