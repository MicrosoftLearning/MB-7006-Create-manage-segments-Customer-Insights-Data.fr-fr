---
lab:
  title: "Labo\_1\_: ingérer des jeux de données"
---

# Labo 1 : ingérer des jeux de données
Dans ce labo, vous allez apprendre à effectuer les opérations suivantes :
- Intégrer plusieurs jeux de données à l’aide de PowerQuery
- Transformer les jeux de données et modifier les types de colonnes
- Surveiller le statut de l’import

Pour créer des segments, nous devons d’abord importer les données que nous utiliserons dans nos segments. Dans ce labo, nous importerons quelques jeux de données comme étape préalable pour unifier les données et construire nos segments.

## Exercice 1 : ingérer des sources de données
Pour ce projet guidé, vous devez importer différentes sources de données. Ces sources de données sont utilisées pour créer vos profils clients unifiés.

### Tâche 1 : ingérer les données client à partir d’une plateforme d’e-commerce
1. Dans **Insights clients - Données**, développez **Données** dans le menu de navigation de gauche et sélectionnez **Sources de données**.

1. Sélectionnez **+Ajouter une source de données**. Affichez les méthodes disponibles pour ingérer des données. Pour ce labo, choisissez **Microsoft Power Query** et nommez la source **eCommerce**, puis sélectionnez **Suivant**.

1. Vous obtiendrez une vue des sources de données **Power Query** que **Customer Insights** est en mesure d’ingérer. Notez les types de connecteurs disponibles. Sélectionnez le connecteur **Texte/CSV**.

1. Saisissez `https://aka.ms/CI-ILT/Contacts` pour **Chemin d’accès du fichier ou URL** et sélectionnez **Suivant**. Le chargement des données peut prendre plusieurs minutes.

1. Vous devriez maintenant voir les données de la source tabulées. Sélectionnez **Transformer les données** pour configurer les types de données et les formats des données que vous ingérez.

1. Vous noterez que l’en-tête de colonne apparaît dans la première ligne des données. Pour corriger ce problème, sélectionnez **Transformer > Utiliser la première ligne comme en-tête** dans l’onglet **Accueil** ou sélectionnez l’onglet **Transformer**, puis **Utiliser la première ligne comme en-tête**.

1. Comme nous avons ingéré des données à partir d’une source **Texte/CSV**, toutes les colonnes sont définies par défaut sur un **Type de données** « Texte ». Pour réussir l’ingestion et la modélisation des données, nous pouvons définir le type de données pour les colonnes non textuelles.

1. Pour modifier le type de données, sélectionnez l’icône **ABC** dans l’en-tête de chaque colonne. Mettez à jour le type de données de ces colonnes :
    - **DateOfBirth** : date
    - **CreatedOn** : date
    - **Income :** devise

1. Vérifiez que le champ **Nom** du volet **Paramètres de requête** est défini sur **Contacts**. Cliquez sur **Suivant**.

1. Sélectionnez **Actualiser manuellement**, puis sélectionnez **Enregistrer**.

Félicitations ! Vous avez maintenant créé votre première source de données avec un jeu de données ! Nous allons continuer à importer le jeu de données suivant dans la tâche suivante.

### Tâche 2 : ingérer les données client du programme de fidélité
1. Dans **Insights client**, développez **Données** dans le menu de gauche et sélectionnez **Sources de données**.

1. Sélectionnez **+Ajouter une source de données** et choisissez **Microsoft Power Query** comme méthode d’importation. Nommez la source **Fidélité**, puis sélectionnez **Suivant**.

1. Sélectionnez le connecteur **Texte/CSV**.

1. Saisissez `https://aka.ms/CI-ILT/LoyaltySchemeCustomers` pour **Chemin d’accès du fichier ou URL**, sélectionnez **Suivant** puis sélectionnez **Transformer les données**.

1. Comme précédemment, sélectionnez **Transformer**, puis **Utiliser la première ligne comme en-têtes**.

1. Mettez à jour le type de données de ces colonnes :
    - **DateOfBirth** : date
    - **RewardsPoints** : nombre entier
    - **CreatedOn** : date

1. Renommez cette requête en **Clients** dans le volet **Paramètres de requête** et sélectionnez **Suivant**.

1. Sélectionnez **Actualiser manuellement**, puis sélectionnez **Enregistrer**.

### Tâche 3 : ingérer des données client à partir des achats en point de vente
1. Dans **Insights clients**, développez **Données** dans le menu de navigation de gauche et sélectionnez **Sources de données**.

1. Sélectionnez **+ Ajouter une source de données**, choisissez **Microsoft Power Query** et nommez la source **PDV**, puis sélectionnez **Suivant**.

1. Sélectionnez le connecteur **Texte/CSV**.

1. Saisissez `https://aka.ms/CI-ILT/POSPurchases` pour **Chemin d’accès du fichier ou URL**. Sélectionnez **Suivant**, puis **Transformer les données**.

1. Comme précédemment, sélectionnez **Transformer**, puis **Utiliser la première ligne comme en-têtes**.

1. Mettez à jour le type de données de ces colonnes :
    - **PurchasedOn** : date
    - **TotalPrice** : devise
    - **RewardPointsAdded :** nombre entier

1. Dans le champ **Nom** du volet **Paramètres de requête**, renommez la requête en **Achats**.

1. Cliquez sur **Suivant**.

1. Choisissez **Actualiser manuellement** et sélectionnez **Enregistrer**.

### Tâche 4 : ingérer les données d’achat en ligne
1. Dans cette tâche, nous allons ingérer des données d’**achat en ligne**, représentant les achats effectués via le site web **Contoso Coffee**.

1. Dans **Insights client**, développez **Données** dans le menu de gauche et sélectionnez **Sources de données**. (Vérifiez que l’état de la source de données** eCommerce** indique **Réussite**.)

1. Sélectionnez le jeu de données **eCommerce** que vous avez créé dans la première tâche, puis sélectionnez **Modifier**. Si vos données sont toujours en cours d’actualisation, attendez que cette opération soit terminée avant de les modifier.

1. Cliquez sur **Suivant**. 

1. Une vue **Power Query** des données des **contacts e-commerce** que vous avez ingérées lors de la tâche 1 devrait s’afficher. Dans l’onglet **Accueil**, sélectionnez **Obtenir des données**.

1. Une vue des connecteurs de source de données que **Insights client** est capable d’ingérer s’affiche. Sélectionnez **Texte/CSV**.

1. Saisissez `https://aka.ms/CI-ILT/OnlinePurchases` pour **Chemin d’accès du fichier ou URL** et sélectionnez **Suivant**. Sélectionnez **Créer**.

1. Comme précédemment, sélectionnez **Transformer**, puis **Utiliser la première ligne comme en-têtes**.

1. Mettez à jour les types de données pour les colonnes suivantes :
    - **PurchasedOn** : date
    - **TotalPrice** : devise

1. Nommez cette requête **Achats**, puis sélectionnez **Enregistrer**.

**Important :** vous devrez attendre que le statut de toutes vos sources de données soit **Réussite** avant de pouvoir passer à l’exercice suivant.
