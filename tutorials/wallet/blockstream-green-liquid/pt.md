---
name: Blockstream Green - Liquid
description: Configurando uma carteira na sidechain Liquid Network
---
![cover](assets/cover.webp)
O protocolo Bitcoin possui limitações técnicas intencionais que ajudam a manter a descentralização da rede e garantir a distribuição de segurança entre todos os usuários. No entanto, esses limites podem às vezes frustrar os usuários, especialmente durante a congestão causada por um alto volume de transações simultâneas. O debate sobre a escalabilidade do Bitcoin há muito divide a comunidade, particularmente durante a Guerra do Tamanho do Bloco. Desde esse episódio, é amplamente reconhecido dentro da comunidade Bitcoin que a escalabilidade deve ser assegurada por soluções fora da cadeia, em sistemas de segunda camada. Entre essas soluções estão as sidechains, que ainda são relativamente desconhecidas e subutilizadas em comparação com outros sistemas como a Lightning Network.

Uma sidechain é uma blockchain independente que opera em paralelo à blockchain principal do Bitcoin. Ela usa bitcoin como uma unidade de conta por meio de um mecanismo chamado "*two-way peg*". Este sistema permite bloquear bitcoins na cadeia principal para replicar seu valor na sidechain, onde circulam como tokens respaldados pelos bitcoins originais. Esses tokens normalmente mantêm uma paridade de valor com os bitcoins bloqueados na cadeia principal, e o processo pode ser revertido para recuperar os fundos no Bitcoin.

O objetivo das sidechains é oferecer funcionalidades adicionais ou melhorias técnicas, como transações mais rápidas, taxas reduzidas ou suporte para contratos inteligentes. Essas inovações nem sempre podem ser implementadas diretamente na blockchain do Bitcoin sem comprometer sua descentralização ou segurança. As sidechains permitem testar e explorar novas soluções enquanto preservam a integridade do Bitcoin. No entanto, esses protocolos muitas vezes exigem compromissos, particularmente em termos de descentralização e segurança, dependendo do modelo de governança e mecanismo de consenso escolhidos.

Hoje, a sidechain mais conhecida é provavelmente a Liquid. Neste tutorial, vou primeiro apresentar o que é a Liquid e, em seguida, orientar sobre como começar a usá-la facilmente por meio do aplicativo Blockstream Green, para aproveitar seus benefícios.

![LIQUID GREEN](assets/fr/01.webp)

## O que é a Liquid Network?

Liquid é uma sidechain federada construída em cima do Bitcoin, desenvolvida pela Blockstream, com o objetivo de melhorar a velocidade, privacidade e funcionalidades das transações. Ela utiliza um mecanismo de ancoragem bilateral estabelecido em uma federação para bloquear bitcoins na cadeia principal e criar, em troca, Liquid-bitcoins (L-BTC), tokens que circulam na Liquid enquanto permanecem respaldados pelos bitcoins originais.

![LIQUID GREEN](assets/fr/02.webp)
A rede Liquid é baseada em uma federação de participantes, consistindo de entidades reconhecidas do ecossistema Bitcoin, que validam blocos e gerenciam a ancoragem bilateral. Além de L-BTC, a Liquid também permite a emissão de outros ativos digitais, como stablecoins ou outras criptomoedas.
![LIQUID GREEN](assets/fr/03.webp)

## Introdução ao Blockstream Green

Blockstream Green é uma carteira de software disponível para dispositivos móveis e desktop. Anteriormente conhecida como *Green Address*, esta carteira tornou-se um projeto da Blockstream após sua aquisição em 2016.

Green é um aplicativo particularmente fácil de usar, tornando-o interessante para iniciantes. Ele oferece todos os recursos essenciais de uma boa carteira Bitcoin, incluindo RBF (*Replace-by-Fee*), uma opção para conectar via Tor, a capacidade de conectar seu próprio nó, a opção SPV (*Simple Payment Verification*), rotulagem e controle de moedas.

Blockstream Green também suporta a rede Liquid, e é isso que vamos explorar neste tutorial. Se você deseja usar o Green para outras aplicações, também recomendo consultar estes outros tutoriais:

https://planb.network/tutorials/wallet/blockstream-green-desktop

https://planb.network/tutorials/wallet/blockstream-green
## Instalando e Configurando o Aplicativo Blockstream Green

O primeiro passo é, naturalmente, baixar o aplicativo Green. Vá até a loja de aplicativos:
- [Para Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Para Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![LIQUID GREEN](assets/fr/04.webp)

Para usuários de Android, você também tem a opção de instalar o aplicativo via arquivo `.apk` [disponível no GitHub da Blockstream](https://github.com/Blockstream/green_android/releases).

![LIQUID GREEN](assets/fr/05.webp)

Inicie o aplicativo, depois marque a caixa "*Eu aceito os termos...*".

![LIQUID GREEN](assets/fr/06.webp)

Quando você abrir o Green pela primeira vez, a tela inicial aparece sem nenhuma carteira configurada. Mais tarde, se você criar ou importar carteiras, elas aparecerão nesta interface. Antes de prosseguir para a criação de uma carteira, aconselho que ajuste as configurações do aplicativo de acordo com suas expectativas. Clique em "*Configurações do Aplicativo*".

![LIQUID GREEN](assets/fr/07.webp)

A opção "*Privacidade Aprimorada*", disponível apenas no Android, melhora a privacidade desativando capturas de tela e ocultando pré-visualizações do aplicativo. Ela também bloqueia automaticamente o acesso ao aplicativo assim que seu telefone é bloqueado, tornando seus dados mais difíceis de serem expostos.
![LIQUID GREEN](assets/fr/08.webp)
Para aqueles que procuram aprimorar sua privacidade, o aplicativo oferece a opção de rotear seu tráfego através do Tor, uma rede que criptografa todas as suas conexões e torna suas atividades difíceis de rastrear. Embora esta opção possa diminuir ligeiramente o desempenho do aplicativo, é altamente recomendada para proteger sua privacidade, especialmente se você não está usando seu próprio nó completo.

![LIQUID GREEN](assets/fr/09.webp)

Para usuários que possuem seu próprio nó completo, a Carteira Green permite que você se conecte a ele via um servidor Electrum, garantindo controle total sobre as informações da rede Bitcoin e a transmissão de transações. No entanto, este recurso é relevante para carteiras Bitcoin tradicionais, então você não precisa dele se estiver usando Liquid.

![LIQUID GREEN](assets/fr/10.webp)

Outra característica alternativa é a opção "*Verificação SPV*", que permite a verificação direta de certos dados da blockchain, reduzindo a necessidade de confiar no nó padrão da Blockstream, embora este método não forneça todas as garantias de um nó completo. Novamente, isso só diz respeito às suas carteiras Bitcoin onchain, e não ao Liquid.

![LIQUID GREEN](assets/fr/11.webp)

Uma vez que essas configurações estejam ajustadas de acordo com suas necessidades, clique no botão "*Salvar*" e reinicie o aplicativo.

![LIQUID GREEN](assets/fr/12.webp)

## Criando uma Carteira Liquid no Blockstream Green

Agora você está pronto para criar uma carteira Liquid. Clique no botão "*Começar*".

![LIQUID GREEN](assets/fr/13.webp)

Você tem a escolha entre criar uma carteira de software localmente ou gerenciar uma carteira fria via uma carteira de hardware. Para este tutorial, focaremos em criar uma carteira quente no Liquid, então você precisará selecionar a opção "*Neste Dispositivo*". Você também pode usar uma carteira de hardware compatível, como o Blockstream Jade, para proteger sua carteira Liquid.

![LIQUID GREEN](assets/fr/14.webp)
Você pode então escolher restaurar uma carteira Bitcoin existente ou criar uma nova. Para os propósitos deste tutorial, criaremos uma nova carteira. No entanto, se você precisar regenerar uma carteira Liquid existente a partir de sua frase mnemônica, por exemplo, devido à perda de sua carteira de hardware, você precisará escolher a segunda opção.
![LIQUID GREEN](assets/fr/15.webp)

Você então tem a escolha entre uma frase mnemônica de 12 palavras ou de 24 palavras. Esta frase permitirá que você recupere o acesso à sua carteira a partir de qualquer software compatível em caso de problemas com seu telefone. Atualmente, optar por uma frase de 24 palavras não oferece mais segurança do que uma frase de 12 palavras. Portanto, eu recomendo escolher uma frase mnemônica de **12 palavras**.
O Green então fornecerá sua frase mnemônica. Antes de continuar, certifique-se de não estar sendo observado. Clique em "*Mostrar frase de recuperação*" para exibi-la na tela.
![LIQUID GREEN](assets/fr/16.webp)

**Esta frase mnemônica dá acesso total e irrestrito a todos os seus bitcoins.** Qualquer pessoa em posse desta frase pode roubar seus fundos, mesmo sem acesso físico ao seu telefone.

Ela permite que você restaure o acesso aos seus bitcoins em caso de perda, roubo ou dano ao seu telefone. Portanto, é muito importante salvá-la cuidadosamente **em um meio físico (não digital)** e armazená-la em um local seguro. Você pode anotá-la em um pedaço de papel, ou, para mais segurança, se esta carteira for significativa, eu recomendo gravá-la em um meio de aço inoxidável para proteger contra os riscos de incêndios, inundações ou desabamentos (para uma carteira quente destinada a segurar uma pequena quantidade de bitcoins, um simples backup em papel provavelmente é suficiente).

*Obviamente, você nunca deve compartilhar essas palavras na internet, ao contrário do que estou fazendo neste tutorial. Esta carteira de exemplo será usada apenas no Liquid Testnet e será deletada ao final do tutorial.*

![LIQUID GREEN](assets/fr/17.webp)

Após anotar corretamente sua frase mnemônica em um meio físico, clique em "*Continuar*". A Carteira Green então pedirá que você confirme algumas palavras de sua frase para verificar se você as registrou corretamente. Preencha os espaços em branco com as palavras que faltam.

![LIQUID GREEN](assets/fr/18.webp)

Escolha o código PIN para o seu dispositivo, que será usado para desbloquear sua carteira Green. É, portanto, uma proteção contra o acesso físico não autorizado. Este código PIN não participa da derivação das chaves criptográficas da sua carteira. Assim, mesmo sem acesso a este código PIN, a posse de sua frase mnemônica de 12 ou 24 palavras permitirá que você recupere o acesso aos seus bitcoins.

É recomendado escolher um código PIN de 6 dígitos o mais aleatório possível. Além disso, certifique-se de salvar este código para não esquecê-lo, caso contrário, você será forçado a recuperar sua carteira a partir da frase mnemônica. Mais tarde, você pode adicionar uma opção de bloqueio biométrico para evitar digitar o PIN toda vez que usá-lo. De modo geral, a biometria é muito menos segura do que o próprio PIN. Portanto, por padrão, eu aconselho contra a configuração desta opção de desbloqueio.

![LIQUID GREEN](assets/fr/19.webp)

Digite seu PIN uma segunda vez para confirmá-lo.

![LIQUID GREEN](assets/fr/20.webp)
Aguarde a criação da sua carteira, depois clique no botão "*Criar uma conta*".
![LIQUID GREEN](assets/fr/21.webp)
Na caixa "*Ativos*", selecione "*Liquid Bitcoin*". Você então tem a escolha entre uma carteira de assinatura única padrão, que usaremos neste tutorial, ou uma carteira protegida por autenticação de dois fatores (2FA).
![LIQUID GREEN](assets/fr/22.webp)

E pronto, sua carteira Liquid foi criada com sucesso usando o aplicativo Green!

![LIQUID GREEN](assets/fr/23.webp)

Antes de receber seus primeiros bitcoins na sua carteira Liquid, **eu aconselho fortemente que você faça um teste de recuperação vazio**. Anote uma informação de referência, como seu xpub ou o primeiro endereço de recebimento, depois delete sua carteira no aplicativo Green enquanto ela ainda estiver vazia. Em seguida, tente restaurar sua carteira no Green usando seus backups em papel. Verifique se a informação de testemunha gerada após a restauração corresponde à que você anotou inicialmente. Se sim, você pode ter certeza de que seus backups em papel são confiáveis. Para aprender mais sobre como realizar um teste de recuperação, aconselho que você consulte este outro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Configurando sua Carteira Liquid

Se desejar personalizar sua carteira, clique nos três pequenos pontos no canto superior direito.

![LIQUID GREEN](assets/fr/24.webp)

A opção "*Renomear*" permite que você personalize o nome da sua carteira, o que é particularmente útil se você gerencia várias carteiras na mesma aplicação.

![LIQUID GREEN](assets/fr/25.webp)

O menu "*Unidade*" dá a opção de mudar a unidade base da sua carteira. Por exemplo, você pode escolher exibi-la em satoshis em vez de em bitcoins.

![LIQUID GREEN](assets/fr/26.webp)

O menu "*Configurações*" fornece acesso às diferentes opções da sua carteira Bitcoin.

![LIQUID GREEN](assets/fr/27.webp)

Aqui você encontrará, por exemplo, seu *descritor* que pode ser útil se você planeja configurar uma carteira somente de visualização a partir desta carteira Liquid.

![LIQUID GREEN](assets/fr/28.webp)

Você também pode alterar o código PIN da sua carteira e habilitar o login biométrico.

![LIQUID GREEN](assets/fr/29.webp)

## Usando sua Carteira Liquid

Agora que sua carteira Liquid está configurada, você está pronto para receber seus primeiros L-sats!
Se você ainda não possui L-BTC, existem várias opções disponíveis para você. A primeira é tê-lo enviado diretamente para você. Se alguém quiser pagar você em bitcoins no Liquid, simplesmente dê a eles um endereço de recebimento. A outra solução é trocar seus bitcoins onchain ou aqueles na rede Lightning por L-BTC. Para fazer isso, você pode usar [uma ponte como a Boltz](https://boltz.exchange/). Basta inserir seu endereço Liquid no site, depois fazer o pagamento via rede Lightning ou onchain.
![LIQUID GREEN](assets/fr/30.webp)

Para gerar um endereço Liquid, clique no botão "*Receber*".

![LIQUID GREEN](assets/fr/31.webp)

O Green então exibirá o primeiro endereço de recebimento em branco da sua carteira. Você pode tanto escanear o código QR associado quanto copiar o endereço diretamente para enviar L-BTC para ele.

![LIQUID GREEN](assets/fr/32.webp)

Quando a transação for transmitida na rede, ela aparecerá na sua carteira.

![LIQUID GREEN](assets/fr/33.webp)

Aguarde para obter confirmações suficientes para considerar a transação como final. No Liquid, as confirmações devem ser rápidas, já que um bloco é publicado a cada minuto.

![LIQUID GREEN](assets/fr/34.webp)
Com L-sats na sua carteira Liquid, agora você também pode enviá-los. Clique em "*Enviar*".
![LIQUID GREEN](assets/fr/35.webp)

Na próxima página, insira o endereço Liquid do destinatário. Você pode inseri-lo manualmente ou escanear o código QR deles.

![LIQUID GREEN](assets/fr/36.webp)

Escolha a quantidade do pagamento.

![LIQUID GREEN](assets/fr/37.webp)

Clique em "*Próximo*" para acessar uma tela de resumo da sua transação. Verifique se o endereço, a quantidade e as taxas estão corretos.

![LIQUID GREEN](assets/fr/38.webp)

Se tudo parecer bom para você, deslize o botão verde na parte inferior da tela para a direita para assinar e transmitir a transação na rede Bitcoin.

![LIQUID GREEN](assets/fr/39.webp)

Sua transação agora aparecerá no painel de controle da sua carteira Bitcoin aguardando confirmação.

![LIQUID GREEN](assets/fr/40.webp)

E é isso, agora você sabe como usar facilmente a sidechain Liquid com o aplicativo Blockstream Green!

Se você achou este tutorial útil, eu apreciaria um joinha abaixo. Sinta-se livre para compartilhar este artigo nas suas redes sociais. Muito obrigado!

Eu também recomendo descobrir este outro tutorial completo sobre o aplicativo móvel Blockstream Green para configurar uma carteira quente de Bitcoin onchain:

https://planb.network/tutorials/wallet/blockstream-green