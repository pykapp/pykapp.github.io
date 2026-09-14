---
title: L'accueil
permalink: /fr/accueil/
---

L'accueil est l'écran sur lequel *people you know* s'ouvre. Cette page dit ce
qu'il contient, ce qui en fait sortir une publication, pourquoi il se termine,
et ce que l'application fait et ne fait pas à côté. La plupart de ce qui suit
est le contraire de la façon dont un fil se comporte d'habitude, donc cela vaut
la peine d'être lu avant que l'application ne vous surprenne.

## C'est une file, et elle se vide

Votre accueil contient les publications que d'autres vous ont adressées et que
vous n'avez pas encore regardées. C'est toute la règle. Rien n'est choisi pour
vous et rien n'est ajouté&#160;: pas de classement, pas de notation, pas de
publications suggérées, pas de publicité, pas de ligne «&#160;personnes que
vous connaissez peut-être&#160;», pas de comptes à découvrir. Une photo est
devant vous parce que quelqu'un vous l'a adressée&#160;: une de vos relations,
ou quelqu'un d'un album où vous êtes tous les deux.

L'accueil a donc une fin. Quand la file est épuisée, l'application dit *vous
êtes à jour*, et il n'y a plus rien à faire défiler. Rien n'est injecté pour
vous faire continuer, parce qu'il n'y a rien ici pour vous retenir&#160;: pas
de portée à faire grandir, pas de total à gonfler, pas de classement à
tromper.

Le défilement lui-même est ordinaire. L'application en charge davantage à
mesure que vous approchez du bas et continue jusqu'à ce que la file soit
vraiment épuisée, quel que soit le nombre de pages. Ce qui est différent, c'est
que la dernière page est suivie d'une ligne de texte plutôt que d'une autre
page.

## Le plus ancien d'abord

La ligne suivante est toujours la chose la plus ancienne que vous n'avez pas
vue. Si Ana vous a envoyé une photo mardi et Bruno il y a une heure, vous
ouvrez l'application sur celle de mardi.

C'est délibéré et cela a un coût qui mérite d'être dit&#160;: la chose la plus
récente n'est pas la première que vous voyez. Ce que cela achète, c'est que la
file peut réellement être finie. Le plus récent d'abord remplit une file par le
bout où vous lisez, donc une arrivée se pose sur ce que vous n'avez pas
atteint, la plus ancienne publication non vue coule sous tout ce qui est venu
après, et *vous êtes à jour* recule aussi vite que vous en approchez. Le plus
ancien d'abord inverse exactement cela&#160;: une arrivée se range derrière
vous, rien ne s'insère jamais devant vous, et la fin ne fait que se rapprocher.

L'ordre est celui du moment où une publication vous est parvenue, pas de celui
où elle a été prise ou écrite. Une publication à laquelle quelqu'un vous ajoute
aujourd'hui arrive aujourd'hui au fond de la file, même si elle a été publiée
en mars.

## Ce que «&#160;vu&#160;» veut dire, exactement

Une publication quitte votre file quand vous avez regardé sa première photo.
Trois choses doivent être vraies en même temps&#160;:

- la ligne montre la première photo, pas la deuxième ni la troisième&#160;;
- la vraie photo est arrivée et a été déchiffrée, pas le flou que
  l'application peint pendant qu'elle la charge&#160;;
- cette photo est entièrement dans l'écran, ou le remplit entièrement, pendant
  une seconde et demie d'affilée. Si elle défile hors de l'écran, le compte
  repart de zéro.

Une publication qui quitte la file ne revient pas, donc l'erreur dangereuse est
de marquer vue une chose que personne n'a regardée. Toute ambiguïté est
tranchée vers le pas-encore, et c'est pourquoi la règle est aussi stricte.

La première photo suffit pour toute la publication. Les exiger toutes
laisserait une publication de vingt photos coincée dans la file pour toujours,
ce qui est précisément ce que l'accueil existe pour éviter.

**Seul l'accueil marque une publication comme vue.** Ouvrir une publication
depuis votre onglet activité, depuis une notification ou depuis le profil de
quelqu'un ne la sort pas de votre file. Il faut quand même regarder la ligne
dans l'accueil.

**Personne n'apprend que vous avez regardé.** Il n'y a nulle part dans
l'application de liste de personnes ayant vu, de compteur de vues ni d'accusé
de lecture. L'application enregistre bien que vous avez vu une publication,
parce que c'est ainsi que votre file se vide et qu'un ensemble de photos rouvre
là où vous l'aviez laissé, et il n'existe ni écran, ni route, ni champ qui le
rapporte à la personne qui a publié. Une version avec la liste des personnes
ayant vu a été construite une fois puis retirée&#160;: un accusé de lecture par
personne fait du fait de regarder une photo un acte qui est rapporté, ce qui
est précisément ce dont ce produit veut être une échappatoire.

## Rien ne disparaît sous votre pouce

Au moment où une publication est marquée vue, le serveur cesse de la renvoyer.
L'application garde la ligne exactement là où elle est pour le reste de la
session. Les lignes ne disparaissent pas en plein défilement, la liste ne se
réorganise pas, et rien de ce que vous lisez ne bouge. La photo jusqu'à
laquelle vous aviez fait défiler reste sous votre pouce tant que la ligne est à
l'écran.

Le temps d'une session, l'application garde délibérément des lignes que le
serveur ne lui enverrait plus. Les deux se réconcilient à la frontière de
session et nulle part ailleurs.

## Quand l'accueil se recharge, et quand il ne se recharge pas

Une session d'accueil se termine de trois façons exactement&#160;:

- l'application est restée en arrière-plan plus de 32 minutes&#160;;
- l'application démarre à froid&#160;;
- vous tirez l'accueil vers le bas. L'indicateur est fait des mots de
  l'application, *tirer pour actualiser* puis *actualisation*, plutôt que d'une
  roue qui tourne.

À la session suivante, tout ce que vous avez vu a disparu et tout ce qui est
nouveau est là. Les publications non vues restent où elles sont, dans l'ordre
des dates, aussi longtemps qu'elles y restent.

Rien d'autre ne recharge l'accueil. Une notification qui arrive ne le fait
pas&#160;: un message est la nouvelle de l'application, pas la vôtre, et ce
n'est pas une quatrième sorte de frontière de session. Il n'y a pas de pastille
«&#160;nouvelles publications&#160;», pas d'actualisation minutée et pas de
réorganisation en arrière-plan. Toucher *accueil* alors que vous y êtes déjà ne
fait rien du tout, parce que reconstruire la file que vous tenez est la seule
chose que l'accueil ne doit pas faire. Revenir d'une publication que vous avez
ouverte vous ramène à l'accueil tel que vous l'aviez laissé.

Le tirage est la seule frontière qui soit une décision plutôt qu'un laps de
temps, et il existe parce que sinon la seule façon de dire «&#160;j'en ai fini
avec celles-ci&#160;» serait de poser le téléphone une demi-heure.

## Vous êtes à jour, et les publications déjà vues

*vous êtes à jour* n'apparaît que lorsque le serveur a dit qu'il n'y a rien
après la dernière ligne. Cela n'apparaît jamais parce qu'une page se trouvait
être courte.

Dessous se trouve un seul lien, *publications déjà vues*. Cet écran est le
passé de l'accueil lui-même&#160;: tout ce qui vous a été livré et que vous
avez regardé, du plus récent au plus ancien selon le moment où vous l'avez vu,
jamais remis en avant, jamais supprimé automatiquement, et sans aucune
pastille. Chaque ligne est la première photo, l'auteur, la date et la légende.
On n'y fait pas défiler les photos, parce que passer image par image sur ce que
vous avez déjà vu est du butinage pour lui-même.

Il vaut la peine de savoir que c'est la seule porte vers cet écran. Ce n'est
pas une ligne dans les paramètres, et on ne peut pas y arriver depuis un onglet
qui contient encore des publications non vues. Si vous avez été interrompu au
milieu d'une lecture et que la publication a déjà quitté votre file, il n'y a
aucun chemin de retour tant qu'une file ne s'est pas vidée. Ce manque est
connu, et il est consigné comme une question ouverte plutôt qu'expliqué.

## Les onglets sont votre propre classement

En haut de l'accueil se trouvent vos groupes, avec *tout le monde* en premier.
Un groupe où vous n'avez mis personne n'a pas d'onglet, donc un compte neuf en
voit un seul.

Un onglet de groupe filtre selon **qui a écrit la publication**, d'après votre
propre classement, et non selon la façon dont l'auteur l'a adressée. Votre
onglet *famille* montre les publications non vues des personnes que vous avez
classées sous famille, quels que soient les destinataires qu'elles ont choisis
de leur côté. Vos groupes n'appartiennent qu'à vous&#160;: ils ne sont pas
réciproques, et personne n'apprend jamais dans lequel de vos groupes il se
trouve, ni même qu'il est dans un. Mettre Ana dans *table du dîner* ne vous met
pas dans le sien, et Ana ne peut pas le découvrir.

Le nombre à côté d'un onglet est le compte des publications non vues qu'il
contient. À part le compte des photos sur une ligne, c'est le seul nombre de
l'accueil, et il est permis parce qu'il est le vôtre, visible par personne
d'autre, et qu'il descend à mesure que vous lisez. Il n'y a pas de compteur de
commentaires sous une photo, pas de total de réactions, pas de compteur de vues
et nulle part de nombre que quelqu'un d'autre puisse faire grossir.

## Ce qui n'est pas dans votre accueil

**Vos propres publications.** L'accueil, c'est ce que les autres vous ont
envoyé. Il n'y a pas de livraison de vous vers vous-même, donc il n'y a pas de
ligne à y mettre&#160;; vos publications vivent sur votre propre profil, qu'on
rejoint par la marque *profil*, et publier vous y amène.

**Le catalogue de qui que ce soit.** Quand vous entrez en relation avec
quelqu'un et qu'il partage ses anciennes publications avec vous, ces photos
apparaissent sur son profil à leurs dates d'origine et n'entrent jamais dans
votre file&#160;: mille vieilles publications arrivant d'un coup laissent
l'accueil vide. Être ajouté à une seule publication qui existe déjà est autre
chose – cette livraison est datée de maintenant, donc elle arrive au fond de la
file comme une nouveauté, et votre onglet activité dit qui vous y a mis.

**Tout ce qui a été repris.** Une publication supprimée pour tout le monde
quitte tous les accueils d'un coup, et rompre une relation vide votre accueil
des publications de cette personne, parce que ce qui part est la clé plutôt
qu'une permission.

**Toute personne que vous avez masquée.** Masquer est un interrupteur sur le
profil de quelqu'un et cela fait exactement une chose&#160;: ses publications
cessent d'arriver ici, et cessent d'être comptées sur vos onglets. Rien n'est
enlevé – chaque photo qu'elle vous a envoyée est toujours sur son profil, et
désactiver l'interrupteur remet la file en place, y compris ce qui est arrivé
pendant. C'est la seule chose sur cette page qui cache une publication au lieu
de la reprendre, et elle n'appartient qu'à vous&#160;: la personne n'en est
jamais informée. Voir
[entrer en relation](/fr/ajouter-des-relations/).

Masquer quelqu'un reconstruit la file la prochaine fois que vous la regardez,
exactement comme tirer l'accueil vers le bas. C'est voulu&#160;: la première
chose que l'on fait après avoir masqué quelqu'un, c'est vérifier, et retrouver
l'accueil tel quel donnerait l'impression que l'interrupteur n'a rien fait.

## Ce qu'une ligne montre

Une ligne, c'est la photo et le nom de l'auteur, la date de publication, les
photos et la légende. Si des personnes y sont identifiées, une ligne lit *avec
anna, bruno*. Si c'est une contribution à un album, une ligne lit *dans Maine*.
Si quelqu'un l'a repartagée, une ligne au-dessus du nom de l'auteur lit *bruno
a repartagé*, et la ligne porte toujours le nom et le visage de l'auteur
d'origine.

Jusqu'à huit photos forment un ensemble que l'on fait défiler, avec des points
dessous dès qu'il y en a plus d'une. Au-delà de huit, les quatre premières sont
montrées en grille avec un lien qui lit *voir les 24* vers l'écran complet. Ce
sont les quatre premières dans l'ordre où l'auteur les a mises, jamais les
meilleures choisies&#160;: choisir les quatre meilleures serait cette
application en train de classer les photos de quelqu'un.

Rien de ce que quelqu'un a publié n'est jamais recadré. La boîte où une photo
est dessinée est bornée, pour qu'une image ne puisse pas prendre tout l'écran
et pousser la légende hors de vue, et une image qui n'entre pas dans cette
boîte y est logée plutôt que rognée. La seule exception est la grille de quatre
ci-dessus, qui carre ses tuiles parce qu'une planche-contact aux bords
irréguliers est plus difficile à lire, et l'image entière est à une touche de
là. Toucher une photo dans l'accueil ouvre la publication à cette photo&#160;;
la toucher à nouveau ouvre l'écran complet, qui n'a aucune borne.

Une légende est raccourcie à trois lignes dans la liste et jamais modifiée&#160;;
elle est entière à une touche de là. Un nom dans une ligne ouvre le profil de
cette personne, ou, pour quelqu'un identifié sur la photo avec qui vous n'êtes
pas en relation, la [fiche](/how-it-works/people/) qui dit qui vous connaissez
tous les deux. Un auteur que ce téléphone ne peut pas nommer s'affiche comme le
simple mot *quelqu'un* et ne mène nulle part. Dans un
[album](/how-it-works/albums/), vous pouvez voir une contribution de quelqu'un
avec qui vous n'avez aucune relation, parce que les membres de l'album en sont
les destinataires&#160;: la ligne le nomme, et le nom n'est pas un lien, parce
qu'il n'y a pas de profil derrière.

Une ligne de l'accueil ouvre toujours ses photos à la première, y compris quand
elle sort de l'écran et y revient&#160;: une ligne revenue à la deuxième ne
pourrait jamais satisfaire la règle du vu, et la publication resterait dans
votre file pour toujours. L'écran d'une publication se comporte
différemment&#160;: une publication que vous ouvrez reprend à la photo que vous
regardiez en dernier. Toucher une photo précise dans l'accueil l'emporte sur
les deux et ouvre la publication à celle-là.

## L'onglet activité

La cloche de la barre est *activité*, et elle contient les choses qui vous
arrivent qu'aucun autre écran ne nomme déjà. Aujourd'hui cela fait
sept&#160;: quelqu'un a réagi à votre publication, quelqu'un l'a commentée,
quelqu'un vous a ajouté à une publication, quelqu'un a accepté votre demande,
quelqu'un vous a ajouté à un album, quelqu'un vous a identifié sur une
publication, et quelqu'un a repartagé votre publication. Toucher une ligne
ouvre ce dont il s'agit.

Une publication qui arrive n'y est pas, parce qu'une publication qui arrive
appartient à l'accueil. Une demande d'ajout n'y est pas non plus, parce qu'elle
est en haut de votre propre profil. L'onglet ne répète pas ce qu'un autre écran
montre déjà.

Toutes les réactions d'une même publication font une seule ligne, qui nomme la
dernière personne à avoir réagi, et elle redevient non lue quand quelqu'un de
nouveau réagit. Ce n'est pas «&#160;anna et trois autres&#160;», parce que
c'est un compte de ce que d'autres ont fait. Les commentaires gardent une ligne
chacun&#160;: trois commentaires sont trois choses que quelqu'un a écrites.

**Il n'y a pas de compteur de non-lus.** Ni sur la cloche, ni sur l'onglet, ni
sur le lien qui l'ouvre. Une ligne arrivée depuis votre dernière visite porte
le mot *nouveau* à côté de sa date, les lignes que vous avez déjà lues sont
dessinées dans une encre plus claire, et c'est tout. Chaque nombre de cette
application est le vôtre, borné et décroissant&#160;; un décompte de ce que
d'autres vous ont fait grandit pendant que vous ne faites rien, ce qui est
précisément ce que l'application essaie de ne pas être.

La cloche peut porter un simple point, qui a deux valeurs quel que soit le
nombre de choses arrivées. Il demande si l'entrée la plus récente est non lue,
donc regarder y répond et il s'éteint à l'ouverture de l'onglet. Le point sur
la marque du profil pose une autre question, celle de savoir si quelqu'un
attend une décision de vous, donc regarder n'y répond rien&#160;: il survit à
votre visite et ne s'éteint que lorsque la dernière demande a été acceptée,
refusée ou a expiré.

## Les notifications

L'application est silencieuse par défaut, et elle demande la permission de vous
notifier depuis l'onglet activité plutôt qu'à l'inscription. La ligne y
lit&#160;: «&#160;Rien ici n'a besoin de vous parvenir. Si vous le souhaitez,
c'est ici qu'il faut le dire.&#160;»

Cinq choses peuvent poser une notification sur votre téléphone&#160;:

- quelqu'un qui demande à vous ajouter, dans *paramètres → notifications* sous
  *quand quelqu'un veut m'ajouter*, le seul interrupteur qui commence
  activé&#160;;
- quelqu'un qui commente votre publication, sous *quand quelqu'un commente ma
  publication*, désactivé jusqu'à ce que vous l'activiez&#160;;
- une personne précise qui publie, ce qui est un interrupteur sur son profil
  qui lit *me prévenir quand anna publie*, désactivé pour tout le monde
  jusqu'à ce que vous le demandiez&#160;;
- quelqu'un qui ajoute des photos à un album précis, ce qui est un interrupteur
  sur l'écran de cet album&#160;;
- quelqu'un qui vous identifie sur une photo, ce qui n'a pas d'interrupteur à
  soi sous *notifications*. Cela dépend de *autoriser mes relations à
  m'identifier*, activé jusqu'à ce que vous le désactiviez, donc autoriser le
  nom autorise la notification et refuser l'un refuse les deux.

Une photo est une interruption&#160;: une publication qui pourrait satisfaire
plusieurs de ces interrupteurs à la fois envoie exactement une notification.
Être identifié est le cas le plus net – la notification à propos du nom arrive
*à la place de* celle que vous auriez eue pour la publication, jamais à côté.

**Une réaction ne peut jamais notifier personne, et aucun réglage ne pourrait
le permettre.** Il n'y a pas de type de notification pour cela, pas de colonne
dans la base et pas de route, et l'écran des paramètres le dit dans une ligne
sous l'interrupteur des commentaires&#160;: «&#160;Les réactions ne préviennent
jamais personne, et rien ne peut les y forcer.&#160;» Vous pouvez déjà voir qui
a réagi en ouvrant votre propre publication, donc la ligne d'activité vous
épargne les touches&#160;; ce qui est refusé, c'est l'interruption. Se faire
repartager est pareil&#160;: cela écrit une ligne dans votre onglet activité et
ne pose aucune notification sur votre téléphone.

Il n'y a pas de «&#160;vous n'avez rien publié depuis un moment&#160;», pas de
résumé, pas de série à tenir et aucun message de relance d'aucune sorte. Ce
n'est pas une règle que quelqu'un pourrait assouplir&#160;: une notification
ici est un seul mot nommant le genre de chose qui s'est produit, sans aucun
champ où une phrase pourrait être mise.

Ce mot est tout ce que la notification porte. Pas de nom, pas de légende, et
pas d'identifiant de publication non plus, parce que deux téléphones recevant
le même identifiant dans la même seconde sont deux personnes d'un même ensemble
de destinataires, et répété assez souvent chez un tiers, c'est votre graphe
social. La phrase que vous lisez, «&#160;anna a commenté votre
publication&#160;», est écrite par votre propre téléphone à partir d'un profil
que nous ne détenons que chiffré et que nous ne pouvons pas ouvrir. La
[politique de confidentialité](/privacy/) dit ce que nous pouvons et ne pouvons
pas voir.

Se déconnecter sur un téléphone arrête tout envoi vers ce téléphone pour ce
compte. C'est le serveur qui le fait, dans la même étape que celle qui termine
la session, plutôt qu'une chose dont l'application devrait se souvenir en
partant.

---

Le reste du guide est à [comment ça marche](/fr/comment-ca-marche/).
