---
title: Jeedom | Plugin BoschIndego
description: Commande et surveillance des robots tondeuse Bosch Indego
---

<img align="right" src="../images/BoschIndego_icon.png" width="100">

# BoschIndego - Plugin pour Jeedom

Commande et surveillance des robots tondeuse Bosch Indego.

[Changelog](changelog.md)<br />

## Configuration du plugin BoschIndego

Après installation du plugin, il vous suffit de l’activer.
Il apparaitra alors dans le menu *Plugins > Objets connectés*
Dans la configuration du plugin, renseignez le nom d'utilisateur et le mot de passe de connexion au site Bosch. Sauvegardez et cliquez sur le bouton Tester connexion. Copiez le numéro de série qui apparait sous Connexion OK. Fermez la fenêtre de test de connexion, et collez le numéro de série dans le champ Numéros de série et sauvegardez la configuration du plugin.


{% include lightbox.html src="../images/ConfigurationPlugin.PNG" data="BoschIndego" title="Configuration" imgstyle="width:550px;display: block;margin: 0 auto;" %}

## Utilisation
En mode Tonte manuelle, au lancement de l'action Tondre, un daemon de surveillance de l'avancement de la tonte démarre et s'arrêtera 2 minutes après le retour de la tondeuse sur la station.

En mode Tonte programmée, la date/heure de la prochaine tonte est récupérée par le plugin. Une entrée cron est créée pour lancer le daemon de surveillance au début de la tonte. En cas de modification de l'heure de tonte, il faut cliquer sur l'icone en haut à droite de la tuile pour synchroniser les données. 

Les actions créées par le plugin sont mow, pause, returntodock, refresh, cronSetEnableOn et cronSetEnableOff. Les 2 dernières actions sont pour le daemon de surveillance de la tonte.

{% include lightbox.html src="../images/BoschIndego_screenshot.jpg" data="BoschIndego" title="Explorateur" imgstyle="width:550px;display: block;margin: 0 auto;" %}

## Remerciements
- A [**fle**](http://www.jeedom.com/forum/memberlist.php?mode=viewprofile&u=1461) pour les scripts et le widget qui m'ont servi de base pour ce plugin.
- A zazaz-de pour la description de l'API Bosch indego disponible [**ici**](https://github.com/zazaz-de/iot-device-bosch-indego-controller/blob/master/PROTOCOL.md)

## Installation
- Depuis mon github, téléchargez le fichier BoschIndego.zip.
- Dans Jeedom après avoir activé les sources de type fichier pour les mises à jour, ajoutez un plugin avec le type de source Fichier. L'ID logique du plugin doit être renseigné à BoschIndego. Puis cliquez sur le bouton Envoyer un plugin et sélectionnez le zip téléchargé précédemment.
{% include lightbox.html src="../images/InstallPluginBoschIndego.PNG" data="BoschIndego" title="Explorateur" imgstyle="width:550px;display: block;margin: 0 auto;" %}
- Cliquez sur Enregistrer Le plugin est maintenant installé.
- Activez le plugin
- Le plugin apparait dans le menu Plugins sous Objets connectés.
- Ajoutez un équipement, renseignez les différents champs et sélectionnez le numéro de série. Sauvegardez. L'équipement est maintenant opérationnel et doit apparaitre sur votre tableau de bord. Redimensionnez la tuile.
