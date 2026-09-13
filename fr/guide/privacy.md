---
title: Comment marche la confidentialité
permalink: /fr/confidentialite/
---

Cette page explique le mécanisme&#160;: ce qui est chiffré et ce qui ne l'est
pas, qui détient quelle clé, ce qui se passe quand vous vous connectez sur un
nouveau téléphone, et ce que reprendre quelque chose fait réellement. La
[politique de confidentialité](/privacy/) fait autorité sur ce que nous
détenons à votre sujet&#160;; cette page est ce qui se trouve dessous, pour
quelqu'un qui préférerait vérifier une affirmation que la croire.

Elle est écrite pour un lecteur attentif qui n'est pas ingénieur. Là où
l'affirmation a une limite, la limite est ici aussi, dans la dernière
section.

## Ce qui est scellé, et ce qui ne l'est pas

Scellé sur votre téléphone, avec des clés que nous ne détenons jamais&#160;:

- les photos, à chaque taille où nous les stockons&#160;;
- les légendes&#160;;
- les commentaires&#160;;
- les titres des albums&#160;;
- votre nom affiché et votre photo de profil&#160;;
- le flou qui tient lieu de photo pendant son chargement.

En clair, parce que livrer quoi que ce soit l'exige&#160;:

- votre pseudo et l'adresse de courriel avec laquelle vous vous êtes
  inscrit&#160;;
- avec qui vous êtes en relation et depuis quand, ainsi que les demandes
  d'ajout que vous envoyez et recevez et les blocages que vous posez&#160;;
- les noms de vos groupes, et dans lesquels de vos groupes une personne se
  trouve&#160;;
- qui est dans chaque album où vous êtes&#160;;
- pour chaque publication&#160;: qui l'a faite, quand, à qui elle a été
  adressée, combien d'images elle contient, quelle est la taille des fichiers
  chiffrés, et, pour chaque destinataire, quelles images il a regardées et
  quand&#160;;
- les réactions, qui sont un émoji chacune&#160;;
- le pointeur qui nomme le fichier chiffré où se trouve votre photo de profil,
  qui est ce qui nous permet de signer le lien qui la sert&#160;;
- l'adresse d'envoi de chaque téléphone sur lequel vous vous êtes connecté, et
  le moment où vous avez confirmé avoir 18 ans ou plus, qui est un moment et
  jamais une date&#160;;
- tout ce que vous tapez dans un signalement ou un rapport de problème, parce
  que ce sont des messages pour nous et que nous devons pouvoir les lire.

C'est la version courte. La [politique de confidentialité](/privacy/) a la
version complète, et c'est elle qui fait autorité si les deux se contredisent
un jour.

Deux de ces points méritent un mot, parce que ce sont ceux qui pourraient
surprendre. **Les titres d'album sont scellés&#160;; les noms de groupe ne le
sont pas**, ni la liste de qui est dedans – bien que personne n'apprenne jamais
dans lequel de vos groupes il se trouve. Un groupe est votre étiquette privée
pour certaines de vos relations, stockée comme du texte, et la borne de 60
caractères dessus est appliquée par le serveur, ce qui n'est possible que parce
que le serveur peut compter les caractères. Et **les réactions sont en clair
exprès**. Un émoji tiré d'un ensemble que n'importe qui peut énumérer est
devinable quelle que soit l'enveloppe, et le serveur détient de toute façon la
ligne disant qui a réagi à quoi, donc le chiffrer serait du théâtre. C'est
listé honnêtement à la place.

### Le flou de remplacement est chiffré aussi

Le rectangle doux qui apparaît pendant qu'une photo arrive encore fait environ
25 octets, et 25 octets sont faciles à garder dans une colonne ordinaire, parce
que cela ne ressemble à rien. Ce n'est pas rien&#160;: c'est une transformation
grossière de l'image, et 25 octets suffisent à porter la composition et les
couleurs. Il est donc scellé, à l'intérieur des données chiffrées de la
publication, qui sont petites et récupérées en premier. C'est pourquoi les
flous apparaissent avant les photos.

### Les données de localisation, et tout ce que l'EXIF porte

Rien n'est retiré de vos images, parce que rien ne survit pour être retiré.
L'image est décodée en une trame de points et réencodée, et une trame de points
n'a pas d'EXIF du tout&#160;: GPS, modèle d'appareil, numéros de série,
objectif, le logiciel qui y a touché, tout cela est simplement absent de ce qui
est scellé. L'approche habituelle est un filtre sur une liste de données, et la
liste est là où vit la fuite, parce qu'elle doit nommer tout ce qui mérite
d'être retiré. Ici il n'y a pas de filtre, donc il n'y a rien qu'un filtre
puisse manquer.

La seule chose gardée est la date de prise de vue, et elle est écrite à
l'intérieur des données scellées plutôt que réécrite sur le fichier. Réécrire
une donnée sur un JPEG demande un fichier sur le disque, et rien dans cette
chaîne ne pose une photo déchiffrée ailleurs que dans la mémoire.

## Comment une photo voyage

Disons qu'anna publie quatre photos pour bruno et carla.

1. Son téléphone engendre une clé au hasard pour cette publication, et pour
   elle seule.
2. Il fabrique chaque taille de chaque photo sur l'appareil et scelle chaque
   fichier sous cette clé. Chaque fichier est lié à son propre emplacement au
   moment où il est scellé&#160;: la copie pleine taille de la troisième photo
   porte une étiquette qui dit exactement cela, donc un stockage qui servirait
   un fichier à la place d'un autre ne serait pas cru par le téléphone qui
   l'ouvre.
3. Il enveloppe la clé de la publication trois fois&#160;: une pour bruno, une
   pour carla, et une pour anna elle-même. Chaque enveloppe utilise la clé
   publique de cette personne, que son téléphone a d'abord comparée à celle
   qu'il a notée la première fois qu'on lui en a donné une pour elle&#160;;
   cette vérification a une section à elle plus bas.
4. Il envoie les fichiers scellés par des liens signés qui expirent au bout de
   quinze minutes et portent le compte exact d'octets dans la signature, donc
   le stockage refuse toute autre longueur. Puis il envoie le manifeste et les
   trois clés enveloppées. Le serveur écrit la publication et les livraisons en
   une seule transaction, donc une publication n'est jamais à moitié faite.
5. Le téléphone de bruno télécharge du chiffré, désenveloppe la clé de la
   publication depuis sa propre livraison, et déchiffre les photos sur le
   téléphone.

Ce que nous finissons par détenir est un tas de fichiers chiffrés, trois
petites clés enveloppées que nous ne pouvons pas ouvrir, et la note qu'une
publication est allée d'anna à bruno et carla à une minute précise.

La copie de la clé qui appartient à anna est une colonne sur la publication
plutôt qu'une livraison à elle-même, et c'est ce qui permet d'élargir les
destinataires ensuite&#160;: son téléphone désenveloppe la clé et l'enveloppe à
nouveau pour la nouvelle personne. Il n'y a jamais eu de moment où le serveur
aurait pu faire cela pour elle, ce qui est pourquoi [ajouter quelqu'un à une
publication](/fr/publier/) est toujours une chose que l'auteur fait. Les
destinataires ne font que s'élargir&#160;: il n'y a nulle part de commande qui
dé-partage une photo avec une personne. Ce qui reprend une photo, c'est retirer
ou bloquer quelqu'un, ou supprimer la publication, et chacun de ces actes est
une clé détruite plutôt qu'une ligne cachée.

Il n'y a aucun cache sur ce chemin. Un lien signé est unique à la requête qui
l'a demandé, donc un cache devant le stockage manquerait à chaque fois par
construction, et tout arrangement qui met en cache voudrait dire remplacer la
signature par quelque chose à nous. Il n'y a pas de réseau de diffusion de
contenu dans ce produit et il n'y en aura pas.

## La clé qui est la vôtre

Votre clé d'identité est engendrée par logiciel sur votre téléphone, par
libsodium, avant que le compte existe. Le serveur reçoit la moitié publique à
l'inscription et n'aurait jamais pu avoir l'autre.

Au repos, la moitié privée est scellée sous une clé engendrée à l'intérieur du
Keystore d'Android, qui ne rendra cette clé à rien ni personne, nous compris.
Là où le téléphone a une puce de sécurité séparée, l'application la demande et
l'utilise&#160;; là où il n'en a pas, elle continue. Une puce est un bonus et
jamais une exigence, parce qu'en exiger une exclurait des téléphones sans
raison de sécurité que nous puissions défendre. Les données de l'application
sont aussi tenues hors de la sauvegarde cloud d'Android.

### Pourquoi la clé n'est pas simplement détenue par la puce

«&#160;Stockée dans l'enclave sécurisée&#160;» est la réponse qui sonne le plus
fort, et c'est la mauvaise ici. Une clé que l'élément sécurisé détient ne peut
pas être exportée&#160;: c'est tout l'intérêt d'un élément sécurisé, et c'est
franchement incompatible avec la phrase au-dessus, qui est que votre clé doit
pouvoir être retrouvée à partir de six mots sur un téléphone de remplacement.
Une clé détenue par la puce ajouterait discrètement «&#160;téléphone
perdu&#160;» à la liste des façons de perdre vos photos, ce qui est un
événement bien plus courant et une bien pire promesse.

La clé est donc engendrée par logiciel et la puce la garde là où elle se
trouve. Un téléphone débridé et déverrouillé entre d'autres mains gagne quand
même, et aucun arrangement sur un système d'exploitation généraliste ne change
cela.

### Une clé par personne, pas une par appareil

Il n'y a pas de liaison d'appareil ici et pas de code à scanner depuis votre
premier téléphone. Chaque personne a une clé, et un deuxième téléphone
l'obtient de la phrase de récupération.

Des clés par appareil sont plus solides et sont délibérément reportées&#160;:
l'enveloppement deviendrait le nombre de destinataires multiplié par le nombre
d'appareils, et ajouter un appareil voudrait dire soit réenvelopper tout votre
historique, soit le perdre. Une clé par personne est la bonne complexité pour
une bêta fermée avec une limite de 128 relations.

## La phrase de récupération

Six mots, tirés par un générateur aléatoire cryptographique d'une liste de
7 776, et montrés une seule fois. Votre clé d'identité est scellée sous une clé
étirée à partir de ces mots avec Argon2id à 128 Mio de mémoire, et le résultat
scellé est stocké sur nos serveurs. Nous ne pouvons pas l'ouvrir.

Vous ne pouvez pas choisir vos propres mots, et la raison est précise plutôt
que pédante. Nous détenons la sauvegarde scellée, ce qui fait de nous le seul
attaquant au monde qui pourrait deviner la phrase hors ligne, à loisir, sans
aucune limite de débit que quiconque pourrait nous imposer. Face à cela, une
phrase de passe inventée par une personne n'est pas un secret doté d'un nombre
de bits&#160;: c'est un mot ou deux et un chiffre, et aucun étirement de clé
tournant sur un téléphone n'achète plus qu'un petit facteur contre une
recherche qui part d'un dictionnaire. Six mots de cette liste font environ 77
bits. Ce n'est pas «&#160;plus solide&#160;»&#160;; c'est une catégorie
différente de chose, hors d'atteinte quel que soit le coût de l'étirement.

Ce que l'application dit sur cet écran est toute la promesse&#160;:

> Ces six mots sont le seul moyen de retrouver vos photos si vous perdez ce
> téléphone. Notez-les et gardez-les en lieu sûr. Nous ne pourrons pas vous les
> montrer à nouveau, ni les retrouver pour vous – non par mauvaise volonté,
> mais parce que nous ne les voyons jamais.

Il y a un lien *copier* sous les mots, et le presse-papiers reçoit exactement
ce que le champ de restauration prend. Les applications de sécurité refusent
d'ordinaire le presse-papiers pour une chose pareille&#160;; le refuser ne
garde pas la phrase hors du téléphone, cela décide seulement quelle copie le
téléphone garde, et la copie vers laquelle les gens se tournent à la place est
une capture d'écran, qui atterrit dans la galerie et va partout où la galerie
est sauvegardée. Le presse-papiers est marqué sensible, donc depuis Android 13
le système le masque dans sa propre confirmation et un clavier doté d'un
historique est prévenu de ce qu'il détient. Rien ne l'efface au bout d'un
délai, parce que l'application ne peut pas savoir quand vous avez collé.

Copier ne rend pas la phrase récupérable ensuite. Dans les *paramètres*, la
ligne *phrase de récupération* dit *notée* ou *pas encore notée*, et jamais les
mots.

### Ce que sa perte coûte

Perdre la phrase et tous les téléphones qui détiennent votre clé signifie que
les photos sont perdues, et il n'y a ni procédure ni recours. Soyez précis sur
la paire, cependant&#160;: perdre la phrase seule ne coûte rien tant qu'un
téléphone détient encore la clé, et perdre tous les téléphones ne coûte rien
tant que la phrase survit. C'est les deux ensemble.

Ce que nous pouvons faire à la sauvegarde scellée, c'est refuser de la rendre,
ou en rendre une plus ancienne. Les deux vous coûtent une restauration. Aucun
des deux ne lit une photo.

## Se connecter sur un nouveau téléphone

Le code envoyé par courriel prouve que vous contrôlez l'adresse. Savoir si ce
téléphone peut *être* ce compte est une question distincte, et la clé en est la
réponse. Trois choses peuvent arriver&#160;: la clé déjà sur le téléphone
correspond au compte, et vous entrez&#160;; le téléphone avait gardé la clé de
ce compte d'une connexion antérieure, il l'adopte, et vous entrez&#160;; ou
ni l'un ni l'autre, et il demande les six mots.

Ce dernier écran dit&#160;: *Ce téléphone n'a pas la clé de ce compte. Les six
mots que vous avez notés la ramènent.*

Restaurer ramène la même clé, donc les téléphones de vos relations ne voient
rien d'inhabituel. Cela restaure aussi le relevé des clés de tout le monde que
votre ancien téléphone avait constitué – sans cela, un nouveau téléphone
traiterait chaque personne que vous connaissez déjà comme un premier contact,
et la vérification décrite plus bas n'aurait rien à comparer.

Se déconnecter laisse votre clé sur le téléphone et ne supprime rien de ce que
vous avez fait. L'adresse d'envoi est supprimée par le serveur dans la
transaction même qui révoque la session, plutôt que par l'application en
partant, parce qu'une application qui doit penser à se désinscrire oubliera
exactement au moment où on la tue.

## Qui distribue les cadenas

C'est le joint que tout système chiffré de bout en bout possède, et il vaut
mieux le dire franchement que s'arrêter à «&#160;nous ne pouvons pas lire vos
messages&#160;».

Votre téléphone scelle une photo avec un cadenas que seule la clé d'anna ouvre.
Mais c'est à *nous* qu'il a demandé ce cadenas. Un serveur malhonnête –
compromis, ou contraint – pourrait remettre à votre téléphone son propre
cadenas portant le nom d'anna. Votre téléphone scelle la photo avec et
l'envoie. Nous l'ouvrons, la lisons, la rescellons avec le vrai cadenas d'anna,
et la transmettons. Elle la reçoit. Rien ne paraît anormal pour aucun des deux,
et personne ne l'apprend jamais.

La défense qui est construite est celle-ci&#160;: la première fois que votre
téléphone reçoit la clé de quelqu'un, il la note. Chaque fois ensuite, il
compare. Une clé inchangée est silencieuse. Une clé changée vous arrête.

Elle vous arrête plutôt que de vous avertir. La fonction qui remet une clé à
quoi que ce soit qui s'apprête à sceller renvoie une clé ou lève une alarme,
jamais les deux&#160;: un appelant qui recevrait les deux devrait penser à
vérifier, et celui qui oublierait scellerait votre photo au cadenas du serveur
et l'enverrait. Donc si la clé d'une personne a changé, la publication échoue
avant qu'un seul octet soit envoyé, et vous voyez ceci&#160;:

> La clé qu'on nous a donnée pour anna n'est pas celle que ce téléphone a vue
> auparavant. Cela arrive quand quelqu'un réinstalle l'application ou change de
> téléphone. Cela arrive aussi quand quelqu'un intercepte vos messages, et
> d'ici nous ne pouvons pas faire la différence. Vérifiez auprès d'elle par un
> autre moyen avant de partager quoi que ce soit.

Les réponses sont *j'ai vérifié, c'est bien eux* et *pas maintenant*. Le texte
ne devine délibérément pas laquelle des explications est la bonne, et il n'y a
pas de «&#160;continuer quand même&#160;» formulé pour être le chemin facile.
Une réinstallation et une interception se ressemblent exactement d'ici, et
adoucir le texte pour le cas courant est ainsi qu'une alerte de sécurité
devient un dialogue que les gens écartent sans lire. L'effacer est une décision
distincte que quelqu'un a prise, pas une nouvelle tentative.

### Où vivent les clés notées

Sur votre téléphone. C'est toute la défense, et une conception antérieure s'y
était trompée&#160;: le relevé devait vivre sur le serveur, en clair. Cela ne
peut pas marcher. Un serveur qui remet le mauvais cadenas peut réécrire le
relevé du bon, puis comparer son propre mensonge à son propre mensonge et ne
rien lever. La vérification a l'air de marcher et ne fait rien du tout.

Le relevé qui compte est donc sur l'appareil. Nous ne détenons qu'une copie que
votre téléphone a scellée avant de l'envoyer, que nous pouvons stocker, ne
pouvons pas ouvrir et ne pouvons pas falsifier. Nous pouvons la retenir ou en
servir une version plus ancienne&#160;; un téléphone qui en a déjà vu une plus
récente refuse une plus ancienne, et un téléphone tout neuf n'a rien à comparer
et doit prendre ce qu'on lui donne.

### Ce que l'affirmation est, exactement

Nous ne pouvons rien lire de ce qui a déjà été envoyé, et nous ne pouvons pas
*commencer* à intercepter sans que chaque téléphone concerné lève cette alarme.
Ce qui n'est pas encore couvert, c'est le tout premier bonjour entre deux
personnes qui n'ont jamais échangé de clé&#160;: un téléphone qui n'a rien noté
prend ce qu'on lui donne.

Refermer cela veut dire comparer les clés hors bande – se lire à voix haute un
code court, ou scanner un carré – et **ce n'est pas construit**. Ce qui existe
aujourd'hui est l'empreinte de votre propre clé dans *paramètres → votre clé*,
24 caractères en six groupes de quatre, qui est ce que deux personnes se
liraient une fois que cela existera. L'écart est petit et universel au
chiffrement de bout en bout, et il est écrit ici plutôt que passé sous
silence.

### Un cadenas n'est remis que là où quelque chose va lui être verrouillé

Huit routes dans toute l'API portent la clé publique de quelqu'un, et elles
sont nommées une par une dans un test qui force chacune à mentir, pour que
l'alarme puisse être vue se déclencher à chaque fois. Ce sont les endroits où
votre téléphone s'apprête à sceller quelque chose&#160;: un résultat de
recherche à qui vous allez envoyer une demande, les gens qui vous attendent,
vos relations, les membres d'un album, et ainsi de suite.

Une liste des personnes qui ont réagi à une photo porte un pseudo et un
identifiant et aucune clé, parce que rien n'est jamais enveloppé pour quelqu'un
qui a regardé une photo. Remettre le cadenas d'un inconnu serait une porte
ouverte sur quelqu'un que l'appelant n'a aucun moyen de vérifier et aucune
raison de croire.

## Reprendre quelque chose, c'est détruire une clé

Sur la plupart des plateformes, retirer quelqu'un change une permission&#160;:
la photo reste où elle est, toujours lisible par la plateforme, derrière un
drapeau qui dit de ne pas la lui montrer. Une permission est une promesse que
le serveur doit tenir.

Ici, la seule copie de la clé d'une publication qu'une personne peut ouvrir est
la copie enveloppée dans sa propre ligne de livraison. Retirer une relation
supprime ces lignes dans les deux sens en une transaction, pour chaque
publication ordinaire, et sort chacun de vous des albums que l'autre a faits,
avec les clés qui allaient avec. Il ne reste rien à vérifier, parce qu'il ne
reste aucune clé contre laquelle vérifier. C'est de l'arithmétique plutôt
qu'une règle, ce qui est pourquoi [retirer quelqu'un](/fr/ajouter-des-relations/)
est silencieux et total.

Ce qu'un retrait n'atteint délibérément pas, c'est un album fait par une tierce
personne. Une livraison là-bas repose sur le fait d'être dans cette pièce
plutôt que sur le lien entre deux des gens qui y sont, donc deux personnes qui
cessent d'être en relation continuent d'y recevoir leurs
[contributions](/fr/albums/) mutuelles. Un blocage est ce qui atteint la
pièce&#160;: dans sa propre transaction unique, chaque livraison entre les deux
s'en va, photos d'album comprises.

La même forme, partout où elle apparaît&#160;:

- Supprimer une publication pour tout le monde détruit deux sortes de clé
  enveloppée, celles des destinataires et celle de l'auteur, au moment où vous
  touchez. Les fichiers chiffrés quittent le stockage huit jours plus tard, ce
  qui est du jeu opérationnel et pas un retour en arrière&#160;: huit jours
  plus tard le chiffré est exactement aussi illisible qu'au premier jour.
- [Sortir quelqu'un d'un album](/fr/albums/) supprime son appartenance et
  chaque clé enveloppée qu'il détenait pour les photos de cet album en une
  seule instruction, et tout ce qui est versé ensuite n'est enveloppé que pour
  les membres qui existent à ce moment-là.
- [Supprimer votre compte](/delete-account/) détruit chaque clé qu'il détient
  et chaque clé qu'il a distribuée, en une transaction.
- Révoquer qui peut lire votre nom et voir votre visage est une ligne
  supprimée, parce que votre clé de profil est enveloppée par personne plutôt
  qu'intégrée à quoi que ce soit.

### Les deux choses que cela ne fait pas

**Tout ce qui a déjà été téléchargé sur le téléphone de quelqu'un lui
appartient.** Détruire la clé empêche toute nouveauté de s'ouvrir&#160;; cela
n'atteint pas un téléphone pour reprendre ce qui a déjà été déchiffré, pas plus
que ne le peut n'importe quelle autre façon d'envoyer une photo à quelqu'un.
L'export dans *paramètres → exporter mes données* est écrit pour respecter la
même ligne&#160;: il contient ce que vous avez fait, pas les photos des autres,
même si votre téléphone détient une clé pour chacune d'elles.

**Un commentaire caché l'est par un filtre, pas par une clé détruite.** C'est
la seule exception du produit, et elle vaut la peine d'être comprise. Un
commentaire est scellé sous la clé de la publication, que chaque destinataire
détient déjà, donc quand quelqu'un sort du groupe de ceux qui peuvent [entendre
un commentaire](/fr/commentaires/), ce qui change est à qui les mots sont
montrés plutôt que qui pourrait en principe les ouvrir. La correction évidente
serait d'enveloper chaque commentaire pour exactement les bonnes personnes, et
elle est pire&#160;: il faudrait dire au téléphone de celui qui écrit
lesquelles de ses relations connaissent l'auteur, ce qui divulgue un graphe
pour en cacher un.

## Un nom et un visage voyagent par clé aussi

Votre nom affiché et votre photo de profil sont scellés eux aussi, sous une clé
dérivée de votre clé d'identité. Dérivée plutôt qu'engendrée, pour que
quiconque peut restaurer votre identité restaure le profil avec&#160;:
engendrer une seconde clé voudrait dire la sauvegarder, et ce produit nomme
exactement une façon de perdre vos photos et ne veut pas d'une seconde chose à
perdre.

Cette clé est enveloppée pour chaque personne qui peut la lire&#160;: vos
relations, et toute personne à qui vous avez envoyé une demande. C'est pourquoi
une demande reçue vous montre un visage et un nom tandis que quelqu'un à qui
vous avez demandé ne vous montre rien jusqu'à ce qu'il accepte. C'est aussi
pourquoi nous ne pouvons pas composer une notification&#160;: nous détenons le
nom sous forme chiffrée.

Il y a un endroit où une clé est remise à quelqu'un par une tierce personne, et
c'est assez inhabituel pour être nommé. Quand une relation met votre nom sur
une photo, les gens qui voient cette photo peuvent n'avoir aucun lien avec vous
et ne pourraient ouvrir ni votre nom ni votre visage. Alors la personne qui
vous a identifié réenveloppe votre clé de profil sur cette publication, depuis
son propre téléphone, pour chacun de ces spectateurs. Nous détenons les copies
et ne pouvons en ouvrir aucune. Chaque copie repose sur la livraison au
spectateur et sur votre identification, donc elle disparaît quand l'une ou
l'autre disparaît, sans qu'aucune partie du système ait à penser à la
supprimer. La tierce personne qui remet la clé est celle qui vous a nommé, et
l'interrupteur qui permet tout cela est le vôtre&#160;: *autoriser mes
relations à m'identifier*, dans les *paramètres*.

## Ce qu'une notification porte

Un mot&#160;: le genre de chose qui s'est produit.

Le message que nous envoyons au service d'envoi de Google est un message de
données avec un seul champ nommant un type, et une priorité de livraison
calculée à partir du type et qui ne dit donc rien que le type ne dise. Il n'y a
rien d'autre dedans&#160;: pas de noms, pas de légendes et pas d'identifiant de
publication. La phrase que vous lisez sur votre téléphone – *anna a commenté
votre publication* – est composée sur votre téléphone, à partir du profil
scellé qu'il peut ouvrir et que nous ne pouvons pas. Quand il ne peut pas
ouvrir un nom, la notification dit *quelqu'un*, ce qui est le même téléphone
faisant le même travail avec moins d'éléments.

L'identifiant est la partie qui surprend, parce qu'elle a l'air inoffensive.
Deux appareils recevant le même identifiant de publication dans la même seconde
sont deux personnes d'un même ensemble de destinataires, et répété assez
souvent c'est la forme de votre graphe, remise à un tiers. Cela ne coûte rien
de l'omettre, puisqu'un téléphone qui doit aller chercher pour apprendre un nom
apprendra l'identifiant de la même réponse.

Le type est une liste de cas fixes sans aucun champ dessus, ce qui est ce qui
fait de «&#160;pas de résumés, pas de séries, pas de vous-n'avez-rien-publié&#160;»
une propriété du système plutôt qu'une note pour un relecteur. Il n'y a aucune
chaîne où une phrase publicitaire pourrait être mise, aucun identifiant pour
corréler deux téléphones, et aucun cas pour une réaction. Et comme le message
ne porte aucun texte d'aucune sorte, on ne demande jamais à Android d'afficher
des mots que nous avons choisis.

## Ce que l'application mesure

Il n'y a pas de bibliothèque de rapport de plantage et pas de bibliothèque
d'analyse dans l'application. Pas désactivées, pas facultatives&#160;:
absentes. Tous les produits de cette catégorie existent pour capturer ce que le
client détient en mémoire – le fil des actions, les variables locales, la
hiérarchie des vues, le texte dans un champ – et sur ce téléphone c'est là que
sont les photos déchiffrées. Comme une décision qui est une absence n'a rien
qui devienne rouge tout seul quand quelqu'un ajoute une dépendance à la hâte,
une vérification dans notre compilation en refuse quatorze par leur nom, dans
chacun des fichiers de compilation de l'application et dans la liste de
versions qu'ils partagent, et refuse les appels de journalisation de la
plateforme dans le code de l'application. Ce que nous obtenons à la place est
le rapport de plantage de Google Play lui-même, depuis les téléphones dont les
propriétaires l'ont activé au niveau du système, qui nous dit que l'application
a planté et où dans notre code et ne contient rien de votre contenu.

Une chose va dans l'autre sens, et elle est activée par défaut sans
interrupteur. Votre téléphone compte combien de choses scellées il a ouvertes
et combien il n'a pas réussi à ouvrir depuis la dernière fois qu'il nous l'a
dit – clés de publication, données, images, commentaires, clés d'album, titres
d'album, profils – avec la version de l'application et celle d'Android, et il
compte un fichier qui n'est jamais arrivé séparément d'un qui est arrivé et n'a
pas voulu s'ouvrir, parce que le premier dit quelque chose sur le stockage et
le second dit quelque chose sur les clés. Jamais quelle publication, quelle
image ni le commentaire de qui&#160;: un échec nommé par identifiant de
publication serait une ligne que nous pourrions joindre au graphe.

Ce nombre compte parce que c'est la seule panne que nous ne pouvons pas voir
nous-mêmes. Nous détenons du chiffré et une clé enveloppée&#160;; savoir s'ils
s'ouvrent se décide sur un téléphone. Le serveur ajoute chaque compte à un
total et répond par rien&#160;: pas de ligne en base, pas de ligne de journal,
pas d'identifiant, donc le lien entre vous et les nombres existe le temps de la
requête et puis n'existe plus. Il n'y a pas d'interrupteur parce qu'il n'y a
rien ici qu'un interrupteur retiendrait, et un interrupteur à côté d'une phrase
expliquant qu'il ne retient rien serait le produit en train de s'annoncer.

L'autre moitié de ce nombre est *paramètres → signaler un problème*, qui est un
paragraphe que vous écrivez et une ligne sur votre téléphone, sans champ de
pièce jointe, sans journal et sans capture d'écran. Le compteur dit à quelle
fréquence quelque chose n'a pas pu s'ouvrir. Seule une personne peut dire ce
qu'elle était en train de faire.

### Journaux et mesures

Nos journaux ne peuvent pas vous nommer, par construction plutôt que par soin.
Il y a une seule façon d'écrire une ligne de journal, et aucun des champs
qu'elle accepte ne peut contenir de texte libre, donc un pseudo, une adresse,
une légende ou un jeton ne peut pas atteindre une ligne de journal, par type.
Le journal d'accès note quelle route a été appelée et non quel chemin, donc ce
qui est écrit est la forme de celui-ci, /v1/users/{userId}/posts, et jamais
l'identifiant qui était à sa place. Une exception est rendue comme sa classe et
ses cadres de pile et jamais comme son message, parce que le message d'erreur
d'une bibliothèque cite ce sur quoi elle a buté. Nous gardons ces journaux 30
jours.

Les mesures d'exploitation n'ont nulle part de champ qui pourrait porter un
compte, et chaque étiquette dessus est un mot fixe, un petit nombre, ou une
version d'application repliée en «&#160;autre&#160;» une fois qu'il y en a eu
plus de 32. Elles sont servies sur un port séparé qui n'est pas exposé
publiquement, et un test affirme qu'elles sont absentes du port public, parce
que garder une chose hors d'une API publique est un fait sur le réseau plutôt
qu'une chose qui devient rouge toute seule.

## Ce dont cela ne vous protège pas

L'affirmation ci-dessus est plus étroite que «&#160;privé&#160;», et voici ses
bords.

- **Les métadonnées.** Nous savons avec qui vous êtes en relation, à qui vous
  avez envoyé une publication et quand, et quelles images chacun a regardées.
  C'est ce dont le serveur a besoin pour livrer quoi que ce soit, et cela
  révèle qui parle à qui. La [politique de confidentialité](/privacy/) le liste
  en entier.
- **Ce qu'un destinataire garde.** Tout ce qui est déjà sur le téléphone de
  quelqu'un lui appartient. L'application n'empêche pas les captures d'écran et
  ne peut pas rappeler une photo d'un téléphone qui l'a déjà téléchargée.
- **Les captures de votre propre écran.** L'application ne bloque les captures
  nulle part, y compris l'écran qui montre vos six mots.
- **Le premier bonjour.** Comparer les clés en personne n'est pas encore
  construit, donc un serveur qui aurait été malhonnête au tout premier échange
  entre deux personnes n'est pas détectable par elles aujourd'hui.
- **La rétention.** Nous pouvons refuser de rendre la sauvegarde scellée de
  votre clé, ou en rendre une plus ancienne. Les deux vous coûtent une
  restauration&#160;; aucun ne lit une photo.
- **La longueur.** Le chiffré fait à peu près la longueur de ce qui y est
  entré, donc nous pouvons dire approximativement la longueur d'une légende.
  Rien ne la rembourre.
- **Les choses qui sont délibérément en clair.** Les réactions, les noms de
  groupe et qui y est, les membres d'un album, et tout ce que vous tapez dans
  un signalement ou un rapport de problème.
- **Votre propre export.** *paramètres → exporter mes données* écrit une copie
  déchiffrée dans les téléchargements de votre téléphone, où tout ce qui peut
  lire ce dossier peut la lire, et partout où le dossier est sauvegardé.
  L'application le dit avant de lancer.
- **Un téléphone que quelqu'un d'autre contrôle.** Un téléphone débridé et
  déverrouillé entre de mauvaises mains met tout cela en échec.

[Ce que le chiffrement veut dire pour la modération](/moderation/) est une page
à part, parce que c'est la même contrainte vue de l'autre côté&#160;: nous ne
pouvons pas examiner ce que nous ne pouvons pas lire, donc tout ce que nous
pouvons faire agit sur un compte et jamais sur une photo.

Le reste de [comment ça marche](/fr/comment-ca-marche/) décrit le produit auquel
ces choix aboutissent.
