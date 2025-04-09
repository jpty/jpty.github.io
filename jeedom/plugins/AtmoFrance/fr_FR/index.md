<img align="right" src="../images/AtmoFrance_icon.png" width="100">

# Atmo France, Pollens - Plugin pour Jeedom

Plugin utilisant l'API d'Atmo France pour afficher les niveaux de pollens.

### 1. Présentation
Le plugin *Atmo France* pour Jeedom permet de récupérer automatiquement les données des pollens pour une commune donnée, en s'appuyant sur le code postal.

### 2. Pré-requis
- Jeedom v4 ou supérieure.
- Connexion Internet active (le plugin interroge une API externe).

### 3. Installation
- Depuis le Market Jeedom, rechercher le plugin "AtmoFrance".
- Installer le plugin et activer-le.

### 4. Configuration de l'équipement
#### a. Création de l'équipement
- Aller dans *Plugins > Météo > AtmoFrance*.
- Ajouter un nouvel équipement.

#### b. Paramètres principaux
- **Nom** : nom de l’équipement.
- **Objet parent** : pièce ou zone où est utilisé l’équipement.

#### c. Code postal & sélection de commune
- Saisir un code postal dans le champ prévu.
- Cliquer sur l’icône loupe ou appuyer sur Entrée pour lancer la recherche.
  - Si **une seule commune** est trouvée, elle est automatiquement sélectionnée.
  - Si **plusieurs communes** existent pour ce code postal, une modale de sélection s’ouvre.
    - Utilisez les flèches, la souris ou un double-clic pour sélectionner.
    - La touche Échap permet d'annuler.

#### d. Résultat
- Le champ **codeZone** se remplit automatiquement au format : `Nom commune (INSEE,EPCI)`.
- Une bordure rouge ou un message d'erreur apparaît si le code postal est invalide.

#### e. Fonctionnement
- Le plugin interroge un fichier PHP (via AJAX) qui retourne les communes correspondant au code postal.
- Le champ texte gère la validation avec un feedback visuel (✅ ou ❌).
- Le champ `codeZone` est utilisé pour les appels API futurs liés à la qualité de l'air.

#### f. Cas particuliers / erreurs
- Si aucune commune n’est trouvée : un message d’erreur s’affiche.
- Si le code postal contient autre chose que 5 chiffres : erreur immédiate.
- Une seule commune = sélection automatique sans affichage de la modale.

#### g. Astuces ou limitations
- Le champ de sélection de commune fonctionne **sans champ caché** ni `setTimeout`, pour plus de fiabilité.
- La roulette souris ne permet pas la sélection, mais le survol met en évidence l’élément pointé.

#### h. FAQ configuration
**Q : Le champ "Communes (INSEE,EPCI)" reste vide ?**
> Vérifiez que le code postal est correct et que vous avez validé la sélection si une modale s'est affichée.

**Q : Peut-on saisir manuellement la commune ?**
> Oui, si vous connaissez le code INSEE de votre commune, le champ Communes (INSEE,EPCI)` peut etre saisi manuellement. Il suffit de respecter le format du champ. C'est au minimum (codeInsee,codeEPCI) 

**Q : Et si l’EPCI n'existe pas pour cette commune ?**
> Il sera remplacé par `----` dans le champ final.

## TODO la doc de l'utilisation.

## Note sur les commandes "Json"
Les fonction statiques  getJsonInfo($cmdId, $request) et extractValueFromJsonTxt($cmdValue, $request) sont fournies pour vous permettre d'extraire des valeurs des commandes Json.
Le paramètre $request est un JsonPath simplifié identique à celui du plugin officiel script

  [Changelog](changelog.md)
