---
name: Introduction aux algorithmes cryptographiques de Bitcoin
goal: Comprendre la création d’un portefeuille Bitcoin d’un point de vue cryptographique
objectives:
  - Démystifier la terminologie de la cryptographie liée aux Bitcoin.
  - Maîtriser la création d'un portefeuille Bitcoin.
  - Comprendre la structure d'un portefeuille Bitcoin.
  - Comprendre les adresses et chemin de dérivation
---

# Un voyage au cœur de la cryptographie

Vous êtes fasciné par Bitcoin ? Vous vous demandez comment fonctionne un portefeuille Bitcoin ? Préparez-vous à embarquer dans un voyage captivant au cœur de la cryptographie ! Loïc, notre expert, vous guidera à travers les méandres de la création d'un portefeuille Bitcoin, dévoilant les mystères derrière les termes techniques intimidants tels que le hachage, la dérivation des clés et les courbes elliptiques.

Cette formation vous dotera non seulement des connaissances pour comprendre la structure d'un portefeuille Bitcoin, mais vous préparera également à plonger plus profondément dans le passionnant univers de la cryptographie. Alors, êtes-vous prêt à entreprendre ce voyage ? Rejoignez-nous et transformez votre curiosité en compétence !

+++

# Introduction
<partId>32960669-d13a-592f-a053-37f70b997cbf</partId>

## Introduction à la cryptographie
<chapterId>fb4e8857-ea35-5a8a-ae8a-5300234e0104</chapterId>


***REFAIRE L'INTRO***



Avant d'explorer en détail le fonctionnement et la construction des portefeuilles Bitcoin, nous allons parcourir plusieurs chapitres qui vous présentent les bases indispensables en cryptographie pour bien comprendre la suite.




# Les fonctions de hachage
<partId>3713fee1-2ec2-512e-9e97-b6da9e4d2f17</partId>

## Introduction aux fonctions de hachage
<chapterId>dba011f5-1805-5a48-ac2b-4bd637c93703</chapterId>

Le premier type d'algorithmes cryptographiques utilisé sur Bitcoin regroupe les fonctions de hachage. Elles jouent un rôle essentiel à différents niveaux du protocole, mais également au sein des portefeuilles Bitcoin. Découvrons ensemble ce qu'est une fonction de hachage et à quoi ça sert sur Bitcoin.

### Définition et principe du hachage

Le hachage est un procédé qui permet de transformer une information de longueur arbitraire en une autre information de longueur fixe par le biais d'une fonction de hachage cryptographique. Autrement dit, une fonction de hachage prend une entrée de taille quelconque et la convertit en une empreinte de taille fixe, appelée "hash".

Le hash peut également parfois être désigné par les termes "digest", "condensat", "condensé" ou "haché".

Par exemple, la fonction de hachage SHA256 produit un hash d'une longueur fixe de 256 bits. Ainsi, si l’on utilise l’entrée "*PlanB*", un message de longueur arbitraire, le hash généré sera l'empreinte de 256 bits suivante :

```txt
24f1b93b68026bfc24f5c8265f287b4c940fb1664b0d75053589d7a4f821b688
```

001

### Caractéristiques des fonctions de hachage

Ces fonctions de hachage cryptographiques possèdent plusieurs caractéristiques essentielles qui les rendent particulièrement utiles dans le contexte de Bitcoin et d'autres systèmes informatiques :
1. L'irréversibilité (ou résistance à la préimage)
2. La résistance à la falsification (effet avalanche)
3. La résistance aux collisions
4. La résistance à la seconde préimage

#### 1. L'irréversibilité (résistance à la préimage) :

L'irréversibilité signifie qu'il est facile de calculer le hash à partir de l'information en entrée, mais que le calcul inverse, c'est-à-dire retrouver l'entrée à partir du hash, est pratiquement impossible. Cette propriété rend les fonctions de hachage parfaites pour créer des empreintes numériques uniques sans compromettre les informations d'origine. On parle souvent de fonction à sens unique ou de "*trap door function*" pour décrire cette caractéristique. 

Dans l'exemple donné, obtenir le hash `24f1b9…` en connaissant l'entrée "*PlanB*" est simple et rapide. Toutefois, retrouver le message "*PlanB*" en connaissant uniquement `24f1b9…` est impossible.

002

Il est donc impossible trouver une préimage $m$ pour un hash $h$ tel que $h = \text{HASH}(m)$, où $\text{HASH}$ est une fonction de hachage.

#### 2. La résistance à la falsification (effet avalanche)

La deuxième caractéristique est la résistance à la falsification, également connue sous le nom d'**effet avalanche**. Cette caractéristique s'observe sur une fonction de hachage si une petite modification du message d'entrée entraîne une modification radicale du hash de sortie.

Si l'on reprend notre exemple avec l’entrée "*PlanB*" et la fonction SHA256, nous avons vu que le hash généré est le suivant :

```txt
24f1b93b68026bfc24f5c8265f287b4c940fb1664b0d75053589d7a4f821b688
```

Si l'on modifie très légèrement l'entrée en utilisant cette fois "*Planb*", alors le simple passage d'un "B" majuscule à un "b" minuscule modifie complètement le hash en sortie de SHA256 :

```txt
bb038b4503ac5d90e1205788b00f8f314583c5e22f72bec84b8735ba5a36df3f
```

003

Cette propriété garantit que même une altération minime du message original est immédiatement détectable, car cela ne modifie pas seulement une petite partie du hash, mais bien tout le hash. Cela pourra nous intéresser dans divers domaines pour vérifier l'intégrité de messages, de logiciels ou encore, de transactions Bitcoin.

#### 3. La résistance aux collisions

La troisième caractéristique est la résistance aux collisions. Une fonction de hachage est résistante aux collisions s'il est computationnellement impossible de trouver 2 messages différents qui produisent le même hash en sortie de la fonction. Formellement, il est difficile de trouver deux messages distincts $m_1$ et $m_2$ tels que :

$$
\text{HASH}(m_1) = \text{HASH}(m_2)
$$

004

En réalité, il est mathématiquement inévitable que des collisions existent pour les fonctions de hachage, car la taille des entrées peut être supérieure à celle des sorties. C'est ce que l'on appelle le principe des tiroirs de Dirichlet : si $n$ objets sont répartis dans $m$ tiroirs, avec $m < n$, alors au moins un tiroir contiendra forcément deux objets ou plus. Pour une fonction de hachage, ce principe s'applique, car le nombre de messages possibles est (presque) infini, tandis que le nombre de hash possibles est fini ($2^{256}$ dans le cas de SHA256).

Ainsi, cette caractéristique ne signifie pas qu'il n'existe aucune collision pour les fonctions de hachage, mais plutôt qu'une bonne fonction de hachage rend la probabilité de trouver une collision négligeable. Cette caractéristique n’est par exemple plus vérifiée sur les algorithmes SHA-0 et SHA-1, prédécesseurs des SHA-2, pour lesquels des collisions ont été trouvées. Ces fonctions sont donc aujourd’hui déconseillées et souvent considérées comme désuètes.

Pour une fonction de hachage de $n$ bits, la résistance aux collisions est de l'ordre de $2^{\frac{n}{2}}$, conformément à l'attaque de l'anniversaire. Par exemple, pour SHA256 ($n = 256$), la complexité de trouver une collision est de l'ordre de $2^{128}$ essais. Concrètement, cela veut dire que si l'on passe $2^{128}$ messages différents dans la fonction, on va probablement trouver une collision. 

#### 4. La résistance à la seconde préimage

La résistance à la seconde préimage est une autre caractéristique importante des fonction de hachage. Elle stipule qu'étant donné un message $m_1$ et son hash $h$, il est computationnellement infaisable de trouver un autre message $m_2 \neq m_1$ tel que :

$$
\text{HASH}(m_1) = \text{HASH}(m_2)
$$

La résistance à la seconde préimage est donc un petit peu similaire à la résistance à la collision, sauf qu'ici, l'attaque est plus difficile car l'attaquant ne peut pas choisir librement $m_1$.

005

### Applications des fonctions de hachage dans Bitcoin

La fonction de hachage la plus utilisée dans Bitcoin est **SHA-256** ("*Secure Hash Algorithm 256 bits"*). Conçue au début des années 2000 par la NSA et standardisée par le NIST, elle produit un hash de 256 bits en sortie.

Cette fonction est utilisée dans de nombreux aspects de Bitcoin. Au niveau protocolaire, elle intervient dans le mécanisme de Proof-of-Work, où elle est appliquée en double hachage pour rechercher une collision partielle entre l'en-tête d'un bloc candidat, créé par un mineur, et la cible de difficulté. Si cette collision partielle est trouvée, le bloc candidat devient valide et peut être ajouté à la blockchain.

SHA256 est également utilisée dans la construction des arbres de Merkle, qui est notamment l'accumulateur utilisé pour l'enregistrement des transactions dans les blocs. On retrouve aussi cette structure dans le protocole Utreexo qui permet de réduire la taille de l'UTXO Set. Aussi, avec l'introduction de Taproot en 2021, SHA256 est exploitée dans les MAST (*Merkelised Alternative Script Tree*), qui permettent de ne révéler que les conditions de dépense effectivement utilisées dans un script, sans divulguer les autres options possibles. On la retrouve également dans le calcul de l'identifiant des transactions, dans la transmission des paquets sur le réseau P2P, dans les signatures électroniques... Enfin, et c'est ce qui nous intéressera particulièrement dans cette formation, SHA256 est utilisée au niveau applicatif pour la construction des portefeuilles Bitcoin et la dérivation des adresses.

La plupart du temps, lorsque vous croiserez l'utilisation de SHA256 sur Bitcoin, ce sera en réalité un double hachage SHA256, noté "**HASH256**", et qui consiste simplement à appliquer SHA256 deux fois successivement :

$$
\text{HASH256}(m) = \text{SHA256}(\text{SHA256}(m))
$$

Cette pratique du double hachage ajoute une couche supplémentaire de sécurité contre certaines attaques potentielles, même si un SHA256 simple est aujourd'hui considéré comme sûr cryptographiquement.

Une autre fonction de hachage disponible dans le langage de Script et utilisée pour la dérivation des adresses de réception est la fonction **RIPEMD160**. Cette fonction produit un hash de 160 bits (donc plus court que SHA256). Elle est généralement combinée avec SHA256 pour former la fonction **HASH160** :

$$
\text{HASH160}(m) = \text{RIPEMD160}(\text{SHA256}(m))
$$

Cette combinaison est employée pour générer des hash plus courts, notamment dans la création de certaines adresses Bitcoin qui représentes des hachages de clés ou des hachages de script, ainsi que pour produire des empreintes de clés.

Enfin, au niveau applicatif uniquement, on utilise parfois également la fonction SHA512, qui intervient de manière indirecte dans la dérivation de clés pour les portefeuilles. Cette fonction est très similaire à SHA256 dans son fonctionnement ; toutes deux appartiennent à la même famille SHA2, mais SHA512 produit, comme son nom l'indique, un hash de 512 bits, contre 256 bits pour SHA256. Nous détaillerons son utilisation dans les chapitres suivants.

Vous connaissez maintenant les bases indispensables sur les fonctions de hachage pour la suite. Dans le chapitre suivant, je vous propose de découvrir plus en détail le fonctionnement de la fonction qui est au cœur de Bitcoin : SHA256. Nous allons la décortiquer pour comprendre comment elle parvient à obtenir les caractéristiques que nous avons décrites ici. Ce prochain chapitre est assez long et technique, mais il n'est pas indispensable pour suivre la suite de la formation. Donc, si vous avez des difficultés à le comprendre, ne vous inquiétez pas et passez directement au chapitre suivant, qui sera lui bien plus accessible.






## Les rouages de SHA256
<chapterId>905eb320-f15b-5fb6-8d2d-5bb447337deb</chapterId>

Nous avons vu précédemment que les fonctions de hachage possèdent des caractéristiques importantes qui justifient leur utilisation sur Bitcoin. Examinons maintenant les mécanismes internes de ces fonctions de hachage qui leur confèrent ces propriétés, et pour ce faire, je vous propose de décortiquer le fonctionnement de SHA256.

Les fonctions SHA256 et SHA512 appartiennent à la même famille des SHA2. Leur mécanisme est basé sur une construction spécifique appelée **construction de Merkle-Damgård**. RIPEMD-160 utilise également ce même type de construction.

Pour rappel, nous avons donc un message  taille arbitraire en entrée de SHA256, et nous allons le passer dans la fonction pour obtenir un hash de 256 bits en sortie.

### Pré-traitement de l'input

Pour commencer, il faut préparer notre message $m$ en entrée afin qu'il ait une longueur standard qui est un multiple de 512 bits. Cette étape est importante pour le bon fonctionnement de l'algorithme par la suite.

Pour ce faire, on commence avec l'étape des bits de rembourrage. On ajoute d'abord un bit séparateur `1` au message, suivi d'un certain nombre de bits `0`. Le nombre de bits `0` ajoutés est calculé de manière à ce que la longueur totale du message après cet ajout soit congrue à 448 modulo 512. On a donc la longueur $L$ du message avec les bits de rembourrage qui est égale à :

$$
L \equiv 448 \mod 512
$$

"$\text{mod}$", pour modulo, est une opération mathématique qui, entre deux nombres entiers, renvoie le reste de la division euclidienne du premier par le second. Par exemple : $16 \mod 5 = 1$. C'est une opération très utilisée en cryptographie.

Ici, l'étape du rembourrage garantit que, après l'ajout des 64 bits de l'étape suivante, la longueur totale du message égalisé sera un multiple de 512 bits. Si le message initial a une longueur de $M$ bits, le nombre ($N$) de bits `0` à ajouter est donc :

$$
N = (448 - (M + 1) \mod 512) \mod 512
$$

Par exemple, si le message initial mesure 950 bits, le calcul sera le suivant : 

$$
\begin{align*}
M & = 950 \\
M + 1 & = 951 \\
(M + 1) \mod 512 & = 951 \mod 512 \\
& = 951 - 512 \cdot \left\lfloor \frac{951}{512} \right\rfloor \\
& = 951 - 512 \cdot 1 \\
& = 951 - 512 \\
& = 439 \\
\\
448 - (M + 1) \mod 512 & = 448 - 439 \\
& = 9 \\
\\
N & = (448 - (M + 1) \mod 512) \mod 512 \\
N & = 9 \mod 512 \\
& = 9
\end{align*}
$$

Nous aurions ainsi 9 `0` en plus du séparateur `1`. Nos bits de rembourrage à ajouter directement après notre message $M$ seraient donc :

```txt
1000 0000 00
```

Après avoir ajouté les bits de rembourrage à notre message $M$, on ajoute également une représentation de 64 bits de la longueur originale du message $M$, exprimée en binaire. Cela permet à la fonction de hachage d'être sensible à l'ordre des bits et à la longueur du message.

Si l'on reprend notre exemple avec un message initial de 950 bits, on va convertir le nombre décimal `950` en nombre binaire ce qui nous donne `1110 1101 10`. On complète ce nombre avec des zéros à la base pour faire 64 bits au total. Dans notre exemple, cela donne :

```txt
0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0011 1011 0110
```

Ce rembourrage de la taille est ajouté à la suite du rembourrage des bits. Le message après notre pré-traitement se compose donc de trois parties :
1. Le message original $M$ ;
2. Un bit `1` suivi de plusieurs bits `0` pour former le rembourrage des bits ;
3. Une représentation de 64 bits de la longueur de $M$ pour former de le rembourrage avec la taille.

006

### Initialisation des variables

SHA-256 utilise huit variables d'état initiales, notées $A$ à $H$, chacune de 32 bits. Ces variables sont initialisées avec des constantes spécifiques, qui sont les parties fractionnaires des racines carrées des huit premiers nombres premiers. Nous allons utiliser ces valeurs par la suite durant le processus du hachage :

- $A = 0x6a09e667$
- $B = 0xbb67ae85$
- $C = 0x3c6ef372$
- $D = 0xa54ff53a$
- $E = 0x510e527f$
- $F = 0x9b05688c$
- $G = 0x1f83d9ab$
- $H = 0x5be0cd19$

SHA-256 utilise également 64 autres constantes, notées $K_0$ à $K_{63}$, qui sont les parties fractionnaires des racines cubiques des 64 premiers nombres premiers :

$$
K[0 \ldots 63] = \begin{pmatrix}
0x428a2f98, & 0x71374491, & 0xb5c0fbcf, & 0xe9b5dba5, \\
0x3956c25b, & 0x59f111f1, & 0x923f82a4, & 0xab1c5ed5, \\
0xd807aa98, & 0x12835b01, & 0x243185be, & 0x550c7dc3, \\
0x72be5d74, & 0x80deb1fe, & 0x9bdc06a7, & 0xc19bf174, \\
0xe49b69c1, & 0xefbe4786, & 0x0fc19dc6, & 0x240ca1cc, \\
0x2de92c6f, & 0x4a7484aa, & 0x5cb0a9dc, & 0x76f988da, \\
0x983e5152, & 0xa831c66d, & 0xb00327c8, & 0xbf597fc7, \\
0xc6e00bf3, & 0xd5a79147, & 0x06ca6351, & 0x14292967, \\
0x27b70a85, & 0x2e1b2138, & 0x4d2c6dfc, & 0x53380d13, \\
0x650a7354, & 0x766a0abb, & 0x81c2c92e, & 0x92722c85, \\
0xa2bfe8a1, & 0xa81a664b, & 0xc24b8b70, & 0xc76c51a3, \\
0xd192e819, & 0xd6990624, & 0xf40e3585, & 0x106aa070, \\
0x19a4c116, & 0x1e376c08, & 0x2748774c, & 0x34b0bcb5, \\
0x391c0cb3, & 0x4ed8aa4a, & 0x5b9cca4f, & 0x682e6ff3, \\
0x748f82ee, & 0x78a5636f, & 0x84c87814, & 0x8cc70208, \\
0x90befffa, & 0xa4506ceb, & 0xbef9a3f7, & 0xc67178f2
\end{pmatrix}
$$

### Division de l'input

Maintenant que nous avons un input égalisé, nous allons maintenant aborder la phase de traitement principal de l'algorithme SHA256 : la fonction de compression. Cette étape est très importante, car c'est principalement elle qui confère à la fonction de hachage ses propriétés cryptographiques que nous avons étudiées dans le chapitre précédent.

Tout d'abord, on commence par diviser notre message égalisé (résultat des étapes de pré-traitement) en plusieurs blocs $P$ de 512 bits chacun. Si notre message égalisé a une taille totale de $n \times 512$ bits, nous aurons donc $n$ blocs, chacun de 512 bits. Chaque bloc de 512 bits sera traité individuellement par la fonction de compression, qui consiste en 64 tours d'opérations successives. Nommons ces blocs $P_1$, $P_2$, $P_3$...

### Opérations logiques

Avant d'explorer en détail la fonction de compression, il est important de comprendre les opérations logiques de base utilisées dans celle-ci. Ces opérations, basées sur l'algèbre de Boole, opèrent au niveau des bits. Les opérations logiques de base utilisées sont :
- **La conjonction (AND)** : notée $\land$, correspond à un "ET" logique.
- **La disjonction (OR)** : notée $\lor$, correspond à un "OU" logique.
- **La négation (NOT)** : notée $\lnot$, correspond à un "NON" logique.

À partir de ces opérations de base, nous pouvons définir des opérations plus complexes, telles que le "OU exclusif" (XOR) noté $\oplus$, qui est très utilisé en cryptographie.

Chaque opération logique peut être représentée par une table de vérité, qui indique le résultat pour toutes les combinaisons possibles des valeurs d'entrée en binaire (deux opérandes $p$ et $q$).

Pour le XOR ($\oplus$) :

| $p$ | $q$ | $p \oplus q$ |
| --- | --- | ------------ |
| 0   | 0   | 0            |
| 0   | 1   | 1            |
| 1   | 0   | 1            |
| 1   | 1   | 0            |

Pour le AND ($\land$) :

| $p$ | $q$ | $p \land q$ |
| --- | --- | ----------- |
| 0   | 0   | 0           |
| 0   | 1   | 0           |
| 1   | 0   | 0           |
| 1   | 1   | 1           |

Pour le NOT ($\lnot p$) :

| $p$ | $\lnot p$ |
| --- | --------- |
| 0   | 1         |
| 1   | 0         |


Prenons un exemple pour bien comprendre le fonctionnement de l'opération XOR au niveau des bits. Si nous avons deux nombres binaires sur 6 bits :

- $a = 101100$
- $b = 001000$

Alors :

$$
a \oplus b = 101100 \oplus 001000 = 100100
$$

En appliquant le XOR bit par bit :

| Position du bit | $a$ | $b$ | $a \oplus b$ |
| --------------- | --- | --- | ------------ |
| 1               | 1   | 0   | 1            |
| 2               | 0   | 0   | 0            |
| 3               | 1   | 1   | 0            |
| 4               | 1   | 0   | 1            |
| 5               | 0   | 0   | 0            |
| 6               | 0   | 0   | 0            |

Le résultat est donc $100100$.

En plus des opérations logiques, la fonction de compression utilise des opérations de décalage de bits, qui vont jouer un rôle essentiel pour la diffusion des bits dans l'algorithme.

Tout d'abord il y a l'opération de décalage logique à droite, notée $ShR_n(x)$, qui décale tous les bits de $x$ vers la droite de $n$ positions, en complétant les bits vacants à gauche par des zéros.

Par exemple, pour $x = 101100001$ (sur 9 bits) et $n = 4$ :

$$
ShR_4(101100001) = 000010110
$$

Schématiquement, l'opération de décalage à droite pourrait être vue comme cela :

007

Une autre opération que l'on utilise dans SHA256 pour manier les bits est celle de la rotation circulaire à droite, notée $RotR_n(x)$, qui décale les bits de $x$ vers la droite de $n$ positions, en réinsérant les bits décalés à droite au début de la chaîne.

Par exemple, pour $x = 101100001$ (sur 9 bits) et $n = 4$ :

$$
RotR_4(101100001) = 000110110
$$

Schématiquement, l'opération de décalage circulaire à droite pourrait être vue comme cela :

008

### Fonction de compression

Maintenant que nous avons compris les opérations de base, examinons la fonction de compression de SHA256 en détail.

À l'étape précédente, nous avons donc divisé notre input en plusieurs morceaux $P$ de 512 bits chacun. Pour chaque bloc $P$ de 512 bits, nous avons :
- **Les mots de message $W_i$** : pour $i$ de 0 à 63.
- **Les constantes $K_i$** : pour $i$ de 0 à 63, définies à l'étape précédente.
- **Les variables d'état $A, B, C, D, E, F, G, H$** : initialisées avec les valeurs de l'étape précédente.

Les 16 premiers mots, $W_0$ à $W_{15}$, sont directement extraits du bloc $P$ de 512 bits traité. Chaque mot $W_i$ est constitué de 32 bits consécutifs du bloc. On prend donc par exemple notre premier morceau de l'input $P_1$, et on le divise encore en de plus petits morceaux de 32 bits chacun que l'on appelle les mots.

Les 48 mots suivants ($W_{16}$ à $W_{63}$) sont générés à l'aide de la formule suivante :

$$
W_i = W_{i-16} + \sigma_0(W_{i-15}) + W_{i-7} + \sigma_1(W_{i-2}) \mod 2^{32}
$$

Avec :
- $\sigma_0(x) = RotR_7(x) \oplus RotR_{18}(x) \oplus ShR_3(x)$
- $\sigma_1(x) = RotR_{17}(x) \oplus RotR_{19}(x) \oplus ShR_{10}(x)$

Dans ce cas, $x$ est égal à $W_{i-15}$ pour $\sigma_0(x)$ et $W_{i-2}$ pour $\sigma_1(x)$.

Une fois que nous avons déterminé tous les mots $W_i$ pour notre morceau de 512 bits, nous pouvons passer à la fonction de compression qui consiste à effectuer 64 tours.

009

Pour chaque tour $i$ de 0 à 63, nous avons donc 3 types d'input différents. D'abord, les $W_i$ que nous venons de déterminer, constitués en partie de notre morceau $P_n$ du message. Ensuite, les 64 constantes $K_i$. Enfin, nous utilisons les variables d'état $A$, $B$, $C$, $D$, $E$, $F$, $G$, et $H$, qui vont évoluer tout au long du processus de hachage et être modifiées à chaque fonction de compression. Cependant, pour le premier morceau $P_1$, on utilise les constantes initiales données précédemment.

Nous effectuons donc les opérations suivantes sur nos inputs :

- **Fonction $\Sigma_0$ :**
$$
\Sigma_0(A) = RotR_2(A) \oplus RotR_{13}(A) \oplus RotR_{22}(A)
$$

- **Fonction $\Sigma_1$ :**
$$
\Sigma_1(E) = RotR_6(E) \oplus RotR_{11}(E) \oplus RotR_{25}(E)
$$

- **Fonction $Ch$ ("*Choose*") :**
$$
Ch(E, F, G) = (E \land F) \oplus (\lnot E \land G)
$$

- **Fonction $Maj$ ("*Majority*") :**
$$
Maj(A, B, C) = (A \land B) \oplus (A \land C) \oplus (B \land C)
$$

Nous calculons ensuite 2 variables temporaires :

- $temp1$ :
$$
temp1 = H + \Sigma_1(E) + Ch(E, F, G) + K_i + W_i \mod 2^{32}
$$

- $temp2$ :
$$
temp2 = \Sigma_0(A) + Maj(A, B, C) \mod 2^{32}
$$

Ensuite, nous mettons à jour les variables d'état comme suit :

$$
\begin{cases}
H = G \\
G = F \\
F = E \\
E = D + temp1 \mod 2^{32} \\
D = C \\
C = B \\
B = A \\
A = temp1 + temp2 \mod 2^{32}
\end{cases}
$$

Le schéma suivant représente un tour de la fonction de compression de SHA256 comme nous venons de le décrire :

010

- Les flèches indiquent le flux des données ;
- Les boîtes représentent les opérations effectuées ;
- Les $+$ entourés représentent l'addition modulo $2^{32}$.

On peut déjà observer que ce tour nous donne en sortie de nouvelles variables d'état $A$, $B$, $C$, $D$, $E$, $F$, $G$, et $H$. Ces nouvelles variables serviront d’entrée pour le tour suivant, qui produira à son tour de nouvelles variables $A$, $B$, $C$, $D$, $E$, $F$, $G$, et $H$, que l'on utilisera pour le tour d'après. Ce processus se poursuit ainsi jusqu'au 64ème tour.

Après les 64 tours, nous mettons à jour les valeurs initiales des variables d'état en les additionnant aux valeurs finales en sortie du tour n°64 :

$$
\begin{cases}
A = A_{\text{initial}} + A \mod 2^{32} \\
B = B_{\text{initial}} + B \mod 2^{32} \\
C = C_{\text{initial}} + C \mod 2^{32} \\
D = D_{\text{initial}} + D \mod 2^{32} \\
E = E_{\text{initial}} + E \mod 2^{32} \\
F = F_{\text{initial}} + F \mod 2^{32} \\
G = G_{\text{initial}} + G \mod 2^{32} \\
H = H_{\text{initial}} + H \mod 2^{32}
\end{cases}
$$

Ces nouvelles valeurs de $A$, $B$, $C$, $D$, $E$, $F$, $G$, et $H$ serviront de valeurs initiales pour le bloc suivant, $P_2$. Pour ce bloc $P_2$, on reproduit le même processus de compression avec 64 tours, puis on met à jour les variables pour le bloc $P_3$, et ainsi de suite jusqu'au dernier bloc de notre input égalisé.

Après avoir traité tous les blocs du message, nous concaténons les valeurs finales des variables $A$, $B$, $C$, $D$, $E$, $F$, $G$, et $H$ pour former le hash final de 256 bits de notre fonction de hachage :

$$
\text{Hash} = A \, || \, B \, || \, C \, || \, D \, || \, E \, || \, F \, || \, G \, || \, H
$$

Chaque variable est un entier de 32 bits, donc leur concaténation donne bien toujours un résultat de 256 bits, et ce, quelle que soit la taille de notre message en input de la fonction de hachage.

### Justification des propriétés cryptographiques

Mais alors, en quoi cette fonction est-elle irréversible, résistante aux collisions et résistante à la falsification ? 

Pour la résistance à la falsification, c’est assez simple à comprendre. Il y a tellement de calculs effectués en cascade, qui dépendent à la fois de l’input et des constantes, que la moindre modification du message initial change complètement le chemin parcouru, et donc change complètement le hash en sortie. C'est ce que l'on appelle l'effet avalanche. Cette propriété est en partie assurée par le mélange des états intermédiaires avec les états initiaux pour chaque morceau.

Ensuite, lorsque l’on parle d’une fonction de hachage cryptographique, le terme "irréversibilité" n’est généralement pas utilisé. À la place, on parle de “résistance à la préimage” qui spécifie que pour tout $y$ donné, il est difficile de trouver un $x$ tel que $h(x) = y$. Cette résistance à la préimage, quant à elle, est garantie par la complexité algébrique et la forte non-linéarité des opérations effectuées dans la fonction de compression, ainsi que par la perte de certaines informations dans le processus. Par exemple, pour un résultat donné à une addition modulo, il existe plusieurs opérandes possibles :

$$
3+2 \mod 10 = 5 \\
7+8 \mod 10 = 5 \\
5+10 \mod 10 = 5
$$

On voit bien dans cet exemple qu’en connaissant uniquement le modulo utilisé (10) et le résultat (5), on ne peut pas déterminer avec certitude quelles sont les deux bonnes opérandes utilisées dans l’addition. On dit qu’il existe plusieurs congrus modulo 10.

Pour l’opération XOR, on est confronté au même problème. Rappelez-vous de la table de vérité de cette opération : toute sortie de 1 bit peut être déterminée par deux configurations différentes en entrées qui ont exactement la même probabilité d’être les bonnes valeurs. On ne peut donc pas déterminer avec certitude les opérandes d’un XOR en connaissant uniquement son résultat. Si on augmente la taille des opérandes du XOR, le nombre de possibles entrées en connaissant uniquement le résultat augmente de façon exponentielle. De plus, le XOR est souvent utilisé aux côtés d’autres opérations au niveau du bit, comme l’opération $\text{RotR}$, qui viennent ajouter encore plus d’interprétations possibles au résultat.

On utilise également au sein de la fonction de compression l’opération $\text{ShR}$. Celle-ci vient supprimer une partie de l’information de base qui est donc impossible à retrouver par la suite. Il n’y a encore une fois pas de moyen algébrique pour inverser cette opération. Toutes ces opérations à sens unique et ces opérations de perte d’information sont utilisées à de très nombreuses reprises dans les fonctions de compression. Le nombre de possibles entrées pour une sortie donnée est donc presque infini, et chaque tentative de calcul inverse mènerait à des équations avec un nombre d’inconnus très élevé qui augmenterait exponentiellement à chaque étape.

Enfin, pour la caractéristique de résistance aux collisions, plusieurs paramètres entrent en compte. Le pré-traitement du message d’origine tient un rôle essentiel. Sans ce pré-traitement, il pourrait être plus facile de trouver des collisions sur la fonction. Bien que, théoriquement, des collisions existent (en raison du principe des tiroirs), la structure de la fonction de hachage, combinée aux propriétés précédentes, rend la probabilité de trouver une collision extrêmement faible.

Pour qu'une fonction de hachage soit résistante aux collisions, il est essentiel que :

- La sortie soit imprévisible : Toute prévisibilité peut être exploitée pour trouver des collisions plus rapidement qu'avec une attaque par force brute. La fonction assure que chaque bit de la sortie dépend de façon non triviale de l'entrée. En d'autres termes, la fonction est conçue pour que chaque bit du résultat final ait une probabilité indépendante d'être 0 ou 1, même si cette indépendance n'est pas absolue en pratique.
- La distribution des hash soit pseudo-aléatoire : Cela assure que les hash sont répartis de manière uniforme.
- La taille du hash soit conséquente : au plus l'espace possible pour les résultats est grand, au plus il est difficile de trouver une collision.

Les cryptographes conçoivent ces fonctions en évaluant les meilleures attaques possibles pour trouver des collisions, puis en ajustant les paramètres pour rendre ces attaques inefficaces.

### Construction de Merkle-Damgård

La structure de SHA256 est basée sur la construction de Merkle-Damgård, qui permet de transformer une fonction de compression en une fonction de hachage pouvant traiter des messages de longueur arbitraire. C'est justement ce que nous venons de voir dans ce chapitre.

Cependant, certaines vieilles fonctions de hachage comme SHA1 ou MD5, qui utilisent cette construction spécifique, sont vulnérables aux attaques par extension de longueur. C'est une technique qui permet à un attaquant qui connaît le hash d’un message $M$ et la longueur de $M$ (sans connaître le message lui-même) de calculer le hash d’un message $M'$ formé de $M$ concaténé avec un contenu supplémentaire.

SHA256, même si elle utilise le même type de construction, est en théorie résistante à ce type d'attaque, contrairement à SHA1 et MD5. C'est peut-être ce qui pourrait expliquer le mystère du double hachage implémenté partout dans Bitcoin par Satoshi Nakamoto. Pour éviter ce type d'attaque, il est possible que Satoshi ait préféré utiliser un double SHA256 :

$$
\text{HASH256}(m) = \text{SHA256}(\text{SHA256}(m))
$$

Cela renforce la sécurité contre les attaques potentielles liées à la construction de Merkle-Damgård, mais cela n'augmente absolument pas la sécurité du processus de hachage en termes de résistance aux collisions. De plus, même si SHA256 avait été vulnérable à ce type d'attaque, cela n'aurait pas eu d'impact grave, car tous les cas d'utilisation des fonctions de hachage dans Bitcoin concernent des données publiques. Or, l'attaque par extension de longueur peut n'être utile pour un attaquant que si les données hachées sont privées et que l'utilisateur a utilisé la fonction de hachage comme un mécanisme d'authentification pour ces données, à la manière d'un MAC. Ainsi, l'implémentation du double hachage reste un mystère dans la conception de Bitcoin.

Maintenant que nous avons vu en détail le fonctionnement des fonctions de hachage, et notamment de SHA256, utilisée partout dans Bitcoin, nous allons nous pencher plus spécifiquement sur les algorithmes de dérivation employés au niveau applicatif, notamment pour dériver les clés de votre portefeuille.



## Les algorithmes utilisés pour la dérivation
<chapterId>cc668121-7789-5e99-bf5e-1ba085f4f5f2</chapterId>

Sur Bitcoin au niveau applicatif, en complément des fonctions de hachage, on utilise des algorithmes de dérivation cryptographiques permettant de générer des données sécurisées à partir d'entrées initiales. Bien que ces algorithmes reposent sur des fonctions de hachage, ils répondent à des objectifs différents, notamment en termes d'authentification et de génération de clés. Ces algorithmes conservent en partie les caractéristiques des fonctions de hachage, telles que l'irréversibilité, la résistance à la falsification et la résistance aux collisions.

Sur les portefeuilles Bitcoin, on utilise principalement 2 algorithmes de dérivation :
1. **HMAC (*Hash-based Message Authentication Code*)**
2. **PBKDF2 (*Password-Based Key Derivation Function 2*)**

Nous allons explorer ensemble le fonctionnement et le rôle de chacun d'eux.

### HMAC-SHA512

HMAC est un algorithme cryptographique permettant de calculer un code d'authentification basé sur une combinaison d’une fonction de hachage et d’une clé secrète. Bitcoin utilise HMAC-SHA512, soit la variante de HMAC utilisant la fonction de hachage SHA512. Nous avons déjà vu dans le chapitre précédent que SHA512 fait parti de la même famille de fonction de hachage que SHA256, mais elle produit un output de 512 bits.

Voici son schéma de fonctionnement général avec $m$ le message en entrée et $K$ une clé secrète :

011

Étudions plus en détail ce qu’il se passe dans cette boîte noire HMAC-SHA512. Soit la fonction HMAC-SHA512 avec :
- $m$ : le message de taille arbitraire choisi par l’utilisateur (premier input) ;
- $K$ : la clé secrète arbitraire choisie par l’utilisateur (second input) ;
- $K'$ : la clé $K$ ajustée à la taille $B$ des blocs de la fonction de hachage (1024 bits pour SHA512, soit 128 octets) ;
- $\text{SHA512}$ : la fonction de hachage SHA512 ;
- $\oplus$ : l'opération XOR (ou exclusif) ;
- $\|$ : l’opérateur de concaténation, reliant les chaînes de bits bout-à-bout ;
- $\text{opad}$ : constante composée de l’octet $0x5c$ répété 128 fois
- $\text{ipad}$ : constante composée de l’octet $0x36$ répété 128 fois

Avant de calculer le HMAC, il est nécessaire d'égaliser la clé et les constantes selon la taille du bloc $B$. Par exemple, si la clé $K$ est plus courte que 128 octets, on la complète avec des zéros pour obtenir la taille $B$. Si $K$ est plus longue que 128 octets, on la compresse avec SHA512, puis on ajoute des zéros jusqu'à atteindre 128 octets. De cette manière on obtient une clé égalisée nommée $K'$.

Les valeurs de $\text{opad}$ et $\text{ipad}$ sont obtenues en répétant leur octet de base ($0x5c$ pour $\text{opad}$, $0x36$ pour $\text{ipad}$ ) jusqu'à atteindre la taille $B$. Ainsi, avec $B = 128$ octets, on a :
$$
\text{opad} = 0x5c5c\ldots5c \quad (\text{*128})
$$

Une fois le prétraitement réalisé, l'algorithme HMAC-SHA512 est défini par l'équation suivante :

$$
\text {HMAC-SHA512}_K(m) = \text{SHA512} \left( (K' \oplus \text{opad}) \parallel \text{SHA512} \left( (K' \oplus \text{ipad}) \parallel m \right) \right)
$$

Cette équation se décompose avec les étapes suivantes :
1. On XOR la clé ajustée $K'$ avec $\text{ipad}$ pour obtenir $\text{iKpad}$ ;
2. On XOR la clé ajustée $K'$ avec $\text{opad}$ pour obtenir $\text{oKpad}$ ;
3. On concatène $\text{iKpad}$ avec le message $m$.
4. On hache ce résultat avec SHA512 pour obtenir un hash intermédiaire $H_1$.
5. On concatène $\text{oKpad}$ avec $H_1$.
6. On hache ce résultat avec SHA512 pour obtenir le résultat final $H_2$.

Ces étapes peuvent être résumées schématiquement comme suit :

012

HMAC est utilisé dans Bitcoin notamment pour la dérivation des clés dans les portefeuilles HD (nous en parlerons plus en détails dans les prochains chapitres) et comme composant de PBKDF2.

### PBKDF2

PBKDF2 (*Password-Based Key Derivation Function 2*) est un algorithme de dérivation de clé destiné à renforcer la sécurité des mots de passe. L'algorithme applique une fonction pseudo-aléatoire (ici HMAC-SHA512) sur un mot de passe et un sel cryptographique, puis répète cette opération un certain nombre de fois pour obtenir une clé en sortie.

Dans Bitcoin, PBKDF2 est utilisé pour générer la graine d'un portefeuille HD à partir d’une phrase mnémonique et d'une passphrase (mais nous en parlerons plus en détail dans les prochains chapitres).

Le processus de PBKDF2 est le suivant, avec :
- $m$ : la phrase de récupération de l'utilisateur
- $s$ : la passphrase optionnelle pour augmenter la sécurité (champs vide si pas de passphrase)
- $n$ : le nombre d'itération de la fonction, dans notre cas c'est 2048

La fonction PBKDF2 est définie de manière itérative. Chaque itération prend en entrée le résultat de la précédente, le passe dans HMAC-SHA512, et combine les résultats successifs pour produire la clé finale :

$$
\text{PBKDF2}(m, s) = \text{HMAC-SHA512}^{2048}(m, s)
$$

Schématiquement, PBKDF2 peut être représenté comme suit :

013

Dans ce chapitre, nous avons exploré les fonctions HMAC-SHA512 et PBKDF2, qui utilisent les fonctions de hachage pour garantir l'intégrité et la sécurité des dérivations de clés dans le protocole Bitcoin. Dans le prochaine partie, nous allons nous pencher sur les signatures numériques, une autre méthode cryptographique largement utilisée sur Bitcoin.


# Les signatures numériques
<partId>76b58a00-0c18-54b9-870d-6b7e34029db8</partId>

## Signatures numériques et courbes elliptiques
<chapterId>c9dd9672-6da1-57f8-9871-8b28994d4c1a</chapterId>

![Signatures numériques et courbes elliptiques](https://youtu.be/gOjYiPkx4z8)

Où sont stockés ces fameux bitcoins ? Pas dans un portefeuille Bitcoin, comme on pourrait le penser. En réalité, un portefeuille Bitcoin conserve les clés privées nécessaires pour prouver la possession des bitcoins. Les bitcoins eux-mêmes sont enregistrés sur la blockchain, une base de données décentralisée qui archive toutes les transactions.

Dans le système Bitcoin, l'unité de compte est le bitcoin (notez le "b" minuscule). Ce dernier est divisible jusqu'à huit décimales, la plus petite unité étant le satoshi. Les UTXO, ou "Unspent Transaction Output", représentent les sorties de transactions non dépensées appartenant à une clef publique qui est elle-même liée mathématiquement à une clef privée. Pour dépenser ces bitcoins, il faut pouvoir répondre à la condition de dépense de la transaction. Une condition de dépense typique consiste à prouver au reste du réseau que l'utilisateur est le propriétaire légitime de la clef publique associée aux UTXO. Pour ce faire, il va devoir démontrer qu'il est en possession de la clé privée correspondante à la clé publique liée à chaque UTXO sans pour autant dévoiler la clef privée. 

C'est ce que permet la signature numérique. Elle sert de preuve mathématique démontrant la possession d'une clé privée associée à une clé publique spécifique. Cette technique de protection des données est essentiellement basée sur un domaine fascinant de la cryptographie appelé la cryptographie sur courbes elliptiques (ECC).

La signature peut etre vérifée mathématiquement par les autres parties prenante du réseau Bitcoin.

![image](assets/image/section2/0.webp)

Pour assurer la sécurité des transactions, Bitcoin fait appel à deux protocoles de signature numérique : l'ECDSA (Elliptic Curve Digital Signature Algorithm) et Schnorr. ECDSA est un protocole de signature intégré à Bitcoin depuis son lancement en 2009, tandis que les signatures de Schnorr ont été ajoutées plus récemment, en novembre 2021. Bien que ces deux protocoles reposent sur la cryptographie sur courbes elliptiques et utilisent des mécanismes mathématiques similaires, ils diffèrent principalement en termes de structure de signature.

Dans ce cours, nous présenterons l'algorithme ECDSA.

### Qu'est-ce qu'une courbe elliptique ?

La cryptographie sur courbe elliptique c'est un ensemble d'algorithmes qui utilisent une courbe elliptique pour ses differentes propriétés geométriques et mathématiques dans un objectif cryptographique et dont la sécurité se base sur la difficulté de calcul du logarithme discret.

Les courbes elliptiques sont utiles dans une variété d'applications cryptographiques sur le protocole Bitcoin, allant des échanges de clés au chiffrement asymétrique en passant par les signatures numériques. 

Les courbes élliptiques ont des propriétés intéressantes :

- la symétrie : Toute droite non verticale coupant deux points sur la courbe elliptique, recoupera la courbe en un troisieme point.
- Toute droite non verticale et tangeante à la courbe en un point, coupera toujours la courbe en un deuxieme point unique.

Le protocole Bitcoin utilise une courbe elliptique particulière nommée Secp256k1 pour effectuer ses opérations cryptographiques. 

Avant de plonger plus profondément dans ces mécanismes de signature, il est important de bien comprendre ce qu'est une courbe elliptique. Une courbe elliptique est définie par l'équation y² = x³ + ax + b. Tout point sur cette courbe a une symétrie distinctive qui est la clé de son utilité en cryptographie.

![image](assets/image/section2/1.webp)

En fin de compte, diverses courbes elliptiques sont reconnues comme étant sécurisées pour un usage cryptographique. Le plus connu est peut-être la courbe secp256r1. Cependant, pour Bitcoin, Satoshi Nakamoto a opté pour une autre courbe : la secp256k1.

Cette courbe se définit par les paramètres a=0 et b=7, et son équation est y² = x³ + 7 modulo n, avec n représentant le nombre premier qui détermine l'ordre de la courbe.

![image](assets/image/section2/2.webp)

La première image représente la courbe secp256k1 sur le corps des réels et son équation. 
La deuxième image est une représentation de la courbe secp256k1 sur le corps ZP, le corps des entiers naturels et positifs, modulo p où p est un nombre premier. Cela ressemble à un nuage de points. Nous utilisons ce corps des entiers naturels et positifs pour éviter les approximations.
p est un nombre premier, c'est l'ordre de la courbe qui est utilisé.
Finalement, l'équation qui est utilisée sur le protocole Bitcoin est :
$$
y^2 = (x^3 + 7) mod(p)
$$
L'équation de la courbe elliptique sur bitcoin correspond à la dernière équation sur l'image précédente.

Dans la prochaine section de ce cours, nous utiliserons des courbes qui sont sur le corps des réels simplement pour faciliter la compréhension.

## Calculer la clé publique à partir de la clé privée
<chapterId>fcb2bd58-5dda-5ecf-bb8f-ad1a0561ab4a</chapterId>

![Calculer la clé publique depuis la clé privée](https://youtu.be/NJENwFU889Y)

Pour commencer, plongeons dans l'univers de l'algorithme Elliptic Curve Digital Signature Algorithm (ECDSA). Bitcoin exploite cet algorithme de signature numérique pour lier les clés privées et publiques. Dans ce système, la clé privée est un nombre aléatoire ou pseudo-aléatoire de 256 bits. Le nombre total de possibilités pour une clé privée est théoriquement de 2^256, mais il est légèrement inférieur à cela dans la réalité. Pour être précis, certaines clés privées de 256 bits ne sont pas valides pour Bitcoin.

Pour être compatible avec Bitcoin, une clé privée doit être comprise entre 1 et n-1, où n représente l'ordre de la courbe elliptique. Cela signifie que le nombre total de possibilités pour une clé privée Bitcoin est presque égal à 1,158 x 10^77. Pour mettre cela en perspective, c'est à peu près le même nombre d'atomes présents dans l'univers observable. 

![image](assets/image/section2/3.webp)

La clé privée unique, notée k, est ensuite utilisée pour déterminer une clé publique.

La clé publique, notée K, est un point sur la courbe elliptique qui est dérivé de la clé privée en utilisant des algorithmes irréversibles comme ECDSA. Lorsque nous avons connaissance de la clef privée, il est très facile de retrouver la clef publique mais lorsque nous possedons uniquement la clef publique, il est impossible de retrouver la clef privée. Cette irréversibilité est la pierre angulaire de la sécurité du portefeuille Bitcoin.

La clé publique fait 512 bits car elle correspond à un point sur la courbe avec une coordonnée x de 256 bits et une coordonnée y de 256 bits. Cependant, elle peut être compressée en un nombre de 264 bits.

![image](assets/image/section2/4.webp)

Le point générateur (G)  est le point sur la courbe à partir duquel toutes les clés publiques sont générées sur le protocole Bitcoin. Il a des coordonnées x et y spécifiques, généralement représentées en hexadécimal. Pour secp256k1, les coordonnées G sont, en hexadécimale :

- `Gx = 79BE667E F9DCBBAC 55A06295 CE870B07 029BFCDB 2DCE28D9 59F2815B 16F81798`
- `Gy = 483ADA77 26A3C465 5DA4FBFC 0E1108A8 FD17B448 A6855419 9C47D08F FB10D4B8`

Ce point est utile pour dériver toutes les clefs publiques. Pour calculer la clef publique K, il suffit de multiplier le point G par la clef privée k, tel que : K = k.G

Nous allons maintenant étudier comment additionner et multiplier des points sur les courbes elliptiques.

#### Addition et doublement de points sur les courbes elliptiques

##### Additionner deux points M + L

L'une des propriétés remarquables des courbes elliptiques est qu'une droite non verticale intersectant la courbe en deux points l'intersectera également en un troisième point, appelé point O dans notre exemple. Cette propriété est utilisée pour déterminer le point U, qui est l'opposé du point O. 

M + L = U

![image](assets/image/section2/5.webp)

##### Addition un point par lui même = Doublement de point

L'addition d'un point G à lui-même se fait en traçant une tangente à la courbe au niveau de ce point. Cette tangeante, selon les propriétés des courbes elliptiques recoupera forcément la courbe en un second point unique -J. L'opposé de ce point, J, est le résultat de l'addition du point G à lui même.
G + G = J

D'ailleur, le point G est le point de départ pour calculer toutes les clés publiques des utilisateurs du système Bitcoin.

![image](assets/image/section2/6.webp)

#### Le produit scalaire sur courbe elliptique

Le produit scalaire d'un point par n revient à ajouter ce point à lui-même n fois.

De la même manière que l'or d'un doublement de point, le produit scalaire du point G par un point n se fait en traçant une tangente à la courbe au niveau du point G. Cette tangeante, selon les propriétés des courbes elliptiques recoupera forcément la courbe en un second point unique -2G. L'opposé de ce point, 2G, est le résultat de l'addition du point G à lui même.

Si n = 4, alors on réitère l'opération jusqu'à arriver à 4G.

![image](assets/image/section2/7.webp)

Voici un exemple de calcul pour 3G :

![image](assets/image/section2/8.webp)

Ces opérations sur les points d'une courbe elliptique sont la base du calcul des clés publiques. La dérivation d'une clef publique en sachant la clef privée est très facile.
Une clef publique est un point sur la courbe elliptique, c'est le résultat de notre addition et doublement du point G k fois. Avec k = clef privée.

Dans cet exemple :

- La clef privée k = 4
- La clef publique K = kG = 4G

![image](assets/image/section2/9.webp)

Connaissant la clé privée k, il est facile de calculer la clé publique K. Impossible en revenche de retrouver la clef privée en fonction de la clef publique. Est-ce le résutat d'une addition ou d'un doublement de point ? 

Dans notre prochain cours, nous explorerons comment une signature numérique est réalisée en utilisant l'algorithme ECDSA avec une clé privée pour dépenser des bitcoins. 

## Signer avec la clé privée
<chapterId>bb07826f-826e-5905-b307-3d82001fb778</chapterId>

![Signer avec la clé privée](https://youtu.be/h2hIyGgPqkM)

Le processus de signature numérique est une méthode clé pour prouver que vous êtes le détenteur d'une clé privée sans avoir à la révéler. Ceci est réalisé en utilisant l'algorithme ECDSA, qui comprend la détermination d'un nonce unique, le calcul d'un nombre spécifique, V, et la création d'une signature numérique composée de deux parties, S1 et S2. 
Il est crucial de toujours utiliser un nonce unique pour éviter les attaques de sécurité. Un exemple notoire de ce qui peut se produire lorsque cette règle n'est pas respectée est le cas du piratage de la PlayStation 3, qui a été compromis en raison de la réutilisation du nonce.

![](assets/image/section2/10.webp)

Etapes :

- Déterminer un nonce v, c'est-à-dire, un nombre unique aléatoire.
  Nonce = Number Only Use Once.
  Il est déterminé par celui qui réalise la signature.
- Calculer par addition et doublement de point sur courbe elliptique à partir du point G, la position de V sur la courbe elliptique. 
  Tel que V = v.G
  x et y sont les coordonnées de V sur le plan
- Calculer S1.
  S1 = x mod n avec n = l'ordre de la courbe et x une coordonnée de V sur le plan.
  NB : Le nombre de possibilité de la clef publique est plus grand que le nombre de points sur la courbe elliptique dans le corps fini des entiers positifs qui est utilisé sur Bitcoin.
  L'ordre de la courbe correspond uniquement aux possibilités que peut prendre la clef publique sur la courbe.
- Calculer S2.
  H(Tx) = Hash de la transaction 
  k = la clef privée
- Calculer la signature : la concatenation de S1 + S2.
- Calculer P, le calcul de vérification de la signature.
  K = la clef publique

Par exemple, pour obtenir la clé publique 3G, vous dessinez une tangente au point G, calculez l'opposé de -G pour obtenir 2G, puis additionnez G et 2G. Pour réaliser une transaction, vous devez prouver que vous connaissez le nombre 3 en débloquant les bitcoins associés à la clé publique 3G.

Pour créer une signature numérique et prouver que vous connaissez la clé privée associée à la clé publique 3G, vous calculez d'abord un nonce, puis le point V associé à ce nonce (dans l'exemple donné, c'est 4G). Ensuite, vous calculez le point T en additionnant la clé publique 3G et le point V, ce qui donne 7G.

![image](assets/image/section2/11.webp)

Vulgarisons le processus de signature numérique.
Sur l'image précédente, la clef privée k = 3. 
Nous pouvons facilement calculer la clef publique K associée à cette clef privée : K = 3G
Ensuite, nous générons pseudo-aléatoirement un nonce : v = 4. 
A partir de ce nonce, il est possible de calculer V tel que : V = v.G = 4G.

A partir de ce point V, nous calculons le point T tel que :
T = t.G = 7G (avec t = 7)



Il est temps de procéder à la vérification de la signature numérique.

La vérification d'une signature numérique est une étape cruciale dans l'utilisation de l'algorithme ECDSA, qui permet de confirmer l'authenticité d'un message signé sans avoir besoin de la clé privée de l'expéditeur. Voici comment cela se déroule en détail :

Dans notre exemple, nous avons deux valeurs importantes : t et V. 
t est une valeur numérique (7 dans cet exemple), et V est un point sur la courbe elliptique (représenté par 4G ici). Ces valeurs sont produites lors de la création de la signature numérique et sont ensuite envoyées avec le message pour permettre la vérification.

Quand le vérificateur reçoit le message, il va également recevoir ces deux valeurs, t et V.

Voici les étapes que le vérificateur va suivre pour valider la signature :

1. Il va d'abord calculer le hachage du message, que nous appellerons H.
2. Ensuite, il calculera u1 et u2. Pour ce faire, il utilisera les formules suivantes :
   - u1 = H /\* (S2)^-1 mod n
   - u2 = T /\* (S2)^-1 mod n
     Où S2 est la deuxième partie de la signature numérique, n est l'ordre de la courbe elliptique et (S2)^-1 est l'inverse de S2 mod n.
3. Le vérificateur calculera ensuite un point P' sur la courbe elliptique à l'aide de la formule : P' = u1 _ G + u2 _ K
   - G est le point de génération de la courbe
   - K est la clé publique de l'expéditeur
4. Le vérificateur calculera alors I', qui est simplement la coordonnée x du point P' modulo n.
5. Enfin, le vérificateur confirmera que I' est égal à t. Si c'est le cas, la signature est considérée comme valide. Si ce n'est pas le cas, la signature est invalide.

Cette procédure garantit que seul l'expéditeur possédant la clé privée correspondante pourrait avoir produit une signature qui passe ce processus de vérification.

![image](assets/image/section2/12.webp)

Vulgarisons : 
Celui qui produit la signature va fournir à celui qui vérifie le nombre t (dans notre exemple, t = 7) et le point V.

Il est impossible de déterminer la clef publique ou la clef privée à partir du nombre 7 et du nombre V.

Les étapes de vérification de la signature numérique sont les suivantes :

- Sur la courbe, il additionne le point de la clef publique avec le point V pour retrouver le point T'.
- Il calcul le nombre t.G
- Il vérifie que le résultat de t.G soit bien égal au nombre T'



En conclusion, la vérification d'une signature numérique est une procédure essentielle dans les transactions Bitcoin. Elle permet de garantir que le message signé n'a pas été altéré lors de sa transmission et que l'expéditeur est bien le détenteur de la clé privée. Cette technique d'authentification numérique repose sur des principes mathématiques complexes, notamment l'arithmétique de courbe elliptique, tout en maintenant la confidentialité de la clé privée. Elle offre une solide base de sécurité pour les transactions cryptographiques.

Cela dit, la gestion de ces clés, ainsi que leur création, est une autre question essentielle dans Bitcoin. Comment générer une nouvelle paire de clés ? Comment organiser une multitude de clés de manière sécurisée et efficace ? Comment les récupérer si nécessaire ?

Pour répondre à ces questions et approfondir votre compréhension de la sécurité de la cryptographie, notre prochain cours se concentrera sur le concept de Portefeuille Déterministe Hiérarchique (HD wallets) et l'utilisation des phrases mnémoniques. Ces mécanismes offrent des moyens élégants de gérer efficacement vos clés de cryptomonnaie tout en renforçant la sécurité.

# La phrase mnémonique
<partId>4070af16-c8a2-58b5-9871-a22c86c07458</partId>

## Évolution des portefeuilles Bitcoin
<chapterId>9d9acd5d-a0e5-5dfd-b544-f043fae8840f</chapterId>

![Évolution des portefeuilles Bitcoin](https://youtu.be/6tmu1R9cXyk)

Le Portefeuille Déterministe Hiérarchique, ou plus couramment appelé portefeuille HD, joue un rôle prépondérant dans l'écosystème des cryptomonnaies. Le terme "portefeuille" peut sembler trompeur pour ceux qui sont novices dans ce domaine, car il n'implique pas la détention d'argent ou de devises. Il fait plutôt référence à une collection de clés cryptographiques privées. 

Les premiers portefeuilles étaient des logiciels regroupant des clefs privées déterminées de manière pseudo-aléatoire mais qui n'avaient aucun lien entres elles. Ces portefeuilles sont nommés "Just a Bunch Of Keys" (JBOK).

Les clefs n'ayant aucun liens entres elles, l'utilisateur est obligé de réaliser une nouvelle sauvegarde pour toute nouvelle paire de clef générée.
Soit l'utilisateur utilise tout le temps la même pair de clef et perd en confidentialité, soit il dérive de nouvelle paire de clef de manière aléatoire et donc doit réaliser une nouvelle sauvegarde de ces clefs. 

![image](assets/image/section3/0.webp)

Cependant, la complexité de la gestion de ces clés est compensée par un ensemble de protocoles, appelés Bitcoin Improvement Proposals (BIP). Ces propositions de mise à niveau sont au cœur de la fonctionnalité et de la sécurité des portefeuilles HD. Par exemple, le [BIP32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki), lancé en 2012, a révolutionné la manière dont ces clés sont générées et stockées, en introduisant le concept de clés dérivées de manière déterministe et hiérarchique. L'idée est de dériver toutes les clefs de façon déterministe et hierarchique depuis une information unique : la seed. Ainsi, le processus de sauvegarde de ces clés est grandement simplifié, tout en conservant leur niveau de sécurité.

![image](assets/image/section3/1.webp)

Par la suite, le [BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) a introduit une innovation marquante : la phrase mnémonique de 24 mots. Ce système a permis de transformer une suite de chiffres complexe et difficile à retenir en une série de mots ordinaires, bien plus facile à mémoriser et à stocker. En outre, le [BIP38](https://github.com/bitcoin/bips/blob/master/bip-0038.mediawiki) a proposé d'ajouter une passphrase supplémentaire pour renforcer la sécurité des clés individuelles. Ces améliorations successives ont abouti aux normes BIP43 et BIP44, qui ont standardisé la structure et la hiérarchisation des portefeuilles HD, rendant ces portefeuilles plus accessibles et plus faciles à utiliser pour le grand public.

Dans les sections suivantes, nous allons plonger plus profondément dans le fonctionnement des portefeuilles HD. Nous aborderons les principes de dérivation des clés et nous examinerons les concepts fondamentaux de l'entropie et de la génération de nombres aléatoires, qui sont essentiels pour garantir la sécurité de votre portefeuille HD.

En guise de synthèse, il est essentiel de souligner le rôle central des BIP32 et BIP39 dans la conception et la sécurisation des portefeuilles HD. Ces protocoles permettent de générer une multitude de clés à partir d'une seule graine, qui est supposée être un nombre aléatoire ou pseudo-aléatoire. Aujourd'hui, ces normes sont adoptées par la majorité des portefeuilles de cryptomonnaies, qu'ils soient dédiés à une seule cryptomonnaie ou qu'ils prennent en charge plusieurs types de devises.



## Entropie et nombre aléatoire
<chapterId>b43c715d-affb-56d8-a697-ad5bc2fffd63</chapterId>

![Entropie et nombre aléatoire](https://youtu.be/k18yH18w2TE)

L'importance de la sécurité des clés privées dans l'écosystème du Bitcoin est incontestable. Elles sont en effet la pierre angulaire qui assure la sécurité des transactions Bitcoin. Pour éviter toute vulnérabilité associée à la prédictibilité, ces clés doivent être générées de manière véritablement aléatoire, ce qui peut rapidement se révéler être un exercice laborieux. Le problème c'est qu'en informatique, il est impossible de générer un nombre véritablement aléatoire puisqu'il est forcément issu d'un processus déterministe ; un code. 
C'est pourquoi il est essentiel de s'informer sur les différents Générateur de Nombres Aléatoires (RNG). Les types de RNG varient, allant des Pseudo-Random Number Generators (PRNG) aux True Random Number Generators (TRNG), ainsi qu'aux PRNG qui intègrent une source d'entropie.

L'entropie désigne l'état de « désordre » d'un système. A partir d'une entropie externe, c'est à dire, une source d'information externe, il est possible d'utiliser un générateur de nombre aléatoire afin d'obtenir un nombre aléatoire.


![image](assets/image/section3/2.webp)

Voyons ensemble le fonctionnement d'un Pseudo-Random Number Generator (PRNG).

Il prend en entrée une graine, c'est à dire, une information qui va correspondre à l'état interne 0.
Sur cet etat interne, il est appliqué une fonction de transformation et le résultat qui est un nombre pseudo-aléatoire correspond à l'état interne 1.
Sur cet etat interne 1, à nouveau, il est apliqué une fonction de transformation qui résulte en un nouveau nombre aléatoire = etat interne 2.
Et ainsi de suite.

L'inconvenient principal c'est que toute graine identique donnera toujours le même résultat en sortie. Et également, si nous connaissons le résultat des fonctions de transformation du début, nous sauront en mesure de retrouver le nombre aléatoire en sortie de processus.

Un exemple de fonction de transformation est le fonction PBKDF2.

**Pour résumer, un PRNG cryptographiquement sûr doit :**

- etre statistiquement aléatoire
- etre imprédictible
- etre résistant même si les résultats sont révélés
- avoir une periode suffisamment longue



![image](assets/image/section3/3.webp)

Dans le cas du Bitcoin, les clés privées sont générées à partir d'une seule information à la base du portefeuille. Cette information permet une dérivation déterministe et hiérarchique des paires de clés enfant. L'entropie est le socle de tout portefeuille HD, bien qu'il n'existe pas de standard pour la génération de ce nombre aléatoire. Par conséquent, la génération de nombres aléatoires est un enjeu majeur pour sécuriser les transactions Bitcoin.

## La phrase mnémonique
<chapterId>8f9340c1-e6dc-5557-a2f2-26c9669987d5</chapterId>

![La phrase mnémonique](https://youtu.be/uJERqH9Xp7I)

La sécurité d'un portefeuille Bitcoin est une préoccupation majeure pour tous ses utilisateurs. Une manière essentielle d'assurer la sauvegarde du portefeuille consiste à générer une phrase mnémonique basée sur l'entropie et la checksum.

![image](assets/image/section3/5.webp)

Pour passer de l'entropie à une phrase mnémonique, il suffit de calculer la checksum de l'entropie et de concaténer entropie et checksum.

Une fois que l'entropie est générée, on utilise la fonction SHA256 sur l'entropie afin d'en créer un hash. 
On récupère les 8 premiers bits du hash, c'est la checksum.
La phrase mnémonique est le résultat de l'entropie additionnée de la checksum.

La checksum assure la vérification de l'exactitude de la phrase de récupération. Sans cette checksum, une erreur dans la phrase pourrait aboutir à la création d'un portefeuille différent et donc à la perte des fonds. On obtient la checksum en passant l'entropie par la fonction SHA256 et en récupérant les 8 premiers bits du hachage.

![image](assets/image/section3/6.webp)

Différents standards existent pour la phrase mnémonique en fonction de la taille de l'entropie. Le standard le plus couramment utilisé pour une phrase de récupération de 24 mots est une entropie de 256 bits. La taille de la checksum est déterminée en divisant la taille de l'entropie par 32.

Par exemple, une entropie de 256 bits génère une checksum de 8 bits. La concaténation de l'entropie et de la checksum conduit alors à des tailles respectives de 128 bits, 160 bits, etc. En fonction de la taille de l'entropie, la phrase de récupération comportera 12 mots pour 128 bits, 15 mots pour 160 bits, et 24 mots pour 256 bits.

**L'encodage de la phrase mnémonique :**

![image](assets/image/section3/7.webp)

Les 8 derniers bits correspondent à la checksum.
Chaque segment de 11 bits est converti en décimal.
Chaque décimal corespond à un mot  issu d'une liste de 2048 mots sur le BIP39. Il est important de préciser qu'aucun mot ne présente les quatre premières lettres dans le même ordre.

Il est essentiel de sauvegarder la phrase de récupération de 24 mots pour préserver l'intégrité du portefeuille Bitcoin. Les deux standards les plus couramment utilisés se basent sur une entropie de 128 ou 256 bits et une concaténation de 12 ou 24 mots. L'ajout d'une passphrase constitue une option supplémentaire pour renforcer la sécurité du portefeuille.

En conclusion, la génération d'une phrase mémonique pour sécuriser un portefeuille Bitcoin est un processus crucial. Il est important de respecter les standards de la phrase mémonique en fonction de la taille de l'entropie. La sauvegarde de la phrase de récupération de 24 mots est essentielle pour prévenir toute perte de fonds. 

## La passphrase
<chapterId>6a51b397-f3b5-5084-b151-cef94bc9b93f</chapterId>

![La passphrase](https://youtu.be/dZkOYO7MXwc)

La passphrase est un mot de passe additionnel qui peut être intégré à un portefeuille Bitcoin pour accroître sa sécurité. Son utilisation est optionnelle et revient à l'appréciation de l'utilisateur. En ajoutant des informations arbitraires qui, conjointement avec la phrase mémonique, permettent de calculer la graine du portefeuille, la passphrase renforce la sécurité de celui-ci.

![image](assets/image/section3/8.webp)

La passphrase est un sel cryptographique optionnel d'une taille choisi par l'utilisateur. Elle permet d'améliorer la sécurité d'un portefeuille HD en ajoutant une information arbitraire qui une fois aglomérée à la phrase mnémonique permettra de calculer la graine. 

Lorsqu'elle a été établie lors de la création d'un portefeuille, elle est nécessaire pour la dérivation de toutes les clefs du portefeuille. La fonction pbkdf2 est utilisée pour générer la graine à partir de la passphrase. Cette graine permet de dériver toutes les paires de clés enfants du portefeuille. Si la passphrase est modifiée, le portefeuille Bitcoin devient complètement différent.

La passphrase est un outil essentiel pour renforcer la sécurité des portefeuilles Bitcoin. Elle peut permettre l'application de diverses stratégies de sécurité. Par exemple, elle peut être utilisée pour créer des doublons et faciliter les sauvegardes de la phrase mémonique. Elle peut également améliorer la sécurité du portefeuille en atténuant les risques associés à la génération aléatoire de la phrase mémonique.

Une passphrase efficace devrait être longue (20 à 40 caractères) et diversifiée (utilisant des majuscules, des minuscules, des chiffres et des symboles). Elle ne devrait pas être directement liée à l'utilisateur ou à son environnement. Il est plus sûr d'utiliser une séquence aléatoire de caractères plutôt qu'un mot simple comme passphrase.

![image](assets/image/section3/9.webp)

Une passphrase est plus sécurisée qu'un simple mot de passe. La passphrase idéale est longue, variée et aléatoire. Elle peut renforcer la sécurité d'un portefeuille ou d'un logiciel chaud. Elle peut également être utilisée pour créer des sauvegardes redondantes et sécurisées.

Il est crucial de prendre soin des sauvegardes de la passphrase pour éviter de perdre l'accès au portefeuille. Une passphrase est une option pour un portefeuille HD. Elle peut être générée aléatoirement avec des dés ou un autre générateur de nombres pseudo-aléatoires. Il est déconseillé de mémoriser une passphrase ou une phrase mémonique.

Dans notre prochain cours, nous examinerons en détail le fonctionnement de la graine et la première paire de clés générée à partir de celle-ci. N'hésitez pas à suivre ce cours pour continuer votre apprentissage. Nous avons hâte de vous retrouver très bientôt.

# Création des portefeuilles Bitcoin
<partId>9c25e767-7eae-50b8-8c5f-679d8fc83bab</partId>

## Création de la graine et de la clé maîtresse
<chapterId>63093760-2010-5691-8d0e-9a04732ae557</chapterId>

![Création de la graine et de la clé maîtresse](https://youtu.be/56yAt_JDWhY)

Dans cette partie du cours, nous allons explorer les étapes de dérivation d'un portefeuille HD (Hierarchical Deterministic Wallet), qui permet de créer et gérer des clés privées et publiques de manière hiérarchique et déterministe.

![image](assets/image/section4/0.webp)

Le fondement du portefeuille HD repose sur deux éléments essentiels : la phrase mnémonique et la passphrase (mot de passe supplémentaire optionnel). Ensemble, ils constituent la seed, une séquence alphanumérique de 512 bits qui sert de base pour dériver les clés du portefeuille. À partir de cette seed, il est possible de dériver toutes les paires de clés enfants du portefeuille Bitcoin. La seed est la clé permettant d'accéder à l'ensemble des bitcoins associés au portefeuille, que vous utilisiez une passphrase ou non.

![image](assets/image/section4/1.webp)

Pour obtenir la seed, on utilise la fonction pbkdf2 (Password-Based Key Derivation Function 2) avec la phrase mnémonique et la passphrase. La sortie de pbkdf2 est une seed de 512 bits. 

A partir de la seed, il est possible de déterminer la clé privée maitresse et le code de chaine en utilisant l'algorithme HMAC SHA-512 (Hash-based Message Authentication Code Secure Hash Algorithm 512). Cet algorithme nécessite un message et une clé en entrée pour générer un résultat. La clé privée maîtresse est calculée à partir de la seed et de la phrase "Bitcoin SEED". Cette phrase est identique pour toutes les dérivations de tous les portefeuilles HD, garantissant ainsi une cohérence entre les portefeuilles.

Initialement, la fonction SHA-512 n'était pas implémentée dans le protocole Bitcoin, c'est pourquoi on utilise HMAC SHA-512. L'utilisation de HMAC SHA-512 avec la phrase "Bitcoin SEED" contraint l'utilisateur à générer un portefeuille spécifique à Bitcoin. Le résultat de HMAC SHA-512 est un nombre de 512 bits, divisé en deux parties : les 256 bits de gauche représentent la clé privée maîtresse, tandis que les 256 bits de droite représentent le code de chaîne maître.

![image](assets/image/section4/2.webp)

La clé privée maîtresse est la clé parente de toutes les futures clés du portefeuille, tandis que le code de chaîne maître intervient dans la dérivation des clés enfants. Il est important de noter qu'il est impossible de dériver une paire de clés enfant sans connaître le code de chaîne correspondant de la paire parente. 

Une paire de clés dans le portefeuille comprend une clé privée, une clé publique et un code de chaîne. Le code de chaîne permet d'introduire une source d'aléatoire dans la dérivation des clés enfants et d'isoler chaque paire de clés pour éviter toute fuite d'information.

Il est important de souligner que la clé privée maîtresse est la première clé privée dérivée à partir de la seed et n'a aucun lien avec les clés étendues du portefeuille.

Dans le prochain cours, nous explorerons en détail les clés étendues, telles que les xPub, xPRV, zPub, et nous comprendrons pourquoi elles sont utilisées et comment elles sont construites.

## Les clés étendues
<chapterId>8dcffce1-31bd-5e0b-965b-735f5f9e4602</chapterId>

![Les clés étendues](https://youtu.be/TRz760E_zUY)

Dans cette partie du cours, nous allons étudier les clés étendues (xPub, zPub, yPub) et leurs préfixes, qui jouent un rôle important dans la dérivation des clés enfants dans un portefeuille HD (Hierarchical Deterministic Wallet).

![image](assets/image/section4/3.webp)

Les clés étendues se distinguent des clés maîtresses. Un portefeuille HD génère une phrase mnémonique et une graine pour obtenir la clé maîtresse et le code de chaîne maître. Les clés étendues sont utilisées pour dériver les clés enfants et nécessitent à la fois la clé parente et le code de chaîne correspondant. Une clé étendue combine ces deux informations pour simplifier le processus de dérivation.

![image](assets/image/section4/4.webp)

Les clés publiques étendues ne peuvent dériver que des clés publiques enfants normales, tandis que les clés privées étendues permettent de dériver des clés enfants publiques et privées, que ce soit sur une dérivation normale ou endurcie. 
La dérivation endurcie est la dérivation à partir de la clef parent privée. La dérivation normale correspond à la dérivation à partir de la clef parent publique.

L'utilisation de clés étendues avec le préfixe XPUB permet de dériver de nouvelles adresses sans remonter jusqu'aux clés privées correspondantes, offrant ainsi une meilleure sécurité. Les métadonnées associées aux clés étendues fournissent des informations importantes sur leur rôle et leur position dans la hiérarchie des clés.

Les clés étendues sont identifiées par des préfixes spécifiques (XPRV, XPUB, YPUB, ZPUB) qui indiquent s'il s'agit d'une clé étendue privée ou publique, ainsi que son objectif spécifique. Les métadonnées associées à une clé étendue comprennent la version (préfixe), la profondeur, l'empreinte de la clé publique, l'index et la charge utile (code de chaîne et clé parente).

![image](assets/image/section4/5.webp)

La version correspond à type de clef : xpub, xprv, ...

La profondeur correspond au nombre de dérivation entre parent-enfant qu'il y a eu depuis la clef maitresse.

L'empreinte parent c'est les 4 premiers octets du hash 160 de la clef parent.

L'index est le numéro de la paire qui est utilisée pour générer la clef étendu parmis ses soeurs. (soeurs = clefs de même profondeur)
exemple : si on souhaite dériver la xpub de notre 3ieme compte, son index sera 2 (car index commence à 0).

La charge utile est composée du code de chaîne (32 octets) et de la clé parente (33 octets).

Les clés publiques compressées ont une taille de 33 octets, tandis que les clés publiques brutes sont de 512 bits. Les clés publiques compressées conservent les mêmes informations que les clés brutes, mais avec une taille réduite. Les clés étendues ont une taille de 82 octets et leur préfixe est représenté en base 58 grâce à une conversion en hexadécimal. Le checksum est calculé à l'aide de la fonction de hachage HASH256.

![image](assets/image/section4/6.webp)

Les dérivations renforcées commencent à partir des indexes qui sont des puissances de 2 (2^31). Il est intéressant de noter que les préfixes les plus couramment utilisés sont xpub et zpub, qui correspondent respectivement aux standards legacy et segwit v1 et segwit v0.

Dans notre prochain cours, nous nous pencherons sur la dérivation des paires de clés enfants en utilisant les connaissances acquises sur les clés étendues et la clé maîtresse du portefeuille.

## Dérivation des paires de clés enfants
<chapterId>61c0807c-845b-5076-ad06-7f395b36adfd</chapterId>

![Dérivation des paires de clés enfants](https://youtu.be/FXhI-GmE9Aw)

Pour rappel, nous avons abordé le calcul de la graine et de la clé maîtresse, qui constituent les premiers éléments essentiels pour la hiérarchisation et la dérivation du portefeuille HD (Hierarchical Deterministic Wallet). La graine, d'une longueur de 128 à 256 bits, est générée de manière aléatoire ou à partir d'une phrase secrète. Elle joue un rôle déterministe dans la dérivation de toutes les autres clés. La clé maîtresse est la première clé dérivée à partir de la graine, et elle permet de dériver toutes les autres paires de clés enfants.

Le code de chaîne maître joue un rôle important dans la reprise du portefeuille à partir de la graine. Il est à noter que toutes les clés dérivées à partir de la même graine auront le même code de chaîne maître.

![image](assets/image/section4/7.webp)

La hiérarchisation et la dérivation du portefeuille HD offrent une gestion plus efficace des clés et des structures de portefeuille. Les clés étendues permettent la dérivation d'une paire de clés enfant à partir d'une paire parent en utilisant des calculs mathématiques et des algorithmes spécifiques.

Il existe différents types de paires de clés enfants, notamment les clés renforcées et les clés normales. La clé publique étendue permet uniquement la dérivation de clés publiques enfants normales, tandis que la clé privée étendue permet la dérivation de toutes les clés enfants, à la fois publiques et privées, qu'elles soient en mode normal ou renforcé. Chaque paire de clés dispose d'un index qui permet de les différencier les unes des autres.

![image](assets/image/section4/8.webp)

La dérivation des clés enfants utilise la fonction HMAC-SHA512 en utilisant la clé parent concaténée à l'index et au code de chaîne associé à la paire de clés. Les clés enfants normales ont un index compris entre 0 et 2 puissance 31 moins 1, tandis que les clés enfants renforcées ont un index compris entre 2 puissance 31 et 2 puissance 32 moins 1.

![image](assets/image/section4/9.webp)

![image](assets/image/section4/10.webp)

Il existe deux types de paires de clés enfants : les paires renforcées et les paires normales. Le processus de dérivation des clés enfants utilise les clés publiques pour générer les conditions de dépense, tandis que les clés privées sont utilisées pour la signature. La clé publique étendue permet uniquement la dérivation de clés publiques enfants normales, tandis que la clé privée étendue permet la dérivation de toutes les clés enfants, à la fois publiques et privées, en mode normal ou renforcé.

![image](assets/image/section4/11.webp)
![image](assets/image/section4/12.webp)

La dérivation renforcée utilise la clé privée parent, tandis que la dérivation normale utilise la clé publique parent. La fonction HMAC-SHA512 est utilisée pour la dérivation renforcée, tandis que la dérivation normale utilise un condensat de 512 bits. La clé publique enfant est obtenue en multipliant la clé privée enfant par le générateur de la courbe elliptique.

![image](assets/image/section4/13.webp)
![image](assets/image/section4/14.webp)

La hiérarchisation et la dérivation de nombreuses paires de clés de manière déterministe permettent de créer un schéma en arbre pour la dérivation hiérarchique. Dans le prochain cours de cette formation, nous étudierons la structure du portefeuille HD ainsi que les chemins de dérivation, en mettant notamment l'accent sur les notations des chemins de dérivation.

## Structure du portefeuille et chemins de dérivation
<chapterId>34e1bbda-67de-5493-b268-1fded8d67689</chapterId>

![Structure du portefeuille et chemins de dérivation](https://youtu.be/etO9UxwyE2I)

Dans ce chapitre, nous allons étudier la structure de l'arbre de dérivation dans un portefeuille HD (Hierarchical Deterministic Wallet). Nous avons déjà exploré le calcul de la graine, la clé maîtresse et la dérivation des paires de clés enfants. Maintenant, nous allons nous concentrer sur l'organisation des clés au sein du portefeuille.

Le portefeuille HD utilise des couches de profondeur pour organiser les clés. Chaque dérivation d'une paire parent vers une paire enfant correspond à une couche de profondeur. 

![image](assets/image/section4/15.webp)

- La profondeur 0 correspond à la clé maîtresse et au code de chaîne maître.

- La profondeur 1 est utilisée pour dériver des clés enfants selon un objectif spécifique, qui est déterminé par l'index. Les objectifs sont conformes aux standards BIP 84 et Segwit v0/v1.

- La profondeur 2 permet de différencier les comptes de différentes cryptomonnaies ou réseaux. Cela permet d'organiser le portefeuille en fonction des différentes sources de fonds. Pour bitcoin, l'index sera 0.

- La profondeur 3 est utilisée pour organiser le portefeuille en différents comptes, offrant ainsi une structure plus claire et organisée.

- La profondeur 4 correspond aux chaînes interne et externe, qui sont utilisées pour les adresses destinées à être communiquées publiquement. L'index 0 est associé à la chaîne externe, tandis que l'index 1 est associé à la chaîne interne. Chaque compte dispose de deux chaînes : la chaîne externe (0) et la chaîne interne (1). La profondeur 4 est également utilisée pour gérer les types de script dans le cas des portefeuilles multi signatures.

- La profondeur 5 est utilisée pour les adresses de réception sur un portefeuille classique. Dans la prochaine section, nous examinerons plus en détail la dérivation des paires de clés enfants.

![image](assets/image/section4/16.webp)

Pour chaque couche de profondeur, nous utilisons des index pour différencier les paires de clés enfants. 

L'index sans apostrophe correspond à l'index réel utilisé, tandis que l'index avec apostrophe correspond à l'index réel + 2^31. Les dérivations renforcées utilisent des index de 2^31 à 2^32-1. Par exemple, l'index 44' correspond à l'index réel 2^31 + 44.

Pour générer une adresse de réception spécifique, nous dérivons une paire de clés enfants à partir de la clé maîtresse et du code de chaîne maître. Ensuite, nous utilisons l'index pour différencier les différentes paires de clés enfants de la même profondeur.

Les clés étendues, telles que XPUB, permettent de partager votre portefeuille avec plusieurs personnes. La chaîne de dérivation est utilisée pour différencier la chaîne externe (adresses destinées à être communiquées) et la chaîne interne (adresses de change).

Dans le prochain chapitre, nous allons étudier les adresses de réception, leurs avantages d'utilisation et les étapes de leur construction.

# Qu'est-ce qu'une adresse Bitcoin ?
<partId>81ec8d17-f8ee-5aeb-8035-d370866f4281</partId>

## Les adresses Bitcoin
<chapterId>0a887ed8-3424-5a52-98e1-e4b406150475</chapterId>

![Les adresses Bitcoin](https://youtu.be/nqGBMjPtFNI)

Dans ce chapitre, nous allons explorer les adresses de réception, qui jouent un rôle crucial dans le système Bitcoin. Elles permettent de recevoir des fonds sur une pièce et sont générées à partir de paires de clés privées et publiques. Bien qu'il existe un type de script appelé Pay2PublicKey qui permet de bloquer des bitcoins sur une clé publique, les utilisateurs préfèrent généralement utiliser des adresses de réception plutôt que ce script.

![image](assets/image/section5/0.webp)

Lorsqu'un destinataire souhaite recevoir des bitcoins, il fournit une adresse de réception à l'émetteur plutôt que sa clé publique. Une adresse est en réalité un hash d'une clé publique, avec un format spécifique. La clé publique est dérivée de la clé privée enfant en utilisant des opérations mathématiques telles que l'addition et le doublement de points sur les courbes elliptiques.

![image](assets/image/section5/1.webp)

Il est important de noter qu'il n'est pas possible de remonter de l'adresse vers la clé publique, ni de la clé publique vers la clé privée. L'utilisation d'une adresse permet de réduire la taille de l'information de la clé publique, qui initialement fait 512 bits. 

Les adresses Bitcoin ont été réduites en taille pour faciliter leur utilisation. Elles possèdent une checksum, ce qui permet de détecter les fautes de frappe et de réduire les risques de perte de bitcoins. En revanche, les clés publiques n'ont pas de checksum, ce qui signifie que les fautes de frappe peuvent entraîner la perte des fonds correspondants.

Les adresses offrent également une deuxième couche de sécurité entre l'information publique et privée, rendant plus difficile la prise de contrôle de la clé privée.

Il est essentiel de souligner que chaque adresse devrait être à usage unique. La réutilisation d'une même adresse pose des problèmes de confidentialité et doit être évitée. 

Différents préfixes sont utilisés pour les adresses Bitcoin. Par exemple, BC1Q correspond à une adresse Segwit V0, BC1P à une adresse Taproot/Segwit V1, et les préfixes 1 et 3 sont associés aux adresses Pay2PublicKeyH/Pay2ScriptH (legacy). Dans le prochain cours, nous expliquerons étape par étape la dérivation d'une adresse à partir d'une clé publique.

## Comment créer une adresse Bitcoin ?
<chapterId>6dee7bf3-7767-5f8d-a01b-659b95cfe0a5</chapterId>

![Comment créer une adresse Bitcoin ?](https://youtu.be/ewMGTN8dKjI)

Dans ce chapitre, nous allons aborder la construction d'une adresse de réception pour les transactions Bitcoin. Une adresse de réception est une représentation sous forme de caractères alphanumériques d'une clé publique compressée. La conversion d'une clé publique en une adresse de réception passe par plusieurs étapes.

### Etape 1 : Compression de la clef publique

![image](assets/image/section5/14.webp)

Une adresse est dérivée à partir d'une clé publique enfant.

Une clef publique est un point sur la courbe elliptique. Grâce à la symétrie de la courbe elliptique, un point sur la courbe elliptique aura une abscisse x uniquement associée à deux valeurs possibles pour y : positive ou négative. 
Cependant, sur le protocole Bitcoin, nous travaillons avec un corps d'entiers positifs finis plutôt qu'avec le corps des réels. Pour faire la distinction entre les deux valeurs possible de y, il suffit donc d'indiquer si y est pair ou bien impair.

La compression d'une clé publique permet de réduire sa taille de 520 bits à 264 bits. 

Nous utilisons le préfixe 0x02 pour un y pair et 0x03 pour un y impair. C'est la forme compressée de la clé publique.

### Etape 2 : Hachage de la clef publique compressée

![image](assets/image/section5/3.webp)

Le hachage de la clef publique compressée est effectuée avec la fonction SHA256. La fonction RIPEMD160 est ensuite appliquée sur le condensat.

### Etape 3 : Le payload = Charge utile de l'adresse

![image](assets/image/section5/4.webp)

Le condensat en binaire de RIPEMD160(SHA256(K)) permet de former des groupes de 5 bits. Chaque groupe est transformé en base16 (Hexadécimal) et/ou en base 10.

### Etape 4 : Ajout des métadonnées pour le calcul de la checksum avec le programme BCH

![image](assets/image/section5/5.webp)

Dans le cas des adresses legacy, nous utilisons le double hachage SHA256 pour générer la somme de contrôle de l'adresse. Cependant, pour les adresses Segwit V0 et V1, nous faisons appel à la technologie de checksum BCH pour assurer la détection des erreurs. Le programme BCH est capable de suggérer et de corriger les erreurs avec une probabilité d'erreur extrêmement faible. Actuellement, le programme BCH est utilisé pour détecter et suggérer les modifications à apporter, mais il ne les effectue pas automatiquement à la place de l'utilisateur.

Le programme BCH requiert plusieurs informations en entrée, dont le HRP (Human Readable Part) qui doit être étendu. L'extension du HRP consiste à encoder chaque lettre en base 2 celon leur code ASCII. Puis, en prenant les transformer les 3 premiers bits du résultat pour chaque lettre en base 10 (en bleu sur l'image). Insérer un séparateur 0. Puis concatener à la suite les 5 derniers bits de chaque lettre préalablement transformés en base 10 (en jaune sur l'image).

L'extension du HRP en base 10 permet d'isoler les cinq derniers bits de chaque caractère, renforçant ainsi la checksum.

La version Segwit V0 est représentée par le code 00 et le "payload" est en noir, en base 10. Cela est suivi de six caractères réservés pour la checksum. 

### Etape 5 : Calcul de la somme de contrôle avec le programme BCH

![image](assets/image/section5/6.webp)

L'entrée contenant les métadonnées est ensuite soumise au programme BCH pour obtenir la checksum en base 10. 

Nous avons ici la checksum.

### Etape 6 : Construction de l'adresse et conversion en Bech32

![image](assets/image/section5/7.webp)

La concaténation de la version, du payload et de la checksum permet de construire l'adresse. Les caractères en base 10 sont ensuite convertis en caractères bech32 à l'aide d'une table de correspondance. L'alphabet bech32 comprend tous les caractères alphanumériques, à l'exception de 1, b, i et o, afin d'éviter toute confusion.



### Etape 7 : Ajout du HRP et du séparateur

![image](assets/image/section5/8.webp)

En rose la checksum.
En noir, le payload = le hash de la clef publique.
En bleu, la version.

Le tout est converti en Bech32, puis est rajouté 'bc' pour bitcoin et '1' comme séparateur et voici l'adresse.

# Allez plus loins
<partId>58111408-b734-54db-9ea7-0d5b67f99f99</partId>

## Création d’une seed depuis 128 lancés de dés !
<chapterId>0f4d40a7-cf0e-5faf-bc4d-691486771ac1</chapterId>

![Création d’une seed depuis 128 lancés de dés !](https://youtu.be/lUw-1kk75Ok)

La création d'une phrase mnémonique est une étape cruciale pour la sécurisation de votre portefeuille de crypto-monnaie. Il existe plusieurs méthodes pour générer une phrase mnémonique, cependant, nous allons nous focaliser sur la méthode de génération manuelle utilisant des dés. Il est important de souligner que cette méthode n'est pas adaptée pour un portefeuille de grande valeur. Il est conseillé d'utiliser un logiciel open source ou un portefeuille matériel pour générer la phrase mnémonique. Pour créer une phrase mnémonique, nous allons utiliser des dés pour générer une information binaire. L'objectif est de comprendre le processus de création de la phrase mnémonique.

**Étape 1 - Préparation :**
Assurez-vous d'avoir une distribution Linux amnésique, comme Tails OS, installée sur une clé USB pour plus de sécurité. Notez que ce tutoriel ne devrait pas être utilisé pour créer un portefeuille principal.

**Étape 2 - Génération d'un nombre aléatoire binaire :**
Nous allons utiliser des dés pour générer une information binaire. Lancez un dé 128 fois et notez chaque résultat (1 pour impair, 0 pour pair).

**Étape 3 - Organisation des nombres binaires :**
Organisez les nombres binaires obtenus en rangées de 11 chiffres pour faciliter les calculs ultérieurs. La douzième ligne ne devrait que 7 chiffres.

**Étape 4 - Calcul de la checksum :**
Les derniers 4 chiffres pour la douxième ligne correspondent à la checksum. Pour calculer cette checksum, il nous faut utiliser un terminal d'une distribution Linux. Il est conseillé d'utiliser [TailOs](https://tails.boum.org/index.fr.html) qui est une distribution sans mémoire bootable à partir d'une clé USB. Une fois sur votre terminal, entrez la commande `echo <binary number> | shasum -a 254 -0`. Remplacer `<binary number>` par votre liste de 128 zéro et un. La sortie est un hash en hexadécimal. Relevez le premier caractère de ce hash et convertissez le en binaire. Vous pouvez vous aider de cette [table](https://www.educative.io/answers/decimal-binary-and-hex-conversion-table). Ajoutez la checksum en binaire (4 chiffres) à la douxième ligne de votre feuille.

**Étape 5 - Conversion en décimale :**
Pour trouver les mots associés à chacune de vos lignes, il vous faut d'abord convertir en décimal chaque séries de 11 bits. Ici vous ne pouvez pas utiliser de convertisseur en ligne car ces bits représentent votre phrase mnémonique. Il va donc falloir convertir à l'aide d'une calculatrice et d'une astuce que voici : chaque bit est associé à une puissance de 2 ainsi de la gauche vers la droite nous avons 11 rangs qui correspondent à respectivement 1024, 512, 256, 128, 64, 32, 16, 8, 4, 2, 1. Pour convertir votre série de 11 bit en décimal il vous suffit d'additionner uniquement les rangs qui contiennent un 1. Par exemple pour la série 00110111011, cela correspond à l'addtion suivante : 256 + 128 + 32 + 16 + 8 + 2 + 1 = 443. Vous pouvez maintenant convertir chaque ligne en décimale. Et avant de passer à l'encodage en mots il faut ajouter +1 à toutes les lignes car l'index de la liste des mots BIP39 commence à partir de 1 et non 0.

**Étape 8 - Génération de la phrase mnémonique :**
Commencez par imprimer la [liste des 2048 mots](https://seedxor.com/files/wordlist.pdf) pour faire la conversion entre vos nombres décimales et les mots du BIP39. La particularité de cette liste est qu'aucun mot ne possède ces 4 premières lettres en commun avec tous les autres mots de ce dictionnaire. Puis chercher pour chacune de vos lignes le mots associés au nombre décimal.

**Étape 9 - Test de la phrase mnémonique :**
Testez immédiatement votre phrase mnémonique sur Sparrow Wallet en créant un portefeuille à partir de celle-ci. Si vous obtenez une erreur de checksum invalide, il est probable que vous ayez fait une erreur de calcul. Corrigez cette erreur en repartant à l'étape 4 et testez à nouveau sur Sparrow Wallet. Voilà ! Vous venez de créer un nouveau portefeuille Bitcoin à partir de 128 lancés de dés.

Générer une phrase mnémonique est un processus important pour sécuriser votre portefeuille de crypto-monnaie. Il est recommandé d'utiliser des méthodes plus sécurisées, comme l'utilisation de logiciels open source ou de hardware wallet, pour générer la phrase mnémonique. Toutefois, réaliser cet atelier permet de mieux saisir comment à partir d'un nombre aléatoire nous pouvons créer un portefeuille Bitcoin.

## BONUS: Interview avec Théo Pantamis
<chapterId>39f0ec5a-e258-55cb-9789-bc46d314d816</chapterId>

Une autre méthode cryptographique grandement utilisée sur le protocole Bitcoin est la méthode des signatures numériques.

![video](https://youtu.be/c9MvtGJsEvY?si=bQ1N5NCd6op0G6nW)



## Évaluez ce cours
<chapterId>0cd71541-a7fd-53db-b66a-8611b6a28b04</chapterId>
<isCourseReview>true</isCourseReview>

## Examen final
<chapterId>a53ea27d-0f84-56cd-b37c-a66210a4b31d</chapterId>
<isCourseExam>true</isCourseExam>


## Conclusion et fin
<chapterId>d291428b-3cfa-5394-930e-4b514be82d5a</chapterId>

### Remerciements et continuez à creuser le terrier du lapin

Nous tenons à vous remercier sincèrement d'avoir suivi la formation Crypto 301. Nous espérons que cette expérience a été enrichissante et formatrice pour vous. Nous avons abordé de nombreux sujets passionnants, allant des mathématiques à la cryptographie en passant par le fonctionnement du protocole Bitcoin.

Si vous souhaitez approfondir davantage le sujet, nous avons une ressource supplémentaire à vous offrir. Nous avons réalisé une interview exclusive avec Théo Pantamis et Loïc Morel, deux experts renommés dans le domaine de la cryptographie. Cette interview explore en profondeur divers aspects du sujet et offre des perspectives intéressantes.

N'hésitez pas à regarder cette interview pour continuer à explorer le domaine fascinant de la cryptographie. Nous espérons que cela vous sera utile et inspirant dans votre parcours. Encore une fois, merci de votre participation et de votre engagement tout au long de cette formation.

### Soutiens-nous

Ce cours, ainsi que l'intégralité du contenu présent sur cette université, vous a été offert gratuitement par notre communauté. Pour nous soutenir, vous pouvez le partager autour de vous, devenir membre de l'université et même contribuer à son développement via GitHub. Au nom de toute l'équipe, merci !

### Note la formation

Un système de notation pour la formation sera bientôt intégré à cette nouvelle plateforme de E-learning ! En attendant, merci beaucoup d'avoir suivi le cours et si vous l'avez apprécié, pensez à le partager autour de vous.

