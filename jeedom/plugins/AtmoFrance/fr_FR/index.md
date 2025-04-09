<img align="right" src="../images/AtmoFrance_icon.png" width="100">

# Atmo France, Pollens - Plugin pour Jeedom

Plugin utilisant l'API d'Atmo France pour afficher les niveaux de pollens.

Le plugin *Atmo France* pour Jeedom permet de récupérer automatiquement les données des pollens pour une commune donnée, en s'appuyant sur le code postal.

## 🧰 1. Pré-requis
- Jeedom v4 ou supérieure.
- Connexion Internet active (le plugin interroge une API externe).
- ### 🔑 Création d’un compte API
  
Avant de configurer le plugin dans Jeedom, vous devez créer un compte API sur le site d’Atmo France :

1. Rendez-vous sur le lien suivant pour faire une demande de création de compte :  
   👉 [https://admindata.atmo-france.org/inscription-api](https://admindata.atmo-france.org/inscription-api)

   La validation par Atmo France est manuelle.
3. Une fois la demande validée, vous recevrez un e-mail d’**Atmo France - Agrégateur** contenant un lien pour initialiser votre mot de passe.

4. Cliquez sur ce lien et définissez votre mot de passe. Attention: pas de " ou de ' dans le mot de passe.

5. Conservez précieusement **l’identifiant** (ce n'est pas votre e-mail) et **le mot de passe**, car ils seront utilisés dans Jeedom.

## 📦 2. Installation
- Depuis le Market Jeedom, rechercher le plugin "AtmoFrance".
- Installer le plugin et activer-le.

## 🛠️ 3. Configuration du plugin

### ⚙️ Paramétrage dans Jeedom

Une fois le compte API actif :

- Accédez à la page de configuration du plugin AtmoFrance dans Jeedom.
- Renseignez les informations d’identification dans les champs suivants :

| Champ         | Description                                                       |
|---------------|-------------------------------------------------------------------|
| **Identifiant** | L’identifiant fourni par Atmo France. |
| **Mot de passe** | Le mot de passe que vous avez défini via le lien reçu par mail.         |


## 🛠️ 4. Configuration de l'équipement
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

## ❓5. FAQ configuration
**Q : Le champ "Communes (INSEE,EPCI)" reste vide ?**
> Vérifiez que le code postal est correct et que vous avez validé la sélection si une modale s'est affichée.

**Q : Peut-on saisir manuellement la commune ?**
> Oui, si vous connaissez le code INSEE de votre commune, le champ **codeZone** Communes (INSEE,EPCI)  peut etre saisi manuellement. Il suffit de respecter le format du champ. C'est au minimum (codeInsee,codeEPCI) 

**Q : Et si l’EPCI n'existe pas pour cette commune ?**
> Il sera remplacé par `----` dans le champ final.

## TODO la doc de l'utilisation.

## 💡Note sur les commandes "Json"
Les fonction statiques  getJsonInfo($cmdId, $request) et extractValueFromJsonTxt($cmdValue, $request) sont fournies pour vous permettre d'extraire des valeurs des commandes Json.
Le paramètre $request est un JsonPath simplifié identique à celui du plugin officiel script

  [Changelog](changelog.md)
