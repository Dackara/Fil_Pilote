![Static Badge](https://img.shields.io/badge/Work_In_Progress-Projet_en_cours_de_r%C3%A9alisation-red?logo=adblock&logoColor=red&style=plastic)

![Static Badge](https://img.shields.io/badge/Realease-Beta-blue?style=plastic)
[![Static Badge](https://img.shields.io/badge/License-Beerware-yellow?style=plastic)](https://fr.wikipedia.org/wiki/Beerware)
[![Static Badge](https://img.shields.io/badge/Donate-ko--fi_%E2%99%A5-pink?logo=kofi&style=plastic)](https://ko-fi.com/dackara)
[![Static Badge](https://img.shields.io/badge/Sponsor-On_Github-darkgreen?logo=github&logoColor=lightgrey&style=plastic)](https://github.com/sponsors/Dackara)

# Fil_Pilote
> [!IMPORTANT]
> Carte de **Gestion Centralisé** des `Fil Pilote` de chauffage.
> 
> Design conçus pour être [monté](https://github.com/Dackara/Fil_Pilote/blob/main/Image/PVBRAIN2_and_Fil_Pilote.png) sur la carte [![Static Badge](https://img.shields.io/badge/PvBrain-v2.0-black?style=social&logo=quasar)](https://github.com/SeByDocKy/pvbrain2) développé par [![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17) et [![Static Badge](https://img.shields.io/badge/SeByDocKy-black?logo=git&style=flat)](https://github.com/SeByDocKy) de la chaine [![Static Badge](https://img.shields.io/badge/Youtube-e--2--nomy-black?style=social&logo=youtube)](https://www.youtube.com/@e2nomy).

> [!NOTE]
> La carte `Fil Pilote` est néanmoins totalement utilisable sans la carte [![Static Badge](https://img.shields.io/badge/PvBrain-v2.0-black?style=social&logo=quasar)](https://github.com/SeByDocKy/pvbrain2) (le hardware fonctionne avec nimporte quel ESP32 / ESP8266, ou tout autre système compatible **i2c**).
>
> L'intéret est que les trous de fixation des deux carte correspondent. Cela permet de les imbriquer l'une sur l'autre, tout en profitant de l'[esp32](https://amzn.to/3RCapBQ) déja présent sur le PvBrain.
> 
> Montage sur le [PVbrain v1](https://github.com/Bandit-17/PVBRAIN) également [possible](https://github.com/Dackara/Fil_Pilote/blob/main/Image/PVBRAIN1_and_Fil_Pilote.png).

> [!TIP]
> Développé pour [![Static Badge](https://img.shields.io/badge/ESPHome-_-black?logo=esphome&style=social)](https://esphome.io).
> 
> Automatisable sous [![Static Badge](https://img.shields.io/badge/Home_Assistant-_-black?logo=homeassistant&style=social)](http://homeassistant.io) très simplement en suivant par exemple ce tuto sur [![Static Badge](https://img.shields.io/badge/HACF-_-black?logo=homebridge&style=social)](https://hacf.fr/blog/confort-gestion-chauffage/).

## Ce que permet la carte :
### Controler jusqu'à 4 zones de chauffage par carte :
 > - Une seule carte permet de contrôler jusqu'à 4 zones de chauffage en 6 ordres (plusieurs chauffages peuvent être câblés dans une même "zone").
 > - Possibilité d'utiliser plusieurs cartes, de jumeler deux cartes ensemble en n'utilisant qu'un seul i2c extender [SX1509](https://amzn.to/3vddUae) (via un système de pontage) et un seul [esp32](https://amzn.to/3RCapBQ).
 > - Deux entrées de phase sont disponible par carte pour permettre le montage en Triphasé.
 > - Son design permet de réduire le coût de fabrication des PCB pour ceux qui souhaitent utiliser plus de 4 zones ou l'utiliser en Triphasé.
### Être utilisé en Monophasé ou Triphasé :
 > - En Monophasé : Une seule phase par carte, dans ce cas, faire le pontage sur **PH2** comme indiqué au verso de la carte.
 > - En Triphasé : deux phases par carte, jumelage de deux cartes pour obtenir `3x2` ou `2x2 + 1x4`. (Le signal **230V** envoyé au `Fil Pilote` doit provenir de la même `Phase` que l'allimentation du chauffage piloté !)
 > - Possible aussi pour des montages moins courant d'avoir une phase sur `réseau ENEDIS-EDF` et une phase sur `système Solaire`.
### En option :
 > - Un module **`TIC`** { **T**<sub>_élé_</sub> **I**<sub>_nformation_</sub> **C**<sub>_lient_</sub> } pour communiquer avec les **Compteurs Linky** est disponble.

## Le code ESPHome :
Le code est simplifié pour la modification via `packages:` et `substitutions:`. 

Tout se passe dans le fichier [fil_pilote.yaml](https://github.com/Dackara/Fil_Pilote/blob/main/Software_esphome/fil_pilote.yaml) présent à la racine.

L'intégralité des fichiers présents de [ce répertoire](https://github.com/Dackara/Fil_Pilote/tree/main/Software_esphome) est nécessaire à son bon fonctionnement.

## Schema de principe :
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Schematic.png)

## La carte :
- **Gerber** files : `arrive dès que définitivement validé`
- **B**ill **O**f **M**aterials : [BOM files](https://github.com/Dackara/Fil_Pilote/blob/main/Hardware/BOM_Fil_Pilote_Mini_v1_2024-01-01.csv)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Circuit.png)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/TopSide.png)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/BottomSide.png)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/3D_View.png)

### Fonctionnement du Fil Pilote :
- Principe de fonctionnement en [image](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Signal_fil_pilote.png).
- Démonstration du fonctionnement des 6 ordres en [image](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Fil_pilote_demo.png).

### Crédit :
- Schéma électronique : `@Dackara` & `@Luc`
- Designe PCB : `@Dackara` & `@Bandit-17`
- Code esphome : `@Dackara`
