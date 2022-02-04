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
**CSS** = Cascading Style Sheet

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

> Les chemins relatifs sont donc _généralement_ à privilégier : ce sera plus utile pour déployer une maquette en ligne, car elle pourra fonctionner de la même façon que votre version locale

## `div` : la balise de division de contenu

Nous avons déjà vu ensemble quelques balises et leur utilité. En réalité, il existe une autre balise à vocation plus généraliste : la balise `div`.

Elle va vous permettre de déclarer des conteneurs (c'est une balise double), mais sans leur donner une signification particulière dans le code HTML. En gros, si vous n'avez pas besoin d'un titre, d'un paragraphe, d'un lien, etc...mais que vous avez quand même besoin d'occuper un espace, pour un contenu, alors vous pouvez utiliser une div.

La syntaxe est très simple, comme une balise double :

```html
<div>
  <!-- Mon contenu -->
</div>
```

> Pourquoi on parle de cette balise qui semble ne servir à rien, au premier abord ? Parce qu'en réalité, c'est l'une des balises les plus utilisées sur le web

## Les types de balises

Nous allons voir ensemble les 2 types principaux de balises HTML, et leur différence fondamentale. Nous avons déjà vu maintes fois que le fait d'écrire du HTML permettait de parler à un navigateur, qui peut comprendre, interpréter notre code.

Selon les balises qu'on va utiliser, le navigateur va, par défaut, les afficher différemment.

### Les balises block

La caractéristique des balises `block` est qu'elles vont occuper tout l'espace horizontal disponible.

Exemple : h1, h2, h3, h4, h5, h6, div, p...

![h1_block](img/h1_block.png "h1_block")

Ainsi, à l'écran, dans un navigateur, elles vont systématiquement se placer sous la balise précédente, et au-dessus de la balise suivante. Car en occupant tout l'espace horizontal disponible, alors elles repoussent la balise suivante sur une nouvelle ligne.

### Les balises inline

Les balises `inline`, quant à elle, n'occupent que l'espace horizontal nécessaire à leur affichage.

Exemple : a, img...

![a_inline](img/a_inline.png "a_inline")

## CSS

CSS est l'acronyme de **Cascading Style Sheet**.

Nous avons vu ensemble que HTML permettait de définir le **squelette**, ou encore le **corps** de la page. CSS, quant à lui, définit l'habillage, l'apparence des éléments de notre page.

### Syntaxe générale

Comme tout langage, CSS a sa syntaxe.

Globalement, pour appliquer une apparence à un élément de la page, cela se déroulera en 2 temps : on indique un sélecteur, pour pouvoir cibler l'élément qu'on veut styliser, puis on applique des valeurs à des règles (ou propriétés) CSS, entre des accolades.

Exemple :

```css
h1 { /* <-- Sélecteur : toutes les balises h1 */
  color: blue; /* <-- Règle : couleur du texte, Valeur : bleu */
}
```

> Note : vous constatez qu'on peut également écrire des commentaire en CSS avec la syntaxe `/* ... */`

Chaque règle a un nom et un but bien particulier. Nous pouvons donc déclarer plusieurs règles, les unes à la suite des autres, pour un sélecteur donné. Chaque ligne spécifiant une valeur pour une règle donnée doit être terminée par un point-virgule.

Autre exemple :

Nous parlions plus tôt des types de balises (block, inline). La règle CSS associée à ces valeurs est `display`.

Ainsi, pour un élément donné, qui serait par exemple `inline` par défaut, on peut tout à fait changer sa propriété CSS `display` pour le passer en `block` :

```css
a { /* <-- a est un élément inline par défaut */
  display: block;
}
```

### Liaison avec un fichier HTML

Lorsque vous avez déclaré un ensemble de règles et les valeurs à associer pour des sélecteurs donnés, vous souhaitez appliquer cette **feuille de styles** à un document HTML.

Pour ce faire, il suffit de vous rendre dans votre document HTML, et d'utiliser une balise `link` dans la partie `head` de votre page :

```html
<head>
  <!-- ... -->
  <link rel="stylesheet" href="style.css" />
  <!-- ... -->
</head>
```

### Couleurs (texte, arrière-plan)

La propriété de couleur de texte en CSS est `color`. Pour la couleur d'arrière-plan, on peut utiliser `background-color`.

Dans les deux cas, ces propriétés attendent une valeur représentant une couleur, afin que le navigateur puisse l'appliquer sur l'élément cible.

En CSS, on peut représenter une couleur de façons différentes.

#### Un nom

On peut spécifier une couleur avec un nom : `white`, `blue`, `yellow`, ...

#### RGB

RGB est l'acronyme de **Red, Green, Blue**. Quand vous définissez une couleur en RGB, vous définissez la quantité de bleu, vert et rouge que vous allez inclure dans votre couleur finale. Cela va nous permettre de définir des couleurs plus fines que `blue`, si vous voulez un bleu un peu plus clair par exemple.

![rgb](img/rgb.png "rgb")

#### RGBA

RGBA ajoute une notion de transparence dans la couleur, avec un paramètre supplémentaire (alpha).

![rgba](img/rgba.png "rgba")

#### HEX

Vous pouvez également spécifier une valeur en **hexadécimal**. Dans ce cas, vous allez utiliser une base 16 et non plus une base 10.

La base 10 permet de compter de 0 jusqu'à 9, puis de 10 jusqu'à 19, etc...10 par 10.

En base 16, on va compter de 0 jusqu'à 9, puis de A jusqu'à F :

|Base 16  |0  |1  |2  |3  |4  |5  |6  |7  |8  |9  |A  |B  |C  |D  |E  |F  |
|---------|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|Base 10  |0  |1  |2  |3  |4  |5  |6  |7  |8  |9  |10 |11 |12 |13 |14 |15 |

![hex](img/hex.png "hex")

Une couleur en hexadécimal est représentée sur 6 caractères. En réalité, si on divise par 3, alors on peut retrouver notre RVB (ou RGB en anglais).

Dans l'image ci-dessus, nous avons la valeur `#5f5fff`. Il s'agit de la représentation hexadécimale de notre précédent exemple en RGB.

Prenons les 2 premiers caractères, `5f`. Il doit s'agir, logiquement, de la quantité de R, donc rouge, dans notre couleur.

Dans la représentation RGB, nous avions `95` pour le rouge, donc en base 10.

Si nous comptons, à la place, en base 16, alors logiquement nous devrions avoir le tableau de comparaison base 10 et base 16 ci-dessus, de 0 jusqu'à 15, puis, 16 en base 10 équivaut donc à 10 en base 16.

Donc si nous allons de 16 en 16 :

|Base 10  |16 |...|32 |...|48 |...|64 |...|80 |
|---------|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|Base 16  |10 |...|20 |...|30 |...|40 |...|50 |

Puis :

|Base 10  |81 |82 |83 |84 |85 |86 |87 |88 |89 |90 |91 |92 |93 |94 |95 |
|---------|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|Base 16  |51 |52 |53 |54 |55 |56 |57 |55 |59 |5A |5B |5C |5D |5E |5F |

On retrouve donc bien l'équivalent `5F` en base 16, pour la valeur `95` qu'on trouvait en base 10 dans notre couleur représentée en RGB initialement.

La couleur noire sera donc `#000000` et la couleur blanche `#FFFFFF`.

> Note : On peut raccourcir la représentation hexadécimale si les caractères sont les mêmes : `#000000` peut être `#000`, `#FFFFFF` sera `#FFF`, `#FF0000` devient `#F00`, etc...
