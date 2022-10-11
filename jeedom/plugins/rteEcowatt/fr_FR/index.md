<img align="right" src="../images/rteEcowatt_icon.png" width="100">

# Rte Ecowatt - Plugin pour Jeedom

Plugin utilisant l'API Rte Ecowatt pour extraire les données.

## Prérequis chez Rte

Le plugin nécessite un compte sur le site [**data.rte-france**](https://data.rte-france.com) Cliquez sur "Se connecter" pour la création d'un nouveau compte ou l'utilisation d'un compte existant.
- Dans la rubrique Consommation, cliquez sur "Découvrir l'API" de la tuile Ecowatt.
- Cliquez alors sur "Abonnez-vous à l'API"
- Rattachez ensuite cette API à une application existante ou créez une nouvelle application.
- Dans la rubrique "Mes applications" cliquez sur votre application. En cliquant sur le bouton "Copier en base 64", vos ID client et ID secret encodés en base 64 pourront être collés dans la configuration du plugin. 

## Configuration

Après installation du plugin, il vous suffit de l’activer.
Il apparaitra alors dans le menu *Plugins > Energie*
- Collez l'ID client et l'ID secret encodés en base64 dans la configuration.

## Utilisation
Ajoutez un équipement.
Les commandes créées sont: TODO

## Précisions sur le fonctionnement

- Chaque heure, le plugin met à jour l'ensemble des commandes avec les données récupérées précédemment.
- Le plugin interroge Rte une fois par heure à la minute définie dans la configuration du plugin.


[Changelog](changelog.md)

