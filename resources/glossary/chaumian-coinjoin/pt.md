---
term: CHAUMIAN COINJOIN
---

Um protocolo de coinjoin que utiliza as assinaturas cegas de David Chaum e Tor para comunicações entre os participantes e o servidor do coordenador. O objetivo de um Chaumian coinjoin é garantir aos participantes que o coordenador não pode roubar bitcoins, nem vincular as entradas e saídas juntas.

Para alcançar isso, os usuários submetem sua entrada e um endereço de recepção criptograficamente cegado ao coordenador. Este endereço, uma vez desvelado, destina-se a receber os bitcoins como uma saída do coinjoin. O coordenador assina esses tokens e os devolve aos usuários. Os usuários então se reconectam anonimamente ao servidor do coordenador com uma nova identidade Tor e revelam seus endereços de saída em texto simples para a construção da transação. O coordenador pode verificar que todos esses endereços de recepção vêm de usuários legítimos, pois ele já assinou sua versão cegada com sua chave privada. No entanto, ele não pode associar um endereço de saída específico a um usuário de entrada dado. Portanto, não há ligação entre as entradas e saídas, mesmo do ponto de vista do coordenador. Uma vez que a transação é construída pelo coordenador, ele a envia de volta aos participantes que a assinam para desbloquear sua entrada, após verificar que sua saída está de fato nesta transação. Os participantes enviam a assinatura ao coordenador. Uma vez que todas as assinaturas são coletadas, o coordenador pode transmitir a transação de coinjoin na rede Bitcoin.

![](../../dictionnaire/assets/38.png)

Este método garante que o coordenador não pode comprometer o anonimato dos participantes nem roubar os bitcoins durante todo o processo de coinjoin.

É difícil determinar com certeza quem introduziu pela primeira vez a ideia de coinjoin no Bitcoin e quem teve a ideia de usar as assinaturas cegas de David Chaum neste contexto. Geralmente se acredita que Gregory Maxwell foi o primeiro a discuti-lo em [uma mensagem no BitcoinTalk em 2013](https://bitcointalk.org/index.php?topic=279249.0):

> *"Usando assinaturas cegas de Chaum: Usuários se conectam e fornecem entradas (e endereços de troco) bem como uma versão criptograficamente cegada do endereço para o qual desejam enviar suas moedas privadas; o servidor assina os tokens e os devolve. Usuários se reconectam anonimamente, desmascaram seus endereços de saída e os retornam ao servidor. O servidor pode ver que todas as saídas foram assinadas por ele e que, portanto, todas as saídas vêm de participantes válidos. Mais tarde, as pessoas se reconectam e assinam."*

Maxwell, G. (2013, 22 de agosto). *CoinJoin: Privacidade do Bitcoin para o mundo real*. Fórum BitcoinTalk. https://bitcointalk.org/index.php?topic=279249.0
No entanto, existem outras menções anteriores, tanto para as assinaturas de Chaum no contexto de mistura, quanto para coinjoins. [Em junho de 2011, Duncan Townsend apresentou no BitcoinTalk](https://bitcointalk.org/index.php?topic=12751.0) um mixer que usa as assinaturas de Chaum de uma maneira bastante semelhante aos modernos Chaumian coinjoins. No mesmo tópico, há [uma mensagem de hashcoin em resposta a Duncan Townsend](https://bitcointalk.org/index.php?topic=12751.msg315793#msg315793) para melhorar seu mixer. Esta mensagem apresenta precisamente o que mais se assemelha a coinjoins. Há também uma menção de um sistema similar em [uma mensagem de Alex Mizrahi em 2012](https://gist.github.com/killerstorm/6f843e1d3ffc38191aebca67d483bd88#file-laundry), enquanto ele estava aconselhando os criadores do Tenebrix. O termo "coinjoin" em si não teria sido inventado por Greg Maxwell, mas viria de uma ideia de Peter Todd.