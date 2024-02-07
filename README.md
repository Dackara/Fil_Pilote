[![Static Badge](https://img.shields.io/badge/Realease-v1.0-blue?style=plastic)](https://github.com/Dackara/Fil_Pilote)
[![Static Badge](https://img.shields.io/badge/License-Beerware-yellow?style=plastic)](https://fr.wikipedia.org/wiki/Beerware)
[![Static Badge](https://img.shields.io/badge/Donate-ko--fi_%E2%99%A5-pink?logo=kofi&style=plastic)](https://ko-fi.com/dackara)
[![Static Badge](https://img.shields.io/badge/Sponsor-On_Github-darkgreen?logo=github&logoColor=lightgrey&style=plastic)](https://github.com/sponsors/Dackara)

![alt text](../main/Image/Photo/IMG_3848.JPG)

# Fil_Pilote
> [!IMPORTANT]
> Carte de **Gestion Centralisé** des `Fil Pilote` de chauffage.
> 
> Design conçus pour être [monté](../main/Image/Exemple/PVBRAIN2_and_Fil_Pilote.png) sur la carte [![Static Badge](https://img.shields.io/badge/PvBrain-v2.0-black?style=social&logo=quasar)](https://github.com/SeByDocKy/pvbrain2) développé par [![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17) et [![Static Badge](https://img.shields.io/badge/SeByDocKy-black?logo=git&style=flat)](https://github.com/SeByDocKy) de la chaine [![Static Badge](https://img.shields.io/badge/Youtube-e--2--nomy-black?style=social&logo=youtube)](https://www.youtube.com/@e2nomy).

> [!NOTE]
> La carte `Fil Pilote` est néanmoins totalement utilisable sans la carte [![Static Badge](https://img.shields.io/badge/PvBrain-v2.0-black?style=social&logo=quasar)](https://github.com/SeByDocKy/pvbrain2) (le hardware fonctionne avec n'importe quel ESP32 / ESP8266, ou tout autre système compatible **i2c**).
>
> L'intérêt est que les trous de fixation des deux carte correspondent. Cela permet de les imbriquer l'une sur l'autre, tout en profitant de l'[esp32](https://amzn.to/3RCapBQ) déjà présent sur le PvBrain.
> 
> Montage sur le [![Static Badge](https://img.shields.io/badge/PvBrain-v1.0-black?style=social&logo=quasar)](https://github.com/Bandit-17/PVBRAIN) également [possible](../main/Image/Exemple/PVBRAIN1_and_Fil_Pilote.png).

> [!TIP]
> Développé pour [![Static Badge](https://img.shields.io/badge/ESPHome-_-black?logo=esphome&style=social)](https://esphome.io).
> 
> Automatisable sous [![Static Badge](https://img.shields.io/badge/Home_Assistant-_-black?logo=homeassistant&style=social)](http://homeassistant.io) très simplement en suivant par exemple ce tuto sur [![Static Badge](https://img.shields.io/badge/HACF-_-black?logo=homebridge&style=social)](https://hacf.fr/blog/confort-gestion-chauffage/).

## Ce que permet la carte :
### Contrôler jusqu'à 4 zones de chauffage par carte :
 > - Une seule carte permet de contrôler jusqu'à 4 zones de chauffage en 6 ordres (plusieurs chauffages peuvent être câblés dans une même "zone").
 > - Possibilité d'utiliser plusieurs cartes, de jumeler deux cartes ensemble en n'utilisant qu'un seul i2c extender [SX1509](https://amzn.to/3vddUae) (via un système de pontage) et un seul [esp32](https://amzn.to/3RCapBQ).
 > - Deux entrées de phase sont disponible par carte pour permettre le montage en Triphasé.
 > - Son design permet de réduire le coût de fabrication des PCB pour ceux qui souhaitent utiliser plus de 4 zones ou l'utiliser en Triphasé.
### Utilisation en Monophasé ou Triphasé :
 > - En Monophasé : Une seule phase par carte, dans ce cas, faire le pontage sur **PH2** comme indiqué au verso de la carte.
 > - En Triphasé : deux phases par carte, jumelage de deux cartes pour obtenir `3x2` ou `2x2 + 1x4`. (Le signal **230V** envoyé au `Fil Pilote` doit provenir de la même `Phase` que l'alimentation du chauffage piloté !)
 > - Possible aussi pour des montages moins courant d'avoir une phase sur `réseau ENEDIS-EDF` et une phase sur `système Solaire`.
### En option :
 > - Un module **`TIC`** { **T**<sub>_élé_</sub> **I**<sub>_nformation_</sub> **C**<sub>_lient_</sub> } pour communiquer avec les **Compteurs Linky** est disponble.

## Le code ESPHome :
Le code est simplifié pour la modification via `packages:` et `substitutions:`. 

Tout se passe dans le fichier [fil_pilote.yaml](../main/Software_esphome/fil_pilote.yaml) présent à la racine.

L'intégralité des fichiers présents dans [ce répertoire](../main/Software_esphome) est nécessaire à son bon fonctionnement.

## La carte :
- Fichier **Gerber** et **BOM** : [Dossier Hardware](../main/Hardware)

| Face avant                | Face arrière              |
| :-----------------------: | :-----------------------: |
| ![alt text](../main/Image/TopSide.png) | ![alt text](../main/Image/BottomSide.png) |
| __Vue 3D__                | __Circuit__               |
| ![alt text](../main/Image/3D_View.png) | ![alt text](../main/Image/Circuit.png) |
| __Schematic Fil Pilote__  | __Schematic TIC__         |
| ![alt text](../main/Image/SchematicFP.png) | ![alt text](../main/Image/SchematicTIC.png) |

### Fonctionnement du Fil Pilote :
- Principe de fonctionnement en [image](../Image/Exemple/Signal_fil_pilote.png).
- Démonstration du fonctionnement des 6 ordres en [image](../Image/Exemple/Fil_pilote_demo.png).

### Crédit :
- Schéma électronique : [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara) & ![Static Badge](https://img.shields.io/badge/Luc-black?logo=git&style=flat)
- Designe PCB : [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara) & [![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17)
- Code esphome : [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)

## Impression 3D :
[Fichier 3D](../main/Hardware/3D_Print) à imprimer pour montage de la carte sur rail DIN (tableau électrique).
| Face avant                | Face arrière              |
| :-----------------------: | :-----------------------: |
| ![alt text](../main/Hardware/3D_Print/3D_front.png) | ![alt text](../main/Hardware/3D_Print/3D_back.png) |
