<img align="right" src="../images/weatherForecast_icon.png" width="100">

# Weather Forecast - Plugin pour Jeedom

Plugin utilisant OpenWeatherMap ou weatherApi pour afficher les prévisions météo.

## Configuration du plugin

Après installation du plugin, il vous suffit de l’activer.
Il apparaitra alors dans le menu *Plugins > Météo*
Selon la source de données utilisée, il est nécessaire de posséder une clé API.

## Configuration pour l'utilisation de la source OpenWeatherMap

Si vous utilisiez le plugin officiel Jeedom weather d'avant avril 2024, vous avez déjà un compte OpenWeatherMap. Il vous suffit de récupérer la clé API à cette adresse : [**OpenWeatherMap.org**](https://home.openweathermap.org/api_keys) et de la coller dans la configuration du plugin.
Le plugin utilise les APIs gratuites "Current Weather Data" et "5 Day / 3 Hour Forecast".

### Utilisation
- Créez un équipement. 
- Choississez la source de données OpenWeatherMap.
- Renseignez les coordonnées GPS de la localisation désirée.
- Sélectionnez le template d'affichage. Icônes, Images ou Pas de template
  <img src="../images/TemplatesOwm.png">
  Sans template, seule la commande "Météo H0 - Json pour widget" est affichée. le widget Clock lui est affecté.
