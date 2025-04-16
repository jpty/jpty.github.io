<img align="right" src="../images/AtmoFrance_icon.png" width="100">

# Atmo France, Pollens et Qualité de l'air - Plugin pour Jeedom

Le plugin *Atmo France* pour Jeedom permet de récupérer automatiquement les données des pollens pour une commune donnée, en s'appuyant sur le code INSEE.
Source des données : Atmo France et les Associations agréées de surveillance de la qualité de l’air.(AASQA)


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
- Depuis le Market Jeedom, recherchez le plugin "AtmoFrance".
- Installez le plugin et activez-le.

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
#### 4-a. Création de l'équipement
- Allez dans *Plugins > Météo > AtmoFrance*.
- Ajoutez un nouvel équipement.

#### 4-b. Paramètres principaux
- **Nom** : nom de l’équipement.
- **Objet parent** : pièce ou zone où est utilisé l’équipement.

#### 4-c. Code postal & sélection de commune
- Saisissez un code postal dans le champ prévu.
- Cliquez sur l’icône loupe ou appuyer sur Entrée pour lancer la recherche.
  - Si **une seule commune** est trouvée, elle est automatiquement sélectionnée.
  - Si **plusieurs communes** existent pour ce code postal, une modale de sélection s’ouvre.
    - Utilisez les flèches, la souris ou un double-clic pour sélectionner.
    - La touche Échap permet d'annuler.

#### 4-d. Résultat
- Le champ **codeZone** se remplit automatiquement au format : `Nom commune (INSEE,EPCI)`.
- Une bordure rouge ou un message d'erreur apparaît si le code postal est invalide.

#### 4-e. Fonctionnement
- Le plugin interroge un fichier PHP (via AJAX) qui retourne les communes correspondant au code postal.
- Le champ texte gère la validation avec un feedback visuel (✅ ou ❌).
- Le champ `codeZone` est utilisé pour les appels API futurs liés à la qualité de l'air.

#### 4-f. Cas particuliers / erreurs
- Si aucune commune n’est trouvée : un message d’erreur s’affiche.
- Si le code postal contient autre chose que 5 chiffres : erreur immédiate.
- Une seule commune = sélection automatique sans affichage de la modale.

#### 4-g. Astuces ou limitations
- La roulette souris ne permet pas la sélection, mais le survol met en évidence l’élément pointé.

## 5. Principales commandes créées par le plugin

| ID commande   | Description                                                       |
|---------------|-------------------------------------------------------------------|
| **date_maj** | La date des données récupérées. |
| **code_zone** | Le code INSEE de la commune. |
| **lib_zone** | Le libellé de la commune. |
| **aasqa** | Le code de l'association. |
| **source** | Le libellé de l'association source des données. |

### Type d'équipement Pollens:

| ID commande   | Description                                                       |
|---------------|-------------------------------------------------------------------|
| **pollensJson** | Le résultat brut de la requête en Json sur 3 jours. |

Pour chaque jour Jx, le plugin crée aussi ces commandes avec x de 0 à 2.

| ID commande   | Description                                                       |
|---------------|-------------------------------------------------------------------|
| **pollens**Jx**Json** | Le résultat brut de la requête en Json du jour Jx. |
| **date_ech**Jx | La date du jour Jx. |
| **code_qual**Jx | Le code qualité générale du jour Jx. |

Puis pour chaque jour Jx et chaque pollen parmi ambr, arm, aul, boul, gram et oliv le plugin crée aussi ces commandes.

| ID commande   | Description                                                       |
|---------------|-------------------------------------------------------------------|
| **code_pollen**Jx | Le code du pollen pour le jour Jx. Les valeurs possible vont de 0 à 6. |

Les données pour les concentrations de ces pollens sont également disponibles, mais le plugin ne crée pas de commande.
### Type d'équipement indice ATMO

| ID commande   | Description                                                       |
|---------------|-------------------------------------------------------------------|
| **aqisJson** | Le résultat brut de la requête en Json sur 3 jours. |

| ID commande   | Description                                                       |
|---------------|-------------------------------------------------------------------|
| **aqi**Jx**Json** | Le résultat brut de la requête en Json du jour Jx. |
| **date_ech**Jx | La date du jour Jx. |
| **code_qual**Jx | Le code qualité générale du jour Jx. |

Puis pour chaque jour Jx et chaque aqi parmi no2, o3, so2, pm25 et pm10 le plugin crée aussi ces commandes.

| ID commande   | Description                                                       |
|---------------|-------------------------------------------------------------------|
| **code_aqi**Jx | Le code du pollen pour le jour Jx. Les valeurs possible vont de 0 à 6. |

#### 💡Note sur les commandes "Json" 
Les fonction statiques  getJsonInfo($cmdId, $request) et extractValueFromJsonTxt($cmdValue, $request) sont fournies pour vous permettre d'extraire des valeurs des commandes Json.
Le paramètre $request est un JsonPath simplifié identique à celui du plugin officiel script


## ❓6. FAQ
**Q : Lors de la configuration d'un équipement, le champ "Communes (INSEE,EPCI)" reste vide ?**
> Vérifiez que le code postal est correct et que vous avez validé la sélection si une modale s'est affichée.

**Q : Peut-on renseigner manuellement le champ "Communes (INSEE,EPCI)" ?**
> Oui, si vous connaissez le code INSEE de votre commune, le champ **codeZone** Communes (INSEE,EPCI)  peut etre saisi manuellement. Il suffit de respecter le format du champ. Les formats possibles sont: `codeInsee`, `codeInsee,codeEPCI`, `(codeInsee,codeEPCI)` ou `Nom_commune (codeInsee,codeEPCI)` 

**Q : Quand le plugin récupère-t-il les données chez Atmo France ?**
> Les données sont mises à jour chez Atmo France une fois par jour entre 12h et 15h. Le plugin va donc chercher les données à partir de 15h. Il le fait à une minute définie par le plugin sur votre Jeedom. Ceci afin de ne pas surcharger leur serveur avec les requêtes Jeedom en même temps. Il est toutefois possible de forcer la mise à jour d'un équipement en cliquant sur l'icône Refresh en haut à droite de sa tuile.

**Q : A la création ou lors de la modification du codeInsee d'un équipement, les données ne se mettent pas à jour**
> Il est nécessaire de cliquer sur l'icône Refresh en haut à droite de sa tuile ou d'attendre que le cron passe(fréquence horaire).


  [Changelog](changelog.md)
