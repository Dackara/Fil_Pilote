# Fil_Pilote
Carte de Gestion des Fil Pilote de chauffage, conçus pour être monté sur la carte [PVBRAIN 2.0](https://github.com/Bandit-17/PVBRAIN)
- Possibilité d'utiliser plusieur carte, voir de jumeler deux carte ensemble en n'utilisant qu'un seul i2c extender **SX1509** via un système de pontage.
- Chaque carte parmet de contrôler jusqu'a 4 zones de chauffage en 6 ordres.
- Deux entrées de phase sont disponible par carte pour permettre le montage en Triphasé.
- La carte est utilisable en monophasé ou triphasé :
  - En Monophasé : Une seul phase par carte, dans ce cas, faire un pontage sur **PH2**
  - En Triphasé : deux phase par carte, jumelage de deux cartes pour obtenir 3x2 ou (2x2 + 1x4)
  - Possible aussi pour des montages moins courant d'avoir une phase sur réseau ENEDIS-EDF et une phase sur Solaire.
- En option, un module **TIC** (**T**élé **I**nformation **C**lient) pour communiquer avec les Compteur Linky est disponble.
