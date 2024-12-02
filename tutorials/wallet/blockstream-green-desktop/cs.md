---
name: Blockstream Green - Desktop
description: Používání softwaru Green Wallet na počítači
---
![cover](assets/cover.webp)

V tomto tutoriálu prozkoumáme, jak používat software Blockstream Green na počítači pro správu bezpečné peněženky na hardwarové peněžence. Při používání hardwarové peněženky je nezbytné používat software na vašem počítači pro správu této peněženky. Tento správcovský software nemá přístup k privátním klíčům; slouží pouze k ověření zůstatku vaší peněženky, generování přijímacích adres a sestavování a vysílání transakcí, které budou podepsány hardwarovou peněženkou. Green představuje jedno z mnoha dostupných řešení pro správu vaší Bitcoin hardwarové peněženky.

V roce 2024 je Blockstream Green kompatibilní pouze s zařízeními Ledger Nano S (starší verze), Ledger Nano X, Trezor One, Trezor T a Blockstream Jade.

## Úvod do Blockstream Green

Blockstream Green je software dostupný jak pro mobilní zařízení, tak pro desktop. Dříve známý jako Green Address, tento peněženka se stala projektem Blockstream po jeho akvizici v roce 2016.

Green je velmi uživatelsky přívětivá aplikace, což ji činí obzvláště vhodnou pro začátečníky. Nabízí různé funkce, jako je správa hot peněženek, hardwarových peněženek, stejně jako peněženek na Liquid sidechainu. Můžete jej také použít k nastavení peněženky pouze pro sledování.

![GREEN-DESKTOP](assets/fr/01.webp)

V tomto tutoriálu se zaměříme výhradně na používání softwaru na počítači. Prozkoumání dalších využití Green vás zvu, abyste se podívali na naše další specializované tutoriály:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Instalace a nastavení softwaru Blockstream Green

Začněte instalací softwaru Blockstream Green na váš počítač. Přejděte na [oficiální webové stránky](https://blockstream.com/green/) a klikněte na tlačítko "*Download Now*". Poté postupujte podle instalačního procesu podle vašeho operačního systému.

![GREEN-DESKTOP](assets/fr/02.webp)

Spusťte aplikaci, poté zaškrtněte políčko "*I accept the terms...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Když otevřete Green poprvé, objeví se úvodní obrazovka bez jakékoli nakonfigurované peněženky. Později, pokud vytvoříte nebo importujete peněženky, objeví se v tomto rozhraní. Než přejdete k vytvoření peněženky, doporučuji vám upravit nastavení aplikace podle vašich očekávání. Klikněte na ikonu nastavení vlevo dole.

![GREEN-DESKTOP](assets/fr/04.webp)

V menu "*General*" můžete změnit jazyk softwaru a povolit experimentální funkce, pokud si to přejete.

![GREEN-DESKTOP](assets/fr/05.webp)
V menu "*Network*" můžete povolit připojení přes Tor, síť, která šifruje všechna vaše připojení a činí vaše aktivity obtížně sledovatelnými. Ačkoli tato možnost může mírně zpomalit výkon aplikace, je vysoce doporučena k ochraně vašeho soukromí, zejména pokud nepoužíváte vlastní full node.
![GREEN-DESKTOP](assets/fr/06.webp)

Pro uživatele, kteří mají vlastní full node, Green nabízí možnost připojit se k němu přes Electrum server, což zajišťuje plnou kontrolu nad informacemi Bitcoinové sítě a vysíláním transakcí. K tomu klikněte na menu "*Custom servers and validation*" a poté zadejte informace o vašem Electrum serveru.

![GREEN-DESKTOP](assets/fr/07.webp)
Další alternativní funkcí je možnost "*SPV ověření*", která umožňuje přímé ověření určitých dat blockchainu, čímž se snižuje potřeba důvěřovat výchozímu uzlu Blockstream, ačkoli tato metoda neposkytuje všechny záruky plného uzlu. Tato možnost se také nachází v menu "*Vlastní servery a ověřování*".
![GREEN-DESKTOP](assets/fr/08.webp)

Po přizpůsobení těchto nastavení podle vašich potřeb můžete toto rozhraní opustit.

## Import peněženky Bitcoin do Blockstream Green

Nyní jste připraveni importovat vaši Bitcoin peněženku. Klikněte na tlačítko "**Začínáme**".

![GREEN-DESKTOP](assets/fr/09.webp)

Máte na výběr mezi vytvořením lokální softwarové peněženky nebo správou studené peněženky prostřednictvím hardwarové peněženky. V tomto návodu se zaměříme na správu hardwarové peněženky, takže budete muset vybrat možnost "*Na hardwarové peněžence*".

Na druhou stranu, možnost "*Pouze pro sledování*" vám umožňuje importovat rozšířený veřejný klíč (`xpub`) pro zobrazení transakcí peněženky bez možnosti utrácet přidružené prostředky.

![GREEN-DESKTOP](assets/fr/10.webp)

Pokud používáte Jade, klikněte na příslušné tlačítko. V opačném případě vyberte "*Připojit jiné hardwarové zařízení*". V mém případě používám Ledger Nano S. Uživatelé Ledgeru by měli na své hardwarové peněžence nainstalovat aplikaci "*Bitcoin Legacy*", protože Green podporuje pouze tuto verzi.

![GREEN-DESKTOP](assets/fr/11.webp)

Připojte svou hardwarovou peněženku k počítači a vyberte ji v Green.

![GREEN-DESKTOP](assets/fr/12.webp)

Počkejte, až Green importuje informace z vaší peněženky, poté k ní budete mít přístup.

![GREEN-DESKTOP](assets/fr/13.webp)

V tomto bodě jsou možné dva scénáře. Pokud jste svou hardwarovou peněženku již dříve používali, měli byste na softwaru vidět svůj účet. Ale pokud, jako já, jste právě inicializovali svou hardwarovou peněženku generováním mnemonické fráze bez jejího dosavadního použití, budete muset vytvořit účet. Klikněte na "*Vytvořit účet*".
![GREEN-DESKTOP](assets/fr/14.webp)
Vyberte "*Standardní*", pokud si přejete použít klasickou peněženku.

![GREEN-DESKTOP](assets/fr/15.webp)

Nyní máte přístup ke svému účtu.

![GREEN-DESKTOP](assets/fr/16.webp)

## Používání hardwarové peněženky s Blockstream Green

Nyní, když je vaše Bitcoin peněženka nastavena, jste připraveni přijmout vaše první satoshi! Stačí kliknout na tlačítko "*Přijmout*".

![GREEN-DESKTOP](assets/fr/17.webp)

Klikněte na tlačítko "*Kopírovat adresu*", abyste zkopírovali adresu, nebo naskenujte její QR kód.

![GREEN-DESKTOP](assets/fr/18.webp)

Jakmile je transakce odeslána do sítě, objeví se ve vaší peněžence. Počkejte, až dostanete dostatečný počet potvrzení, abyste mohli transakci považovat za neměnnou.

![GREEN-DESKTOP](assets/fr/19.webp)

S bitcoiny ve vaší peněžence nyní můžete posílat. Klikněte na tlačítko "*Poslat*".

![GREEN-DESKTOP](assets/fr/20.webp)

Na následující stránce zadejte adresu příjemce. Můžete ji zadat ručně nebo naskenovat QR kód pomocí webové kamery.

![GREEN-DESKTOP](assets/fr/21.webp)

Vyberte částku platby.

![GREEN-DESKTOP](assets/fr/22.webp)
Na spodní části obrazovky můžete vybrat sazbu poplatku pro tuto transakci. Máte možnost následovat doporučení aplikace nebo si poplatky přizpůsobit. Čím vyšší jsou poplatky ve srovnání s ostatními čekajícími transakcemi, tím rychleji bude vaše transakce zpracována. Pro informace o trhu s poplatky můžete navštívit [Mempool.space](https://mempool.space/) v sekci "*Poplatky za transakce*".
![GREEN-DESKTOP](assets/fr/23.webp)

Pokud si přejete specificky vybrat, které UTXO použít ve vaší transakci, klikněte na tlačítko "*Ruční výběr mincí*".

![GREEN-DESKTOP](assets/fr/24.webp)

Zkontrolujte nastavení vaší transakce a pokud je vše podle vašich očekávání, klikněte na "*Další*".

![GREEN-DESKTOP](assets/fr/25.webp)

Ještě jednou ověřte, že adresa, částka a poplatky jsou správné, poté klikněte na "*Potvrdit transakci*".

![GREEN-DESKTOP](assets/fr/26.webp)

Ujistěte se, že všechny parametry transakce jsou správné na obrazovce vaší hardwarové peněženky, poté transakci podepište pomocí ní.

![GREEN-DESKTOP](assets/fr/27.webp)

Jakmile je transakce podepsána z hardwarové peněženky, Green ji automaticky vysílá do sítě Bitcoin. Vaše transakce se poté objeví na přehledu vaší Bitcoin peněženky, čekajíc na potvrzení.

![GREEN-DESKTOP](assets/fr/28.webp)

A to je vše, nyní víte, jak snadno nastavit software Blockstream Green pro správu vaší Bitcoin peněženky na hardwarové peněžence.
Pokud se vám tento návod líbil, byl bych vděčný, kdybyste níže zanechali palec nahoru. Neváhejte tento článek sdílet na vašich sociálních sítích. Moc vám děkuji!
Doporučuji také zkontrolovat tento kompletní návod na mobilní aplikaci Blockstream Green pro nastavení hot peněženky:

https://planb.network/tutorials/wallet/blockstream-green