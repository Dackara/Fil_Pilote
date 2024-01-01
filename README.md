`/!\ Projet en cours de réalisation /!\
Quelques test sont encore necessaire /!\`
# Fil_Pilote
Carte de Gestion Centralisé des `Fil Pilote` de chauffage, conçus pour être monté sur la carte [PVBRAIN 2.0](https://github.com/Bandit-17/PVBRAIN) dévellopé par [Bandit-17](https://github.com/Bandit-17) [SeByDocKy](https://github.com/SeByDocKy) de la chaine Youtube [e-2-nomy](https://www.youtube.com/@e2nomy).

Dévellopé pour [ESPHome](http://esphome.io).

Automatisable sous [HA](http://homeassistant.io) très simplement en suivant par exemple ce tuto sur [HACF](https://hacf.fr/blog/confort-gestion-chauffage/).

### Ce que permet la carte :
- Controler jusqu'a 4 zone de chauffage par carte.
  - Une seul carte parmet de contrôler jusqu'a 4 zones de chauffage en 6 ordres (plusieurs chauffage peuvent être cablé dans une même "zone").
  - Possibilité d'utiliser plusieur carte, de jumeler deux carte ensemble en n'utilisant qu'un seul i2c extender [SX1509](https://amzn.to/3vddUae) (via un système de pontage) et une seul [esp32](https://amzn.to/3RCapBQ).
  - Deux entrées de phase sont disponible par carte pour permettre le montage en Triphasé.
- Utilisable en Monophasé ou Triphasé :
  - En Monophasé : Une seul phase par carte, dans ce cas, faire un pontage sur **PH2**
  - En Triphasé : deux phase par carte, jumelage de deux cartes pour obtenir `3x2` ou `2x2 + 1x4`. (Le signal **230V** envoyé au `Fil Pilote` doit provenir de la même `Phase` que l'allimentation du chauffage piloté !)
  - Possible aussi pour des montages moins courant d'avoir une phase sur `réseau ENEDIS-EDF` et une phase sur `système Solaire`.
- En option, un module **TIC** (**T**élé **I**nformation **C**lient) pour communiquer avec les Compteur Linky est disponble.

## Le code ESPHome :
Le code est simplifié pour la modification via `packages:` et `substitutions:`. Tout ce passe dans le fichier [Main](https://github.com/Dackara/Fil_Pilote/blob/main/esphome/fil-pilote.yaml).

L'intégralité des fichier présent de [ce répertoire](https://github.com/Dackara/Fil_Pilote/tree/main/esphome) est necessaire à son bon fonctionnement.

## Schema de principe :
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Schematic.png)

## La carte :
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Circuit.png)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/TopSide.png)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/BottomSide.png)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/3D_View.png)

## Fonctionnement du Fil Pilote :
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Signal_fil_pilote.png)

### Si vous aimez mon travail et souhaitez me soutenir :

[![alt text](https://assets-global.website-files.com/5c14e387dab576fe667689cf/64f1a9ddd0246590df69ea15_kofi_long_button_dark%25402x-p-500.png)](https://ko-fi.com/dackara)
