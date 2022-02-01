# STUDI - HTML/CSS

- [Introduction](#introduction)
  - [La communication client / serveur](#la-communication-client--serveur)
  - [Le contenu HTML](#le-contenu-html)
  - [Votre premier fichier HTML](#votre-premier-fichier-html)
- [Structure des balises HTML](#structure-des-balises-html)
  - [Balises doubles](#balises-doubles)
  - [Balises simples (ou auto-fermantes)](#balises-simples-ou-auto-fermantes)
  - [Attributs](#attributs)
- [L'inspecteur d'éléments](#linspecteur-déléments)
- [Le cache du navigateur](#le-cache-du-navigateur)
- [Les balises head et body](#les-balises-head-et-body)
- [Les balises de titres](#les-balises-de-titres)
- [Lien hypertexte](#lien-hypertexte)
  - [Faire un lien interne à la page](#faire-un-lien-interne-à-la-page)
- [Les commentaires](#les-commentaires)
- [Les images](#les-images)
- [Les chemins relatifs et absolus](#les-chemins-relatifs-et-absolus)
  - [Chemin absolu](#chemin-absolu)
  - [Chemin relatif](#chemin-relatif)

## Introduction

**HTML** = HyperText Markup Language

### La communication client / serveur

![Client_serveur](img/schema_client_serveur.png "Client_serveur")

Le **client**, un navigateur web, va communiquer avec un **serveur** via le protocole **HTTP**.

Le serveur, en réponse, va lui envoyer une réponse **HTML**.

Cette réponse peut être issue d'un document HTML **statique**, tel que ceux que nous allons réaliser ensemble tout au long de ce module, ou bien issue d'une application web plus complexe, et plus **dynamique** : dans ce cas, la réponse est adaptée au contexte dans lequel on se trouve (si je suis connecté, alors je vois _mon feed_ et pas celui d'un autre...).

### Le contenu HTML

Sur n'importe quel site, vous pouvez consulter le code HTML de la page, en faisant un clic droit n'importe où sur la page et en cliquant sur "Inspecter".

> Vous pouvez également utiliser la touche _F12_ pour ouvrir l'inspecteur d'éléments, sous Windows, ou encore _Command+Shift+C_ sur Mac

Sur toutes les pages qu'on va visiter, nous aurons au minimum cette **structure** dans les outils de développement (inspecteur d'éléments) :

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
```

> Le contenu HTML d'une page représente sa structure, c'est-à-dire l'ensemble des éléments qui composent la page

### Votre premier fichier HTML

Pour pouvoir créer et éditer votre premier fichier HTML, vous allez installer un **IDE** : Integrated Development Environment.

Dans ce module, j'utiliserai [Visual Studio Code](https://code.visualstudio.com/).

Vous pouvez reprendre le [replay du live n°1](https://app.studi.fr/#/dashboard/events/26365/replay) pour avoir les détails d'installation et de configuration, ainsi que les extensions à installer.

Dans Visual Studio Code, on va ouvrir un dossier en passant par le menu ou en utilisant le raccourci _Ctrl+K Ctrl+O_.

Le fait d'ouvrir un dossier nous permet de nous placer dans un **environnement de travail**. C'est dans ce dossier qu'on pourra créer nos différents fichiers.

Une fois dans ce dossier, on va créer un fichier `index.html`, et y inscrire ce contenu :

```html
<!DOCTYPE html>
<html lang="fr">
  <head></head>
  <body>
    Coucou
  </body>
</html>
```

Ensuite, on va se rendre dans un navigateur, puis ouvrir ce fichier directement avec le raccourci _Ctrl+O_.

On doit normalement voir apparaître "Coucou" à l'écran.

## Structure des balises HTML

Lors de la réalisation de nos maquettes HTML, nous utiliserons 2 types de balises :

- Les balises doubles
- Les balises simples (ou auto-fermantes)

### Balises doubles

La structure est très simple :

```html
<balise> ... </balise>
```

Le principe est d'avoir un "tag" d'ouverture et un autre de fermeture. Ainsi, on peut y inscrire du contenu supplémentaire.

Exemple :

```html
<head>
  <title>Le titre de ma page qui s'affichera dans l'onglet</title>
</head>
```

Ici, nous avons utilisé 2 balises doubles : les balises `head` et `title`.

### Balises simples (ou auto-fermantes)

La syntaxe est légèrement différente, mais très simple à retenir :

```html
<balise />
```

Pour le moment nous n'en avons pas encore utilisé concrètement, mais nous en verrons plusieurs.

A titre d'exemple, tout de même, si vous voulez faire un retour à la ligne dans une page, vous pouvez utiliser la balise `br` :

```html
<br />
```

Une petite note supplémentaire sur la syntaxe des balises simples : ça fonctionne aussi sans le `/`, donc sous la forme `<balise>`. Mais personnellement, j'utilise beaucoup plus souvent la syntaxe avec le `/` pour l'auto-fermeture.

![balises](img/balises_html.png "balises")

> Important : chaque balise HTML a un rôle précis, on n'utilise pas les balises au hasard. On vient de découvrir, notamment, que la balise `title` sert à définir le titre de la page, qui apparaîtra dans l'onglet du navigateur par exemple. Ou encore `br`, qui est une balise simple, pour faire un retour à la ligne

### Attributs

Dans toutes les balises, on peut ajouter des attributs sous la forme suivante :

```html
<balise attribut="valeur"></balise>
<balisesimple attribut="valeur" />
```

Par exemple, dans la balise `<html>`, on retrouve l'élément `lang` avec la valeur `fr` :

```html
<html lang="fr">
  ...
</html>
```

## L'inspecteur d'éléments

Dans votre navigateur, vous pouvez **inspecter** le contenu de la page que vous avez à l'écran. En gros, vous pouvez explorer son code source (et son CSS, on le verra plus tard) :

![dev_tools](img/dev_tools.png "dev_tools")

Vous pouvez également modifier le code se trouvant dans la partie "Elements".

> Attention, si vous réalisez un changement, cela ne signifie pas que vous avez modifié le site, vous avez seulement changé l'apparence dans votre navigateur, donc pour vous uniquement. Si je change "Coucou" en un autre texte, cela n'aura pas modifié mon fichier dans VSCode

## Le cache du navigateur

Le cache du navigateur permet au navigateur, quand il affiche une page, de stocker les fichiers (images, CSS, etc...) associés à cette page. Ainsi, si vous souhaitez consulter la même page un peu plus tard, il n'est pas obligé d'aller demander au serveur, il peut vous afficher de nouveau la même page.

> Pensez, quand vous voulez faire des changements dans votre page HTML et que vous l'avez correctement enregistré dans VSCode, à rafraîchir avec le raccourci `Ctrl+R` ou `Ctrl+Shift+R` au lieu de `F5`. Cela est censé vider le cache pour la page que vous voulez rafraîchir

## Les balises `head` et `body`

Les balises `head` et `body` sont **indispensables** dans toute page web.

Elles se trouvent toutes les deux en-dessous de la balise **racine**, la balise `html`.

- La balise `head` permet de décrire au navigateur les **métadonnées** concernant la page qu'on souhaite afficher. Par exemple, quand on utilise la balise `title`, alors on doit l'inscrire dans la balise `head` et pas ailleurs. Son rôle est d'indiquer au navigateur le titre de la page. Mais ce titre n'est pas forcément celui qui apparaîtra dans la page. En l'occurence, on voit que le navigateur s'en sert pour l'afficher dans l'onglet

- La balise `body`, comme son nom l'indique, représente le **corps** de la page : c'est ce qu'on va voir à l'écran

## Les balises de titres

Les balises de `h1` à `h6` permettent, dans le body, d'indiquer au navigateur des titres d'importances variées. Le niveau 1 sera le plus important, on essayera donc de n'avoir qu'une seule balise `h1` sur notre page. Les niveaux de 1 à 6 vont du plus important au moins important.

## Lien hypertexte

La balise `a` est une **balise double**, elle doit avoir au moins un attribut pour nous permettre de naviguer : `href`.

```html
<a href="https://github.com">Cliquez ici pour aller sur Github</a>
```

On a également vu qu'on pouvait forcer l'ouverture du lien dans un nouvel onglet, en ajoutant l'attribut `target` avec la valeur `_blank` :

```diff
-<a href="https://github.com">Cliquez ici pour aller sur Github</a>
+<a href="https://github.com" target="_blank">Un clic sur ce lien s'ouvrira dans un nouvel onglet</a>
```

### Faire un lien interne à la page

On peut également créer un lien qui pointe vers un autre élément de la page.

Pour ce faire, il faut commencer par donner un **identifiant unique** à l'élément. Nous utilisons l'attribut `id` pour ça :

```html
<p id="important">
  ...
</p>
```

Ensuite, dans notre balise de lien, nous pouvons pointer vers cet élément à l'aide d'un `#` suivi de l'identifiant cible :

```html
<a href="#important">Lien vers le paragraphe important</a>
```

Lors du clic, le navigateur se positionnera à hauteur de l'élément important.

> On peut également pointer un identifiant d'une autre page en indiquant le nom de la page puis `#identifiant`. L'attribut href prendrait alors la valeur `pagecible.html#identifiant`

## Les commentaires

Les commentaires, dans n'importe quel langage de programmation, permettent d'écrire du contenu qui sera ignoré par l'interpréteur (votre navigateur) ou le compilateur (s'il s'agit d'un langage compilé).

En HTML, la syntaxe est la suivante :

```html
<!-- Voici un commentaire -->
```

On doit donc encadrer un commentaire par `<!--` et `-->`.

On peut également l'écrire sur plusieurs lignes :

```html
<!--
Voici un commentaire sur
plusieurs lignes
Parce qu'il est un peu plus long à lire
Donc on peut utiliser plusieurs lignes
pour l'écrire
-->
```

On peut par exemple utiliser les commentaires pour décrire une partie du code qu'on a écrit :

```html
<!-- Suite de titres par ordre d'importance -->
<h1>Coucou</h1>
<h2>Coucou</h2>
<h3>Coucou</h3>
```

Alors, à l'écran, on ne verra pas la première ligne, mais seulement les titres.

> Attention, tout commentaire HTML apparaît quand même dans la source de la page, donc dans vos outils de développement si vous les ouvrez ! Veillez donc à ne pas indiquer d'informations sensibles ou confidentielles dans les commentaires HTML

On peut aussi utiliser les commentaires pour désactiver une partie de notre code :

```html
<p>
  Lorem ipsum dolor sit amet
  <!-- <br /> -->
  Pariatur perspiciatis maxime cupiditate, facere illo at eum explicabo nemo
  et veritatis!
</p>
```

Dans l'exemple ci-dessus, la balise `<br />` sera ignorée par le navigateur, bien que le commentaire apparaisse quand même dans le code source de la page.

## Les images

Avec la balise **simple** `<img />`, nous avons la possibilité d'intégrer des images dans nos pages.

Nous devons simplement définir au minimum 2 attributs à cette balise : la source de l'image à afficher, et un texte alternatif décrivant l'image si celle-ci n'a pas pu être chargée.

```html
<img src="landscape.png" alt="Un magnifique paysage" />
```

## Les chemins relatifs et absolus

Dans la section ci-dessus, décrivant la balise `img`, on a indiqué dans l'attribut `src` un chemin vers l'image à afficher.

Ce chemin peut être soit **absolu**, soit **relatif**.

### Chemin absolu

Un chemin absolu désigne un chemin **complet** vers une ressource.

Le terme complet signifie que les éléments inclus dans le chemin vont de la **racine** jusqu'au nom du fichier.

Exemple :

```html
<img src="D:\Documents\Studi\HTML_CSS_01_2022\img\dev_tools.png" alt="Outils de développement" />
```

Ici, j'utilise un chemin local, donc sur ma machine. La racine désigne la lettre du lecteur, puis l'ensemble du chemin à parcourir jusqu'au fichier.

On peut également définir des chemins absolus se trouvant sur internet :

```html
<img src="https://www.google.com/logos/doodles/2022/lunar-new-year-2022-multiple-countries-6753651837109349.3-law.gif" alt="Google Nouvel An Lunaire 2022" />
```

> Note : il est possible que Google retire cette image plus tard, puisqu'elle fait référence à un événement particulier, le nouvel an chinois de 2022. C'est donc normal si en suivant ce lien plus tard qu'en Février 2022, le fichier n'existe plus

Ici, la racine de mon chemin est `https://www.google.com/`, puis l'ensemble des dossiers à parcourir pour aller chercher le fichier d'extension `.gif`.

### Chemin relatif

Un chemin relatif, quant à lui, n'inclura pas l'ensemble du chemin du fichier.

A la place, on va désigner un chemin **relativement au répertoire courant**.

Comment déduire le répertoire courant ?

Par exemple, si je me trouve dans le fichier `index.html` et que je souhaite intégrer une image, alors je vais regarder le répertoire dans lequel se trouve `index.html` : c'est mon répertoire courant.

Ensuite, si j'ai dans le même répertoire un dossier `img/`, comme c'est notre cas ici, je peux le désigner directement, puis indiquer l'image se trouvant dans `img/` :

```html
<img src="img/dev_tools.png" alt="Outils de développement" />
```

Alors, lorsqu'on va afficher la page, le navigateur va **résoudre** automatiquement le chemin en partant de notre répertoire courant. Pour ce faire, il prend en compte le fichier que nous sommes en train de consulter, et résout le chemin vers l'image.
