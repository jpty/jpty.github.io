<img align="right" src="../images/AtmoFrance_icon.png" width="100">

#  Atmo France, Pollens et Qualité de l'air - Plugin pour Jeedom

Plugin utilisant l'API d'Atmo France pour afficher les niveaux de pollens.

## Changelog

>*Remarque : en cas de mise à jour non listée ici, c'est que celle-ci ne comporte que des changements mineurs du type documentation ou corrections de bugs mineurs.*

***


### 22/04/2025 beta
- Pré-renseignement du code postal avec celui de la configuration de Jeedom.
- Vérification du couple Insee/Epci
- Amélioration formattage des logs

***
### 16/04/2025 beta ( Demande passage en stable )
- Interrogation de l'API à la création ou à la modification de la localisation d'un équipement. Le refresh manuel de l'équipement devient inutile.
- La durée de vie du jeton est de 24h. C'est encodé en base64 dans le jeton.
- Correction de la perte du code Insee en édition d'un équipement existant. Sélection du code Insee dans une modale quand il existe plusieurs code Inseee correspondant au code postal.
- La recherche du code Insee peut se faire dans le champ code Postal par Enter ou un click sur la loupe à droite.
- Ajout du type d'équipement "Indice Atmo" (aqi) avec son widget "codeAQI". Voir les paramètres optionnels de ce widget.
- Le widget par défaut "codePollens" contient la LED ( taille modifiée, couleur niveau Faible plus foncé, pas de cercle autour du rond central). Voir les paramètres optionnels de ce widget.
- L'autre type de widget Pollens est nommé "codePollensBranch". Il y a un manque de visibilté sur fond clair. Voir les paramètres optionnels de ce widget.
- Widgets identiques pour le mobile.
- Mise à jour des équipements existants lors de la mise à jour du plugin.

***  
### 10/04/2025
- Synchro API à partir de 15h (16h auparavant)
- A la création/modification d'un équipement, l'équipement n'est plus mis à jour automatiquement. Il faut cliquer sur le bouton refresh. Ca générait trop de requêtes à l'API lors de la mise au point de l'apparence de l'équipement.
- Ajout des widgets pour le mobile.
- Nouveau widget pour l'affichage des couleurs des pollens.

### 06/04/2025
- Version initiale.

[Retour à la documentation du plugin](index.md)
