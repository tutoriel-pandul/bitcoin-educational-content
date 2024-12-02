---
name: Blockstream Green - Mobile
description: Configurando uma carteira de software móvel
---
![cover](assets/cover.webp)

Uma carteira de software é uma aplicação instalada em um computador, smartphone ou qualquer outro dispositivo conectado à Internet, permitindo o gerenciamento e a segurança das chaves da carteira Bitcoin. Ao contrário das carteiras de hardware, que isolam as chaves privadas, as carteiras "quentes" operam em um ambiente potencialmente exposto a ciberataques, aumentando os riscos de hacking e roubo.

Carteiras de software devem ser usadas para gerenciar quantidades razoáveis de bitcoins, especialmente para transações diárias. Isso também pode ser uma opção interessante para pessoas com um portfólio Bitcoin limitado, para quem investir em uma carteira de hardware pode parecer desproporcional. No entanto, sua constante exposição à Internet as torna menos seguras para armazenar suas economias de longo prazo ou fundos significativos. Para estes, é preferível optar por soluções mais seguras, como carteiras de hardware.

Neste tutorial, vou apresentar uma das melhores soluções de carteira de software móvel: **Blockstream Green**.

![GREEN](assets/fr/01.webp)

Se você estiver interessado em aprender como usar o Blockstream Green em um computador, por favor, consulte este outro tutorial:

https://planb.network/tutorials/wallet/blockstream-green-desktop

## Introdução ao Blockstream Green

Blockstream Green é uma carteira de software disponível tanto para dispositivos móveis quanto para computadores. Anteriormente conhecida como *Green Address*, esta carteira tornou-se um projeto da Blockstream após sua aquisição em 2016.

Green é uma aplicação particularmente fácil de usar, tornando-a interessante para iniciantes. Oferece todas as características essenciais de uma boa carteira Bitcoin, incluindo RBF (*Replace-by-Fee*), uma opção para conectar via Tor, a capacidade de conectar o próprio nó, a opção SPV (*Simple Payment Verification*), rotulagem e controle de moedas.

O Blockstream Green também suporta a rede Liquid, uma sidechain do Bitcoin desenvolvida pela Blockstream para realizar transações rápidas e confidenciais fora da blockchain principal. Este tutorial foca exclusivamente no Bitcoin, mas um futuro abordará o uso do Liquid.

## Instalando e Configurando o Aplicativo Blockstream Green

O primeiro passo é naturalmente baixar o aplicativo Green. Vá à sua loja de aplicativos:
- [Para Android](https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet);
- [Para Apple](https://apps.apple.com/us/app/green-bitcoin-wallet/id1402243590).

![GREEN](assets/fr/02.webp)

Para usuários de Android, você também tem a opção de instalar o aplicativo via arquivo `.apk` [disponível no GitHub do Blockstream](https://github.com/Blockstream/green_android/releases).

![GREEN](assets/fr/03.webp)
Lance o aplicativo, então marque a caixa "*Eu aceito as condições...*".
![GREEN](assets/fr/04.webp)

Quando você abre o Green pela primeira vez, a tela inicial aparece sem nenhuma carteira configurada. Mais tarde, se você criar ou importar carteiras, elas aparecerão nesta interface. Antes de prosseguir para a criação de uma carteira, aconselho ajustar as configurações do aplicativo de acordo com suas expectativas. Clique em "*Configurações do Aplicativo*".

![GREEN](assets/fr/05.webp)

A opção "*Privacidade Aprimorada*", disponível apenas no Android, melhora a privacidade desativando capturas de tela e ocultando pré-visualizações do aplicativo. Também bloqueia automaticamente o acesso ao aplicativo assim que seu telefone é bloqueado, tornando seus dados mais difíceis de serem expostos.

![GREEN](assets/fr/06.webp)
Para aqueles que desejam aumentar sua privacidade, o aplicativo oferece a opção de rotear seu tráfego via Tor, uma rede que criptografa todas as suas conexões e torna suas atividades difíceis de rastrear. Embora esta opção possa diminuir ligeiramente o desempenho do aplicativo, é altamente recomendada para proteger sua privacidade, especialmente se você não estiver usando seu próprio nó completo.
![GREEN](assets/fr/07.webp)

Para usuários que possuem seu próprio nó completo, a Green Wallet oferece a possibilidade de se conectar a ele via um servidor Electrum, garantindo controle total sobre as informações da rede Bitcoin e a transmissão de transações.

![GREEN](assets/fr/08.webp)

Outra característica alternativa é a opção de "*Verificação SPV*", que permite a verificação direta de certos dados da blockchain, reduzindo a necessidade de confiar no nó padrão da Blockstream, embora este método não ofereça todas as garantias de um nó completo.

![GREEN](assets/fr/09.webp)

Uma vez que essas configurações estejam ajustadas de acordo com suas necessidades, clique no botão "*Salvar*" e reinicie o aplicativo.

![GREEN](assets/fr/10.webp)

## Criando uma Carteira Bitcoin na Blockstream Green

Você está agora pronto para criar uma carteira Bitcoin. Clique no botão "*Começar*".

![GREEN](assets/fr/11.webp)

Você tem a escolha entre criar uma carteira de software localmente ou gerenciar uma carteira fria via uma carteira de hardware. Para este tutorial, focaremos em criar uma carteira quente, então você precisará selecionar a opção "*Neste Dispositivo*". Em um tutorial futuro, mostrarei como usar a outra opção.

A opção "*Somente Visualização*", por outro lado, permite que você importe uma chave pública estendida (`xpub`) para visualizar transações de uma carteira sem poder gastar os fundos associados, o que é conveniente para monitorar uma carteira em uma carteira de hardware, por exemplo.

![GREEN](assets/fr/12.webp)
Você pode então escolher restaurar uma carteira Bitcoin existente ou criar uma nova. Para os propósitos deste tutorial, criaremos uma nova carteira. No entanto, se você precisar regenerar uma carteira Bitcoin já existente a partir de sua frase mnemônica, por exemplo, devido à perda de sua carteira de hardware, você precisará escolher a segunda opção.
![GREEN](assets/fr/13.webp)

Você então tem a escolha entre uma frase mnemônica de 12 palavras ou 24 palavras. Esta frase permitirá que você recupere o acesso à sua carteira a partir de qualquer software compatível em caso de problemas com seu telefone. Atualmente, optar por uma frase de 24 palavras não oferece mais segurança do que uma frase de 12 palavras. Portanto, recomendo escolher uma frase mnemônica de **12 palavras**.

A Green então fornecerá sua frase mnemônica. Antes de continuar, certifique-se de não estar sendo observado. Clique em "*Mostrar frase de recuperação*" para exibi-la na tela.

![GREEN](assets/fr/14.webp)

**Esta frase mnemônica dá acesso total e irrestrito a todos os seus bitcoins.** Qualquer pessoa em posse desta frase pode roubar seus fundos, mesmo sem acesso físico ao seu telefone.

Ela permite que você restaure o acesso aos seus bitcoins em caso de perda, roubo ou dano ao seu telefone. Portanto, é muito importante salvá-la cuidadosamente **em um meio físico (não digital)** e armazená-la em um local seguro. Você pode anotá-la em um pedaço de papel, ou, para mais segurança, se esta carteira for importante, recomendo gravá-la em um meio de aço inoxidável para proteger contra os riscos de incêndios, inundações ou desabamentos (para uma carteira quente destinada a garantir uma pequena quantidade de bitcoins, um simples backup em papel provavelmente é suficiente).
*Obviamente, você nunca deve compartilhar essas palavras na internet, ao contrário do que estou fazendo neste tutorial. Esta carteira de exemplo será usada apenas no Testnet e será deletada ao final do tutorial.*
![GREEN](assets/fr/15.webp)

Após anotar corretamente sua frase mnemônica em um meio físico, clique em "*Continuar*". A carteira Green então pedirá que você confirme certas palavras da sua frase para verificar se você as registrou corretamente. Preencha os espaços em branco com as palavras que faltam.

![GREEN](assets/fr/16.webp)

Escolha o código PIN para o seu dispositivo, que será usado para desbloquear sua carteira Green. Isso é, portanto, uma proteção contra acesso físico não autorizado. Este código PIN não participa da derivação das chaves criptográficas da sua carteira. Assim, mesmo sem acesso a este código PIN, a posse da sua frase mnemônica de 12 ou 24 palavras permitirá que você recupere o acesso aos seus bitcoins.
É recomendado escolher um PIN de 6 dígitos o mais aleatório possível. Além disso, certifique-se de fazer backup deste código para não esquecê-lo, caso contrário, você será forçado a recuperar sua carteira usando a frase mnemônica. Posteriormente, você pode adicionar uma opção de bloqueio biométrico para evitar digitar o PIN a cada uso. De modo geral, a biometria é muito menos segura do que o próprio PIN. Portanto, por padrão, eu aconselho contra a configuração desta opção de desbloqueio.
![GREEN](assets/fr/17.webp)

Digite seu PIN uma segunda vez para confirmá-lo.

![GREEN](assets/fr/18.webp)

Aguarde a criação da sua carteira, depois clique no botão "*Criar uma conta*".

![GREEN](assets/fr/19.webp)

Você então tem a escolha entre uma carteira de assinatura única padrão, que usaremos neste tutorial, ou uma carteira protegida por autenticação de dois fatores (2FA).

![GREEN](assets/fr/20.webp)

A opção 2FA no Green cria uma carteira multisignature 2/2, uma das chaves é mantida pela Blockstream. Isso significa que, para fazer uma transação, ambas as chaves são necessárias: uma chave local protegida pelo seu PIN no seu telefone, e uma chave remota segura por 2FA nos servidores da Blockstream. Em caso de perda de acesso ao 2FA ou indisponibilidade dos serviços da Blockstream, mecanismos de recuperação baseados em scripts de time-lock garantem a possibilidade de recuperar independentemente seus fundos. Embora esta configuração reduza significativamente o risco de seus bitcoins serem roubados, é mais complexa de gerenciar e depende parcialmente da Blockstream. Para este tutorial, optaremos por uma carteira de assinatura única clássica, com chaves armazenadas localmente no telefone.

E é isso, sua carteira Bitcoin foi criada com sucesso usando o aplicativo Green!

![GREEN](assets/fr/21.webp)

Antes de receber seus primeiros bitcoins em sua carteira, **eu aconselho fortemente a realizar um teste de recuperação a seco**. Anote uma informação de referência, como seu xpub ou o primeiro endereço de recebimento, depois delete sua carteira no aplicativo Green enquanto ela ainda estiver vazia. Em seguida, tente restaurar sua carteira no Green usando seus backups em papel. Verifique se a informação testemunha gerada após a restauração corresponde àquela que você anotou inicialmente. Se for o caso, você pode ter certeza de que seus backups em papel são confiáveis. Para aprender mais sobre como realizar um teste de recuperação, aconselho que consulte este outro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Configurando sua carteira no Blockstream Green
Se você quiser personalizar seu portfólio, clique nos três pequenos pontos no canto superior direito.
![GREEN](assets/fr/22.webp)
A opção "*Rename*" permite que você personalize o nome do seu portfólio, o que é particularmente útil se você gerencia múltiplos portfólios no mesmo aplicativo.
![GREEN](assets/fr/23.webp)

O menu "*Unit*" dá a opção de mudar a unidade base do seu portfólio. Por exemplo, você pode escolher exibi-lo em satoshis em vez de em bitcoins.

![GREEN](assets/fr/24.webp)

O menu "*Settings*" fornece acesso às diferentes opções da sua carteira Bitcoin.

![GREEN](assets/fr/25.webp)

Aqui, por exemplo, você encontrará sua chave pública estendida e seu *descriptor*, útil se você planeja configurar uma carteira somente de observação a partir desta carteira.

![GREEN](assets/fr/26.webp)

Você também pode alterar o código PIN da sua carteira e habilitar o login biométrico.

![GREEN](assets/fr/27.webp)

## Usando o Blockstream Green

Agora que sua carteira Bitcoin está configurada, você está pronto para receber seus primeiros sats! Para fazer isso, basta clicar no botão "*Receive*".

![GREEN](assets/fr/28.webp)

O Green exibirá então o primeiro endereço de recebimento em branco da sua carteira. Você pode escanear o código QR associado ou copiar o endereço diretamente para enviar bitcoins para ele. Este tipo de endereço não especifica o valor a ser enviado pelo pagador. No entanto, você pode gerar um endereço que solicita um valor específico, clicando nos três pequenos pontos no canto superior direito, depois em "*Request Amount*", e inserindo o valor desejado.

Como você está usando uma conta Segwit v0 (BIP84), seu endereço começará com `bc1q...`. No meu exemplo, estou usando uma carteira Testnet, então o prefixo é ligeiramente diferente.

![GREEN](assets/fr/29.webp)

Quando a transação é transmitida na rede, ela aparecerá na sua carteira.

![GREEN](assets/fr/30.webp)

Aguarde receber confirmações suficientes para considerar a transação como final.

![GREEN](assets/fr/31.webp)

Com bitcoins na sua carteira, você agora também pode enviá-los. Clique em "*Send*".

![GREEN](assets/fr/32.webp)

Na próxima página, insira o endereço do destinatário. Você pode inseri-lo manualmente ou escanear um código QR.

![GREEN](assets/fr/33.webp)

Escolha o valor do pagamento.

![GREEN](assets/fr/34.webp)
Na parte inferior da tela, você pode selecionar a taxa de comissão para esta transação. Você tem a opção de seguir as recomendações do aplicativo ou personalizar suas taxas. Quanto mais altas as taxas em comparação com outras transações pendentes, mais rápido sua transação será processada. Para entender o mercado de taxas, você pode visitar [Mempool.space](https://mempool.space/) na seção "*Transaction Fees*".
![GREEN](assets/fr/35.webp)

Clique em "*Next*" para acessar uma tela de resumo da sua transação. Verifique se o endereço, o valor e as taxas estão corretos.

![GREEN](assets/fr/36.webp)

Se tudo estiver ao seu gosto, deslize o botão verde na parte inferior da tela para a direita para assinar e transmitir a transação na rede Bitcoin.

![GREEN](assets/fr/37.webp)

Sua transação agora aparecerá no painel de controle da sua carteira Bitcoin aguardando confirmação.

![GREEN](assets/fr/38.webp)
*Este tutorial é baseado em [uma versão original pertencente à Bitstack](https://www.bitstack-app.com/blog/installer-portefeuille-bitcoin-green-wallet) escrita por Loïc Morel. A Bitstack é uma neo-banco francesa de Bitcoin que oferece a possibilidade de poupar em bitcoins, seja através de DCA (Dollar Cost Averaging) ou por meio de um sistema automático de arredondamento de despesas diárias.*