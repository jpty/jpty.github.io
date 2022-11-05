<img align="right" src="../images/rteEcowatt_icon.png" width="100">

# Rte Ecowatt - Plugin pour Jeedom

Plugin utilisant l'API Rte.

## Changelog

<!-- >*Remarque : en cas de mise à jour non listée ici, c'est que celle-ci ne comporte que des changements mineurs du type documentation ou corrections de bugs mineurs.*
-->

### 05/11/2022 Beta
- Correction mineures sur Tempo et EJP.

### 03/11/2022 18:57:02 Beta

#### EDF EJP
- Ajout d'un nouveau type d'équipement: EJP La source utilisée est le site Web d'EDF. 3 commandes: Aujourd'hui, demain et EJP restants.
- Valeurs possibles pour Aujourd'hui et demain : EJP, NOT_EJP, UNDEFINED et OUT_OF_PERIOD.
- Il suffit de créer un équipement de ce type. Je n'ai testé qu'avec les jours non EJP actuels.
- Selon le site EDF, la mise à jour des données est effectuée quotidiennement vers 15h30, cependant des contraintes d'exploitation peuvent la retarder jusqu'à 5h du matin du jour EJP. Le plugin interroge EDF à 1h(heure de fin d'un jour EJP), 6h(avant le début d'un jour EJP, 12h, 16h (heure où demain passe dans le plugin de Non défini à EJP ou Non EJP. Si c'est Non EJP ce n'est pas définitif), 17h, 19h et 22h. 
- Par sécurité et avant l'arrivée des jours EJP, abonnez-vous aux notifications EDF. Ca serait dommage de payer 0.9418€/kWh au lieu de 0,1283€ sans être prévenu. (Tarifs du 1er aout 2022 )


#### Tempo
- Correction des commandes Aujourdhui timestamp et Demain timestamp qui n'étaient pas créées en numérique.
- Correction du message en bas de la tuile


### 31/10/2022 17:12:21 Beta
#### Ecowatt
- L'heure actuelle est maintenant toujours sur le jour 0 même entre 0h et 1h
- Possibilité de choisir un template pour l'affichage des données. Si le template custom était utilisé, il sera nécessaire de le resélectionner dans la configuration de l'équipement.
- Ajout template halloween avec le graphique des alertes du site monecowatt.fr. Merci phpvarious pour l'idée. Le nom vient de la couleur où ce template est apparu sur community. J'ai préféré mettre en avant la couleur de l'heure actuelle.
- Ajout template 'alerte heure+jours+heures' et 'alerte heure+heures' pour une représentation différente des données.
#### Tempo
- Ajout de 2 nouvelles commandes 'Aujourdhui timestamp' et 'Demain timestamp' pour horodater aujourdhui et demain.
- Correction sur le passage heure été vers heure d'hiver.
- Réduction du nombre d'appel de synchronisation. Normalement il n'y en a plus qu'un seul par jour (si RTE répond).
#### -
### 26/10/2022 09:59:56
Passage du plugin en version stable sur le market. La version est identique à la beta de ce matin.

### 26/10/2022 beta
- Support partiel de la template Legacy. Couleur des donuts.
- Ajout de 2 paramètres optionnels sur l'équipement: innerSizeAM et innerSizePM permettant de changer l'épaisseur du donut. Les valeurs peuvent être en pourcentage du diamètre extérieur ou en pixel. La valeur par défaut est 75%. La valeur 0% permet d'obtenir un camembert. Si la valeur est trop grande, le graphique n'est pas affiché.
- Possibilité d'utiliser une template custom. Si le fichier plugins/rteEcowatt/core/template/dashboard/custom.rte_ecowatt.html existe, il est utilisé à la place du fichier rte_ecowatt.html. Avant d'installer cette version, si vous avez modifié la template fournie avec le plugin et que vous désirez conserver vos modifications, copiez la en custom.rte_ecowatt.html
- La catégorie Energie peut être déselectionnée.
- En mode demo, les jours varient du 3 au 5 juin
- Possibilité d'afficher dataHoursJson dans la template. Commence à l'heure actuelle et durée paramétrable dans la configuration de l'équipement
- Correction du cron de recupération des données Ecowatt. Pas de synchro si le 1er équipement était en démo.
- Suppression de l'appel à RTE pour Tempo à 0h. (Transfert de tomorrow en today)

### 17/10/2022 beta
- Création d'un cron pour récupération des données chez Rte. Le cron minute avec le choix de la minute est supprimé dans la configuration du plugin. La minute à laquelle les données seront récupérées, est visible dans le Moteur des tâches sur la ligne où la Classe de la tâche est rteEcowatt et la Fonction pullDataEcowatt.
- Le mode démo est maintenant déplacé dans l'équipement. Cela vous permet de créer un nouvel équipement en mode démo pour tester les scénarios utilisant les commandes de cet équipement. Le mode démo ne nécessite pas de compte Rte. Les données sont fournies avec le plugin.
- Correction de la commande "Timestamp de la prochaine alerte" et "Valeur prochaine alerte". Ces commandes peuvent être des déclencheurs de scénario.
- Correction de la template. Ajout de marges. Remplacement de la punaise du niveau de l'alerte de l'heure actuelle.
- Nettoyage des sources


### 14/10/2022 01:09 beta
- Version minimum pour l'installation: 4.1
- Ajout des images png du site monecowatt dans le répertoire plugins/rteEcowatt/core/template/images pour une utilisation future ou pour vos virtuels.

### 12/10/2022 beta
- Ajout des commandes "Valeur prochaine alerte" et "Timestamp de la prochaine alerte". Ajout sur la template.
- Ajout de la commande "Données horaires Json". Cette commande ne doit pas être historisée. Les données contenues sont trop volumineuses.
- Suppression des espaces début et fin de chaine sur l'IDclient/IDsecret
- Correction marges sur la template.
- Suppression des appels setlocale et strftime

L'équipement doit être sauvé pour que ces nouvelles commandes soient créées.

### 11/10/2022 beta
- Version initiale.


[Retour à la documentation du plugin](index.md)
