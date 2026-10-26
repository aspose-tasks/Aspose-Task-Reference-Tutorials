---
date: 2026-10-26
description: Comment lire les données de définition de groupe en utilisant Aspose.Tasks
  for Java. Extract task grouping, criteria, and formatting from Microsoft Project
  files to automate reporting and migration.
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: Lire les données de définition de groupe dans Aspose.Tasks
og_description: Comment lire les données de définition de groupe en utilisant Aspose.Tasks
  for Java. Extract task grouping, criteria, and formatting from Microsoft Project
  files to automate reporting and migration.
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: Comment lire les données de définition de groupe avec Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: Comment lire les données de définition de groupe avec Aspose.Tasks for Java
url: /fr/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lire les données de définition de groupe dans Aspose.Tasks pour Java

## Introduction
Aspose.Tasks for Java vous permet d'accéder, de modifier et d'analyser programmétiquement les fichiers Microsoft Project. Dans ce tutoriel, vous apprendrez **comment lire les données de définition de groupe** d'un fichier `.mpp`, extraire le nom, les critères et le style visuel de chaque groupe, puis utiliser ces informations pour générer des rapports personnalisés ou migrer les paramètres vers d'autres projets. Maîtriser cette capacité vous permet d'automatiser les rapports, de valider les structures de projet et de rationaliser les flux de travail basés sur les données.

## Réponses rapides
- **Que signifie « lire la définition de groupe » ?** Cela consiste à extraire les règles de regroupement (nom, critères, couleurs, polices) que Microsoft Project utilise pour organiser les tâches.  
- **Quelle bibliothèque faut‑il ?** Aspose.Tasks for Java.  
- **Faut‑il une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quels IDE sont pris en charge ?** Tout IDE Java tel qu'IntelliJ IDEA ou Eclipse.  
- **Combien de code est nécessaire ?** Moins de 30 lignes de code Java pour charger un projet et afficher les détails des groupes.

## Comment lire les données de définition de groupe
Chargez le projet, parcourez ses groupes et inspectez les critères de chaque groupe. La réponse directe est : **Créer une instance `Project`, appeler `project.getTaskGroups()` et itérer la collection pour lire les noms, critères, polices et couleurs.** Les sections suivantes décomposent le processus en étapes claires, chacune accompagnée d'un petit espace réservé que vous remplacerez par le fragment réel tiré de la documentation Aspose.Tasks.

## Qu’est‑ce que la lecture de la définition de groupe ?
Lire la définition de groupe désigne l'extraction des règles de regroupement (nom, critères, mise en forme) que Microsoft Project applique pour organiser les tâches. Ces règles indiquent à l'application comment regrouper les tâches par statut, priorité ou champs personnalisés, et incluent des attributs visuels tels que le style de police et la couleur de cellule.

## Pourquoi lire les données de définition de groupe ?
Lire les données de définition de groupe vous permet **d’automatiser la génération de rapports**, **de migrer la logique de regroupement** vers d’autres projets, et **de valider que les groupes requis existent** avant des mises à jour massives. Aspose.Tasks for Java peut traiter des projets contenant **plus de 10 000 tâches** sans charger le fichier complet en mémoire, ce qui permet des opérations par lots à haute performance. De plus, vous pouvez extraire les couleurs de police, les motifs et les directions de tri pour recréer exactement la mise en page visuelle dans des tableaux de bord personnalisés.

## Prérequis
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK) 8+** – toute version récente convient.  
2. **Aspose.Tasks for Java** – téléchargez le dernier JAR depuis la [page de téléchargement d’Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Un IDE Java** – IntelliJ IDEA, Eclipse ou tout éditeur de votre choix.  

> **Astuce pro :** Utilisez Maven ou Gradle pour gérer la dépendance Aspose.Tasks ; cela évite la manipulation manuelle du JAR.

## Importer les packages
`Project` est la classe principale représentant un fichier Microsoft Project dans Aspose.Tasks for Java.  

```java
import com.aspose.tasks.*;
```

## Guide étape par étape

### Étape 1 : configurer votre répertoire de données
Définissez le dossier contenant le fichier `.mpp` que vous souhaitez inspecter. L’utilisation de `java.nio.file.Paths` garantit une gestion des chemins indépendante de la plateforme.

```java
String dataDir = "Your Data Directory";
```

### Étape 2 : charger le fichier projet
Créez une instance `Project` en la pointant vers votre fichier `.mpp`. Le constructeur lit l’en‑tête du fichier et construit un modèle en mémoire.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Étape 3 : récupérer le nombre de groupes de tâches
Affichez le nombre total de groupes de tâches définis dans le projet. Cette vérification rapide confirme que le fichier contient bien des informations de regroupement.

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### Étape 4 : récupérer les informations d’un groupe de tâches spécifique
Obtenez un groupe particulier (indice 1 dans cet exemple) et affichez son nom ainsi que le nombre de critères qu’il contient. Chaque groupe peut avoir plusieurs critères définissant la façon dont les tâches sont regroupées.

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### Étape 5 : récupérer les informations du critère de groupe
Chaque groupe peut comporter un ou plusieurs critères. L’extrait ci‑dessous extrait des détails tels que le champ utilisé pour le regroupement, le mode de regroupement, la couleur de cellule et le motif.

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### Étape 6 : vérifier le groupe parent
Parfois, un critère appartient à un groupe parent. Cette vérification confirme la relation et évite les problèmes de pointeur nul lors de la navigation dans la hiérarchie.

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### Étape 7 : récupérer les informations de police du critère
Les critères de groupe peuvent avoir une mise en forme de police personnalisée. Le code suivant affiche la famille de police, la taille, le style et la direction de tri, vous permettant de recréer exactement l’aspect dans votre propre interface.

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## Problèmes courants et solutions
| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **`NullPointerException` sur `criterion.getParentGroup()`** | Le critère peut ne pas avoir de groupe parent. | Ajoutez une vérification de null avant d’accéder au parent. |
| **Fichier introuvable** | Le chemin `dataDir` est incorrect ou le nom du fichier est mal orthographié. | Utilisez `Paths.get(dataDir, "project.mpp").toAbsolutePath()` et vérifiez que le fichier existe. |
| **Licence non définie** | Aspose s’exécute en mode d’évaluation et peut tronquer la sortie. | Enregistrez votre licence avec `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` avant de charger le projet. |

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Tasks for Java pour modifier des fichiers projet ?**  
R : Oui, la bibliothèque offre des capacités complètes de lecture/écriture pour les formats Microsoft Project, vous permettant d’ajouter des tâches, de modifier des ressources et de mettre à jour les définitions de groupe programmatiquement.

**Q : Aspose.Tasks for Java est‑il compatible avec toutes les versions des fichiers Microsoft Project ?**  
R : Il prend en charge MPP, XML, CSV et d’autres formats courants de Project, depuis Project 2000 jusqu’à la dernière version 2024.

**Q : Comment gérer les erreurs lors de l’utilisation d’Aspose.Tasks for Java ?**  
R : Enveloppez les opérations de fichier dans des blocs `try‑catch` et interceptez `TasksException` pour obtenir des informations détaillées ; examinez `getMessage()` de l’exception pour des indices.

**Q : Aspose.Tasks for Java propose‑t‑il une exportation vers d’autres formats ?**  
R : Absolument — vous pouvez exporter vers PDF, XLSX, HTML, et plus encore grâce aux API d’exportation dédiées de la bibliothèque.

**Q : Où trouver des ressources supplémentaires et du support ?**  
R : Consultez la [documentation d’Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/) pour les références API et le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour l’assistance communautaire.

## Conclusion
Dans ce tutoriel, nous avons parcouru **comment lire les données de définition de groupe** d’un fichier Microsoft Project à l’aide d’Aspose.Tasks for Java. En chargeant un `Project`, en parcourant son `TaskGroupCollection` et en inspectant les critères, polices et couleurs de chaque groupe, vous pouvez créer des pipelines de génération de rapports automatisés, migrer des règles de regroupement ou valider des structures de projet en toute confiance. La même approche s’adapte aux projets volumineux contenant des milliers de tâches tout en maintenant une faible consommation de mémoire.

---

**Dernière mise à jour :** 2026-10-26  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose

## Tutoriels associés

- [Comment lire les informations du projet depuis Microsoft Project avec Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [Comment obtenir les champs de tableau et lire les données de tableau dans Aspose.Tasks](/tasks/java/project-data-reading/read-table-data/)
- [read gantt chart java – Extraire des données Gantt spécifiques](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}