# Changelog (public)

Toutes les modifications notables visibles pour les utilisateurs sont documentées ici.

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
