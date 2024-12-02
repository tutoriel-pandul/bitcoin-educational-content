---
name: Blockstream Green - Desktop
description: Usando o software Green Wallet em um computador
---
![cover](assets/cover.webp)

Neste tutorial, exploraremos como usar o software Blockstream Green em um computador para gerenciar uma carteira segura em uma carteira de hardware. Ao usar uma carteira de hardware, é essencial usar um software no seu computador para gerenciar esta carteira. Este software de gerenciamento não tem acesso às chaves privadas; ele é usado apenas para verificar o saldo da sua carteira, gerar endereços de recebimento e construir e transmitir transações que serão assinadas pela carteira de hardware. Green representa uma das muitas soluções disponíveis para gerenciar sua carteira de hardware Bitcoin.

Em 2024, Blockstream Green é compatível apenas com Ledger Nano S (versão mais antiga), Ledger Nano X, Trezor One, Trezor T e dispositivos Blockstream Jade.

## Introdução ao Blockstream Green

Blockstream Green é um software disponível tanto para dispositivos móveis quanto para desktop. Anteriormente conhecido como Green Address, esta carteira tornou-se um projeto da Blockstream após sua aquisição em 2016.

Green é uma aplicação muito amigável, tornando-a particularmente adequada para iniciantes. Oferece várias funcionalidades, como o gerenciamento de carteiras quentes, carteiras de hardware, bem como carteiras na sidechain Liquid. Você também pode usá-lo para configurar uma carteira somente de visualização.

![GREEN-DESKTOP](assets/fr/01.webp)

Neste tutorial, focaremos exclusivamente no uso do software em um computador. Para explorar outros usos do Green, convido você a conferir nossos outros tutoriais dedicados:

https://planb.network/tutorials/wallet/blockstream-green

https://planb.network/tutorials/wallet/blockstream-green-watch-only

## Instalando e Configurando o Software Blockstream Green

Comece instalando o software Blockstream Green no seu computador. Acesse [o site oficial](https://blockstream.com/green/) e clique no botão "*Download Now*". Em seguida, siga o processo de instalação de acordo com o seu sistema operacional.

![GREEN-DESKTOP](assets/fr/02.webp)

Lance o aplicativo, depois marque a caixa "*I accept the terms...*".

![GREEN-DESKTOP](assets/fr/03.webp)

Quando você abrir o Green pela primeira vez, a tela inicial aparece sem nenhuma carteira configurada. Mais tarde, se você criar ou importar carteiras, elas aparecerão nesta interface. Antes de prosseguir para a criação de uma carteira, aconselho que você ajuste as configurações do aplicativo de acordo com suas expectativas. Clique no ícone de configurações no canto inferior esquerdo.

![GREEN-DESKTOP](assets/fr/04.webp)

No menu "*General*", você pode alterar o idioma do software e habilitar recursos experimentais, se desejar.

![GREEN-DESKTOP](assets/fr/05.webp)
No menu "*Network*", você pode habilitar a conexão via Tor, uma rede que criptografa todas as suas conexões e torna suas atividades difíceis de rastrear. Embora esta opção possa diminuir ligeiramente o desempenho do aplicativo, é altamente recomendada para proteger sua privacidade, especialmente se você não estiver usando seu próprio nó completo.
![GREEN-DESKTOP](assets/fr/06.webp)

Para usuários que possuem seu próprio nó completo, o Green oferece a possibilidade de se conectar a ele via um servidor Electrum, garantindo controle total sobre as informações da rede Bitcoin e a transmissão de transações. Para fazer isso, clique no menu "*Custom servers and validation*", e então insira as informações do seu servidor Electrum.

![GREEN-DESKTOP](assets/fr/07.webp)
Uma alternativa de recurso é a opção "*SPV Verification*", que permite a verificação direta de certos dados da blockchain, reduzindo a necessidade de confiar no nó padrão da Blockstream, embora este método não ofereça todas as garantias de um nó completo. Esta opção também é encontrada no menu "*Servidores personalizados e validação*".
![GREEN-DESKTOP](assets/fr/08.webp)

Uma vez que essas configurações estejam ajustadas de acordo com suas necessidades, você pode sair desta interface.

## Importando uma Carteira Bitcoin para o Blockstream Green

Você está agora pronto para importar sua carteira Bitcoin. Clique no botão "**Começar**".

![GREEN-DESKTOP](assets/fr/09.webp)

Você tem a escolha entre criar uma carteira de software local ou gerenciar uma carteira fria por meio de uma carteira de hardware. Para este tutorial, focaremos no gerenciamento de uma carteira de hardware, então você precisará selecionar a opção "*Em Carteira de Hardware*".

A opção "*Somente Visualização*", por outro lado, permite importar uma chave pública estendida (`xpub`) para visualizar as transações de uma carteira sem poder gastar os fundos associados.

![GREEN-DESKTOP](assets/fr/10.webp)

Se você estiver usando um Jade, clique no botão correspondente. Caso contrário, selecione "*Conectar um Dispositivo de Hardware diferente*". No meu caso, estou usando um Ledger Nano S. Para usuários do Ledger, certifique-se de instalar o aplicativo "*Bitcoin Legacy*" em sua carteira de hardware, pois o Green só suporta esta versão.

![GREEN-DESKTOP](assets/fr/11.webp)

Conecte sua carteira de hardware ao computador e selecione-a no Green.

![GREEN-DESKTOP](assets/fr/12.webp)

Aguarde enquanto o Green importa as informações da sua carteira, após o que você poderá acessá-la.

![GREEN-DESKTOP](assets/fr/13.webp)

Neste ponto, dois cenários são possíveis. Se você já havia usado sua carteira de hardware antes, você deverá ver sua conta aparecer no software. Mas se, como eu, você acabou de inicializar sua carteira de hardware gerando uma frase mnemônica sem tê-la usado ainda, você precisará criar uma conta. Clique em "*Criar Conta*".
![GREEN-DESKTOP](assets/fr/14.webp)
Escolha "*Padrão*" se desejar usar uma carteira clássica.

![GREEN-DESKTOP](assets/fr/15.webp)

Você agora tem acesso à sua conta.

![GREEN-DESKTOP](assets/fr/16.webp)

## Usando uma carteira de hardware com o Blockstream Green

Agora que sua carteira Bitcoin está configurada, você está pronto para receber seus primeiros sats! Para fazer isso, basta clicar no botão "*Receber*".

![GREEN-DESKTOP](assets/fr/17.webp)

Clique no botão "*Copiar endereço*" para copiar o endereço, ou escaneie seu código QR.

![GREEN-DESKTOP](assets/fr/18.webp)

Uma vez que a transação seja transmitida na rede, ela aparecerá em sua carteira. Aguarde para obter confirmações suficientes para considerar a transação como imutável.

![GREEN-DESKTOP](assets/fr/19.webp)

Com bitcoins em sua carteira, você agora é capaz de enviá-los. Clique no botão "*Enviar*".

![GREEN-DESKTOP](assets/fr/20.webp)

Na página seguinte, insira o endereço do destinatário. Você pode inseri-lo manualmente ou escanear um código QR com sua webcam.

![GREEN-DESKTOP](assets/fr/21.webp)

Escolha o valor do pagamento.

![GREEN-DESKTOP](assets/fr/22.webp)
Na parte inferior da tela, você pode selecionar a taxa de cobrança para esta transação. Você tem a opção de seguir as recomendações do aplicativo ou personalizar suas taxas. Quanto mais altas forem as taxas em comparação com outras transações pendentes, mais rápido sua transação será processada. Para conhecer o mercado de taxas, você pode visitar [Mempool.space](https://mempool.space/) na seção "*Taxas de Transação*".
![GREEN-DESKTOP](assets/fr/23.webp)

Se desejar selecionar especificamente quais UTXOs usar em sua transação, clique no botão "*Seleção manual de moedas*".

![GREEN-DESKTOP](assets/fr/24.webp)

Verifique as configurações da sua transação e, se tudo estiver conforme você espera, clique em "*Próximo*".

![GREEN-DESKTOP](assets/fr/25.webp)

Verifique mais uma vez se o endereço, o valor e as taxas estão corretos, então clique em "*Confirmar transação*".

![GREEN-DESKTOP](assets/fr/26.webp)

Certifique-se de que todos os parâmetros da transação estão corretos na tela da sua carteira de hardware, então assine a transação usando-a.

![GREEN-DESKTOP](assets/fr/27.webp)

Uma vez que a transação é assinada pela carteira de hardware, o Green automaticamente a transmite na rede Bitcoin. Sua transação então aparecerá no painel de controle da sua carteira Bitcoin, aguardando confirmação.

![GREEN-DESKTOP](assets/fr/28.webp)

E é isso, agora você sabe como configurar facilmente o software Blockstream Green para gerenciar sua carteira Bitcoin em uma carteira de hardware.
Se você achou este tutorial útil, eu apreciaria se você pudesse deixar um joinha abaixo. Sinta-se livre para compartilhar este artigo em suas redes sociais. Muito obrigado!
Eu também recomendo conferir este tutorial completo sobre o aplicativo móvel Blockstream Green para configurar uma carteira quente:

https://planb.network/tutorials/wallet/blockstream-green