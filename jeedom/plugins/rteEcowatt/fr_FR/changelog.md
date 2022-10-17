<img align="right" src="../images/rteEcowatt_icon.png" width="100">

# Rte Ecowatt - Plugin pour Jeedom

Plugin utilisant l'API Rte.

## Changelog

>*Remarque : en cas de mise à jour non listée ici, c'est que celle-ci ne comporte que des changements mineurs du type documentation ou corrections de bugs mineurs.*

### 17/10/2022
- Création d'un cron pour récupération des données chez Rte. Le cron minute avec le choix de la minute est supprimé dans la configuration du plugin. La minute à laquelle les données seront récupérées, est visible dans le Moteur des tâches sur la ligne où la Classe de la tâche est rteEcowatt et la Fonction pullDataEcowatt.
- Le mode démo est maintenant déplacé dans l'équipement. Cela vous permet de créer un nouvel équipement en mode démo pour tester les scénarios utilisant les commandes de cet équipement. Le mode démo ne nécessite pas de compte Rte. Les données sont fournies avec le plugin.
- Correction de la commande "Timestamp de la prochaine alerte" et "Valeur prochaine alerte". Ces commandes peuvent être des déclencheurs de scénario.
- Correction de la template. Ajout de marges. Remplacement de la punaise du niveau de l'alerte de l'heure actuelle.
- Nettoyage des sources


### 14/10/2022 01:09
- Version minimum pour l'installation: 4.1
- Ajout des images png du site monecowatt dans le répertoire plugins/rteEcowatt/core/template/images pour une utilisation future ou pour vos virtuels.

### 12/10/2022
- Ajout des commandes "Valeur prochaine alerte" et "Timestamp de la prochaine alerte". Ajout sur la template.
- Ajout de la commande "Données horaires Json". Cette commande ne doit pas être historisée. Les données contenues sont trop volumineuses.
- Suppression des espaces début et fin de chaine sur l'IDclient/IDsecret
- Correction marges sur la template.
- Suppression des appels setlocale et strftime

L'équipement doit être sauvé pour que ces nouvelles commandes soient créées.

### 11/10/2022
- Version initiale.


[Retour à la documentation du plugin](index.md)
