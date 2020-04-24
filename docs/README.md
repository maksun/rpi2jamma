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


## Installation matérielle

* Insérez la carte MicroSD dans le RPi
* Insérez la clé USB dans un des ports USB du RPi
* Couplez le RPi à la carte RPI2JAMMA via les connecteurs GPIO respectifs. Le port MicroSD du RPi doit être orienté vers le port JAMMA. Veillez à bien aligner les broches et donc à ne pas les décaler.

Votre RPI2JAMMA est maintenant prêt à l'utilisation, bien sûr vous pouvez l'installer correctement sur un support (planche en bois, plexiglas etc.) avec des pieds de PCB.

## Prise en main

### Prérequis
Votre borne doit être conforme au standard JAMMA (non modifié de manière exotique). La tension délivrée par le peigne JAMMA (entre les pin 1 & 3 ou 1 & 4) doit être située entre 5v et 5,25v maximum.
Si vous ne passez pas le son par le JAMMA, connectez les HP de votre borne sur le connecteur « Konami » ou « Egret ».
Si vous utilisez plus de 3 boutons, connectez les "Kick Harness" (format CPS1).
Si votre borne est 3 ou 4 joueurs, connectez les J3 & J4 (plus les "Kick Harness" si plus de 3 boutons).

### Mise en route
* Branchez le RPI2JAMMA sur le port JAMMA de votre borne
* Sélectionnez la sortie son HP ou JAMMA avec l’interrupteur
* Sélectionnez le son Mono ou Stéréo avec l’interrupteur. Normalement en Mono si par le peigne JAMMA (sauf si câblé MVS)
* Allumez la borne
* Le RPI2JAMMA démarre et créé les répertoires nécessaires sur la clé USB
* Le menu principal doit s'afficher, si ce n'est pas le cas reportez-vous à la section "Dépannage"
* Sélectionnez "Settings" puis "01_Shutdown" et attendez quelques secondes avant d'éteindre la borne.
* Récupérez la clé USB et installez des ROMs dans les répertoires adéquats (snes, nes, neogeo etc.). Pour les émulateurs de jeux d'arcade les versions de "romset" sont précisées dans la FAQ ou dans le fichier “__Emulators_version__.txt” du répertoire “Config_RPI2XXXXX”. 
* Rebranchez la clé USB dans le RPi et rallumez votre borne
* Borne allumée, vérifiez à nouveau la tension de 5v

### Extinction
* Quitter le jeu en cours
* Revenir au menu principal (accueil)
* Sélectionner « Settings »
* Sélectionner « Shutdown »
* Attendre quelques secondes
* Éteindre la borne.

## Menu principal
| Menu | Description |
|------|-------------|
| 01_Shutdown | Éteindre le RPI2JAMMA |
| 02_Restart System | Redémarrer le RPI2JAMMA |
| 03_Screen | <p>**AdvanceMAME Config**<br>Configurer la sortie vidéo de l'émulateur AdvanceMAME<br>**Display test**<br>Afficher des mires de test.<br>**Switch to Horizontal**<br>Basculer vers l'affichage horizontal (Yoko)<br>**Switch to Vertical**<br>Basculer vers l'affichage vertical (Tate)<br>**Switch to Vertical (inversed)**<br>Basculer vers l'affichage vertical (Tate) inversé</p> |
| 04_Tools | <p>**Clear Game Database**<br>Effacer la base de donnée des jeux<br>**Install Update Patch**<br>Permet d’installer un patch de mise à jour (si disponible)<br>**Scrap All Roms**<br>"Scrapper" toutes les ROMs<br>**erify USB Key**<br>Vérifier et corriger les éventuelles erreurs du système de fichier de la clé USB</p> |
| 05_NeoGeo | <p>**Switch to AES mode**<br>Basculer l'émulateur Neo Geo en mode AES (console)<br>**Switch to MVS mode**<br>Basculer l'émulateur Neo Geo en mode MVS (arcade)</p> |
| 06_Amiga | <p>**Scan for Roms**<br>Permet de scanner les ROMs amiga et créer les fichiers de configuration adéquats (jeux multi-disques par exemple)</p> |
| 07_Extras | <p>**01_MalditaCastilla**<br>Lancer le jeu MalditaCastilla<br>**02_SuperCrateBox**<br>Lancer le jeu SuperCrateBox</p> |
| 08_WIFI | <p>**Disable**<br>Désactiver la fonction Wi-Fi du RPI2JAMMA<br>**Enable**<br>Activer la fonction Wi-Fi du RPI2JAMMA<p> |
| 09_Info | <p>Affiche la version courante des émulateurs et des romsets</p> |

## Contrôles
### Légende
| Menu                 | Description                     |
|----------------------|---------------------------------|
| Player 1 / 2 / 3 / 4 | P1 / P2 / P3 / P4               |
| Bouton 1 / 2 / 3 / 4 | B1 / B2 / B3 / B4               |
| Start (0,5s)         | Appui long Start (0,5s minimum) |

### Dans les menus
| Menu                  | Description |
|-----------------------|-------------|
| Valider               | B1          |
| Retour                | B2          |
| Options (sur un jeu)  | B4          |
| Menu EmulationStation | Start       |

### En jeu
| Menu | Description |
|------|-------------|
| Quitter | Start (0,5s) + B2 |
| Créditer | Start (0,5s) + B1 |
| Pause | Start (0,5s) + Bas |
| Volume - / + | Start (0,5s) + Gauche / Droite |
| Options émulateur | Start P1 (5s) |
| Test mode | Start P2 (5s) |
| Menu UniBios (Neo Geo) | Start P1 (0,5s) + B1 + B2 + B3 |

### Émulation Amstrad
| Menu | Description |
|------|-------------|
| Touche "Enter" | Start |
| Barre d'espace | B4 |
| Touche "Y" | B5 |
| Touche "N" | B6 |
| Option | Start (5s) |

### Émulation Atari
| Menu           | Description |          |
|----------------|-------------|----------|
|                | Player 1    | Player 2 |
| Fire           | B1          | B1       |
| Barre d'espace | B2          |          |
| Touche "F1"    | B3          |          |
| Touche "F2"    |             | B3       |
| Touche "T"     | B4          |          |
| Touche "Y"     | B5          |          |
| Touche "N"     | B6          |          |
| Touche "1"     | Start       |          |
| Touche "2"     |             | Start    |

### Émulateurs arcades
Le bouton de service et le monnayeur de la borne ont leurs fonctions normales.

## Options avancées
### Réseau
#### Ethernet
Connectez un câble RJ45 entre le RPi et votre box Internet, celle-ci attribuera automatiquement une adresse IP au RPI2JAMMA (via le protocole DHCP).
#### WiFi
Éditez le fichier wifi_config.txt dans le dossier Config_RPI2XXXXX qui se trouve à la racine de la clé USB puis modifiez les deux lignes suivantes :
```
psk="la_clé_de_votre_réseau_wifi"
ssid="le_nom_de_votre_réseau_wifi"
```
Sous Windows il faut convertir le fichier en format Unix à l'aide de Notepad++ (Edition > Convertir les sauts de ligne > Convertir en format Unix)
Puis activez le wifi dans le menu principal : 08_WIFI.

### Ajout de roms
#### Via le réseau
Depuis votre ordinateur, saisissez \\RPI2JAMMA\UsbKey\roms dans l'explorateur Windows. Ajoutez des ROMs dans le dossier correspondant à l'émulateur de votre choix puis redémarrez le RPI2JAMMA afin de mettre à jour la liste des ROMs.

#### Via la clé USB
Éteignez le RPI2JAMMA puis débranchez la clé USB. Branchez-là sur votre ordinateur puis ajoutez des ROMs dans le dossier correspondant à l'émulateur de votre choix. Débranchez proprement la clé USB de votre ordinateur puis branchez-là sur le RPI2JAMMA, pour finir démarrez le RPI2JAMMA.

### BIOS Neo Geo
Le pack Neo Geo proposé sur le forum Neo-Arcadia fournit les différents BIOS (dans le répertoire "BIOS") et propose par défaut un BIOS de type "unibios".
Si vous souhaitez en utiliser un autre, renommez simplement le fichier du BIOS choisi en "neogeo.zip" et prenez soin au préalable de renommer le fichier correspondant au bios actuel pour ne pas le perdre (ex : neogeo_UNIBIOS.zip).

### Autoboot
L'autoboot permet de lancer un jeu automatiquement au démarrage du RPI2JAMMA. Modifiez le fichier autoboot.txt dans le dossier Config_RPI2XXXXX qui se trouve à la racine de la clé USB.
Le fichier doit contenir les deux lignes suivantes :
```
system=nom_du_système (nom du dossier)
game=nom_du_jeu (avec extension)
```
Exemple avec le jeu Metal Slug sur Neo Geo :
```
system=neogeo
game=mslug.zip
```
Sous Windows il faut convertir le fichier en format Unix à l'aide de Notepad++ (Edition > Convertir les sauts de ligne > Convertir en format Unix).

### RetroAchievements
Les retroachievements sont des succès/trophées à débloquer en jeu en réalisant certaines actions. Ce système est connu sur les consoles de nouvelle génération et grâce à la plateforme https://retroachievements.org il est possible de faire la même chose avec les jeux "rétro".

Prérequis :
* Créer un compte sur le site https://retroachievements.org
* Connecter votre RPI2XXXXX à internet

Modifiez le fichier RetroAchievements.txt dans le dossier Config_RPI2XXXXX qui se trouve à la racine de la clé USB.
Le fichier doit contenir les lignes suivantes :
```
cheevos_enable = "false"
cheevos_test_unofficial = "false"
cheevos_hardcore_mode_enable = "false"
cheevos_username = ""
cheevos_password = ""
```

#### Description
| Option           | Description                                                           |
|------------------|-----------------------------------------------------------------------|
| cheevo_enable    | ```"true"|"false"```Activer/Désactiver la fonction retroachievements. |
| cheevos_test_unofficial (true ou false) | Activer/Désactiver les retroachievements non officiels. Ces derniers ne rapportent aucun point. Cette fonction existe à des fins de test et est plutôt réservée à ceux qui développent les retroachievements.                                                                         |
| cheevos_hardcore_mode_enable (true ou false) | Activer/Désactiver le mode Hardcore. Lorsqu'il est actif toutes les fonctions comme le ralenti, les codes de triche et les savestates sont désactivées. L'expérience de jeu est alors identique au système original et l'avantage est que vos points sont doublés.                         |
| cheevos_username | Saisir votre nom d'utilisateur.                                       |
| cheevos_password | Saisir votre mot de passe.                                            |






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

