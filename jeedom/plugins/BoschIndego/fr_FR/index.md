<img align="right" src="../images/BoschIndego_icon.png" width="100">
# Bosch Indego - Plugin pour Jeedom

Commande et surveillance des robots tondeuse Bosch Indego Connect.

## Information importante.
22/07/2024 Plugin supprimé

## Configuration

Après installation du plugin, il vous suffit de l’activer.
Il apparaitra alors dans le menu *Plugins > Objets connectés*

- Renseignez le nom d'utilisateur et le mot de passe de connexion au site Bosch avec l'app mobile.
- Sauvegardez et cliquez sur le bouton Tester connexion.
- Copiez le numéro de série qui apparait sous Connexion OK.
- Fermez la fenêtre de test de connexion, et collez le numéro de série dans le champ Numéros de série.
- Sauvegardez la configuration du plugin.

<img src="../images/ConfigurationPlugin.PNG" width="550px">

## Utilisation

Ajoutez un équipement, renseignez les différents champs et sélectionnez un numéro de série. Sauvegardez. L'équipement est maintenant opérationnel et doit apparaitre sur votre tableau de bord.

Ci-dessous le rendu sur le tableau de bord avec les commandes réparties sur un virtuel et le plugin.

<img src="../images/BoschIndego_screenshot.PNG" width="550px">
Le plugin virtuel ne permet plus d'afficher la carte. Celle-ci doit rester sur la tuile principale du plugin.

## Précisions sur le fonctionnement

En mode Tonte manuelle, au lancement de l'action Tondre, un daemon de surveillance de l'avancement de la tonte démarre et s'arrêtera 2 minutes après le retour de la tondeuse sur la station et la fin de la charge de la batterie.

En mode Tonte programmée, la date/heure de la prochaine tonte est récupérée par le plugin. Une entrée cron est créée pour lancer le daemon de surveillance au début de la tonte. En cas de modification de l'heure de tonte dans l'appli Bosch Indego, il faut cliquer sur l'icone en haut à droite de la tuile pour synchroniser les données. 

Les actions créées par le plugin sont mow, pause, returntodock, refresh, cronSetEnableOn et cronSetEnableOff. Les 2 dernières actions sont pour l'activation de la surveillance de la tonte.

## Remerciements
- A [**fle**](https://community.jeedom.com/u/fle/summary) pour les scripts et le widget qui m'ont servi de base pour ce plugin.
- A zazaz-de pour la description de l'API Bosch indego disponible [**ici**](https://github.com/zazaz-de/iot-device-bosch-indego-controller/blob/master/PROTOCOL.md)

[Changelog](changelog.md)
