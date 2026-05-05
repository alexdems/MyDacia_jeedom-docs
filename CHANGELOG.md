# Changelog (public)

Toutes les modifications notables visibles pour les utilisateurs sont documentées ici.

## [1.4.0] - 2026-05-05

### Nouvelles fonctionnalités
- **Commandes adaptées au type de véhicule** : lors de la découverte, le plugin détecte automatiquement si le véhicule est électrique, hybride ou thermique. Les commandes non pertinentes sont masquées (ex. : *Batterie*, *Prise*, *Charge* restent cachées sur un thermique ; *Autonomie carburant* est cachée sur un électrique).

### Améliorations
- **Synchronisation jusqu'à 5× plus rapide** : les 5 appels API par véhicule (batterie, cockpit, HVAC, position, mode de charge) sont désormais exécutés en parallèle au lieu de l'être séquentiellement. Testé en production : 4 véhicules synchronisés en ~2 secondes.
- **Réessai automatique** : si un appel API échoue pour une raison réseau transitoire, le plugin retente automatiquement une fois avant de signaler l'erreur.
- **Page de configuration encore plus rapide** : suppression des appels réseau supplémentaires déclenchés à chaque sauvegarde d'équipement.
- **Stabilité** : correction d'une erreur rare au chargement si un véhicule n'avait pas d'image associée dans l'API.
- **Détection hybride améliorée** : les véhicules full-hybrid (ex. Dacia Bigster HEV) sont correctement classifiés via le champ `engineEnergyType` de l'API.

### Validé en production avec les véhicules suivants
| Modèle | Type | Résultat |
|---|---|---|
| Dacia Spring (×2) | Électrique | ✅ Batterie, autonomie, position |
| Dacia Bigster HEV | Hybride full | ✅ Cockpit + position (battery endpoint non supporté, normal) |
| Dacia Duster Diesel | Thermique | ✅ Privacy mode détecté, warnings propres |

---

## [1.3.0] - 2026-05-04

### Nouvelles fonctionnalités
- **Commande Rafraîchir** sur chaque véhicule : permet de déclencher une mise à jour immédiate des données depuis l'interface Jeedom sans attendre la synchro automatique.
- **Commande `Autonomie carburant`** (kms, historisée) : remonte l'autonomie restante pour les véhicules thermiques et hybrides.
- **Commande `Carburant restant`** (litres, historisée) : remonte la quantité de carburant dans le réservoir pour les véhicules thermiques et hybrides.

### Améliorations
- **Logs visibles dans Jeedom** (`Analyse > Logs > MyDACIA`) : les logs du plugin étaient écrits dans un fichier invisible par l'interface Jeedom. Désormais toutes les étapes clés (connexion, synchronisation, erreurs) sont correctement tracées.
- **Synchronisation automatique toutes les 5 minutes** : la tâche planifiée est maintenant correctement enregistrée dans Jeedom. Elle est visible dans `Réglages > Système > Tâches cron`.
- **Erreurs API** (véhicule thermique sur un endpoint électrique, données absentes) : affichées en niveau *Warning* dans les logs au lieu d'être silencieuses, avec un message explicatif.
- **Page de configuration** : chargement nettement plus rapide (suppression d'appels réseau bloquants au chargement).
- Migration automatique des nouvelles commandes sur les équipements existants : aucune action manuelle requise après la mise à jour.

---

## [1.2.2]

- Corrections mineures.

---

## [1.2.1]

- Précisions documentation :
  - données remontées selon le véhicule et l'API,
  - exemple Dacia Spring (températures parfois absentes),
  - latence API et bonnes pratiques de cadence des commandes.

## [1.2.0]

- Suppression des commandes Lock/Unlock.

## [1.1.0]

- Support de deux comptes MyDacia.
