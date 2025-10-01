# cop-adaptation

## Description

Ce dépôt contient un plugin personnalisé Grist (Custom Widget) permettant de visualiser les fiches d'adaptation COP et de les exporter facilement (impression unitaire ou en lot). Il s'intègre à une table Grist pour afficher, parcourir et imprimer les fiches à partir des données en temps réel.

## Fonctionnalités

L'application permet de :

- **Consulter les priorités d'adaptation COP** : Visualisation des priorités identifiées pour l'adaptation au changement climatique
- **Navigation entre les fiches** : Parcourir les fiches avec des boutons précédent/suivant
- **Affichage détaillé** : Chaque fiche présente :
  - Le contexte territorial (région, département, effets du changement climatique)
  - La description de la priorité et son niveau
  - Les parties prenantes et le soutien disponible
  - Les freins identifiés (régionaux et nationaux)
  - Le budget anticipé
- **Export/Impression** : Imprimer une fiche individuelle ou toutes les fiches en un clic
- **Intégration Grist** : Connexion directe avec la base Grist via l'API plugin pour un accès en temps réel aux données

## Utilisation

L'application est conçue pour être intégrée dans Grist et permet aux utilisateurs de naviguer facilement à travers les différentes actions d'adaptation au changement climatique, facilitant ainsi la planification et le suivi des initiatives territoriales.

### Intégration dans Grist (Custom Widget)

1. Héberger le fichier `grist/fiche-adaptation.html` (ex. via Pages, serveur statique ou URL interne).
2. Dans votre document Grist, ajouter un widget « Custom URL » relié à la table contenant les fiches.
3. Renseigner l'URL publique du fichier hébergé.
4. Donner au widget l'accès « read table » (défini par le code) pour lire les enregistrements.

Le widget détecte automatiquement les enregistrements de la table et permet :
- de naviguer fiche par fiche,
- d'imprimer la fiche courante,
- d'imprimer toutes les fiches en lot.

### Champs de données attendus (extraits)

Le widget lit notamment les colonnes suivantes si elles existent :
- `Intitule_de_la_priorite_identifiee`
- `Region`, `Departement`
- `Effet_du_changement_climatique`, `Sensibilite`, `Levier`
- `Niveau_de_priorite`, `Description_de_la_priorite`, `Date_de_fin_prevue_pour_l_action`
- `Criteres_de_reussites_yc_indic_de_performance_2`
- `Identification_des_parties_prenantes_a_mobiliser_si_deja_disponible_`
- `Porteur_d_aide_ingenierie_si_identifie_`, `Porteur_d_aide_financement_si_identifie_`
- `Freins_a_lever_Remontees_regionales`, `Freins_a_lever_Remontees_nationales`
- `Budget_total_anticipe_evoque_a_date_`