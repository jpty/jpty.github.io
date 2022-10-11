<img align="right" src="../images/rteEcowatt_icon.png" width="100">

# Rte Ecowatt - Plugin pour Jeedom

Plugin utilisant l'API Rte Ecowatt pour extraire les données.

## Prérequis chez Rte

Le plugin nécessite un compte sur le site [**data.rte-france**](https://data.rte-france.com) 
- A partir de votre compte, il faut ensuite créer une application.
- Dans la rubrique Consommation, cliquez sur "Découvrir l'API" de la tuile Ecowatt.
- Cliquez alors sur "Abonnez-vous à l'API"
- Rattachez ensuite cette API à votre application.
- En cliquant sur le bouton "Copier en base 64", vos ID client et ID secret encodés en base 64 pourront être collés dans la configuration du plugin. 

## Configuration

Après installation du plugin, il vous suffit de l’activer.
Il apparaitra alors dans le menu *Plugins > Energie*
- Collez l'ID client et l'ID secret dans la configuration.
- Choisissez la minute de récupération des données chez Rte.

## Utilisation
Ajoutez un équipement.
Les commandes créées sont: TODO

## Précisions sur le fonctionnement

- Chaque heure, le plugin met à jour l'ensemble des commandes avec les données récupérées précédemment.
- Le plugin interroge Rte une fois par heure à la minute définie dans la configuration du plugin.


[Changelog](changelog.md)

