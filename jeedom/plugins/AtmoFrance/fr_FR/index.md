<img align="right" src="../images/AtmoFrance_icon.png" width="100">

# Weather Forecast, CAP alerts - Plugin pour Jeedom

Plugin utilisant OpenWeatherMap ou weatherApi pour afficher les prévisions météo.

## Configuration du plugin

Après installation du plugin, il vous suffit de l’activer.
Il apparaitra alors dans le menu *Plugins > Météo*.


### Utilisation
- Créez un équipement. 
- Renseignez le code postal et lancer la recherche des codes INSEE et EPCI
- S'il y a plusieurs communes avec le même code postal, choisissez une commune
- Sauvegardez l'équipement.

## TODO

## Les commandes "Json"
Les fonction statiques  getJsonInfo($cmdId, $request) et extractValueFromJsonTxt($cmdValue, $request) sont fournies pour vous permettre d'extraire des valeurs des commandes Json.
Le paramètre $request est un JsonPath simplifié identique à celui du plugin officiel script

  [Changelog](changelog.md)
