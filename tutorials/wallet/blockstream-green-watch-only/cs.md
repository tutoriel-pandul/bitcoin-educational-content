---
name: Blockstream Green - Pouze pro sledování
description: Nastavení peněženky pouze pro sledování
---
![cover](assets/cover.webp)

V tomto tutoriálu se naučíte, jak snadno nastavit peněženku pouze pro sledování na mobilu pomocí aplikace Blockstream Green.

## Co je peněženka pouze pro sledování?

Peněženka pouze pro sledování, nebo "watch-only wallet", je typ softwaru navržený tak, aby umožnil uživateli sledovat transakce spojené s jedním nebo více konkrétními veřejnými klíči Bitcoinu, aniž by měl přístup k odpovídajícím soukromým klíčům.

Tento typ aplikace uchovává pouze data nezbytná pro monitorování Bitcoinové peněženky, včetně zobrazení jejího zůstatku a historie transakcí, ale nemá přístup k soukromým klíčům. Proto je nemožné utratit bitcoiny držené v peněžence v aplikaci pouze pro sledování.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Peněženka pouze pro sledování je obvykle používána v doplňku k hardwarové peněžence. Ta umožňuje bezpečné uchování soukromých klíčů peněženky na zařízení nepřipojeném k internetu, které má minimální útokovou plochu, čímž izoluje soukromé klíče od potenciálně zranitelných prostředí. Aplikace pouze pro sledování na druhé straně výhradně uchovává rozšířený veřejný klíč (`xpub`, `zpub` atd.) Bitcoinové peněženky. Tento rodičovský klíč neumožňuje odhalení přidružených soukromých klíčů a tedy neumožňuje utrácení bitcoinů. Nicméně umožňuje odvození dceřinných veřejných klíčů a přijímacích adres. S vědomím adres peněženky zabezpečené hardwarovou peněženkou může aplikace pouze pro sledování sledovat tyto transakce na Bitcoinové síti, což uživateli nabízí možnost sledovat jejich zůstatek a generovat nové přijímací adresy, aniž by musel každé připojovat svou hardwarovou peněženku.

V tomto tutoriálu navrhuji objevit jedno z nejpopulárnějších řešení peněženky pouze pro sledování na mobilu: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Úvod do Blockstream Green

Blockstream Green je software dostupný na mobilu a počítači. Dříve známý jako Green Address, tato peněženka se stala projektem Blockstream po jeho akvizici v roce 2016.

Green je velmi snadno použitelná aplikace, což ji činí obzvláště vhodnou pro začátečníky. Nabízí různé funkce, jako je správa hotovostních peněženek, hardwarových peněženek, stejně jako peněženek na Liquid sidechainu.

V tomto tutoriálu se zaměříme výhradně na vytvoření peněženky pouze pro sledování. Prozkoumání dalších využití Green vás zvu, abyste si prohlédli naše další specializované tutoriály:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Instalace a nastavení aplikace Blockstream Green
Prvním krokem je samozřejmě stáhnout aplikaci Green. Přejděte do svého obchodu s aplikacemi:
- [Pro Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Pro Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Uživatelé Androidu mají také možnost nainstalovat aplikaci prostřednictvím souboru `.apk` [dostupného na GitHubu Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Spusťte aplikaci, poté zaškrtněte políčko "*Souhlasím s podmínkami...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Když otevřete Green poprvé, objeví se domovská obrazovka bez nakonfigurované peněženky. Později, pokud vytvoříte nebo importujete peněženky, objeví se v tomto rozhraní. Předtím, než přejdete k vytvoření peněženky, doporučuji vám upravit nastavení aplikace podle vašich očekávání. Klikněte na "*Nastavení aplikace*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

Možnost "*Zvýšené soukromí*", dostupná pouze na Androidu, zlepšuje soukromí zakázáním snímání obrazovky a skrytím náhledů aplikace. Také automaticky uzamkne přístup k aplikaci, jakmile je váš telefon zamčen, což činí vaše data obtížněji přístupná.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Pro ty, kteří si přejí zvýšit své soukromí, aplikace nabízí směrování vašeho provozu přes Tor, síť, která šifruje všechna vaše připojení a činí vaše aktivity obtížně sledovatelnými. Ačkoli tato možnost může mírně zpomalit výkon aplikace, je vysoce doporučena k ochraně vašeho soukromí, zejména pokud nepoužíváte vlastní úplný uzel.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Pro uživatele, kteří mají svůj vlastní úplný uzel, Green Wallet nabízí možnost připojit se k němu přes Electrum server, což zajišťuje plnou kontrolu nad informacemi Bitcoinové sítě a vysíláním transakcí.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Další alternativní funkcí je možnost "*SPV ověření*", která umožňuje přímé ověření určitých dat blockchainu, čímž se snižuje potřeba důvěřovat výchozímu uzlu Blockstream, ačkoli tato metoda neposkytuje všechny záruky úplného uzlu.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Jakmile jsou tyto nastavení upravena podle vašich potřeb, klikněte na tlačítko "*Uložit*" a restartujte aplikaci.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Vytvoření watch-only peněženky na Blockstream Green
Nyní jste připraveni vytvořit watch-only peněženku. Klikněte na tlačítko "*Začít*".
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Budete mít na výběr z několika typů peněženek. Pro tento návod chceme vytvořit watch-only peněženku, takže klikněte na příslušné tlačítko.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Vyberte možnost "*Jednoduchý podpis*".

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Poté vyberte "*Bitcoin*". Z mé strany provádím tento návod na testnet peněžence, ale postup zůstává stejný na hlavní síti.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Budete požádáni o poskytnutí buď rozšířeného veřejného klíče (`xpub`, `zpub` atd.), nebo deskriptoru výstupního skriptu.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Tuto informaci budete muset získat z peněženky, kterou chcete sledovat prostřednictvím vaší watch-only peněženky. Rozšířený veřejný klíč není citlivý z hlediska bezpečnosti, protože neumožňuje přístup k soukromým klíčům, ale je citlivý pro vaše soukromí, protože odhaluje všechny vaše veřejné klíče a tedy všechny vaše Bitcoinové transakce.

Představte si, že používáte Sparrow Wallet pro správu vaší peněženky na hardwarové peněžence, tuto informaci najdete v sekci "*Nastavení*". Nalezení této informace bude záviset na softwaru pro správu peněženky, který používáte, ale obvykle se nachází v nastavení.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Zkopírujte svůj rozšířený veřejný klíč a zadejte ho do aplikace Green, poté klikněte na "*Připojit*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Poté budete moci vidět zůstatek spojený s tímto klíčem, stejně jako historii transakcí.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Kliknutím na "*Přijmout*" můžete vygenerovat přijímací adresu pro přijetí bitcoinů na vaší hardwarové peněžence. Doporučuji však tuto možnost nepoužívat, aniž byste nejprve ověřili na displeji hardwarové peněženky, že drží soukromý klíč spojený s vygenerovanou adresou, než ji použijete k uzamčení bitcoinů. To je dobrá praxe, kterou byste měli dodržovat.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

Možnost "*Sweep*" vám umožňuje ručně zadat soukromý klíč pro přímé utrácení prostředků přímo z vaší aplikace Green. Kromě velmi specifických případů nedoporučuji tuto funkci používat, protože vyžaduje odhalení vašeho soukromého klíče na telefonu, což je mnohem více zranitelné vůči kybernetickým útokům než vaše hardwarová peněženka.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
A máte to, nyní víte, jak snadno nastavit peněženku pouze pro sledování na vašem smartphonu! Je to velmi praktický nástroj pro monitorování peněženky na hardwarové peněžence bez nutnosti ji pokaždé připojovat a odemykat.

Pokud se vám tento návod líbil, ocenil bych, kdybyste níže zanechali palec nahoru. Neváhejte tento článek sdílet na vašich sociálních sítích. Velmi vám děkuji!

Doporučuji také prohlédnout si tento kompletní návod na aplikaci Blockstream Green pro nastavení hot peněženky:

https://planb.network/tutorials/wallet/blockstream-green