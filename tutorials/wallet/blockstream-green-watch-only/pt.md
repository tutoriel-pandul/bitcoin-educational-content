---
name: Blockstream Green - Somente Visualização
description: Configurando uma carteira somente de visualização
---
![cover](assets/cover.webp)

Neste tutorial, você aprenderá como configurar facilmente uma carteira somente de visualização no celular usando o aplicativo Blockstream Green.

## O que é uma Carteira Somente de Visualização?

Uma carteira somente de visualização, ou "watch-only wallet," é um tipo de software projetado para permitir que o usuário observe transações associadas a uma ou mais chaves públicas específicas do Bitcoin, sem ter acesso às chaves privadas correspondentes.

Este tipo de aplicativo retém apenas os dados necessários para monitorar uma carteira Bitcoin, incluindo visualizar seu saldo e histórico de transações, mas não tem acesso às chaves privadas. Portanto, é impossível gastar os bitcoins mantidos na carteira no aplicativo somente de visualização.

![GREEN-WATCH-ONLY](assets/fr/01.webp)

Geralmente, a carteira somente de visualização é usada em adição a uma carteira de hardware. Esta última permite o armazenamento seguro das chaves privadas da carteira em um dispositivo não conectado à internet, que possui uma superfície de ataque mínima, isolando assim as chaves privadas de ambientes potencialmente vulneráveis. O aplicativo somente de visualização, por outro lado, armazena exclusivamente a chave pública estendida (`xpub`, `zpub`, etc.) da carteira Bitcoin. Esta chave-mãe não permite a descoberta das chaves privadas associadas e, consequentemente, não permite o gasto dos bitcoins. No entanto, permite a derivação de chaves públicas filhas e endereços de recebimento. Com o conhecimento dos endereços da carteira protegida pela carteira de hardware, o aplicativo somente de visualização pode rastrear essas transações na rede Bitcoin, oferecendo ao usuário a capacidade de monitorar seu saldo e gerar novos endereços de recebimento, sem ter que conectar sua carteira de hardware todas as vezes.

Neste tutorial, proponho descobrir uma das soluções de carteira somente de visualização mais populares no celular: **Blockstream Green**.

![GREEN-WATCH-ONLY](assets/fr/02.webp)

## Introdução ao Blockstream Green

Blockstream Green é um software disponível em celular e computador. Anteriormente conhecido como Green Address, esta carteira tornou-se um projeto da Blockstream após sua aquisição em 2016.

Green é uma aplicação muito fácil de usar, tornando-a particularmente adequada para iniciantes. Oferece várias funcionalidades, como o gerenciamento de carteiras quentes, carteiras de hardware, bem como carteiras na sidechain Liquid.

Neste tutorial, focaremos exclusivamente na criação de uma carteira somente de visualização. Para explorar outros usos do Green, convido você a consultar nossos outros tutoriais dedicados:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green

## Instalando e Configurando o Aplicativo Blockstream Green
O primeiro passo é naturalmente baixar o aplicativo Green. Vá para a sua loja de aplicativos:
- [Para Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Para Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN-WATCH-ONLY](assets/fr/03.webp)

Para usuários de Android, você também tem a opção de instalar o aplicativo via arquivo `.apk` [disponível no GitHub do Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN-WATCH-ONLY](assets/fr/04.webp)

Lance o aplicativo, então marque a caixa "*Eu aceito os termos...*".

![GREEN-WATCH-ONLY](assets/fr/05.webp)
Quando você abre o Green pela primeira vez, a tela inicial aparece sem uma carteira configurada. Mais tarde, se você criar ou importar carteiras, elas aparecerão nesta interface. Antes de prosseguir para a criação de uma carteira, aconselho que ajuste as configurações do aplicativo de acordo com suas expectativas. Clique em "*Configurações do Aplicativo*".
![GREEN-WATCH-ONLY](assets/fr/06.webp)

A opção "*Privacidade Aprimorada*", disponível apenas no Android, melhora a privacidade desativando capturas de tela e ocultando pré-visualizações do aplicativo. Também bloqueia automaticamente o acesso ao aplicativo assim que seu telefone é bloqueado, tornando seus dados mais difíceis de serem expostos.

![GREEN-WATCH-ONLY](assets/fr/07.webp)

Para aqueles que desejam aprimorar sua privacidade, o aplicativo oferece a opção de rotear seu tráfego através do Tor, uma rede que criptografa todas as suas conexões e torna suas atividades difíceis de rastrear. Embora esta opção possa diminuir ligeiramente o desempenho do aplicativo, é altamente recomendada para proteger sua privacidade, especialmente se você não estiver usando seu próprio nó completo.

![GREEN-WATCH-ONLY](assets/fr/08.webp)

Para usuários que possuem seu próprio nó completo, a Green Wallet oferece a possibilidade de se conectar a ele via um servidor Electrum, garantindo controle total sobre as informações da rede Bitcoin e a transmissão de transações.

![GREEN-WATCH-ONLY](assets/fr/09.webp)

Outra funcionalidade alternativa é a opção "*Verificação SPV*", que permite a verificação direta de certos dados da blockchain, reduzindo a necessidade de confiar no nó padrão da Blockstream, embora este método não ofereça todas as garantias de um nó completo.

![GREEN-WATCH-ONLY](assets/fr/10.webp)

Uma vez que essas configurações estejam ajustadas de acordo com suas necessidades, clique no botão "*Salvar*" e reinicie o aplicativo.

![GREEN-WATCH-ONLY](assets/fr/11.webp)

## Criando uma carteira somente de visualização no Blockstream Green
Agora você está pronto para criar uma carteira somente de visualização. Clique no botão "*Começar*".
![GREEN-WATCH-ONLY](assets/fr/12.webp)

Você terá a escolha entre vários tipos de carteiras. Para este tutorial, queremos criar uma carteira somente de visualização, então clique no botão correspondente.

![GREEN-WATCH-ONLY](assets/fr/13.webp)

Escolha a opção "*Assinatura Única*".

![GREEN-WATCH-ONLY](assets/fr/14.webp)

Em seguida, selecione "*Bitcoin*". Por minha parte, estou conduzindo este tutorial em uma carteira de testnet, mas o procedimento permanece o mesmo na mainnet.

![GREEN-WATCH-ONLY](assets/fr/15.webp)

Será solicitado que você forneça um chave pública estendida (`xpub`, `zpub`, etc.), ou um descritor de script de saída.

![GREEN-WATCH-ONLY](assets/fr/16.webp)

Você precisará recuperar essa informação da carteira que deseja acompanhar através da sua carteira somente de visualização. A chave pública estendida não é sensível em termos de segurança, pois não permite acesso às chaves privadas, mas é sensível para sua privacidade, já que revela todas as suas chaves públicas e, portanto, todas as suas transações Bitcoin.

Imagine que você está usando o Sparrow Wallet para gerenciar sua carteira em uma carteira de hardware, você encontrará essa informação na seção "*Configurações*". Encontrar essa informação dependerá do software de gerenciamento de carteira que você está usando, mas geralmente é encontrado nas configurações.

![GREEN-WATCH-ONLY](assets/fr/17.webp)

Copie sua chave pública estendida e insira-a no aplicativo Green, em seguida, clique em "*Conectar*".

![GREEN-WATCH-ONLY](assets/fr/18.webp)

Você então poderá ver o saldo associado a esta chave, bem como o histórico de transações.
![GREEN-WATCH-ONLY](assets/fr/19.webp)
Ao clicar em "*Receber*", você pode gerar um endereço de recebimento para receber bitcoins na sua carteira de hardware. No entanto, eu aconselho contra o uso desta opção sem antes verificar na tela da carteira de hardware se ela possui a chave privada associada ao endereço gerado, antes de usá-lo para bloquear bitcoins. Esta é uma boa prática a seguir.

![GREEN-WATCH-ONLY](assets/fr/20.webp)

A opção "*Varrer*" permite que você insira manualmente uma chave privada para gastar fundos diretamente da sua aplicação Green. Exceto em casos muito específicos, recomendo não usar esta função, pois ela exige revelar sua chave privada em um telefone, o que é muito mais vulnerável a ataques cibernéticos do que sua carteira de hardware.

![GREEN-WATCH-ONLY](assets/fr/21.webp)
E é isso, agora você sabe como configurar facilmente uma carteira somente de visualização no seu smartphone! É uma ferramenta muito útil para monitorar uma carteira em uma carteira de hardware sem ter que conectá-la e desbloqueá-la toda vez.

Se você achou este tutorial útil, eu ficaria grato se você pudesse deixar um polegar para cima abaixo. Sinta-se livre para compartilhar este artigo nas suas redes sociais. Muito obrigado!

Eu também recomendo conferir este tutorial completo sobre a aplicação Blockstream Green para configurar uma carteira quente:

https://planb.network/tutorials/wallet/blockstream-green