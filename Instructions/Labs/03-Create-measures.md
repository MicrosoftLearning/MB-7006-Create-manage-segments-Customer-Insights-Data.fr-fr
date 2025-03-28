---
lab:
  title: "Labo\_3\_: créer des mesures"
---

# Labo 3 : créer des mesures

Dans ce labo, vous allez apprendre à effectuer les opérations suivantes :
- Définir des mesures d’entreprise pour suivre les performances et la santé de l’entreprise
- Définir des mesures client pour obtenir des informations sur les clients individuels

## Exercice 1 : définir des mesures et des attributs
### Tâche 1 : valeur moyenne des achats en magasin
Dans cette première tâche, nous allons créer une mesure pour définir la valeur moyenne de tous les achats en magasin effectués chez **Contoso Coffee**.

1. Développez **Insights** et sélectionnez **Mesures** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau** dans la barre d’outils, puis sélectionnez **Créer vos propres mesures**.

1. En regard de l’en-tête **Mesure sans titre**, sélectionnez **Modifier les détails**.

1. Définissez le **nom** sur **Valeur moyenne des achats en magasin ($)** et sélectionnez **Terminé**.

1. Changez le **type de mesure** de **Client** vers **Entreprise**.

1. En regard de **Calcul 1**, sélectionnez **Modifier le nom**.

1. Définissez le **nom** sur **Valeur moyenne des achats en magasin ($)**.

1. Vérifiez que le **nom de l’attribut de sortie** est défini sur **AverageStorePurchaseValue**.

1. Cliquez sur **Terminé**.

1. Sous le calcul **Valeur moyenne des achats en magasin ($)**, choisissez **Moyenne** dans la liste déroulante **Sélectionner une fonction**.

1. Sélectionnez **+ Ajouter un attribut**, développez **Achats : PDV**, puis sélectionnez **TotalPrice**.

1. Sélectionnez **Ajouter**.

1. Sélectionnez le bouton **Exécuter** pour terminer votre mesure.

    Dans cette tâche, nous allons créer une mesure pour définir la valeur moyenne de tous les achats effectués en ligne auprès de **Contoso Coffee**.

1. Sélectionnez **Insights > Mesures** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau > Créer vos propres mesures** à partir de la barre d’outils.

1. En regard de l’en-tête **Mesure sans titre**, sélectionnez **Modifier les détails**.

1. Définissez le **nom** sur **Valeur moyenne des achats en ligne ($)** et sélectionnez **Terminé**.

1. Changez le **type de mesure** de **Client** vers **Entreprise**.

1. En regard de **Calcul 1**, sélectionnez **Modifier le nom**.

1. Définissez le **nom** sur **Valeur moyenne des achats en ligne ($)**.

1. Vérifiez que le **nom de l’attribut de sortie** est défini sur **AverageWebPurchaseValue**.

1. Cliquez sur **Terminé**.

1. Sous le calcul **Valeur moyenne des achats en ligne ($)**, choisissez **Moyenne** dans la liste déroulante **Sélectionner une fonction**.

1. Sélectionnez **+ Ajouter un attribut**, développez **Achats : e-commerce**, puis sélectionnez **TotalPrice**.

1. Sélectionnez **Ajouter**.

1. Sélectionnez le bouton **Exécuter** pour terminer votre mesure.

### Tâche 2 : définir des mesures client
Nous aurons besoin de deux mesures client qui peuvent être utilisées pour calculer un attribut client. Nous allons créer une mesure pour déterminer les dépenses totales des clients sur les **achats en ligne** et une mesure pour déterminer leurs dépenses totales sur les **achats en magasin**. Une fois ces mesures créées, nous pourrons créer un attribut client pour les mettre en commun.

Dans cette tâche, nous allons créer une mesure pour définir le total de tous les achats effectués en magasin.

1. Sélectionnez **Insights > Mesures** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau > Créer vos propres mesures** à partir de la barre d’outils.

1. En regard de l’en-tête **Mesure sans titre**, sélectionnez **Modifier les détails**.

1. Définissez le **nom** sur **Total des dépenses en magasin**, puis sélectionnez **Terminé**.

1. Sous le calcul **Total des dépenses en magasin**, choisissez **Somme** dans la liste déroulante **Sélectionner une fonction**.

1. Sélectionnez **+ Ajouter un attribut**, développez **Achats : PDV**, sélectionnez **TotalPrice**, puis sélectionnez **Ajouter**.

1. Pour configurer le calcul des mesures, sélectionnez **Dimensions (1)**.

1. Sélectionnez **Modifier les dimensions**.

1. Développez **Achats : PDV**, sélectionnez **LoyaltyId**, puis sélectionnez **Terminé**.

1. Sélectionnez **Appliquer**.

1. Sélectionnez le bouton **Exécuter** pour terminer votre mesure. Si vous rencontrez une erreur et que vous devez choisir le **chemin de la relation**, sélectionnez **PoS_Purchases > Client** et sélectionnez le bouton **Exécuter** pour terminer.

    Ensuite, nous allons créer une mesure pour définir le total de tous les achats effectués en ligne.

1. Sélectionnez **Insights > Mesures** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau > Créer vos propres mesures** à partir de la barre d’outils.

1. En regard de l’en-tête **Mesure sans titre**, sélectionnez **Modifier les détails**.

1. Définissez le **nom** sur **Total des dépenses en ligne**, puis sélectionnez **Terminé**.

1. Sous le calcul **Total des dépenses en ligne**, choisissez **Somme** dans la liste déroulante **Sélectionner une fonction**.

1. Sélectionnez **+ Ajouter un attribut**, développez **Achats : e-commerce**, sélectionnez **TotalPrice**, puis cliquez sur **Ajouter**.

1. Sous **Configurer les calculs de mesures**, sélectionnez **Dimensions (1)**.

1. Sélectionnez **Modifier les dimensions**.

1. Développez **Achats : e-commerce**, sélectionnez **ContactId**, puis sélectionnez **Terminé**.

1. Sélectionnez **Appliquer**.

1. Sélectionnez le bouton **Exécuter** pour terminer votre mesure.

### Tâche 3 : définir des attributs client 
Tout d’abord, nous allons définir le **nombre total de points de fidélité** gagnés par chaque client.

1. Si nécessaire, sélectionnez **Insights > Mesures** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau > Créer vos propres mesures** à partir de la barre d’outils.

1. En regard de l’en-tête **Mesure sans titre**, sélectionnez **Modifier les détails**.

1. Définissez le **nom** sur **Total des points Club**, puis sélectionnez **Terminé**.

1. Sous le calcul **Total des points Club**, choisissez **Somme** dans la liste déroulante **Type de fonction**.

1. Sélectionnez **+ Ajouter un attribut**, développez **Achats : PDV**, sélectionnez **RewardPointsAdded** et sélectionnez **Ajouter**.

1. Sélectionnez le bouton **Exécuter** pour terminer votre mesure.

    Ensuite, nous allons définir la valeur totale de tous les achats effectués pour chaque client.

1. Sélectionnez **Insights > Mesures** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau > Créer vos propres mesures** à partir de la barre d’outils.

1. En regard de l’en-tête **Mesure sans titre**, sélectionnez **Modifier les détails**.

1. Définissez le **nom** sur **Dépenses totales ($)** et sélectionnez **Terminé**.

1. Sous le calcul **Dépenses totales ($)**, choisissez **Somme** dans la liste déroulante **Type de fonction**.

1. Sélectionnez **+ Ajouter un attribut**.

1. Sélectionnez l’onglet **Mesures**, développez **TotalInStoreSpend : CustomerInsights**, sélectionnez **Calcul 1**, puis sélectionnez **Ajouter**.

1. Sélectionnez **+ (signe plus)** pour ajouter un signe plus après l’attribut que vous venez d’ajouter. Le signe plus doit apparaître dans la formule de calcul.

1. Sélectionnez **+ Ajouter un attribut**.

1. Sélectionnez l’onglet **Mesures**, développez **TotalOnlineSpend : CustomerInsights**, sélectionnez **Calcul 1**, puis Sélectionnez **Ajouter**.

1. Sélectionnez le bouton **Exécuter** pour terminer votre mesure.

    Ensuite, nous allons définir la valeur moyenne de tous les achats en magasin pour chaque client.

1. Sélectionnez **Insights > Mesures** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau > Créer vos propres mesures** à partir de la barre d’outils.

1. En regard de l’en-tête **Mesure sans titre**, sélectionnez **Modifier les détails**.

1. Définissez le nom sur **Moyenne des achats en magasin ($)** et sélectionnez **Terminé**.

1. Sous le calcul **Moyenne des achats en magasin ($)**, choisissez **Moyenne** dans la liste déroulante **Sélectionner une fonction**.

1. Sélectionnez **+ Ajouter un attribut**, développez **Achats : PDV**, sélectionnez **Prix total**, puis sélectionnez **Ajouter**.

1. Sélectionnez le bouton **Exécuter** pour terminer votre mesure.

### Tâche 4 : valeur moyenne des achats en ligne
Ensuite, nous allons définir la valeur moyenne de tous les achats effectués en ligne pour chaque client.

1. Si nécessaire, sélectionnez **Mesures** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau > Créer vos propres mesures** à partir de la barre d’outils.

1. En regard de l’en-tête **Mesure sans titre**, sélectionnez **Modifier les détails**.

1. Définissez le nom sur **Moyenne des achats en ligne ($)** et sélectionnez **Terminé**.

1. Sous le calcul **Moyenne des achats en ligne ($)**, choisissez **Moyenne** dans la liste déroulante **Sélectionner une fonction**.

1. Sélectionnez **+ Ajouter un attribut**, développez **Achats : e-commerce**, sélectionnez **Prix total**, puis **Ajouter**.

1. Sélectionnez le bouton **Exécuter** pour terminer votre mesure.
