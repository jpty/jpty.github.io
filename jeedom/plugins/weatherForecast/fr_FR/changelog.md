<img align="right" src="../images/weatherForecast_icon.png" width="100">

#  Weather Forecast, CAP alerts - Plugin pour Jeedom

Plugin utilisant OpenWeatherMap.org ou weatherApi.com pour afficher les prévisions météo et meteoalarm.org ou meteofrance.com pour les alertes météo. les prévisions de pluie de Météo-France sont disponibles.

## Changelog

>*Remarque : en cas de mise à jour non listée ici, c'est que celle-ci ne comporte que des changements mineurs du type documentation ou corrections de bugs mineurs.*

***

### 06/06/2026 stable et beta
- Corrections mineures de la beta précédente.
- Publication de la version stable identique à la beta.
- La procédure de récupération de l'APPLICATION_ID pour les vigilances et la Météo des forêts sur le site de Météo France a été détaiilé https://community.jeedom.com/t/actualites-du-plugin-weather-forecast-cap-alerts/135292/19?u=jpty

### 02/06/2026 beta
- Avec les données du début de la saison, mise au point de la Météo des forêts. Cette année les serveurs MF semblent opérationnels. 
- Ebauche de la tarduction du plugin.
- Corrections et reformatage divers
- Changement de sous-type en numérique pour les commandes niveaux de pluie dans l'heure

### 16/05/2026 beta
- Ajout d'une dépendance php-intl permettant de formater les dates et nombres.
- Ajout des vigilances Météo des forêts. Il faut souscrire à cette API dans votre Application chez Meteo France. C'est une information saisonnière disponible uniquement de juin à septembre. En espérant que les serveurs MF soient opérationnels. Lors de mes premiers essais il y a 2 ans, une requete à MF sur 3 passait à la trappe pour cette API. Si c'est encore le cas, il suffira de décocher l'utilisation de cette API dans la configuration du plugin.
- Corrections et reformatage divers

### 02/05/2026 beta
- Possibilité d'utiliser l'API vigilance de Meteo France. Il faut pour cela renseigner APPLICATION_ID et cocher la case Utilisation API dans la configuration du plugin.
- Suppression des références au plugin meteofrance.
- Correction des templates mobile
- 7 jours de prévisions Meteo France
- Ajout des commandes uvMax par jour (4 premiers) pour MF

***

### 11/04/2026 stable et beta
- Corrections mineures de la beta précédente.
- Publication de la version stable identique à la beta.

### 01/04/2026 beta
- Ajout de Météo France comme source de données des prévisions météo.

***

### 07/03/2026 stable et beta
- Corrections mineures de la beta précédente.
- Publication de la version stable identique à la beta.

### 05/03/2026 beta
- Ajout des prévisions de pluie dans l'heure de Meteo France.
- Tri des commandes dans des onglets dans la configuration de l'équipement.
- Ajout du widget 1hRainWidget pour utilisation sur un design, sur une commande d'un virtuel ou sur un équipement weatherForecast sans template. La commande à représenter est : 1hRainForecastJson de l'onglet Json cmds.
- Intégration dans le template weatherForecast.html de la prévision de pluie dans l'heure.
- Correction de la sauvegarde des équipements à la mise à jour du plugin

### 17/04/2025 beta
- Corrections mineures typage des données.
- Copyright sur alarmes Meteoalarm
- Corrections du widget clockWF.
  - Séparateur décimales et séparateur des milliers selon la langue du navigateur.
  - Chargement possible des polices qui se trouvent dans le répertoire data/customTemplates/fonts. Les polices connues par le navigateur sont utilisables.
- Icones différentes sur les alertes Flood et Rain flood
- Ajout bouton Dupliquer pour copier un équipement existant.

***

### 02/03/2025 stable et beta
- Publication de la version stable identique à la beta.

### 25/02/2025 beta
- Ajout des commandes indice UV de l'heure courante et de l'indice UV max du jour avec la source weatherApi.
- Récupération et affichage des alertes Météo de Meteoalarm.org (38 pays ). CAP (Common Alerting Protocol) est utilisé. Les commandes ajoutées sont MeteoalarmAlertsJson, MeteoalarmColorMax, MeteoalarmColorMaxNow et MeteoalarmList
- Ajout de la function getInfoJson et extractValueFromJsonTxt permettant d'extraire des valeurs des commandes Json en utilisant un JsonPath simplifié.
- Possibilité de template custom pour les prévisions par jour. ( Si le fichier custom.forecast.html existe, il est utilisé en remplacement du fichier forecast.html fourni. )

***

### 09/02/2025 stable
- Publication de la version stable identique à la beta du 06/02
- Le changement de noms des widgets VigilanceWF et ClockWF nécessite qu'ils soient réaffectés aux commandes.
  
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

### 29/12/2024 beta
- Ajout de la sélection du fuseau horaire dans la configuration de l’équipement.
- Ajout des commandes sunriseTs et sunsetTs.
- Passage des icones du widget Vigilance en images svg.

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

### 08/12/2024 beta
- Ajout de paramètres optionnels dans le widget Clock afin de pouvoir choisir la police de l'horloge et positionner les textes.
- Ajout du paramètre optionnel clockTheme et des thémes Digital et KrisKringle
 
### 24/11/2024 beta
- Ajout de paramètres optionnels dans le widget Clock afin de pouvoir afficher les secondes sur une seule ligne.

### 22/11/2024 beta
- Corrections diverses. ( Vitesse des rafales, nom de commande trop long ... )
- Suppression des fichiers de polices weather-icons non utilisés. Il reste 9 fichiers. 
- Utilisation des coordonnées de la Configuration Jeedom lors de la création d'un nouvel équipemement.

***

### 13/11/2024
- Version initiale.

[Retour à la documentation du plugin](index.md)
