<img align="right" src="../images/weatherForecast_icon.png" width="100">

#  Weather Forecast - Plugin pour Jeedom

Plugin utilisant OpenWeatherMap ou weatherApi pour afficher les prévisions météo.

## Changelog

>*Remarque : en cas de mise à jour non listée ici, c'est que celle-ci ne comporte que des changements mineurs du type documentation ou corrections de bugs mineurs.*

### 24/02/2025 beta
- Ajout des commandes indice UV de l'heure courante et de l'indice UV max du jour avec la source weatherApi.
- Récupération et affichage des alertes Météo de Meteoalarm.org (38 pays). CAP (Common Alerting Protocol) est utilisé. Les commandes ajoutées sont MeteoalarmAlertsJson, MeteoalarmColorMax, MeteoalarmColorMaxNow et MeteoalarmList
- Ajout de la function getInfoJson et extractValueFromJsonTxt permettant d'extraire des valeurs des commandes Json en utilisant un JsonPath simplifié.
- Possibilité de template custom pour les prévisions par jour. ( Si le fichier custom.forecast.html existe, il est utilisé en remplacement du fichier forecast.html fourni. )

***
### 09/02/2025 stable
- Publication de la version stable identique à la beta du 06/02
- Le changement de noms des widgets VigilanceWF et ClockWF nécessite qu'ils soient réaffectés aux commandes.
  
***
### 06/02/2025 beta
- Récupération et utilisation des 48x2 icônes de WeatherApi par le template Icônes.
- Utilisation des 58x2 icônes de la police Wi pour la source OpenweatherMap par le template Icônes.
- Fin de l'utilisation des 8 icônes fa fas via les classes meteo du core. Le template Images et le widget clockWF utilisent encore les 10 images png.
- Affichage possible des graphiques d'historique en fond de tuile.
- Changement des noms des widgets Vigilance en VigilanceWF et Clock en ClockWF en raison de conflit possible entre plugins ou le core. Un seul widget Vigilance est listé par l'interface de sélection de widget Jeedom alors qu'il peut être défini plusieurs fois. Ex: meteofrance::Vigilance ou weatherForecast::Vigilance.
- Correction sur les fuseaux horaires.
- Ebauche de la traduction du plugin.
***
### 05/01/2025 stable et beta
- Les versions stable et beta sont identiques.
- Widget Clock retaillable.
 ***
### 29/12/2024 beta
- Ajout de la sélection du fuseau horaire dans la configuration de l’équipement.
- Ajout des commandes sunriseTs et sunsetTs.
- Passage des icones du widget Vigilance en images svg.
***
### 24/12/2024 beta
- Ajout des vigilances météo de Météo France. Elles apparaissent dés qu'un département est choisi dans la configuration de l'équipement.
- Ajout du widget Vigilance pour les afficher. Il est affecté à la commande Vigilance - Json
***
### 19/12/2024 stable et beta
- Corrections mineures dans widget Clock
- Ajout thème EasterEgg.
- Modifications des images pour le market Jeedom.
- Paramètre optionnel clockTimezone possible même avec la météo.
***
### 18/12/2024 stable et beta
- Ajout de captures d'écran pour affichage sur le market.
- Changement du nom du plugin en Weather Forecast au lieu de OpenWeatherMap, WeatherApi
***  
### 17/12/2024 stable
- Première version stable.
***
### 08/12/2024 beta
- Ajout de paramètres optionnels dans le widget Clock afin de pouvoir choisir la police de l'horloge et positionner les textes.
- Ajout du paramètre optionnel clockTheme et des thémes Digital et KrisKringle
*** 
### 24/11/2024 beta
- Ajout de paramètres optionnels dans le widget Clock afin de pouvoir afficher les secondes sur une seule ligne.
***
### 22/11/2024 beta
- Corrections diverses. ( Vitesse des rafales, nom de commande trop long ... )
- Suppression des fichiers de polices weather-icons non utilisés. Il reste 9 fichiers. 
- Utilisation des coordonnées de la Configuration Jeedom lors de la création d'un nouvel équipemement.
***
### 13/11/2024
- Version initiale.

[Retour à la documentation du plugin](index.md)
