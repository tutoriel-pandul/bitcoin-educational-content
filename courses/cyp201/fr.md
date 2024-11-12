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


***REFAIRE L'INTRO + ACCROCHE PAGE D'ACCUEIL***



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

La deuxième méthode cryptographique utilisée dans Bitcoin concerne les algorithmes de signatures numériques. Examinons ensemble en quoi cela consiste et comment cela fonctionne.

### Bitcoins, UTXOs et conditions de dépense

Le terme "*wallet*" sur Bitcoin est assez déroutant pour les débutants. En effet, ce que l'on appelle un portefeuille Bitcoin est un logiciel qui ne conserve pas directement vos bitcoins, contrairement à un portefeuille physique qui permet de conserver des pièces ou des billets. Les bitcoins sont simplement des unités de compte. Cette unité de compte est représentée par des **UTXO** (*Unspent Transaction Outputs*), qui sont des sorties de transactions non dépensées. Si ces sorties ne sont pas dépensées, cela signifie qu'elles appartiennent à un utilisateur. Les UTXOs sont donc en quelque sorte des morceaux de bitcoins, d'une taille variable, appartenant à un utilisateur.

Le protocole Bitcoin est distribué et fonctionne sans autorité centrale. On ne peut donc pas faire comme dans les registres bancaires traditionnels, où les euros qui vous appartiennent sont simplement associés à votre identité personnelle. 

Sur Bitcoin, vos UTXOs vous appartiennent car ils sont protégés par des conditions de dépense spécifiées dans le langage Script. Pour simplifier, il existe deux types de scripts : le script de verrouillage (*scriptPubKey*), qui protège un UTXO, et le script de déverrouillage (*scriptSig*), qui permet de déverrouiller un UTXO et ainsi de dépenser les unités de bitcoins qu'il représente.

Le fonctionnement initial de Bitcoin avec les scripts P2PK consiste à utiliser une clé publique pour verrouiller les fonds, en spécifiant dans un *scriptPubKey* que la personne souhaitant dépenser cet UTXO doit fournir une signature valide avec la clé privée correspondant à cette clé publique. Pour déverrouiller cet UTXO, il est donc nécessaire de fournir une signature valide dans le *scriptSig*. Comme leurs noms l'indiquent, la clé publique est connue de tous puisqu'elle est diffusée sur la blockchain, tandis que la clé privée est uniquement connue du propriétaire légitime des fonds.

Ça, c'est le fonctionnement de base de Bitcoin, mais au fil des mises à jour, ce fonctionnement s'est complexifié. D'abord, Satoshi a également introduit les scripts P2PKH, qui utilisent une adresse de réception dans le *scriptPubKey*, laquelle représente le hachage de la clé publique. Puis, le système s'est encore complexifié avec l'arrivée de SegWit puis de Taproot. Cependant, le principe général reste fondamentalement le même : une clé publique ou une représentation de cette clé sert à verrouiller les UTXOs, et une clé privée correspondante est requise pour les déverrouiller et donc les dépenser.

L'utilisateur qui souhaite faire une transaction Bitcoin doit donc établir une signature numérique à l'aide de sa clé privée sur la transaction en question. La signature pourra être vérifiée par les autres participants du réseau. Si elle est valide, cela signifie que l'utilisateur qui initie la transaction est bien le propriétaire de la clé privée, et donc qu'il est bien le propriétaire des bitcoins qu'il souhaite dépenser. Les autres utilisateurs pourront alors accepter et propager la transaction.

En conséquence, un utilisateur qui possède des bitcoins verrouillés avec une clé publique doit trouver un moyen de stocker de manière sécurisée ce qui permet de débloquer ses fonds : la clé privée. Un portefeuille Bitcoin est justement un dispositif qui va vous permettre de conserver facilement toutes vos clés sans que d'autres personnes n'y aient accès. Cela ressemble donc plus à un porte-clés qu'à un portefeuille.

Le lien mathématique entre une clé publique et une clé privée, ainsi que la possibilité de réaliser une signature pour prouver la possession d'une clé privée sans la dévoiler, sont rendus possibles par un algorithme de signature numérique. Dans le protocole Bitcoin, on utilise 2 algorithmes de signature : **ECDSA** (*Elliptic Curve Digital Signature Algorithm*) et le **schéma de signature de Schnorr**. ECDSA est le protocole de signature numérique utilisé dans Bitcoin depuis ses débuts. Schnorr est plus récent dans Bitcoin, puisqu'il a été introduit en novembre 2021 avec la mise à jour Taproot.

Ces deux algorithmes sont assez similaires dans leurs mécanismes. Ils sont tous deux basés sur la cryptographie sur les courbes elliptiques. La différence majeure entre ces deux protocoles réside dans la structure de la signature et certaines propriétés mathématiques spécifiques. Nous allons donc étudier le fonctionnement de ces algorithme en commençant par le plus ancien : ECDSA.

### La cryptographie sur les courbes elliptiques

La cryptographie sur les courbes elliptiques (ECC) est un ensemble d'algorithmes qui utilisent une courbe elliptique pour ses différentes propriétés mathématiques et géométriques dans un objectif cryptographique. La sécurité de ces algorithmes repose sur la difficulté du problème du logarithme discret sur les courbes elliptiques. Les courbes elliptiques sont notamment utilisées pour réaliser des échanges de clés, du chiffrement asymétrique, ou encore pour réaliser des signatures numériques.

Une propriété importante de ces courbes est qu'elles sont symétriques par rapport à l'axe des abscisses. Ainsi, toute droite non verticale coupant la courbe en deux points distincts intersectera toujours la courbe en un troisième point. De plus, toute tangente à la courbe en un point non singulier recoupera la courbe en un autre point. Ces propriétés seront utiles pour définir les opérations sur la courbe.

Voici une représentation d'une courbe elliptique sur le corps des réels :

014

Toute courbe elliptique est définie par une équation de la forme :

$$
y^2 = x^3 + ax + b
$$

### secp256k1

Pour utiliser ECDSA ou Schnorr, il faut choisir les paramètres de la courbe elliptique, c'est-à-dire les valeurs de $a$ et de $b$ dans l'équation de la courbe. Il existe différents standards de courbes elliptiques réputées cryptographiquement sûres. La plus connue est la courbe *secp256r1*, définie et recommandée par le NIST (*National Institute of Standards and Technology*).

Malgré cela, Satoshi Nakamoto, l'inventeur de Bitcoin, a choisi de ne pas utiliser cette courbe. La raison de ce choix est inconnue, mais certains pensent qu'il a préféré trouver une alternative car les paramètres de cette courbe pourraient potentiellement contenir une backdoor. À la place, le protocole Bitcoin utilise la courbe standard ***secp256k1***. Cette courbe définie par les paramètres $a = 0$ et $b = 7$. Son équation est donc :

$$
y^2 = x^3 + 7
$$

Sa représentation graphique sur le corps des réels ressemble à ceci :

015

Cependant, en cryptographie, nous travaillons sur des ensembles finis de nombres. Plus précisément, nous travaillons sur le corps fini $\mathbb{F}_p$, qui est le corps des entiers modulo un nombre premier $p$.

**Définition** : Un nombre premier est un entier naturel supérieur ou égal à 2 qui n'admet que deux diviseurs entiers positifs distincts : 1 et lui-même. Par exemple, le nombre 7 est un nombre premier puisqu'il ne peut être divisé que par 1 et 7. En revanche, le nombre 8 n'est pas premier, car il peut être divisé par 1, 2, 4 et 8.

Dans Bitcoin, le nombre premier $p$ utilisé pour définir le corps fini est très grand. Il est choisi de manière à ce que l'ordre du corps (c'est-à-dire le nombre d'éléments dans $\mathbb{F}_p$) soit suffisamment grand pour assurer la sécurité cryptographique.

Le nombre premier $p$ utilisé est :

```txt
p = 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFEFFFFFC2F
```

En notation décimale, cela correspond à :
$$
p = 2^{256} - 2^{32} - 977
$$

Ainsi, l'équation de notre courbe elliptique est en réalité :
$$
y^2 \equiv x^3 + 7 \mod p
$$

Étant donné que cette courbe est définie sur le corps fini $\mathbb{F}_p$, elle ne ressemble plus à une courbe continue mais plutôt à un ensemble discret de points. Par exemple, voici à quoi ressemble la courbe utilisée dans Bitcoin pour un tout petit $p = 17$ :

016

Dans cet exemple, nous avons intentionnellement limité le corps fini à $p = 17$ pour des raisons pédagogiques, mais il faut imaginer que celui utilisé dans Bitcoin est immensément plus grand, presque $2^{256}$.

Nous utilisons un corps fini d'entiers modulo $p$ afin d'assurer la précision des opérations sur la courbe. En effet, les courbes elliptiques sur le corps des réels sont sujettes à des imprécisions dues aux erreurs d'arrondi lors des calculs informatiques. Si l'on effectue de nombreuses opérations sur la courbe, ces erreurs s'accumulent et le résultat final peut être incorrect ou difficilement reproductible. L'utilisation exclusive d'entiers positifs permet d'assurer une précision parfaite des calculs et donc une reproductibilité du résultat.

Les mathématiques des courbes elliptiques sur les corps finis sont analogues à celles sur le corps des réels, avec l'adaptation que toutes les opérations sont effectuées modulo $p$. Pour simplifier les explications, nous continuerons dans les prochains chapitres à illustrer les concepts en utilisant une courbe définie sur les nombres réels, tout en gardant à l'esprit que, dans la pratique, la courbe est définie sur un corps fini.

Si vous souhaitez en savoir plus sur les bases mathématiques de la cryptographie moderne, je vous conseille par la suite de consulter également cette autre formation sur PlanB Network :

https://planb.network/courses/cyp302




## Calculer la clé publique à partir de la clé privée
<chapterId>fcb2bd58-5dda-5ecf-bb8f-ad1a0561ab4a</chapterId>

Comme vu précédemment, les algorithmes de signature numérique sur Bitcoin sont basés sur un couple clé privée / clé publique qui sont liées mathématiquement. Découvrons ensemble quel est ce lien mathématique et comment elles sont générées.

### La clé privée

La clé privée est simplement un nombre aléatoire ou pseudo-aléatoire. Dans le cas de Bitcoin, ce nombre est d'une taille de 256 bits. Le nombre de possibilités pour une clé privée Bitcoin est donc théoriquement de $2^{256}$.

**Remarque** : Un "nombre pseudo-aléatoire" est un nombre qui possède des propriétés s'approchant de celles d'un nombre véritablement aléatoire, mais qui est généré par un algorithme déterministe.

Cependant, en pratique, il existe seulement $n$ points distincts sur notre courbe elliptique secp256k1, où $n$ est l'ordre du point générateur $G$ de la courbe. Nous verrons plus tard à quoi correspond ce nombre, mais retenez simplement qu'une clé privée valide est un nombre entier compris entre $1$ et $n-1$, en sachant que $n$ est un nombre proche mais légèrement plus petit que $2^{256}$. Il existe donc certains nombres de 256 bits qui ne sont pas valides pour devenir une clé privée dans Bitcoin, en l'occurrence, ce sont tous les nombres compris entre $n$ et $2^{256}$. Si la génération du nombre aléatoire (la clé privée) produit une valeur $k$ telle que $k \geq n$, celle-ci est considérée comme invalide, et il faudra générer une nouvelle valeur aléatoire.

Le nombre de possibilités pour une clé privée Bitcoin est donc d'environ $n$, qui est un nombre proche de $1.158 \times 10^{77}$. C'est un nombre tellement grand que si vous choisissez une clé privée aléatoirement, il est statistiquement presque impossible de tomber sur la clé privée d'un autre utilisateur. Pour vous donner un ordre de grandeur, le nombre de clés privées possibles sur Bitcoin est d’un ordre de magnitude proche de celui des atomes estimés dans l'univers observable.

Comme nous le verrons dans les prochains chapitres, aujourd'hui, la majorité des clés privées utilisées sur Bitcoin ne sont pas générées aléatoirement mais sont le résultat d'une dérivation déterministe depuis une phrase mnémonique, elle-même pseudo-aléatoire (c'est la fameuse phrase de 12 ou 24 mots). Cette information ne change rien pour l'utilisation des algorithmes de signature comme ECDSA, mais elle permet de recentrer notre vulgarisation sur Bitcoin.

Pour la suite de l'explication, la clé privée sera notée par la lettre minuscule $k$.

### La clé publique

La clé publique est un point sur la courbe elliptique, noté par la lettre majuscule $K$, et est calculée à partir de la clé privée $k$. Ce point $K$ est représenté par une paire de coordonnées $(x, y)$ sur la courbe elliptique, chaque coordonnée étant un entier modulo $p$, le nombre premier définissant le corps fini $\mathbb{F}_p$.

En pratique, une clé publique non compressée est représentée par 512 bits (ou 64 octets), correspondant à deux nombres mis bout-à-bout de 256 bits ($x$ et $y$). Ces nombres, ce sont l'abscisse ($x$) et l'ordonnée ($y$) de notre point sur secp256k1. Si l'on ajoute le préfixe, la clé publique fait au total 520 bits.

Cependant, il est aussi possible de représenter la clé publique de manière compressée en utilisant seulement 33 octets (264 bits) en conservant uniquement l'abscisse $x$ de notre point sur la courbe et un octet indiquant la parité de $y$. C'est ce qu'on appelle une clé publique compressée. Je vous en parlerai plus en détail dans les derniers chapitres de cette formation. Mais ce qu'il faut retenir, c'est qu'une clé publique $K$ est un point décris par $x$ et $y$.

Pour calculer le point $K$ qui correspond à notre clé publique, nous utilisons l'opération de multiplication scalaire sur les courbes elliptiques, définie comme une addition répétée ($k$ fois) du point générateur $G$ :

$$
K = k \cdot G
$$

où :
- $k$ est la clé privée (un entier aléatoire compris entre $1$ et $n-1$) ;
- $G$ est le point générateur de la courbe elliptique utilisé par tous les participants du réseau Bitcoin ;
- $\cdot$ représente la multiplication scalaire sur la courbe elliptique, qui équivaut à ajouter le point $G$ à lui-même $k$ fois.

Le fait que ce point $G$ soit commun à toutes les clés publiques sur Bitcoin nous permet d'être sûr qu'une même clé privée $k$ nous donnera toujours la même clé publique $K$ :

017

La principale caractéristique de cette opération est qu'elle est une fonction à sens unique. Il est facile de calculer la clé publique $K$ en connaissant la clé privée $k$ et le point générateur $G$, mais il est pratiquement impossible de calculer la clé privée $k$ en connaissant seulement la clé publique $K$ et le point générateur $G$. Trouver $k$ à partir de $K$ et $G$ revient à résoudre le problème du logarithme discret sur les courbes elliptiques, un problème mathématiquement difficile pour lequel il n'existe pas d'algorithme efficace connu. Même les calculateurs les plus puissants actuels sont incapables de résoudre ce problème dans un temps raisonnable.

018

### Addition et doublement de points sur les courbes elliptiques

La notion d'addition sur les courbes elliptiques est définie de manière géométrique. Si nous avons deux points $P$ et $Q$ sur la courbe, l'opération $P + Q$ est calculée en traçant la droite passant par $P$ et $Q$. Cette droite coupera forcément la courbe en un troisième point $R'$. Nous prenons alors le symétrique de ce point par rapport à l'axe des abscisses pour obtenir le point $R$, qui est le résultat de l'addition :

$$
P + Q = R
$$

Graphiquement, cela peut être représenté comme suit :

019

Pour le doublement d'un point, c'est-à-dire l'opération $P + P$, nous traçons la tangente à la courbe en ce point $P$. Cette tangente coupe la courbe en un autre point $S'$. Nous prenons alors le symétrique de ce point par rapport à l'axe des abscisses pour obtenir le point $S$, qui est le résultat du doublement :

$$
2P = S
$$

Graphiquement, cela donne :

020

En utilisant ces opérations d'addition et de doublement, nous pouvons effectuer la multiplication scalaire d'un point par un entier $k$, notée $kP$, en effectuant des doublements répétés et des additions.

Par exemple, supposons que nous ayons choisi une clé privée $k = 4$. Pour calculer la clé publique associée, nous effectuons :

$$
K = k \cdot G = 4G
$$

Graphiquement, cela correspond à effectuer une série d'additions et de doublements :
- Calculer $2G$ en doublant $G$.
- Calculer $4G$ en doublant $2G$.

021

Si l’on souhaite, par exemple, calculer le point $3G$, nous devons d’abord calculer le point $2G$ en doublant le point $G$, puis additionner $G$ et $2G$. Pour additionner $G$ et $2G$, il suffit de tracer la droite reliant ces deux points, de récupérer le point unique $-3G$ à l’intersection entre cette droite et la courbe elliptique, puis de déterminer $3G$ comme l’opposé de $-3G$.

Nous aurons donc :
$$
G + G = 2G
$$
$$
2G + G = 3G
$$

Graphiquement, cela se représenterait ainsi :

022

### Fonction à sens unique

Grâce à ces opérations, nous pouvons comprendre pourquoi il est facile de dériver une clé publique à partir d'une clé privée, mais l'inverse est pratiquement impossible.

Reprenons notre exemple simplifié. Avec une clé privée $k = 4$. Pour calculer la clé publique associée, nous effectuons :

$$
K = k \cdot G = 4G
$$

Nous avons donc pu facilement calculer la clé publique $K$ en connaissant $k$ et $G$.

Maintenant, si quelqu'un connaît uniquement la clé publique $K$, il est confronté au problème du logarithme discret : trouver $k$ tel que $K = k \cdot G$. Ce problème est considéré comme difficile car il n'existe pas d'algorithme efficace pour le résoudre sur les courbes elliptiques. Cela assure la sécurité des algorithmes ECDSA et Schnorr.

Bien sûr, dans cet exemple simplifié avec $k = 4$, il serait possible de trouver $k$ par essai successif, car le nombre de possibilités est faible. Cependant, en pratique sur Bitcoin, $k$ est un entier de 256 bits, ce qui rend le nombre de possibilités astronomiquement grand (environ $1.158 \times 10^{77}$). Il est donc infaisable de trouver $k$ par force brute.


## Signer avec la clé privée
<chapterId>bb07826f-826e-5905-b307-3d82001fb778</chapterId>

Maintenant que vous savez dériver une clé publique à partir d’une clé privée, vous pouvez déjà recevoir des bitcoins en utilisant cette paire de clés comme condition de dépense. Mais comment les dépenser ? Pour dépenser des bitcoins, il va falloir déverrouiller le *scriptPubKey* apposé sur votre UTXO pour prouver que vous en êtes bien le propriétaire légitime. Pour ce faire, il faut produire une signature $s$ qui correspond à la clé publique $K$ présente dans le *scriptPubKey* à l'aide de la clé privée $k$ qui a servi initialement à calculer $K$. La signature numérique est ainsi une preuve irréfutable que vous êtes bien en possession de la clé privée associée à la clé publique que vous revendiquez.

### Les paramètres de la courbe elliptique

Pour réaliser une signature numérique, il faut tout d’abord que tous les participants se mettent d'accord sur les paramètres de la courbe elliptique utilisée. Dans le cas de Bitcoin, les paramètres de **secp256k1** sont les suivants :

Le champ fini $\mathbb{Z}_p$ défini par :

$$
p = 2^{256} - 2^{32} - 977
$$

```txt
p = 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFEFFFFFC2F
```

$p$ est un nombre premier très grand légèrement inférieur à $2^{256}$.

La courbe elliptique $y^2 = x^3 + ax + b$ sur $\mathbb{Z}_p$ définie par :

$$
a = 0, \quad b = 7
$$

Le point générateur ou point d'origine $G$ :

```txt
G = 0x0279BE667EF9DCBBAC55A06295CE870B07029BFCDB2DCE28D959F2815B16F81798
```

Ce nombre est la forme compressée qui donne uniquement l’abscisse du point $G$. Le préfixe `02` au départ permet de déterminer laquelle des deux valeurs ayant cette abscisse $x$ est à utiliser comme point générateur.

L'ordre $n$ de $G$ (le nombre de points existants) et le cofacteur $h$ :

```txt
n = 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFEBAAEDCE6AF48A03BBFD25E8CD0364141
```

$n$ est un nombre très grand légèrement inférieur à $p$.

$$
h=1
$$

$h$ est le cofacteur ou le nombre de sous-groupes. Je ne vais pas développer ce que cela représente ici, car c’est assez complexe, et dans le cas de Bitcoin, nous n’avons pas besoin de le prendre en compte puisqu’il est égal à $1$.

Toutes ces informations sont publiques et connues de tous les participants. Grâce à elles, les utilisateurs sont en capacité de réaliser une signature numérique et de la vérifier.

### Signature avec ECDSA

L'algorithme ECDSA permet à un utilisateur de signer un message en utilisant sa clé privée, de manière à ce que toute personne connaissant la clé publique correspondante puisse vérifier la validité de la signature, sans que la clé privée ne soit jamais révélée. Dans le contexte de Bitcoin, le message à signer dépend du *sighash* choisi par l'utilisateur. C'est ce *sighash* qui va déterminer quelles parties de la transaction sont couvertes par la signature. Je vous en parlerai plus en détail dans le chapitre suivant. 

Voici les étapes pour générer une signature ECDSA :

Tout d'abord on va calculer le hash ($e$) du message qui doit être signé. Le message $m$ est donc passé dans une fonction de hachage cryptographique, généralement SHA256 ou double SHA256 dans le cas de Bitcoin :
$$
e = \text{HASH}(m)
$$

Ensuite, on va calculer un nonce. En cryptographie, un nonce est simplement un nombre généré de manière aléatoire ou pseudo-aléatoire qui est utilisé une seule fois. C'est-à-dire qu'à chaque fois que l'on réalise une nouvelle signature numérique avec cette paire de clés, il sera très important d'utiliser un nonce différent, sinon cela compromettra la sécurité de la clé privée. Il suffit donc de déterminer un entier aléatoire et unique $r$ tel que $1 \leq r \leq n-1$, où $n$ est l'ordre du point générateur $G$ de la courbe elliptique.

Puis, nous allons calculer le point $R$ sur la courbe elliptique avec les coordonnées $(x_R, y_R)$ tel que :
$$
R = r \cdot G
$$

On extrait la valeur de l'abscisse du point $R$ ($x_R$). Cette valeur représente la première partie de la signature. Et enfin, on calcule la seconde partie de la signature $s$ de cette manière :
$$
s = r^{-1} \left( e + k \cdot x_R \right) \mod n
$$

où :
- $r^{-1}$ est l'inverse modulaire de $r$ modulo $n$, c'est-à-dire un entier tel que $r \cdot r^{-1} \equiv 1 \mod n$ ;
- $k$ est la clé privée de l'utilisateur ;
- $e$ est le hash du message ;
- $n$ est l'ordre du point générateur $G$ de la courbe elliptique.

La signature est alors simplement la concaténation $x_R$ et de $s$ :
$$
\text {SIG} = x_R \| s
$$

### Vérification de la signature ECDSA

Pour vérifier une signature $(x_R, s)$, toute personne connaissant la clé publique $K$ et les paramètres de la courbe elliptique peut procéder de cette façon :

Tout d'abord, on vérifie que $x_R$ et $s$ sont bien dans l'intervalle $[1, n-1]$. Cela garantit que la signature respecte les contraintes mathématiques du groupe elliptique. Si ce n’est pas le cas, le vérificateur rejette immédiatement la signature comme invalide.

Puis, on calcul le hash du message :
$$
e = \text{HASH}(m)
$$

On calcule l'inverse modulaire de $s$ modulo $n$ :
$$
s^{-1} \mod n
$$

On calcule deux valeurs scalaires $u_1$ et $u_2$ de cette manière :
$$
\begin{align*}
u_1 &= e \cdot s^{-1} \mod n \\
u_2 &= x_R \cdot s^{-1} \mod n
\end{align*}
$$

Et enfin, on calcule le point $V$ sur la courbe elliptique tel que :
$$
V = u_1 \cdot G + u_2 \cdot K
$$

La signature est valide uniquement si $x_V \equiv x_R \mod n$, où $x_V$ est la coordonnée $x$ du point $V$. En effet, en combinant $u_1 \cdot G$ et $u_2 \cdot K$, on obtient un point $V$ qui, si la signature est valide, doit correspondre au point $R$ utilisé lors de la signature (modulo $n$).


### Signature avec le protocole de Schnorr

Le schéma de signature de Schnorr est une alternative à ECDSA qui offre de nombreux avantages. Il est possible de l'utiliser sur Bitcoin depuis 2021 et l'introduction de Taproot, avec les modèles  script P2TR. Comme ECDSA, le schéma de Schnorr permet de signer un message en utilisant une clé privée, de manière à ce que la signature puisse être vérifiée par toute personne connaissant la clé publique correspondante.

Dans le cas de Schnorr on utilise exactement la même courbe que ECDSA avec les mêmes paramètres. En revanche, les clés publiques sont représentées légèrement différemment par rapport à ECDSA. En effet, on les désigne uniquement par la coordonnée $x$ du point sur la courbe elliptique. Contrairement à ECDSA, où les clés publiques compressées sont représentées par 33 octets (avec l'octet de préfixe indiquant la parité de $y$), Schnorr utilise des clés publiques de 32 octets, correspondant uniquement à la coordonnée $x$ du point $K$, et on considère que $y$ est pair par défaut. Cette représentation simplifiée permet de réduire la taille des signatures et facilite certaines optimisations dans les algorithmes de vérification.

La clé publique est alors la coordonnée $x$ du point $K$ :
$$
\text{pk} = K_x
$$

La première étape pour générer une signature est de hacher le message. Mais contrairement à ECDSA, on va le faire avec d'autres valeurs et on va utiliser une fonction de hachage étiquetée pour éviter les collisions dans différents contextes. Une fonction de hachage étiquetée consiste simplement à ajouter une étiquette arbitraire dans les inputs de la fonction de hachage aux côté des données du message.

023

En plus du message, on va également passer dans la fonction étiquetée l'abscisse de la clé publique $K_x$, ainsi qu'un point $R$ calculé à partir du nonce $r$ ($R=r \cdot G$) qui est lui-même un entier unique pour chaque signature, calculé de manière déterministe à partir de la clé privée et du message pour éviter les vulnérabilités liées à la réutilisation du nonce. De la même manière que pour la clé publique, seule l'abscisse du point du nonce $R_x$ est conservée pour décrire le point.

Le résultat de ce hachage noté $e$ s'appelle le "challenge" :

$$
e = \text{HASH}(\text{``BIP0340/challenge''}, R_x || K_x || m) \mod n
$$

Ici, $\text{HASH}$ est la fonction de hachage SHA256, et $\text{``BIP0340/challenge''}$ est le tag spécifique pour le hachage.

Et enfin, on calcule le paramètre $s$ de cette manière à partir de la clé privée $k$, du nonce $r$ et du challenge $e$ :
$$
s = (r + e \cdot k) \mod n
$$

La signature est ensuite simplement le couple $Rx$ et $s$. 
$$
\text{SIG} = R_x || s
$$

### Vérification de la signature Schnorr

La vérification d'une signature Schnorr est plus simple que celle d'une signature ECDSA. Voici les étapes pour vérifier la signature $(R_x, s)$ avec la clé publique $K_x$ et le message $m$ :

Tout d'abord, on vérifie que $K_x$ est un entier valide et inférieur à $p$. Si c'est le cas, on récupère le point correspondant sur la courbe avec $K_y$ pair. On va également extraire $R_x$ et $s$ en séparant la signature $\text{SIG}$. Puis, nous vérifions que $R_x < p$ et $s < n$ (l'ordre de la courbe).

Ensuite, on calcule le challenge $e$ de la même manière que l'a fait l'émetteur de la signature :
$$
e = \text{HASH}(\text{``BIP0340/challenge''}, R_x || K_x || m) \mod n
$$

Et enfin, on calcule un point de référence sur la courbe de cette façon :
$$
R' = s \cdot G - e \cdot K
$$

Enfin, on vérifie que $R'_x = R_x$. Si les deux abscisses correspondent, alors la signature $(R_x, s)$ est bien valide avec la clé publique $K_x$.

### Pourquoi cela fonctionne-t-il ?

Le signataire a calculé $s = r + e \cdot k \mod n$, donc $R' = s \cdot G - e \cdot K$ devrait être égal au point $R$ original, car :
$$
s \cdot G = (r + e \cdot k) \cdot G = r \cdot G + e \cdot k \cdot G
$$

Puisque $K = k \cdot G$, on a $e \cdot k \cdot G = e \cdot K$. Ainsi :
$$
R' = r \cdot G = R
$$

On a donc bien : 
$$
R'_x = R_x
$$

### Les avantages des signatures de Schnorr

Le schéma de signature de Schnorr présente plusieurs avantages pour Bitcoin par rapport à l'algorithme original ECDSA. Tout d’abord, Schnorr permet l'agrégation des clés et des signatures. Cela signifie que plusieurs clés publiques peuvent être combinées en une seule clé.

024

Et de même, plusieurs signatures peuvent être agrégées en une seule signature valide. Ainsi, dans le cas d'une transaction multisignatures, un ensemble de participants peut signer avec une seule signature et une seule clé publique agrégée. Cela réduit considérablement les coûts de stockage et de calcul pour le réseau, car chaque nœud n’a besoin de vérifier qu'une seule signature.

025

De plus, l’agrégation des signatures améliore la confidentialité. Avec Schnorr, il devient impossible de distinguer une transaction multisignature d'une transaction standard à une seule signature. Cette homogénéité rend les analyses de la chaîne plus difficile, car elle limite la possibilité d'identifier des empreintes de portefeuille.

Enfin, Schnorr offre également la possibilité de vérification par lot. En vérifiant plusieurs signatures simultanément, les nœuds peuvent gagner en efficacité, surtout pour les blocs contenant de nombreuses transactions. Cette optimisation réduit le temps et les ressources nécessaires pour valider un bloc.

Aussi, les signatures Schnorr ne sont pas malléables, contrairement aux signatures produites avec ECDSA. Cela signifie qu'un attaquant ne peut pas modifier une signature valide pour créer une autre signature valide pour le même message et la même clé publique. Cette vulnérabilité était présente auparavant sur Bitcoin et empêchait notamment la mise en place de manière sécurisée du Lightning Network. Elle a été résolue pour ECDSA avec le softfork SegWit en 2017, qui consiste à déplacer les signatures dans une base de données séparée des transactions afin d'empêcher leur malléabilité.

### Pourquoi Satoshi a-t-il choisi ECDSA ?

Nous l'avons vu, Satoshi a initialement choisi d'implémenter ECDSA pour les signatures numériques sur Bitcoin. Pourtant, nous avons également vu que Schnorr est bien supérieur à ECDSA sur de nombreux aspects, et ce protocole a été créé par Claus-Peter Schnorr en 1989, soit 20 ans avant l'invention de Bitcoin. 

Et bien, on ne sait pas vraiment pourquoi Satoshi ne l'a pas choisi, mais une hypothèse probable est que ce protocole était sous brevet jusqu'en 2008. Bien que Bitcoin ait vu le jour un an plus tard, en janvier 2009, aucune standardisation open-source pour les signatures de Schnorr n'était alors disponible. Peut-être que Satoshi a jugé plus sûr d'utiliser ECDSA, qui était déjà largement utilisé et testé dans des logiciels open-source et bénéficiait de plusieurs implémentations reconnues (notamment la bibliothèque OpenSSL utilisée jusqu'en 2015 sur Bitcoin Core, puis remplacée par libsecp256k1 dans la version 0.10.0). Ou alors, peut-être qu'il n'avait tout simplement pas connaissance du fait que ce brevet allait expirer en 2008. Dans tous les cas, l'hypothèse la plus probable semble liée à ce brevet et au fait qu'ECDSA avait alors un historique éprouvé et était plus facile à implémenter.


## Les sighash flags
<chapterId>231c41a2-aff2-4655-9048-47b6d2d83d64</chapterId>

Comme nous l'avons vu dans les chapitres précédents, les signatures numériques sont souvent utilisées pour déverrouiller le script d'un input. Dans le processus de signature, il est nécessaire d’inclure la donnée signée dans le calcul, désignée dans nos exemples par le message $m$. Cette donnée, une fois signée, ne peut plus être modifiée sans rendre la signature invalide. En effet, que ce soit pour ECDSA ou pour Schnorr, le vérificateur de la signature doit inclure dans son calcul le même message $m$. Si celui-ci diffère du message $m$ utilisé initialement par le signataire, le résultat sera incorrect et la signature sera jugée invalide. On dit alors qu'une signature couvre une certaine donnée et la protège en quelque sorte contre les modifications non autorisées.

### C'est quoi un sighash flag ?

Dans le cas spécifique de Bitcoin, nous avons vu que le message $m$ correspond à la transaction. Mais en réalité, c'est un peu plus complexe. En effet, il est possible, grâce aux sighash flags, de sélectionner les données spécifiques dans la transaction qui seront couvertes ou non par la signature.

Le "sighash flag" est donc un paramètre ajouté à chaque input, permettant de déterminer les composants d'une transaction qui sont couverts par la signature associée. Ces composants sont les inputs et les outputs. Le choix du sighash flag détermine ainsi quels inputs et quels outputs de la transaction sont figés par la signature et lesquels peuvent encore être modifiés sans invalider celle-ci. Ce mécanisme permet aux signatures d'engager les données de transaction selon les intentions du signataire.

Évidemment, une fois la transaction confirmée sur la blockchain, elle devient immuable, quels que soient les sighash flags utilisés. La possibilité de modification via les sighash flags est limitée à la période entre la signature et la confirmation.

Généralement, les logiciels de portefeuille ne vous proposent pas de modifier manuellement le sighash flag de vos inputs lorsque vous construisez une transaction. Par défaut, c'est le `SIGHASH_ALL` qui est paramétré. Personnellement, je ne connais que Sparrow Wallet qui permette de faire cette modification depuis l'interface utilisateur.

### Quels sont les sighash flags existants sur Bitcoin ?

Sur Bitcoin, il y a tout d'abord 3 sighash flags de base :

- `SIGHASH_ALL` (`0x01`) : La signature s'applique à tous les inputs et tous les outputs de la transaction. La transaction est donc entièrement couverte par la signature et ne peut plus être modifiée. `SIGHASH_ALL` est le sighash le plus couramment utilisé dans les transactions au quotidien, lorsque l'on souhaite simplement faire une transaction sans qu'elle puisse être modifiée.

026

Dans tous les schémas de ce chapitre, la couleur orange représente les éléments couverts par la signature, tandis que la couleur noire indique ceux qui ne le sont pas.

- `SIGHASH_NONE` (`0x02`) : La signature couvre tous les inputs mais aucun output, ce qui permet ainsi la modification des outputs après la signature. Concrètement, il s’agit d’un chèque en blanc. Le signataire déverrouille les UTXOs en inputs, mais laisse le champ des outputs entièrement modifiable. N'importe qui connaissant cette transaction peut donc y ajouter l’output de son choix, par exemple en spécifiant une adresse de réception pour récupérer les fonds consommés par les inputs, puis diffuser la transaction pour récupérer les bitcoins. La signature du propriétaire des inputs ne sera pas invalidée, car elle couvre uniquement les inputs.

027

- `SIGHASH_SINGLE` (`0x03`) : La signature couvre tous les inputs ainsi qu’un seul output, correspondant à l’index de l’input signé. Par exemple, si la signature déverrouille le *scriptPubKey* de l'input #0, alors elle couvre également l'output #0. LA signature protège également tous les autres inputs, qui ne peuvent plus être modifiés. Cependant, n'importe qui peut ajouter un output supplémentaire sans invalider la signature, à condition de ne pas modifier l'output #0, qui est le seul couvert par celle-ci.

028

En complément de ces trois sighash flags, il existe également le modificateur `SIGHASH_ANYONECANPAY` (`0x80`). Ce modificateur peut être combiné avec un sighash flag de base pour créer trois nouveaux sighash flags :

- `SIGHASH_ALL | SIGHASH_ANYONECANPAY` (`0x81`) : La signature couvre un seul input tout en incluant l'intégralité des outputs de la transaction. Ce sighash flag combiné permet, par exemple, de créer une transaction de financement participatif. L’organisateur prépare l'output avec son adresse et le montant cible, et chaque investisseur peut ensuite ajouter des inputs pour financer cet output. Une fois les fonds suffisants réunis en inputs pour satisfaire l'output, la transaction peut être diffusée.

029

- `SIGHASH_NONE | SIGHASH_ANYONECANPAY` (`0x82`) : La signature couvre un seul input, sans engager aucun output ;

030

- `SIGHASH_SINGLE | SIGHASH_ANYONECANPAY` (`0x83`) : La signature couvre un seul input ainsi que l'output ayant le même index que cet input. Par exemple, si la signature déverrouille le *scriptPubKey* de l'input #3, elle couvrira également l'output #3. Le reste de la transaction demeure modifiable, tant au niveau des autres inputs que des autres outputs.

031

### Les projets d'ajout de nouveaux sighash flags

Actuellement (2024), seuls les sighash flags présentés dans la section précédente sont utilisables sur Bitcoin. Cependant, certains projets envisagent l’ajout de nouveaux sighash flags. Par exemple, le BIP118, proposé par Christian Decker et Anthony Towns, introduit deux nouveaux sighash flags : `SIGHASH_ANYPREVOUT` et `SIGHASH_ANYPREVOUTANYSCRIPT` (*AnyPrevOut = "Any Previous Output"*).

Ces deux sighash flags offriraient une possibilité supplémentaire sur Bitcoin : créer des signatures qui ne couvrent aucun input spécifique de la transaction.

032

Cette idée a initialement été formulée par Joseph Poon et Thaddeus Dryja dans le White Paper de Lightning. Avant son renommage, ce sighash flag portait le nom de `SIGHASH_NOINPUT`.

Si ce sighash flag est intégré à Bitcoin, il permettra l'utilisation de covenants, mais c'est aussi un prérequis obligatoire pour implémenter Eltoo, un protocole généraliste pour les secondes couches qui définit la manière de gérer conjointement la propriété d'un UTXO. Eltoo a notamment été conçu pour résoudre les problèmes associés aux mécanismes de négociation de l'état des canaux Lightning, c'est-à-dire entre l'ouverture et la fermeture.

Pour approfondir vos connaissances sur le Lightning Network, après la formation CYP201, je vous recommande vivement la formation LNP201 de Fanis Michalakis, qui aborde le sujet en détail :

https://planb.network/courses/lnp201





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

