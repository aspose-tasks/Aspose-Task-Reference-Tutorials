---
date: 2026-05-26
description: Apprenez comment ajouter une vue à un projet en utilisant Aspose.Tasks
  pour Java, enregistrer une vue personnalisée et définir les propriétés de la vue
  pour des rapports MS Project robustes.
keywords:
- add view to project
- save custom view
- persist custom view
- create gantt chart view
- set view properties
linktitle: Vues personnalisées dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to add view to project using Aspose.Tasks for Java, save
    custom view, and set view properties for robust MS Project reporting.
  headline: How to Add View to Project with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes – Aspose.Tasks lets you create custom task sheets, resource sheets,
      and even custom tables, giving you full control over every visual aspect.
    question: Can I customize views beyond Gantt charts?
  - answer: Absolutely. The library processes projects with **500,000+ tasks** using
      a streaming API that keeps memory usage under 200 MB.
    question: Is Aspose.Tasks for Java suitable for large‑scale projects?
  - answer: Yes – you can export a view to PDF, XLSX, HTML, and several image formats
      directly from the API.
    question: Does Aspose.Tasks for Java support exporting views to different formats?
  - answer: Certainly. The API is fully scriptable, allowing you to generate, modify,
      and persist views in batch jobs or CI pipelines.
    question: Can I automate the creation of custom views using Aspose.Tasks for Java?
  - answer: Yes, you can get help from other developers and Aspose staff in the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks for Java support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Comment ajouter une vue à un projet avec Aspose.Tasks
url: /fr/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter une vue à un projet avec Aspose.Tasks

## Introduction
Si vous recherchez **comment ajouter une vue à un projet** afin que vos rapports correspondent exactement aux besoins des parties prenantes, vous êtes au bon endroit. Personnaliser les vues de MS Project vous permet de mettre en avant les données les plus pertinentes, d'éliminer le désordre et d'accélérer la prise de décision. **Aspose.Tasks for Java** fournit une API puissante et typée qui vous permet de créer, configurer et persister des vues personnalisées directement dans un fichier MPP. Dans ce guide, nous parcourrons chaque étape — de la préparation de l'environnement à l'enregistrement de la vue — afin que vous puissiez fournir une solution soignée et réutilisable.

## Réponses rapides
- **Quel est le but principal ?** Ajouter une vue à un projet et la persister dans le fichier MPP en utilisant Aspose.Tasks for Java.  
- **Quelle classe crée une vue ?** `GanttChartView` (ou d'autres types de vues comme `TaskSheetView`).  
- **Comment faire apparaître la vue dans le menu ?** Appelez `view.setShowInMenu(true)` avant d'enregistrer.  
- **Comment enregistrer la vue avec le projet ?** Utilisez `MPPSaveOptions` avec `setWriteViewData(true)`.  
- **Ai-je besoin d'une licence ?** Oui – une licence valide Aspose.Tasks est requise pour les déploiements en production.

## Qu’est-ce que « ajouter une vue à un projet » ?
*Ajouter une vue à un projet* signifie créer une nouvelle représentation visuelle (par ex., diagramme de Gantt, feuille de tâches) et intégrer sa définition dans le fichier MPP afin que Microsoft Project puisse l'afficher ultérieurement. Cette opération est entièrement programmée avec Aspose.Tasks, éliminant les étapes manuelles de l'interface utilisateur.

## Pourquoi utiliser des vues personnalisées ?
Aspose.Tasks prend en charge **plus de 50 propriétés liées aux vues** et peut gérer des projets contenant **des centaines de milliers de tâches** sans charger le fichier complet en mémoire. En définissant une vue une fois et en la persistant, vous assurez une cohérence des rapports pour tous les membres de l'équipe et réduisez le risque d'erreurs de configuration manuelle.

## Prérequis
- **Java Development Kit** (JDK 8 ou ultérieur) installé et configuré sur votre machine.  
- Bibliothèque **Aspose.Tasks for Java** – téléchargez‑la depuis [ici](https://releases.aspose.com/tasks/java/).  
- Un fichier de licence **Aspose.Tasks** valide pour une utilisation en production (l'essai gratuit fonctionne pour l'évaluation).

## Importer les packages
Les classes `GanttChartView`, `MPPSaveOptions` et les classes associées se trouvent dans l'espace de noms `com.aspose.tasks`. Importez‑les en haut de votre fichier source :

`GanttChartView` représente une définition de vue de diagramme de Gantt.  
`MPPSaveOptions` contrôle la façon dont un projet est enregistré, y compris les données de vue.  
`Project` est la classe principale représentant un fichier MS Project.  
`View` est la classe de base pour tous les types de vues.  

```text
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```
```

## Étape 1 : Configurer le projet
Créez une nouvelle instance `Project` ou chargez un fichier existant. Cet objet contient toutes les données du projet, y compris les tâches, les ressources et les vues. `Prj` fournit des clés constantes pour les propriétés du projet telles que le nom du projet.

```text
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
```

## Étape 2 : Créer une vue
`GanttChartView` est la représentation Aspose.Tasks d'un diagramme de Gantt classique. Elle vous permet de contrôler les colonnes, les styles de barres, les échelles de temps, et plus encore.

```text
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```
```

## Étape 3 : Personnaliser les propriétés de la vue *(définir les propriétés de la vue)*
Ici, vous pouvez affiner l'apparence de la vue : définir la première colonne visible, spécifier les couleurs des barres et ajuster la granularité de l'échelle de temps. `setShowInMenu(boolean)` détermine si la vue apparaît dans le menu de MS Project. `setHighlightFilter(boolean)` indique si le filtre est mis en évidence pour la vue.

```text
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```
```

### Comment afficher le menu de la vue
Appeler `view.setShowInMenu(true)` garantit que la vue nouvellement créée apparaît dans le menu **View** de MS Project, offrant aux utilisateurs finaux un accès instantané sans configuration supplémentaire.

## Étape 4 : Ajuster les paramètres de la vue
Les paramètres avancés tels que la mise en page, les options d'impression et les largeurs de colonnes sont configurés à cette étape. Un réglage approprié garantit que les rapports imprimés correspondent à la vue à l'écran.

```text
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```
```

## Étape 5 : Ajouter la vue au projet *(ajouter une vue personnalisée java)*
Après avoir configuré la vue, ajoutez‑la à la collection `Views` du projet. `getViews()` renvoie la collection des vues du projet. Cette étape **ajoute réellement la vue au projet** afin qu'elle devienne partie intégrante de la structure interne du fichier.

```text
```java
// Add the view to our project
project.getViews().add(view);
```
```

## Étape 6 : Enregistrer le projet *(enregistrer la vue du projet)*
Lors de la persistance du projet, vous devez indiquer à Aspose.Tasks d'écrire les données de la vue. La classe `MPPSaveOptions` contrôle ce comportement. `setWriteViewData(boolean)` indique au sauvegardeur d'intégrer les définitions de vue.

```text
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```
```

### Pourquoi l'enregistrement de la vue du projet est important
Définir `options.setWriteViewData(true)` indique à Aspose.Tasks d'intégrer la définition de la vue personnalisée dans le fichier MPP. Sans ce drapeau, la vue n'existerait que en mémoire et disparaîtrait après la fermeture du fichier.

## Étape 7 : Vérifier les propriétés de la vue
Après l'enregistrement, vous pouvez recharger le projet et vérifier que la vue apparaît correctement dans l'interface et que toutes les propriétés (colonnes, styles de barres, etc.) sont conservées.

```text
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```
```

## Cas d'utilisation courants
- **Rapports aux parties prenantes :** Afficher uniquement les jalons et les tâches du chemin critique pour la direction.  
- **Allocation des ressources :** Afficher les ressources côte à côte avec leurs tâches assignées pour la planification de capacité.  
- **Instantanés prêts à imprimer :** Configurer la taille de la page, l'orientation et la visibilité des colonnes pour générer des PDF clairs pour une révision hors ligne.

## Conseils de dépannage
- **Vue n'apparaît pas dans le menu :** Assurez‑vous que `view.setShowInMenu(true)` est appelé *avant* l'enregistrement et que `MPPSaveOptions.setWriteViewData(true)` est activé.  
- **Colonnes manquantes dans l'impression :** Vérifiez que `setFirstColumnsCount` correspond au nombre de colonnes que vous avez définies et activez `setPrintFirstColumnsCountOnAllPages(true)`.  
- **Exceptions de licence :** Chargez le fichier de licence avec `License license = new License(); license.setLicense("Aspose.Tasks.lic");` avant de créer tout objet `Project`.

## Questions fréquemment posées

**Q : Puis‑je personnaliser les vues au‑delà des diagrammes de Gantt ?**  
A : Oui – Aspose.Tasks vous permet de créer des feuilles de tâches personnalisées, des feuilles de ressources et même des tableaux personnalisés, vous offrant un contrôle complet sur chaque aspect visuel.

**Q : Aspose.Tasks for Java convient‑il aux projets de grande envergure ?**  
A : Absolument. La bibliothèque traite des projets contenant **plus de 500 000 tâches** en utilisant une API de streaming qui maintient l'utilisation de la mémoire en dessous de 200 Mo.

**Q : Aspose.Tasks for Java prend‑il en charge l'exportation des vues vers différents formats ?**  
A : Oui – vous pouvez exporter une vue en PDF, XLSX, HTML et plusieurs formats d'image directement depuis l'API.

**Q : Puis‑je automatiser la création de vues personnalisées avec Aspose.Tasks for Java ?**  
A : Certainement. L'API est entièrement scriptable, vous permettant de générer, modifier et persister des vues dans des travaux batch ou des pipelines CI.

**Q : Existe‑t‑il un forum communautaire pour le support d'Aspose.Tasks for Java ?**  
A : Oui, vous pouvez obtenir de l'aide d'autres développeurs et du personnel Aspose sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Dernière mise à jour :** 2026-05-26  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un fichier MPP – Créer et enregistrer un projet vide au format MPP avec Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Définir le répertoire de données pour la vue du diagramme de Gantt dans Aspose.Tasks](/tasks/java/project-configuration/configure-gantt-chart/)
- [Charger un fichier MPP Java – Gérer les propriétés du projet avec Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}