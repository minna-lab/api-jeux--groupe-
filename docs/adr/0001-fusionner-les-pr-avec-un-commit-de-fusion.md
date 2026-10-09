# 1. Fusionner les pull requests avec un commit de fusion

- **Date** : 2026-10-06
- **Statut** : Approuvée

## Contexte

Le projet est réalisé en équipe et les modifications sont développées sur des branches séparées avant d'être intégrées dans `main` par des pull requests.

Pour la PR des statistiques, notre groupe a utilisé la méthode de fusion avec un commit de fusion.

Nous devons définir une stratégie de fusion claire afin de conserver un historique compréhensible et de savoir comment intégrer les prochaines pull requests.

## Options envisagées

### 1. Create a merge commit

**Pour :**
- conserve les commits de la branche ;
- garde une trace explicite de la fusion de la pull request ;
- permet de visualiser l'historique des différentes branches.

**Contre :**
- l'historique peut devenir plus chargé ;
- plusieurs commits intermédiaires peuvent rester visibles dans `main`.

### 2. Squash and merge

**Pour :**
- regroupe tous les commits de la branche en un seul commit ;
- produit un historique de `main` plus simple et plus lisible.

**Contre :**
- les commits individuels de la branche disparaissent de l'historique de `main` ;
- une partie du détail du travail réalisé est perdue.

### 3. Rebase and merge

**Pour :**
- conserve les commits individuels ;
- produit un historique linéaire sans commit de fusion supplémentaire.

**Contre :**
- ne matérialise pas clairement la fusion de la pull request dans l'historique ;
- peut rendre l'origine des différents développements moins évidente.

## Décision

Nous retenons la méthode **Create a merge commit**.

Cette méthode correspond à celle utilisée pour la pull request des statistiques. Elle permet de conserver les différents commits réalisés sur la branche ainsi qu'une trace explicite de la fusion de la pull request dans `main`.

## Conséquences

- Les commits réalisés pendant le développement restent visibles dans l'historique.
- La fusion de chaque pull request reste clairement identifiable.
- L'historique de `main` peut devenir plus chargé lorsque de nombreuses branches sont fusionnées.
- Cette décision pourra être revue si l'historique devient difficile à lire ou si l'équipe souhaite privilégier un historique plus compact.

