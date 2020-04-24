## Présentation

Le RPI2JAMMA est une carte permettant de connecter un Raspberry Pi (RPi) sur une borne d'arcade JAMMA et ainsi profiter de l'émulation de plusieurs systèmes (console et arcade).

Cette carte a été créée, fabriquée et distribuée par « aje_fr ». Elle se destine à un usage de loisir privé et n’est en aucun cas destinée à une utilisation en exploitation commerciale ou à un commerce de revente.

## Spécifications

* Le RPi est alimenté par le port JAMMA
* Sortie RVB 18 bits, 15khz, 24khz (les menus sont en 15khz et si un jeu 24khz est lancé, le système bascule en 24khz)
* Affichage horizontal (yoko) ou vertical (tate)
* "Pixel Perfect", chaque jeu utilise sa propre modeline donc résolution et fréquence de rafraîchissement respectées
* Pas de tearing !
* Ampli stéréo intégré
* Interrupteur pour le choix Mono / Stéreo
* Interrupteur pour le choix de la sortie HP ou sur JAMMA
* Connecteurs pour HP externes 4 points (format Konami) ou 6 points (Egret 3 par ex.)
* Réglage numérique du volume et balance par bouton. Une led indique le mode (balance ou volume). Volume accessible également via un raccourci (voir "Contrôles")
* Jusqu'à 4 joueurs !
* Kick harness au format CPS1 pour les boutons 4, 5, 6 des 4 joueurs (les boutons 4 et 5 des joueurs 1 et 2 aussi disponibles sur le peigne JAMMA)
* Connecteurs 15 points (format Konami) pour joueurs 3 et 4
* Optimisé pour RPi3b+, RPi3 et RPi2.

## Schéma de présentation

IMAGE

## Les différents connecteurs

IMAGE

## Matériel nécessaire

* Une carte RPI2JAMMA
* Un RPi (RPi3b+ ou RPi3 conseillé pour de bonnes performances)
* Une carte MicroSD de 4Go minimum (classe 10 de préférence)
* Une clé USB (bon débit en USB2 conseillé)
* Un ordinateur (Windows / OSX / Linux)
* Un multimètre (fortement conseillé)

## Installation logicielle

### Système (MicroSD)

* Téléchargez l'image de la distribution depuis le lien fourni par aje_fr
* Décompressez l'archive pour extraire l'image (fichier .img)
* Téléchargez "Etcher" (Windows, OSX et Linux) disponible ici ou “Win32diskimager” disponible ici
* Flashez l'image sur la carte MicroSD avec "Etcher" ou “Win32diskimager”

### Stockage (Clé USB)

Formatez la clé USB en FAT32 de préférence (voir ci-dessous), en exFat ou NTFS. Les autres systèmes de fichier ne sont pas supportés.

#### Windows

Pour les clés USB de capacité inférieure ou égale à 32 Go un simple clic-droit sur le lecteur concerné permettra de formater la clé en FAT32. Pour les clés USB de capacité supérieure à 32 Go il faudra utiliser "fat32format" ou un logiciel équivalent.

#### OSX

Quelle que soit la capacité de la clé USB, l'utilitaire de disque natif permet de la formater en FAT32. Il faut utiliser l'onglet "Partition" et bien choisir "Master Boot Record" lorsque l'assistant le propose.

#### Linux
Quelle que soit la capacité de la clé USB, l'utilitaire "gparted" permet de la formater en FAT32.

Vos périphériques de stockage (MicroSD et clé USB) sont prêts à être installés, vous pouvez passer à l'étape suivante.


## Horizontal Rules

___

---

***


## Typographic replacements

Enable typographer option to see result.

(c) (C) (r) (R) (tm) (TM) (p) (P) +-

test.. test... test..... test?..... test!....

!!!!!! ???? ,,  -- ---

"Smartypants, double quotes" and 'single quotes'


## Emphasis

**This is bold text**

__This is bold text__

*This is italic text*

_This is italic text_

~~Strikethrough~~


## Blockquotes


> Blockquotes can also be nested...
>> ...by using additional greater-than signs right next to each other...
> > > ...or with spaces between arrows.


## Lists

Unordered

+ Create a list by starting a line with `+`, `-`, or `*`
+ Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    * Ac tristique libero volutpat at
    + Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
+ Very easy!

Ordered

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa


1. You can use sequential numbers...
1. ...or keep all the numbers as `1.`

Start numbering with offset:

57. foo
1. bar


## Code

Inline `code`

Indented code

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code


Block code "fences"

```
Sample text here...
```

Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```

## Tables

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

Right aligned columns

| Option | Description |
| ------:| -----------:|
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |


## Links

[link text](http://dev.nodeca.com)

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)


## Images

![Minion](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

Like links, Images also have a footnote style syntax

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg  "The Dojocat"


## Plugins

The killer feature of `markdown-it` is very effective support of
[syntax plugins](https://www.npmjs.org/browse/keyword/markdown-it-plugin).


### [Emojies](https://github.com/markdown-it/markdown-it-emoji)

> Classic markup: :wink: :crush: :cry: :tear: :laughing: :yum:
>
> Shortcuts (emoticons): :-) :-( 8-) ;)

see [how to change output](https://github.com/markdown-it/markdown-it-emoji#change-output) with twemoji.


### [Subscript](https://github.com/markdown-it/markdown-it-sub) / [Superscript](https://github.com/markdown-it/markdown-it-sup)

- 19^th^
- H~2~O


### [\<ins>](https://github.com/markdown-it/markdown-it-ins)

++Inserted text++


### [\<mark>](https://github.com/markdown-it/markdown-it-mark)

==Marked text==


### [Footnotes](https://github.com/markdown-it/markdown-it-footnote)

Footnote 1 link[^first].

Footnote 2 link[^second].

Inline footnote^[Text of inline footnote] definition.

Duplicated footnote reference[^second].

[^first]: Footnote **can have markup**

    and multiple paragraphs.

[^second]: Footnote text.


### [Definition lists](https://github.com/markdown-it/markdown-it-deflist)

Term 1

:   Definition 1
with lazy continuation.

Term 2 with *inline markup*

:   Definition 2

        { some code, part of Definition 2 }

    Third paragraph of definition 2.

_Compact style:_

Term 1
  ~ Definition 1

Term 2
  ~ Definition 2a
  ~ Definition 2b


### [Abbreviations](https://github.com/markdown-it/markdown-it-abbr)

This is HTML abbreviation example.

It converts "HTML", but keep intact partial entries like "xxxHTMLyyy" and so on.

*[HTML]: Hyper Text Markup Language

### [Custom containers](https://github.com/markdown-it/markdown-it-container)

::: warning
*here be dragons*
:::

    © 2020 GitHub, Inc.
    Terms
    Privacy
    Security
    Status
    Help

    Contact GitHub
    Pricing
    API
    Training
    Blog
    About

