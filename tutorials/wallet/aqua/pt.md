---
name: Aqua
description: Bitcoin, Lightning e Liquid em uma única carteira
---
![cover](assets/cover.webp)

Aqua é um aplicativo móvel que permite a criação fácil de uma carteira quente (hot wallet) para Bitcoin e Liquid, e também oferece a possibilidade de usar Lightning sem a complexidade de gerenciar um nó, graças a swaps integrados. Ele também suporta o gerenciamento de stablecoins USDT em várias redes.

Desenvolvido pela empresa JAN3 sob a liderança de Samson Mow, o aplicativo Aqua foi inicialmente projetado especificamente para as necessidades dos usuários na América Latina, embora seja adequado para qualquer usuário em todo o mundo. É particularmente interessante para iniciantes e aqueles que usam Bitcoin diariamente para seus pagamentos.

Neste tutorial, exploraremos como usar as muitas funcionalidades do Aqua. Mas antes disso, vamos dedicar um momento para entender o que é uma sidechain no Bitcoin e como o Liquid funciona, o que nos permitirá compreender plenamente o interesse do Aqua.

![AQUA](assets/fr/01.webp)

## O que é uma sidechain?

O protocolo Bitcoin possui limitações técnicas intencionais que ajudam a manter a descentralização da rede e garantir uma distribuição de segurança entre todos os usuários. No entanto, esses limites podem às vezes frustrar os usuários, especialmente durante a congestão causada por um alto volume de transações simultâneas. O debate sobre a escalabilidade do Bitcoin há muito divide a comunidade, particularmente durante a Guerra do Tamanho do Bloco. Desde esse episódio, é amplamente reconhecido dentro da comunidade Bitcoin que a escalabilidade deve ser assegurada por soluções fora da cadeia, em sistemas de segunda camada. Entre essas soluções estão as sidechains, que ainda são relativamente desconhecidas e subutilizadas em comparação com outros sistemas como a Lightning Network.

Uma sidechain é uma blockchain independente que opera em paralelo à blockchain principal do Bitcoin. Ela usa bitcoin como uma unidade de conta por meio de um mecanismo chamado "*two-way peg*". Esse sistema permite bloquear bitcoins na cadeia principal para replicar seu valor na sidechain, onde circulam como tokens respaldados pelos bitcoins originais. Esses tokens normalmente mantêm uma paridade de valor com os bitcoins bloqueados na cadeia principal, e o processo pode ser revertido para recuperar os fundos no Bitcoin.
O objetivo das sidechains é oferecer funcionalidades adicionais ou melhorias técnicas, como transações mais rápidas, taxas reduzidas ou suporte para contratos inteligentes. Essas inovações nem sempre podem ser implementadas diretamente na blockchain do Bitcoin sem comprometer sua descentralização ou segurança. As sidechains, portanto, permitem testar e explorar novas soluções enquanto preservam a integridade do Bitcoin. No entanto, esses protocolos muitas vezes exigem compromissos, particularmente em termos de descentralização e segurança, dependendo do modelo de governança e mecanismo de consenso escolhidos.
## O que é Liquid?

Liquid é uma sidechain federada construída em cima do Bitcoin, desenvolvida pela Blockstream, com o objetivo de aprimorar a velocidade, privacidade e funcionalidades das transações. Ela usa um mecanismo de ancoragem bilateral estabelecido em uma federação para bloquear bitcoins na cadeia principal e criar em retorno Liquid-bitcoins (L-BTC), tokens que circulam no Liquid enquanto permanecem respaldados pelos bitcoins originais.

![AQUA](assets/fr/02.webp)

A rede Liquid é baseada em uma federação de participantes, composta por entidades reconhecidas do ecossistema Bitcoin, que validam os blocos e gerenciam a ancoragem bilateral. Além de L-BTC, o Liquid também permite a emissão de outros ativos digitais, como a stablecoin USDT ou outras criptomoedas.

![AQUA](assets/fr/03.webp)

## Instalando o Aplicativo Aqua

O primeiro passo é naturalmente baixar o aplicativo Aqua. Vá para a sua loja de aplicativos:
- [Para Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Para Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
Para usuários Android, você também tem a opção de instalar o aplicativo via arquivo `.apk` [disponível no GitHub deles](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Inicie o aplicativo, depois marque a caixa "*Eu li e concordo com os Termos de Serviço & Política de Privacidade*".

![AQUA](assets/fr/06.webp)

## Criando Sua Carteira no Aqua

Clique no botão "*Criar Carteira*".

![AQUA](assets/fr/07.webp)

E pronto, sua carteira já está criada!

![AQUA](assets/fr/08.webp)

Mas antes de mais nada, como esta é uma carteira de auto-custódia, é imperativo fazer um backup físico da sua frase mnemônica. **Esta frase mnemônica fornece acesso completo e irrestrito a todos os seus bitcoins**. Qualquer pessoa em posse desta frase pode roubar seus fundos, mesmo sem acesso físico ao seu telefone.
Ela permite que você restaure o acesso aos seus bitcoins em caso de perda, roubo ou dano ao seu telefone. Portanto, é muito importante fazer um backup cuidadoso em um meio físico (não digital) e armazená-lo em um local seguro. Você pode anotá-la em um pedaço de papel, ou, para mais segurança, se esta carteira for significativa, recomendo gravá-la em um meio de aço inoxidável para proteger contra os riscos de incêndios, inundações ou desabamentos (para uma carteira quente destinada a segurar uma pequena quantidade de bitcoins, um simples backup em papel provavelmente é suficiente).
Para fazer isso, clique no menu de configurações.

![AQUA](assets/fr/09.webp)

Em seguida, clique em "*Ver Frase-Semente*". Faça um backup físico desta frase de 12 palavras.

![AQUA](assets/fr/10.webp)

Neste mesmo menu de configurações, você também pode alterar o idioma do aplicativo bem como a moeda fiduciária utilizada.

![AQUA](assets/fr/11.webp)

Antes de receber seus primeiros bitcoins na sua carteira, **eu aconselho fortemente que você faça um teste de recuperação a seco**. Anote uma informação de referência, como seu xpub ou o primeiro endereço de recebimento, depois delete sua carteira no aplicativo Aqua enquanto ela ainda estiver vazia. Em seguida, tente restaurar sua carteira no Aqua usando seus backups em papel. Verifique se a informação de testemunha gerada após a restauração corresponde à que você anotou inicialmente. Se for o caso, você pode ter certeza de que seus backups em papel são confiáveis. Para aprender mais sobre como realizar um teste de recuperação, aconselho que você consulte este outro tutorial:

https://planb.network/tutorials/wallet/recovery-test

## Recebendo bitcoins no Aqua

Agora que sua carteira está configurada, você está pronto para receber seus primeiros sats! Simplesmente clique no botão "*Receber*" no menu "*Carteira*".

![AQUA](assets/fr/12.webp)

Você pode escolher receber bitcoins onchain, no Liquid, ou via Lightning.

![AQUA](assets/fr/13.webp)

Para transações onchain, o Aqua gerará um endereço de recebimento específico onde você pode receber seus sats.

![AQUA](assets/fr/14.webp)

Da mesma forma, optando por Liquid, o Aqua fornecerá a você um endereço Liquid.

![AQUA](assets/fr/15.webp)

Se preferir receber fundos via Lightning, você primeiro precisará especificar o valor desejado.

![AQUA](assets/fr/16.webp)

Então, clique em "*Gerar Fatura*".

![AQUA](assets/fr/17.webp)
A Aqua criará uma fatura para receber fundos de uma carteira Lightning. É importante notar que, ao contrário das opções onchain e Liquid, os fundos recebidos via Lightning serão automaticamente convertidos para L-BTC no Liquid usando a ferramenta Boltz, já que a Aqua não é um nó Lightning. Esse processo permite que você receba e envie fundos via Lightning, mas sem nunca manter seus bitcoins no Lightning. ![AQUA](assets/fr/18.webp)

Pessoalmente, começarei enviando bitcoins via Lightning para a Aqua. Uma vez que a transação for concluída com a fatura fornecida, uma confirmação é recebida.

![AQUA](assets/fr/19.webp)

Para acompanhar o progresso da troca, retorne à página inicial da sua carteira e clique na conta "*L2 Bitcoin*", que lista transações Lightning (via troca) e Liquid.

![AQUA](assets/fr/20.webp)

Aqui, você pode visualizar sua transação assim como seu saldo em L-BTC.

![AQUA](assets/fr/21.webp)

## Trocando bitcoins com a Aqua

Agora que você tem ativos na sua carteira Aqua, você tem a opção de trocá-los diretamente pelo aplicativo, seja para transferi-los para a blockchain principal do Bitcoin ou para o Liquid. Você também pode converter seus bitcoins na stablecoin USDT (ou outras). Para fazer isso, acesse o menu "*Marketplace*".

![AQUA](assets/fr/22.webp)

Clique em "*Swaps*".

![AQUA](assets/fr/23.webp)

Na caixa "*Transfer from*", escolha o ativo que deseja trocar. Atualmente, só tenho L-BTC, então é isso que eu seleciono.

![AQUA](assets/fr/24.webp)

Na caixa "*Transfer to*", escolha o ativo alvo da sua troca. Por minha parte, optei por USDT na rede Liquid.

![AQUA](assets/fr/25.webp)

Digite a quantidade que deseja converter.

![AQUA](assets/fr/26.webp)

Confirme clicando em "*Continue*".

![AQUA](assets/fr/27.webp)

Certifique-se de que as configurações da troca estão do seu agrado, depois confirme deslizando o botão "*Swap*" na parte inferior da tela.

![AQUA](assets/fr/28.webp)

Sua troca agora está confirmada.

![AQUA](assets/fr/29.webp)

Se voltarmos à nossa carteira, podemos ver que agora temos USDT no Liquid.

![AQUA](assets/fr/30.webp)

## Enviando bitcoins com a Aqua

Agora que você tem bitcoins na sua carteira Aqua, você tem a opção de enviá-los. Clique no botão "*Send*".

![AQUA](assets/fr/31.webp)

Escolha o ativo que deseja enviar ou selecione a rede para realizar a transação. Por minha parte, enviarei bitcoins via Lightning.

![AQUA](assets/fr/32.webp)
Em seguida, insira as informações necessárias para enviar o pagamento: para Bitcoin onchain ou Liquid, você precisa inserir um endereço de recebimento; para Lightning, uma fatura é necessária. Você pode colar essas informações diretamente no campo designado ou usar o ícone de código QR para abrir sua câmera e escanear o endereço ou fatura. Em seguida, clique em "*Continue*".
![AQUA](assets/fr/33.webp)

Clique em "*Continue*" novamente se todas as informações parecerem corretas.

![AQUA](assets/fr/34.webp)
A Aqua então apresenta um resumo da transação. Certifique-se de que todas as informações estão corretas, especialmente o endereço de destino, as taxas e o valor. Para confirmar a transação, deslize o botão "*Deslize para enviar*" localizado na parte inferior da tela.
![AQUA](assets/fr/35.webp)

Uma confirmação do envio é então fornecida a você.

![AQUA](assets/fr/36.webp)

E é isso, agora você sabe como usar o aplicativo Aqua para receber e gastar fundos em Bitcoin, Lightning e Liquid, tudo a partir de uma única interface.

Se você achou este tutorial útil, eu ficaria grato se você pudesse deixar um joinha abaixo. Sinta-se livre para compartilhar este artigo em suas redes sociais. Muito obrigado!

Eu também aconselho você a conferir este outro tutorial completo sobre o aplicativo móvel Blockstream Green, que é outra solução interessante para configurar sua carteira Liquid:

https://planb.network/tutorials/wallet/blockstream-green-liquid