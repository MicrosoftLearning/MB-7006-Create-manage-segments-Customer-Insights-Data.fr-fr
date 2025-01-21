---
lab:
  title: "Labo\_4\_: créer des segments"
---

# Labo 4 : créer des segments

Dans ce labo, vous allez apprendre à effectuer les opérations suivantes :
- Créer un segment à partir d’un profil
- Créer un segment à l’aide de mesures
- Créer un segment à partir de zéro

## Exercice 1 : créer des segments à partir de plusieurs sources 
### Tâche 1 : créer un segment à partir d’un profil
Dans cette première tâche, nous allons créer un segment basé sur le profil client. Nous allons identifier tous les clients qui résident dans l’état du Texas. 

1. Développez **Insights** et sélectionnez **Segments** dans le menu de navigation de gauche.

1. Sélectionnez **+ Nouveau > Créer à partir de Profils**.

1. Pour **Champ**, sélectionnez **État** et comme **Valeur**, choisissez **Texas**.

1. Sélectionnez **Révision**.

1. Nommez le segment **Clients du Texas** et vérifiez que le **nom de la table de sortie** a été automatiquement renseigné avec **Clients du Texas**.

1. Cliquez sur **Enregistrer**.

### Tâche 2 : créer un segment à l’aide de mesures 
Contoso Coffee Marketing souhaite lancer une nouvelle promotion. À partir des données historiques, le service marketing a déterminé qu’il souhaite cibler les clients adeptes du café fait maison, dont la valeur des achats en ligne liés au café est supérieure à la moyenne. Cette fois, nous allons créer le segment à l’aide de l’option **Créer à partir de Mesures**. 

1. Dans le menu de navigation de gauche, sélectionnez **Insights > Segments**.

1. Sélectionnez **+ Nouveau > Créer à partir de Mesures**.

1. Sélectionnez l’attribut **Valeur moyenne des achats en magasin ($).**

1. Définissez l’**opérateur** sur **Supérieur à**.

1. Définissez la **valeur** sur **100**. Le graphique devrait afficher la **Valeur moyenne des achats sur le web ($)** par centile.

1. Sélectionnez **Révision**.

1. Nommez le segment **Clients de premier plan** et vérifiez que le **nom de la table de sortie** a été automatiquement renseigné avec **Clients de premier plan**.

1. Cliquez sur **Enregistrer**.

### Tâche 3 : créer un segment à partir de zéro
Chaque saison, Contoso Coffee organise des promotions différentes. Cette année, ils souhaitent organiser une Promotion de fin d’automne pour vendre les modèles restants de la fin d’année. Ils souhaitent cibler les membres de la génération X dont la valeur des achats en magasin liés à leur nouveau café Cold Brew est supérieure à la moyenne. Étant donné que plusieurs critères sont nécessaires pour ce segment, nous allons le créer à partir de zéro.

1. Dans le menu de navigation de gauche, sélectionnez **Insights > Segments**. Sélectionnez **+ Nouveau > Créer votre propre segment**.

1. À côté du texte d’en-tête **Segment sans titre**, sélectionnez **Modifier les détails** et modifiez le **Nom** en **Promotion de fin d’automne**.

1. Vérifiez que le **Nom de l’entité de sortie** a été automatiquement renseigné avec **Promotion de fin d’automne** et sélectionnez **Terminé**.

1. En utilisant le volet **Ajouter à la règle 1** sur le côté droit de l’écran, développez **Client : Insights client** et sélectionnez **Date de naissance**. 

1. Sélectionnez **est** et **le ou après** et entrez la date du **1/1/1965**.

1. Ajoutez une autre condition avec un qualificateur **et**.

1. Définissez cette condition comme **Date de naissance** est **le ou avant le 31/12/1979**.

1. Ajoutez une autre condition avec un qualificateur **et**. 

1. Développez **Mesure_Client : Insights client**.

1. Sélectionnez la mesure **Valeur moyenne des achats sur le web ($)** et ajoutez-la à **Règle 1**. 

1. Sélectionnez l’option **est** et **supérieur ou égal à 125**.

1. Ajoutez une autre condition avec un qualificateur **et**. 

1. Dans le champ **Entrer un nom d’attribut ou ajouter à partir du volet**, entrez **Sexe** et sélectionnez-le dans la liste qui s’affiche. 

1. Sélectionnez **est** et, **égal à masculin**.

1. Cochez la case **Ignorer la casse**.

1. Sous **Règle 1**, sélectionnez **+ Ajouter une règle**. 

1. Sélectionnez la zone **Union** et remplacez-la par **Sauf**.

1. Dans le volet **Ajouter à la règle 2**, développez **Client : Insights client**, puis sélectionnez **État**. 

1. Sélectionnez **est** et **égal à Floride**.

1. Cliquez sur **Enregistrer**.

1. Sélectionnez **Exécuter**.
