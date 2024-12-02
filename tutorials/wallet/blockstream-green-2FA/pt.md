---
name: Blockstream Green - 2FA
description: Configurando um multisig 2/2 na Carteira Green
---
![cover](assets/cover.webp)

Uma carteira de software é um aplicativo instalado em um computador, smartphone ou qualquer outro dispositivo conectado à Internet, permitindo o gerenciamento e a segurança das chaves da carteira Bitcoin. Diferentemente das carteiras de hardware, que isolam as chaves privadas, as carteiras "quentes" operam em um ambiente potencialmente exposto a ciberataques, aumentando os riscos de hacking e roubo.

Carteiras de software devem ser usadas para gerenciar quantidades razoáveis de bitcoins, especialmente para transações diárias. Isso também pode ser uma opção interessante para pessoas com um portfólio limitado de Bitcoin, para quem investir em uma carteira de hardware pode parecer desproporcional. No entanto, sua constante exposição à Internet as torna menos seguras para armazenar suas economias de longo prazo ou fundos significativos. Para estes, é preferível optar por soluções mais seguras, como carteiras de hardware.

Neste tutorial, vou mostrar como aumentar a segurança de uma carteira quente usando a opção "2FA" no Blockstream Green.

![GREEN 2FA MULTISIG](assets/fr/01.webp)

## Introdução ao Blockstream Green

Blockstream Green é uma carteira de software disponível para dispositivos móveis e desktop. Anteriormente conhecida como *Green Address*, essa carteira tornou-se um projeto da Blockstream após sua aquisição em 2016.

Green é um aplicativo particularmente fácil de usar, tornando-o interessante para iniciantes. Oferece todas as características essenciais de uma boa carteira Bitcoin, incluindo RBF (*Replace-by-Fee*), uma opção para conectar via Tor, a capacidade de conectar o próprio nó, a opção SPV (*Simple Payment Verification*), rotulagem e controle de moedas.

O Blockstream Green também suporta a rede Liquid, uma sidechain do Bitcoin desenvolvida pela Blockstream para realizar transações rápidas e confidenciais fora da blockchain principal. Neste tutorial, focamos exclusivamente no Bitcoin, mas também fiz outro tutorial para aprender a usar o Liquid no Green:

https://planb.network/tutorials/wallet/blockstream-green-liquid

## A opção multisig 2/2 (2FA)

No Green, você pode certamente criar uma carteira quente "singlesig" clássica. Mas você também tem a opção "2FA multisig", que permite melhorar a segurança da sua carteira quente sem complicar excessivamente seu gerenciamento diário.
Você configurará, portanto, uma carteira multisig 2/2, o que significa que cada transação exigirá a assinatura de duas chaves. A primeira chave, derivada da sua frase mnemônica de 12 ou 24 palavras, é protegida localmente com um código PIN no seu telefone. Você tem controle total sobre esta chave. A segunda chave é mantida pelos servidores da Blockstream, e seu uso para assinatura requer autenticação, que pode ser alcançada via um código recebido por email, SMS, chamada telefônica ou, como veremos neste tutorial, via um aplicativo de autenticação (Authy, Google Authenticator, etc.).

Para garantir sua autonomia no caso de uma falha da Blockstream (por exemplo, se a empresa falir ou os servidores que mantêm a segunda chave forem destruídos), um mecanismo de timelock é aplicado ao seu multisig. Esse mecanismo transforma o multisig 2/2 em um multisig 1/2 após cerca de um ano (ou precisamente 51.840 blocos, mas esse valor pode ser alterado), após o qual sua carteira só precisará de sua chave local para gastar os bitcoins. Assim, se você perder o acesso aos servidores da Blockstream ou à autenticação 2FA, basta esperar até um ano para poder usar livremente seus bitcoins com seu aplicativo, sem depender da Blockstream.
![GREEN 2FA MULTISIG](assets/fr/02.webp)
Este método aumenta significativamente a segurança da sua carteira quente, enquanto mantém você no controle dos seus bitcoins e facilita o uso diário. No entanto, requer a atualização regular do timelock para manter a segurança do 2FA. A contagem regressiva de 360 dias, durante a qual seus fundos são protegidos pelo 2FA, começa assim que você recebe bitcoins. Se, 360 dias após recebê-los, você não tiver feito uma transação gastando esses fundos, seus bitcoins serão protegidos apenas pela sua chave local, sem o 2FA.

Essa restrição torna a opção de 2FA mais adequada para uma carteira de gastos, onde transações regulares renovam automaticamente os timelocks. Para uma carteira de poupança de longo prazo, isso pode ser problemático, pois você precisará pensar em realizar uma transação de varredura para si mesmo a cada ano antes que o timelock expire.

Outra desvantagem deste método de segurança é que você precisará usar padrões de script minoritários. Isso significa que, do ponto de vista da privacidade, as coisas se complicam: muito poucas pessoas usam o mesmo tipo de script que você, permitindo que um observador externo identifique mais facilmente a pegada da sua carteira. Além disso, esses scripts resultarão em taxas de transação mais altas devido ao seu maior tamanho.
Se você preferir não usar a opção de 2FA e simplesmente quiser configurar uma carteira "singlesig" no Green, convido você a conferir este outro tutorial:
https://planb.network/tutorials/wallet/blockstream-green-liquid

## Instalando e Configurando o Software Blockstream Green

O primeiro passo é naturalmente baixar o aplicativo Green. Vá à sua loja de aplicativos:
- [Para Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Para Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN 2FA MULTISIG](assets/fr/03.webp)

Para usuários de Android, você também tem a opção de instalar o aplicativo via arquivo `.apk` [disponível no GitHub do Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN 2FA MULTISIG](assets/fr/04.webp)

Lance o aplicativo, depois marque a caixa "*Eu aceito os termos...*".

![GREEN 2FA MULTISIG](assets/fr/05.webp)

Quando você abrir o Green pela primeira vez, a tela inicial aparece sem nenhuma carteira configurada. Mais tarde, se você criar ou importar carteiras, elas aparecerão nesta interface. Antes de prosseguir para a criação de uma carteira, aconselho você a ajustar as configurações do aplicativo de acordo com suas expectativas. Clique em "*Configurações do Aplicativo*".

![GREEN 2FA MULTISIG](assets/fr/06.webp)

A opção "*Privacidade Aprimorada*", disponível apenas no Android, melhora a privacidade desativando capturas de tela e ocultando pré-visualizações do aplicativo. Também bloqueia automaticamente o acesso ao aplicativo assim que seu telefone é bloqueado, tornando seus dados mais difíceis de serem expostos.

![GREEN 2FA MULTISIG](assets/fr/07.webp)

Para aqueles que desejam aprimorar sua privacidade, o aplicativo oferece a opção de rotear seu tráfego através do Tor, uma rede que criptografa todas as suas conexões e torna suas atividades difíceis de rastrear. Embora esta opção possa diminuir um pouco o desempenho do aplicativo, é altamente recomendada para proteger sua privacidade, especialmente se você não estiver usando seu próprio nó completo.

![GREEN 2FA MULTISIG](assets/fr/08.webp)

Para usuários que possuem seu próprio nó completo, a Carteira Green oferece a possibilidade de se conectar a ele via um servidor Electrum, garantindo controle total sobre as informações da rede Bitcoin e a transmissão de transações.
![GREEN 2FA MULTISIG](assets/fr/09.webp)
Outra funcionalidade alternativa é a opção de "*Verificação SPV*", que permite a verificação direta de certos dados da blockchain, reduzindo assim a necessidade de confiar no nó padrão da Blockstream, embora este método não ofereça todas as garantias de um nó completo.
![GREEN 2FA MULTISIG](assets/fr/10.webp)
Uma vez que essas configurações estejam ajustadas de acordo com suas necessidades, clique no botão "*Salvar*" e reinicie o aplicativo.

![GREEN 2FA MULTISIG](assets/fr/11.webp)

## Criando uma Carteira Bitcoin na Blockstream Green

Você está agora pronto para criar uma carteira Bitcoin. Clique no botão "*Começar*".

![GREEN 2FA MULTISIG](assets/fr/12.webp)

Você tem a escolha entre criar uma carteira de software localmente ou gerenciar uma carteira fria por meio de uma carteira de hardware. Para este tutorial, focaremos em criar uma carteira quente, então você precisará selecionar a opção "*Neste Dispositivo*".

![GREEN 2FA MULTISIG](assets/fr/13.webp)

Em seguida, você pode escolher restaurar uma carteira Bitcoin existente ou criar uma nova. Para os propósitos deste tutorial, criaremos uma nova carteira. No entanto, se você precisar regenerar uma carteira Bitcoin existente a partir de sua frase mnemônica, por exemplo, devido à perda do seu antigo telefone, você precisará escolher a segunda opção.

![GREEN 2FA MULTISIG](assets/fr/14.webp)

Você então tem a escolha entre uma frase mnemônica de 12 palavras ou de 24 palavras. Esta frase permitirá que você recupere o acesso à sua carteira de qualquer software compatível em caso de problemas com seu telefone. Atualmente, optar por uma frase de 24 palavras não oferece mais segurança do que uma frase de 12 palavras. Portanto, recomendo escolher uma frase mnemônica de **12 palavras**.

A Green fornecerá então sua frase mnemônica. Antes de continuar, certifique-se de não estar sendo observado. Clique em "*Mostrar frase de recuperação*" para exibi-la na tela.

![GREEN 2FA MULTISIG](assets/fr/15.webp)

**Esta frase mnemônica dá acesso completo e irrestrito a todos os seus bitcoins**. Qualquer pessoa em posse desta frase pode roubar seus fundos, mesmo sem acesso físico ao seu telefone (sob condições de timelock expirado ou 2FA no caso de uma carteira 2/2 na Green).

Ela permite que você restaure o acesso às suas chaves locais em caso de perda, roubo ou dano ao seu telefone. Portanto, é muito importante salvá-la cuidadosamente **em um meio físico (não digital)** e armazená-la em um local seguro. Você pode anotá-la em um pedaço de papel, ou, para mais segurança, se esta carteira for importante, recomendo gravá-la em um meio de aço inoxidável para proteger contra os riscos de incêndios, inundações ou desabamentos (para uma carteira quente destinada a garantir uma pequena quantidade de bitcoins, um simples backup em papel provavelmente é suficiente).
*Obviamente, você nunca deve compartilhar essas palavras na internet, ao contrário do que estou fazendo neste tutorial. Esta carteira de exemplo será usada apenas no Testnet e será deletada ao final do tutorial.*
![GREEN 2FA MULTISIG](assets/fr/16.webp)

Após anotar corretamente sua frase mnemônica em um meio físico, clique em "*Continuar*". A Carteira Green então pedirá que você confirme algumas palavras de sua frase para verificar se você as registrou corretamente. Preencha os espaços em branco com as palavras que faltam.

![GREEN 2FA MULTISIG](assets/fr/17.webp)
Escolha o código PIN para o seu dispositivo, que será usado para desbloquear sua carteira Green. Portanto, é uma proteção contra o acesso físico não autorizado. Este código PIN não desempenha um papel na derivação das chaves criptográficas da sua carteira. Assim, mesmo sem acesso a este código PIN, a posse da sua frase mnemônica de 12 ou 24 palavras permitirá que você recupere o acesso às suas chaves locais.
É recomendado escolher um código PIN de 6 dígitos o mais aleatório possível. Além disso, certifique-se de salvar este código para não esquecê-lo, caso contrário, você será forçado a recuperar sua carteira a partir da frase mnemônica. Você pode adicionar mais tarde uma opção para bloqueio biométrico para evitar digitar o PIN toda vez. De modo geral, a biometria é muito menos segura do que o próprio PIN. Portanto, por padrão, eu aconselho contra a configuração desta opção de desbloqueio.

![GREEN 2FA MULTISIG](assets/fr/18.webp)

Digite seu PIN uma segunda vez para confirmá-lo.

![GREEN 2FA MULTISIG](assets/fr/19.webp)

Aguarde enquanto sua carteira está sendo criada, em seguida, clique no botão "*Criar uma conta*".

![GREEN 2FA MULTISIG](assets/fr/20.webp)

Você então tem a escolha entre uma carteira de assinatura única padrão ou uma carteira protegida por autenticação de dois fatores (2FA). Neste tutorial, escolheremos a segunda opção.

![GREEN 2FA MULTISIG](assets/fr/21.webp)

E pronto, sua carteira multisig Bitcoin foi criada com sucesso usando o aplicativo Green!

![GREEN 2FA MULTISIG](assets/fr/22.webp)

## Configurando 2FA

Clique na sua conta.

![GREEN 2FA MULTISIG](assets/fr/23.webp)

Clique no botão verde "*Aumente a segurança da sua conta adicionando 2FA*".

![GREEN 2FA MULTISIG](assets/fr/24.webp)
Você terá então a opção de escolher o método de autenticação para acessar a segunda chave do seu 2/2 multisig. Para este tutorial, usaremos um aplicativo de autenticação. Se você não está familiarizado com este tipo de aplicativo, recomendo consultar nosso tutorial sobre Authy:
https://planb.network/tutorials/others/authy

Selecione "*Aplicativo Autenticador*".

![GREEN 2FA MULTISIG](assets/fr/25.webp)

O Green exibirá então um código QR e uma chave de recuperação. Esta chave permite que você restaure o acesso ao seu 2FA caso perca seu aplicativo Authy. É recomendado fazer um backup seguro desta chave, embora você possa sempre recuperar o acesso aos seus bitcoins após a expiração do timelock, como explicado anteriormente.

No seu aplicativo de autenticação, adicione um novo código, em seguida, escaneie o código QR fornecido pelo Green.

![GREEN 2FA MULTISIG](assets/fr/26.webp)

*Obviamente, você nunca deve compartilhar esta chave e código QR na internet, ao contrário do que estou fazendo neste tutorial. Esta carteira de exemplo será usada apenas no Testnet e será deletada ao final do tutorial.*

Clique no botão "*Continuar*".

![GREEN 2FA MULTISIG](assets/fr/27.webp)

Digite o código dinâmico de 6 dígitos presente no seu aplicativo de autenticação.

![GREEN 2FA MULTISIG](assets/fr/28.webp)

A autenticação de dois fatores está agora ativada.

![GREEN 2FA MULTISIG](assets/fr/29.webp)
Ao navegar por este menu, você também pode ajustar a duração do bloqueio temporário (timelock). Esta contagem regressiva começa ao receber bitcoins, e uma vez que o timelock expira, seus fundos podem ser gastos apenas com sua chave local, sem a necessidade do 2FA. A duração padrão é definida para 12 meses, mas para uma carteira de poupança, escolher 15 meses pode ser prudente para minimizar a frequência de renovações do timelock. Por outro lado, para uma carteira de gastos, um timelock de 6 meses pode ser preferível, pois será frequentemente renovado com suas transações diárias, e um timelock mais curto reduz a espera em caso de problemas com o 2FA. Cabe a você determinar a duração do timelock que melhor lhe convém.
![GREEN 2FA MULTISIG](assets/fr/30.webp)

Você pode agora sair deste menu. Sua carteira multisig está pronta!

![GREEN 2FA MULTISIG](assets/fr/31.webp)

## Configurando sua carteira no Blockstream Green

Se desejar personalizar sua carteira, clique nos três pequenos pontos no canto superior direito.

![GREEN 2FA MULTISIG](assets/fr/32.webp)
A opção "*Renomear*" permite personalizar o nome da sua carteira, o que é particularmente útil se você gerencia várias carteiras na mesma aplicação.
![GREEN 2FA MULTISIG](assets/fr/33.webp)

O menu "*Unidade*" oferece a opção de mudar a unidade base da sua carteira. Por exemplo, você pode escolher exibi-la em satoshis em vez de em bitcoins.

![GREEN 2FA MULTISIG](assets/fr/34.webp)

O menu "*Configurações*" fornece acesso às diferentes opções da sua carteira Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/35.webp)

Aqui, por exemplo, você encontrará sua chave pública estendida e seu *descritor*, úteis se você planeja configurar uma carteira somente de visualização a partir desta carteira.

![GREEN 2FA MULTISIG](assets/fr/36.webp)

Você também pode alterar o código PIN da sua carteira e habilitar o login biométrico.

![GREEN 2FA MULTISIG](assets/fr/37.webp)

## Usando o Blockstream Green

Agora que sua carteira Bitcoin está configurada, você está pronto para receber seus primeiros sats! Para fazer isso, basta clicar no botão "*Receber*".

![GREEN 2FA MULTISIG](assets/fr/38.webp)

O Green exibirá então o primeiro endereço de recebimento em branco da sua carteira. Você pode escanear o código QR associado ou copiar o endereço diretamente para enviar bitcoins para ele. Este tipo de endereço não especifica o valor a ser enviado pelo pagador. No entanto, você pode gerar um endereço que solicita um valor específico, clicando nos três pequenos pontos no canto superior direito, depois em "*Solicitar Valor*", e inserindo o valor desejado.

![GREEN 2FA MULTISIG](assets/fr/39.webp)

Quando a transação é transmitida na rede, ela aparecerá na sua carteira.

![GREEN 2FA MULTISIG](assets/fr/40.webp)

Aguarde para obter confirmações suficientes para considerar a transação como final.

![GREEN 2FA MULTISIG](assets/fr/41.webp)

Com bitcoins na sua carteira, você agora também pode enviá-los. Clique em "*Enviar*".

![GREEN 2FA MULTISIG](assets/fr/42.webp)

Na página seguinte, insira o endereço do destinatário. Você pode inseri-lo manualmente ou escanear um código QR.

![GREEN 2FA MULTISIG](assets/fr/43.webp)

Escolha o valor do pagamento.
![GREEN 2FA MULTISIG](assets/fr/44.webp)Na parte inferior da tela, você pode selecionar a taxa de transação para esta operação. Você tem a opção de seguir as recomendações do aplicativo ou personalizar suas taxas. Quanto mais altas as taxas em comparação com outras transações pendentes, mais rápido sua transação será processada. Para entender o mercado de taxas, você pode visitar [Mempool.space](https://mempool.space/) na seção "*Taxas de Transação*".
![GREEN 2FA MULTISIG](assets/fr/45.webp)

Clique em "*Próximo*" para acessar uma tela de resumo da sua transação. Verifique se o endereço, a quantidade e as taxas estão corretos.

![GREEN 2FA MULTISIG](assets/fr/46.webp)

Se tudo estiver correto para você, deslize o botão verde na parte inferior da tela para a direita para assinar e transmitir a transação na rede Bitcoin.

![GREEN 2FA MULTISIG](assets/fr/47.webp)

Este é o momento em que você precisa inserir seu código de autenticação para desbloquear a segunda chave do multisig mantida pela Blockstream. Insira o código de 6 dígitos exibido no seu aplicativo de autenticação.

![GREEN 2FA MULTISIG](assets/fr/48.webp)

Sua transação agora aparecerá no painel da sua carteira Bitcoin aguardando confirmação.

![GREEN 2FA MULTISIG](assets/fr/49.webp)

E é isso, agora você sabe como configurar facilmente uma carteira multisig 2/2 usando a opção 2FA do Blockstream Green!

Se você achou este tutorial útil, eu apreciaria se você pudesse deixar um polegar verde abaixo. Sinta-se livre para compartilhar este artigo em suas redes sociais. Muito obrigado!

Eu também recomendo conferir este outro tutorial completo sobre o aplicativo móvel Blockstream Green para configurar uma carteira Liquid:

https://planb.network/tutorials/wallet/blockstream-green-liquid