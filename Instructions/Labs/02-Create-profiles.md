---
lab:
  title: "Labo\_2\_: créer des profils client unifiés"
---

# Labo 2 : créer des profils client unifiés
Dans ce labo, vous allez apprendre à effectuer les opérations suivantes :
- Fusionner les données de vos sources de données brutes dans un profil client
- Sélectionner une clé primaire 
- Créer des règles de correspondance
- Définir des index de recherche et de filtre et des activités

Votre objectif vise à découvrir le nombre de profils client uniques que **Contoso Retail** possède au niveau des diverses sources de données.

## Exercice 1 : unifier vos données
### Tâche 1 : mapper les contacts avec les types de données courants
1. Connectez-vous à **Customer Insights - Data**.

1. Dans le menu de navigation de gauche, développez **Données** et sélectionnez **Unifier**. Sélectionnez **Prise en main**.

1. Choisissez **Sélectionner des tables et des colonnes**.

1. Sélectionnez les tables qui représentent le profil client : **Contacts (e-commerce)** et **Clients (fidélité)**. Sélectionnez **Appliquer**.

1. Les mappages de votre table source avec les types de modèle standard vous sont maintenant présentés. Vous pouvez examiner les types dans le tableau.

1. Vous devez choisir une **« Clé primaire »** pour chaque entité ingérée. La clé primaire doit être une référence unique. Pour les **contacts d’e-commence**, sélectionnez **ContactId** comme clé primaire.

1. Les données de **contacts d’e-commerce** contiennent une colonne nommée **Abonné aux e-mails** qui sera mappée avec un type incorrect, **Identity.Service.Email**, en raison du nom. Ouvrez la liste déroulante de cette colonne et sélectionnez l’option vide (rien/vierge). Si nous ne le faisons pas, le comportement par défaut du système consiste à fusionner ce champ avec le champ **EMail**, ce que nous ne voulons pas.

1. Sélectionnez **Fidélité des clients** sous **Tables** et définissez **LoyaltyID** comme clé primaire.

1. Sélectionnez **Enregistrer les colonnes sources** dans le coin supérieur gauche.

1. Sélectionnez **Suivant**, puis à nouveau **Suivant** pour ignorer la vérification des doublons et passer à l’étape **Règles de correspondance**.

### Tâche 2 : spécifier l’ordre de correspondance
Pour la phase suivante, vous devez sélectionner l’ordre dans lequel fusionner les profils. Vous pourrez fusionner des attributs pour vous assurer que les profils unifiés sont complets, ainsi que la priorité des sources à utiliser pour ces attributs.

1. Vous devez sélectionner la source de profil la plus complète ou précise comme **source principale (première)**. Vérifiez que **Contacts : e-commerce** est la source principale (première).

1. Vérifiez que **Clients : fidélité** est la deuxième source dans la liste. 

1. Vérifiez que l’option **Inclure tous les enregistrements** est activée pour les deux sources de données.

### Tâche 3 : créer une règle de correspondance
1. Il existe un indicateur d’avertissement sur la ligne **Clients : fidélité**. Sélectionnez **+ Ajouter une règle**.

1. Ajoutez la première condition en utilisant **FullName** :
    - Pour la table **Contacts : e-commerce**, sélectionnez le champ **FullName**.
    - Pour la table **Clients : fidélité**, sélectionnez le champ **FullName**.
    - Laissez la liste déroulante **Normaliser** vide.
    - Définissez le **niveau de précision** sur **De base**.
    - Définissez la **valeur de précision** sur **Exacte** à l’aide du curseur.
    - Entrez le nom **FullName, Email** pour le **nom de la règle**.

1. Ajoutez une deuxième condition pour l’adresse e-mail en sélectionnant **+ Ajouter**, puis sélectionnez **Ajouter une condition**.
    - Pour la table **Contacts : e-commerce**, sélectionnez le champ **Email**.
    - Pour la table **Clients : fidélité**, sélectionnez le champ **Email**.
    - Laissez la liste déroulante **Normaliser** vide.
    - Définissez le **niveau de précision** sur **De base**.
    - Définissez la **valeur de précision** sur **Exacte**.

1. Cliquez sur **Terminé**.

1. Cliquez sur **Suivant**.

1. Sur l’écran **Vue des données unifiées**, nous n’apporterons aucune modification. Sélectionnez **Suivant** pour passer à l’écran de révision.

1. Dans l’écran **Révision**, sélectionnez **Créer des profils client**. Customer Insights met désormais en correspondance les données client de toutes vos sources d’information client pour identifier le nombre de profils client uniques que vous auriez en fonction de vos règles. La création des profils peut prendre un certain temps.

Félicitations ! Vous avez réussi à unifier des données à partir de plusieurs sources dans **Customer Insights** afin de créer un **profil client unifié** qui permet d’obtenir des informations sur toute votre clientèle.

## Exercice 2 : configurer des index de recherche et de filtre et des activités
Dans cet exercice, nous allons configurer des critères **de recherche et de filtre** pour permettre aux utilisateurs de Customer Insights de rechercher des profils client unifiés. Ensuite, nous allons configurer des activités.

### Tâche 1 : configurer l’index Rechercher des colonnes et filtrer 
1. Dans **Customer Insights**, sélectionnez **Clients** dans le menu de navigation de gauche.

1. Sélectionnez **Index Rechercher et Filtrer**. Certains champs sont déjà ajoutés par défaut. Sélectionnez **+Ajouter** depuis la barre d’outils.

1. Sélectionnez **CustomerId, FirstName, LastName, FullName, DateOfBirth, EMail, PostCode, ContactId (eCommerce_Contacts) et LoyaltyId** (s’ils ne sont pas déjà sélectionnés). Désélectionnez tous les autres champs cochés. Sélectionnez **Appliquer**.

1. Cliquez sur **Enregistrer**.

1. Sélectionnez **Exécuter**.

1. Dans **Customer Insights**, sélectionnez **Clients** dans le menu de navigation de gauche. Un ensemble de cartes client représentant les **profils unifiés** doit vous être présenté. Vous pouvez développer des cartes pour en savoir plus sur le client ou trier les cartes par différents champs. Essayez ces fonctionnalités en sélectionnant **Développer des cartes** et **Trier par** dans la barre d’outils.

1. Vous pouvez utiliser **Rechercher des clients** pour rechercher des attributs de texte relatifs aux profils client unifiés. (Par exemple, la recherche de « 1 » effectue une recherche sur tous les attributs de texte et renvoie des correspondances et des correspondances partielles.)

### Tâche 2 : créer des activités
1. Dans **Customer Insights**, développez **Données > Activités** dans le menu de navigation de gauche et sélectionnez **+ Configurer des activités**.

1. Cliquez sur **Sélectionner les tables**.

1. Sélectionnez les tables **Achats : e-commerce** et **Achats : PDV** , puis sélectionnez **Ajouter**.

1. Pour **Achats : e-commerce**, configurez comme suit :
    - Définissez le **type d’activité** sur **SalesOrder**.
    - Définissez la **clé primaire** sur **PurchaseId**.

1. Pour **Achats : PDV**, configurez comme suit :
    - Définissez le **type d’activité** sur **SalesOrder**.
    - Définissez la **clé primaire** sur **PurchaseId**.

1. Cliquez sur **Suivant**.
   
1. Configurez **E-commerce : achats** comme suit :
    - Entrez **OnlinePurchase** pour le **nom de l’activité**.
    - Renseignez les champs suivants (pour tous les champs non mentionnés, laissez vide) :
        - **Timestamp** : PurchasedOn
        - **Activité de l’événement** : ActivityTypeDisplay
        - **Détails supplémentaires** : Subject
        - **Afficher cette activité dans la chronologie de votre profil client ?** Oui
        - **Icône** : sélectionnez l’icône de panier d’achat.
        - **Définir les types de champs à mapper pour les attributs de votre activité ?** Oui, et configurez comme suit :
            - **ID commande client** : PurchaseID
            - **Date de la commande** : PurchasedOn
            - **Montant des ventes** : TotalPrice

1. Configurez **PDV : achats** comme suit :
    - Entrez **PoSPurchase** pour le **nom de l’activité**.
    - Renseignez les champs suivants (pour tous les champs non mentionnés, laissez vide) :
        - **Timestamp** : PurchasedOn
        - **Activité de l’événement** : ActivityTypeDisplay
        - **Détails supplémentaires** : Subject
        - **Afficher cette activité dans la chronologie de votre profil client ?** Oui
        - **Icône** : sélectionnez l’icône de panier d’achat.
        - **Définir les types de champs à mapper pour les attributs de votre activité ?** Oui, et configurez comme suit :
            - **ID commande client** : PurchaseID
            - **Date de la commande** : PurchasedOn
            - **Montant des ventes** : TotalPrice

1. Cliquez sur **Suivant**.

1. Dans l’écran **Configurer les relations de l’activité**, alors que **E-commerce : achats** est sélectionné, sélectionnez **+ Ajouter une relation**.

1. Dans le volet **Ajouter un chemin de relation**, définissez les valeurs suivantes :
    - **Clé étrangère** : ContactId
    - **Pour le nom de table** : Contacts : e-commerce
    - **Nom de la relation** : eCommPurchasesToContacts
    - Sélectionnez **Appliquer**.

1. Sélectionnez **PDV : achats**. Sélectionnez **+ Ajouter une relation**.

1. Dans le volet **Ajouter un chemin de relation**, définissez les valeurs suivantes :
    - **Clé étrangère** : LoyaltyId
    - **Pour le nom de table** : Clients : fidélité
    - **Nom de la relation** : PoSPurchasesToLoyalty
    - Sélectionnez **Appliquer**.

1. Cliquez sur **Suivant**.

1. Sélectionnez **Créer des activités**.

1. Attendez que les **activités** s’actualisent et s’unifient.



