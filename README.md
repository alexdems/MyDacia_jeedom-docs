# MyDacia pour Jeedom — Documentation publique

Cette documentation publique accompagne le plugin **MyDacia** pour Jeedom.

Le code source principal est maintenu dans un depot prive ; ce depot public contient :

- la documentation utilisateur,
- les informations de publication Market,
- le changelog public,
- le support utilisateur.

## Ce que fait le plugin

Le plugin connecte Jeedom au compte **MyDacia / API Renault-Dacia Kamereon** pour :

- remonter les informations vehicule (batterie, autonomie, position, kilometrage, statut de charge, etc.),
- piloter des actions (HVAC ON/OFF, Charge ON/OFF),
- gerer jusqu'a deux comptes MyDacia.

## Important : disponibilite des donnees

Les valeurs affichees dependent de ce que l'API expose pour le modele.  
Certaines donnees peuvent etre absentes sur certains vehicules (ex. temperatures interieure/exterieure sur certaines Spring).

## Important : latence et cadence des commandes

- Les donnees transitent par l'API MyDacia : une latence existe.
- Eviter d'envoyer trop de commandes dans un laps de temps court.
- Usage recommande : scenarios espaces (par ex. heures pleines / heures creuses pour la charge).

## Liens

- Changelog : `CHANGELOG.md`
- Support : `SUPPORT.md`
