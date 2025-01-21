---
lab:
  title: "Labo\_5\_: générer des insights"
---

# Labo 5 : générer des insights 

Dans ce labo, vous allez apprendre à effectuer les opérations suivantes :
- Générer des insights sur vos segments 
- Afficher les facteurs de différenciation et les chevauchements entre les segments 
- Créer des segments suggérés en fonction d’un segment 

## Exercice 1 : générer des insights sur vos segments
### Tâche 1 : facteurs de différenciation des segments
Souvent, vous aurez des clients qui existent dans plusieurs segments. Il peut être utile de comprendre quand il pourrait y avoir un chevauchement entre eux. Essayons de trouver les clients communs qui appartiennent à la fois aux segments **Clients du Texas** et **Promotion de fin d’automne** et ce qui différencie ces deux segments en termes de **Points de récompense** et de **LifetimeSpend**.

1. Dans le menu de navigation de gauche, sélectionnez **Insights > Segments**. Sélectionnez l’onglet **Informations (aperçu)** et sélectionnez **+ Nouveau** dans la barre de commandes, ou sélectionnez le bouton **+ Nouvelle information**.

1. Vous verrez alors deux options : Commençons par créer à l’aide des **Facteurs de différenciation** pour voir ce qui distingue ces deux segments. Sélectionnez **Facteurs de différenciation**.

1. Choisissez **Promotion de fin d’automne** comme segment principal. Cliquez sur **Suivant**.

1. Choisissez **Clients du Texas** comme autre segment, puis sélectionnez **Suivant**.

1. Choisissez maintenant **Points de récompense** sous **champs Clients** et **LifetimeSpend** sous **champs Mesures** pour voir comment les segments ci-dessus diffèrent les uns des autres en ce qui concerne les **Points de récompense** et **LifetimeSpend**. Effacez tous les autres champs client et mesure.

1. Sélectionnez **Suivant** et nommez l’insight **Promotion d'automne vs Clients du Texas**.

1. Vérifiez que le **nom de l’entité de sortie** est défini sur **PromotiondautomnevsClientsduTexas**. Cliquez sur **Enregistrer**.

1. Une fois l’insight actualisé, ouvrez l’insight créé. Sélectionnez les onglets **Attributs** ou **Mesures** pour voir comment les segments diffèrent les uns des autres par rapport aux champs que vous avez sélectionnés. Observez le **Score de différence**, qui indique le degré de différence. Plus le score est élevé, plus la différence est grande.

1. Sélectionnez chaque mesure et attribut pour afficher des insights plus approfondis.

### Tâche 2 : chevauchement des segments
Maintenant que nous avons créé un insight Segment à l’aide des **Facteurs de différenciation**, nous allons créer un insight en utilisant **Chevauchement**.

1. Vérifiez que vous êtes toujours dans l’onglet **Segments > Informations (aperçu)** et sélectionnez **+ Nouveau** dans la barre de commandes. Choisissez **Chevauchement**.

1. Sélectionnez les deux segments **Promotion de fin d’automne** et **Clients du Texas** pour connaître leurs clients communs.

1. Cliquez sur **Suivant**.

1. Nommez le segment **Clients de la Promotion d'Automne chevauchant les Clients du Texas** et vérifiez que le **Nom de la table de sortie** est défini sur **ClientsdelaPromotiondAutomnechevauchantlesClientsduTexas**. Cliquez sur **Enregistrer**.

1. Une fois l’insight actualisé, ouvrez l’insight créé pour voir le diagramme de Venn montrant le total et le pourcentage de clients partagés entre ces deux segments.

## Exercice 2 : extension du segment et segments suggérés
### Tâche 1 : extension du segment
L’extension de segment peut être utilisée pour rechercher des clients similaires à votre base de clients de segment en utilisant l’intelligence artificielle. Nous avons précédemment créé un segment appelé **Clients de la promotion d’automne**, qui regroupe des clients milléniaux ayant un volume d’achats en magasin supérieur à la moyenne. Maintenant, élargissons ce segment pour trouver des clients similaires à cibler avec notre nouveau café Cold Brew.

1. Sélectionnez **Insights > Segments** dans le menu de navigation de gauche, puis sélectionnez l’onglet **Tous les segments**.

1. Choisissez le segment **Clients de la promotion d’automne**. Cela deviendra notre segment source.

1. Sélectionnez **Rechercher des clients similaires** dans la barre de commandes.

1. Nommez votre segment **Extensiondelapromotiondautomne**.

1. Sélectionnez **Ajouter des champs** à l’étape suivante pour sélectionner des attributs et des mesures utilisés pour rechercher des clients similaires. Nous allons viser des clients ayant des caractéristiques similaires en termes de localisation et d’achats en magasin moyens. Veuillez donc sélectionner **PostCode** et **AverageStorePurchase**. Sélectionnez **Appliquer**.

1. Ensuite, vous devez choisir qui prendre en compte. Pour l’instant, sélectionnez **Tous les clients à l’exception du segment source**.

1. Puis sélectionnez le nombre maximum de clients à inclure. Tenons-nous en à **20 %**.

1. Si vous souhaitez inclure des membres à partir du segment source, cochez la dernière option. Sinon, laissez-la désactivée. Pour nos besoins, nous pouvons ne pas cocher cette case.

1. Sélectionnez **Exécuter**.

1. Une fois le segment actualisé, ouvrez le segment pour rechercher les **scores de similarité** et explorez l’**aperçu des membres du segment**.

### Tâche 2 : obtenir des suggestions de segments 
Utilisez des segments suggérés pour découvrir des segments intéressants en fonction d’un attribut client ou d’une mesure d’intérêt.

1. Sélectionnez **Informations > Segments** dans le menu de navigation de gauche, puis sélectionnez l’onglet **Suggestions (aperçu).**

1. Sélectionnez **Obtenir des suggestions** pour commencer l’expérience de configuration.

1. Choisissez **Améliorer une mesure/métrique**, puis sélectionnez **Démarrer**.

1. Sous **Champs de mesure**, sélectionnez **LifetimeSpend** comme attribut cible. Cliquez sur **Suivant**.

1. Puis, sélectionnez les attributs susceptibles d’influencer l’attribut cible (**LifetimeSpend**)afin que le modèle d’IA puisse identifier des motifs intéressants entre les attributs d’influence et l’attribut cible. Le modèle suggère des segments basés sur ces modèles. Sélectionnez **E-mail abonné**, **Revenu**, **Niveau de fidélité**, **Profession** et **État** comme attributs d’influence.

1. Sélectionnez **Exécuter**. Le modèle IA commence à trouver des modèles entre les attributs d’influence sélectionnés et les attributs cibles pour présenter des suggestions de segment. Attendez quelques minutes que le modèle termine son analyse.

1. Une fois que le modèle a terminé son exécution et s’il parvient à identifier des motifs entre les attributs d’influence et l’attribut cible, des suggestions de segment seront affichées sous l’onglet **Suggestions (aperçu)**.

1. Pour enregistrer le segment, sélectionnez **Enregistrer comme segment** dans le panneau **Détails du segment suggéré**. Cliquez sur **Enregistrer**.

1. Le segment enregistré peut ensuite être consulté dans l’onglet **Tous les segments** et utilisé pour des processus en aval comme n’importe quel autre segment dynamique. Si vous souhaitez examiner les règles que le modèle a apprises après l’enregistrement d’un segment, vous pouvez le faire en sélectionnant **Modifier** sous l’onglet **Tous les segments**.
