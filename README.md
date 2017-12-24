# Minitrue

## Links

* [doc original](https://docs.google.com/document/d/1AcVB2a68YHTU2iRsqCZD25fYDofjoib9ijSqoMVE-Do/edit?usp=sharing)

## Abstract

Minitrue est un réseau social privé, (payant par souscription de 5 euros par mois) regroupant des artistes, des penseurs, des philosophes, journalistes, et les supporteurs de leurs travail. Les membres publient, votent, collaborent et échangent sur les créations entre eux en interne. Une selection des oeuvres les plus populaires peuple la partie publique du site, qui integre les travaux du collectif Minitrue (le noyeau) avec les meilleurs oeuvres de la communauté (la communauté). Un jeu d'esprit implémenté au sein même du réseau social apporte une dynamique qui favorise les échanges et la création.

L'idée et de faciliter la creation, la cocreation, le crowdsourcing, et le crowdfunding de la verité.

## En vrac

* Réseau social
* Privé
* Portfolio
* Blog
* Votes
* Favoris/upvotes + Collection de favoris
* Follow
* Feedback (request d'un user à un autre pour avoir du feed back sur une ouevre; request a la foule pour avoir du feedback de n'importe qui - connecté avec quelqu'un qui propose du feedback)
* Collaborations (mettre sur profil si on est ouvert au collab - offrir une collab - oeuvre apparait sur portfolio commun ou seulement sur chacun?)
* Notifications
* Messagerie interne 
* Crowdsourcing (quelqu'un propose un project (ex un documentaire sur l'argentine), la foule upvote, et un artiste propose de le realiser, propose un budget, et realise un crowdfunding)
* Dictionnaire personnel (partie du portfolio - capacité de definir n'importe quelle mot - quand hover-over, une boite apparait avec la definition personnel. Apliqué au jeu et au mini-verité posté sur le portfolio.) ((System de **GSM**:Grok, Skim, Master (Grok = definition de 5-15 mots; un click, on ouvre le Skim=15-30; un click de plus, on ouvre le Master=30-60 mots)
* Jeu de microblogging philosophique avec dynamique d'echec.
* Chaque verité et chaque jet, oeuvres etc ont un numéro distinct. Une nouvelle ouvre, jets, verité, un numero de plus.
* Resumé de livre, d'article en GSM
* Transactions financières (donation, payement, ...)
    * possibilité d'utiliser des outils externes dans un premier temps: Patreon, Paypal, Crowdfunding dans certains cas...

> "Est-ce qu'une solution polyvalente te va. C'est à dire que les utilisateurs enregistrés, ont la possibilité d'ouvir une "page" (appelons là une page pour le moment) qui leur donne la possibilité d'afficher leur créations (text, image, audio, video) sous la forme d'un blog, (des articles les uns à la suite des autres) mais avec la possibilité de sélectionner un certain nombre de leurs créations pour les mettre en avant."

**Oui**


## Questions

### **Système de upvotes des commentires ("comme Reddit")**

Les points clé d'un système à la reddit ou stack exchange c'est qu'il met en avant non pas le dernier poste écrit, mais les postes les plus pertinents.

Un des gros points forts c'est que ce système est dit "auto modéré". Les postes les moins pertinents ne font pas surface. 

Excellent pour stackExchange qui n'a pas vocation à être une board de discussion mais plus une encyclopédie. <span style="color:green"> Est-ce que c'est ce que tu veux ici?</span>

----

Il s'agit de une part un reseau social traditionel: **"Social"**, d'autre part un reddit pour contenu original **"Work"**, et un jeu qui a aussi un systeme de upvote a la reddit **"Work"**. Trois feed separé.

Il pourrait aussi avoir une feed general qui combine les trois.

# Applications

## Vitrine publique

Site semi statique qui contient une sélection des créations internes mise en avant. Renouvellement du contenu régulier mais globalement peu d'accès à la DB de cette partie.

**Fonction de la Vitrine publique**

* All, New, Popular (comme reddit)
* Choisir les categories qu'on veut.
* Upvote mais pas downvote
* Infinite Scroll 

## Reseau social privé

### Vue haut niveau

Hybride board / réseau social

### Features

**Fonctionnalités communautaires classiques:**
* Votes 
* likes/upvotes
* Follow
* Commentaires (mais suelement dans social; pour Work, seulement avec un accord de feedback)
* Notifications
* Messagerie interne 
* Feeds filtrables
* Tous les objets produits par les utilisateurs sont partageable sur tous les vecteurs de communication offert à l'utilisateur

**Fonctionnalités originales:**
* Feedback (request d'un user à un autre pour avoir du feed back sur une oeuvre)
* TrueGame
* `diff`/versionning d'oeuvres (si on clique sur une oeuvre, on peut voir son passé et contexte. Ceci inclus des notes, des autres oeuvres qui ont inspiré, des autres jets. On peut aussi y voir le feedback donné.)
* Collaborations
* Microtransactions

**Fonctionnalités autres:**
* Page de profile hautement personnalisable
    * Possibilité d'afficher du contenu riche et de façon chronologique en fait un blog
    * Possibilité de définir une section "highlight" pour sticky des objets en fait une vitrine/portfolio

**Querys**:
* match geolocalisation
* match type d'activité
* ...



### Contraintes d'implémentation

#### Divers

* <span style="color:red"> Non possibilité de linker des éléments externes au site </span>
    * $\Rightarrow$ Mallus à l'expérience utilisateur
    * $\Rightarrow$ Oblige le stockage interne des ressources ($)
    * $\Rightarrow$ Compromis possible (white list) mais 
    reste un mallus à l'expérience utilisateur.




> **Commentaire perso**: Je comprends l'idée derrière cette limitation, elle favorise les échanges internes. Aussi je sais que tu ne veux pas d'un clone de FB mais attention à ne pas conffondre outil et utilisation de cet outil. Le fait que ce soit une communauté **privée** est un autre outil que tu utilise implicitement pour filtrer l'acces et donc de potentiellement avoir des utlisateurs qui utiliseront de façon intelligente les outils (partage de liens libre) à leur disposition.

#### Architecture

Architecture de type board, avec des catégories non-dynamiques (fixées à l'avance). L'utilisateur n'a pas la possibilité de créer un groupe de discussion.

<span style="color:red"> Clash avec le concepte de reseau social qui est la main app: </span> 
$\Rightarrow$ Chaque élément de contenu créé par un utilisateur est un potentiel sujet de discussion. Opposition avec le souhait de limiter les catégories de discussions.

<span style="color:red"> Il faut faire un choix d'orientation. C'est soit Facebook soit Reddit, pas les deux </span> 

> ...En attente de précision...



## TrueGame

### Vue haut niveau
Au coeur de la dynamique de la partie privée du réseau, ce jeu permet à un utilisateur de proposer une partie à un autre utilisateur (<span style="color:green">temps réel, ou différé, pas de contrainte de temps sauf si choix explicite</span>). Le premier joueur envoie une _vérité_ (déclaration ou question) formulée entre un minimum de $a$ mots et un maximum de $b$ mots (ou choisis de commencer avec une verité tirer du DB au hasard). Le second joueur y répond avec les mêmes contraintes. Le jeux se termine au bout de $n$ échanges ou en fonction d'une éventuelle contrainte de temps.

On peut aussi commencer une partie en postant dans le feed jeux.



### Contraintes d'implémentation

* L'objet `Partie` doit être partageable sur tout le réseau réseau 
* `Partie` est une aggrégation de `Message` qui est un objet partageable sur le réseau indépendament de sa partie mais qui garde une référence cette dernière.


### Améliorations possibles

* Choix de publier le jeux ou le garder en privé
* Upvote/downvote sur les verité (trois choix: -1, +1, +2) (vote possible partout sur le site)
* Point de profil: un point pour chaque tour, + les points donner par les autres)
* Mettre une selection de ses meilleurs verité sur son portfolio.
* Definir des mots dans son dictionnaire personnel pour que les autres utilisateurs puissent mieux comprendre les verités
* Obs
* Plus que deux joueurs
* regarder le jeux en temps reel de quelqu'un d'autre (les meilleurs jouers)
* Choisir de connecter avec quelqu'un qui a + ou - 100/200/etc de points de soi meme.
* Algo qui assure un certain niveau de profondeur des arguments. (Si jamais on trouve une solution à ça, cette IA sera probablement très proche du niveau d'intelligence d'un être humain et plus rien ne sera pareil après ça :D)
* Jouer contre l'ordinateur: ordinateur anaylze mots clés et repond avec une verité proche.
* Possibilité de proposer une langue pour la partie.
* Dessin à la place de texte
* Audio à la place de texte. (bonne foie pour la longueur des phrases ou algo de traitement du signal qui va compter les mots [QOS: best effort])
(j'ai compter une phrase de 15 mots dis tres lentement: pas plus de 15 secondes)
* Audio + Text + dessin


# Sécurité

Standards en vigueur: 
* https (ssl) ($ obligatoire)
* protection CSRF, XSS
* protection brute force et fishing (ReCaptcha, token inscription/reset mdp...)
* cryptage mdp (sha256)
