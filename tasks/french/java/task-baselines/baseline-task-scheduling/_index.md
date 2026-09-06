---
date: 2026-08-29
description: Apprenez à lire les données de baseline et schedule tasks en utilisant
  Aspose.Tasks pour Java, afin de comparer efficacement la progression prévue à la
  progression réelle.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Planification des tâches de baseline dans Aspose.Tasks
og_description: Apprenez à lire les données de baseline et schedule tasks avec Aspose.Tasks
  pour Java, permettant une comparaison précise de la progression prévue à la progression
  réelle.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Comment lire la baseline et schedule tasks avec Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Comment lire la baseline et schedule tasks avec Aspose.Tasks
url: /fr/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment lire la ligne de base et planifier les tâches avec Aspose.Tasks

Dans ce guide, vous découvrirez **comment lire les informations de ligne de base** et planifier les tâches de manière programmatique en utilisant Aspose.Tasks pour Java. À la fin du tutoriel, vous pourrez capturer le plan de projet original, le comparer avec l'avancement réel et générer des rapports de variance — le tout sans avoir besoin de Microsoft Project installé.

## Introduction à la ligne de base de gestion de projet

Gérer une **ligne de base de gestion de projet** est une pierre angulaire d’une gestion de projet efficace. Elle vous permet de capturer le plan original et de comparer plus tard **le progrès prévu vs réel** afin de repérer les écarts tôt. Dans ce tutoriel, nous parcourrons la façon de planifier les lignes de base des tâches en utilisant Aspose.Tasks pour Java, vous donnant les outils pour **gérer les lignes de base de projet** en toute confiance et maintenir vos projets sur la bonne voie.

## Réponses rapides
- **Que représente une ligne de base de gestion de projet ?**  
  Elle enregistre le planning, le coût et le périmètre approuvés au démarrage du projet, fournissant une référence pour l’analyse des écarts.  
- **Quelle bibliothèque gère la planification des lignes de base en Java ?**  
  Aspose.Tasks pour Java propose une API pure‑Java qui prend en charge plus de 45 formats d’entrée et de sortie et des projets jusqu’à 100 000 tâches.  
- **Ai‑je besoin d’une licence pour exécuter le code ?**  
  Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour une utilisation en production.  
- **Quelles sont les principales conditions préalables ?**  
  Java Development Kit (JDK) 11+ et la bibliothèque Aspose.Tasks pour Java.  
- **Puis‑je voir les dates de ligne de base après les avoir définies ?**  
  Oui — utilisez l’objet `TaskBaseline` pour lire les valeurs de début, de fin et de durée.

## Qu’est‑ce qu’une ligne de base de gestion de projet ?
Une ligne de base de gestion de projet enregistre le planning, le budget et le périmètre approuvés au début de l’exécution. Elle sert de point de référence pour mesurer la performance et identifier les écarts tout au long du cycle de vie du projet. Elle comprend les dates de début et de fin prévues, le coût total et les détails du périmètre, offrant un instantané complet pour les comparaisons futures.

## Pourquoi utiliser Aspose.Tasks pour la planification des lignes de base ?
Aspose.Tasks fournit une API pure‑Java qui fonctionne sans Microsoft Project installé. Elle prend en charge **plus de 45 formats d’entrée et de sortie**, peut traiter des projets contenant **jusqu’à 100 000 tâches** en mode mémoire efficace, et propose des méthodes intégrées pour lire et écrire les données de ligne de base — rendant le reporting automatisé et l’intégration simples.

## Prérequis
- **Java Development Kit (JDK)** – installez JDK 11 ou une version ultérieure. Vous pouvez le télécharger depuis le [site web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Bibliothèque Aspose.Tasks pour Java** – téléchargez la dernière version depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/) et ajoutez le JAR au classpath de votre projet.

## Importer les packages
Les classes `Project`, `Task` et `TaskBaseline` se trouvent dans l’espace de noms `com.aspose.tasks`. Importez‑les en haut de votre fichier source :

La classe `Project` est l’objet de niveau supérieur d’Aspose.Tasks qui représente un fichier de projet unique en mémoire. Elle donne accès aux tâches, aux ressources et aux collections de lignes de base.

## Comment lire la ligne de base ?
Chargez le projet, puis interrogez la collection `TaskBaseline` pour chaque tâche. L’objet `TaskBaseline` renvoie le début, la fin et la durée de la ligne de base qui ont été capturés lorsque vous avez appelé `setBaseline`. Cette approche directe vous permet de lire les valeurs de ligne de base sans analyser de fichiers XML ou binaires.

## Étape 1 : créer une nouvelle instance de projet
La classe `Project` représente le fichier de projet complet en mémoire.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Étape 2 : définir une tâche et définir la ligne de base
`Task` représente un élément de travail individuel, et `setBaseline` capture son planning actuel comme ligne de base.
```java
Project project = new Project();
```

## Étape 3 : accéder aux informations de ligne de base
`TaskBaseline` contient les valeurs enregistrées de début, de fin et de durée d’une ligne de base.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Étape 4 : afficher la durée de la ligne de base
`Duration` représente la durée d’une tâche ou d’une ligne de base.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Étape 5 : afficher la date de début de la ligne de base
`Start` est la date de début prévue de la ligne de base.
```java
System.out.println(baseline.getDuration().toString());
```

## Étape 6 : afficher la date de fin de la ligne de base
`Finish` est la date de fin prévue de la ligne de base.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Problèmes courants et solutions
- **Ligne de base non définie :** Assurez‑vous d’appeler `project.setBaseline(BaselineType.Baseline)` **après** avoir ajouté les tâches ; sinon la collection de lignes de base sera vide.  
- **Valeurs nulles :** Si `task.getBaselines()` renvoie une liste vide, vérifiez que la tâche a été ajoutée à la hiérarchie du projet avant de définir la ligne de base.  
- **Format de date :** Les méthodes `getStart()` et `getFinish()` renvoient des objets `java.util.Date`. Utilisez `SimpleDateFormat` si vous avez besoin d’un format d’affichage personnalisé.

## Questions fréquemment posées

**Q : Comment créer une nouvelle instance de projet dans Aspose.Tasks ?**  
R : Instanciez la classe `Project` (`Project project = new Project();`). Cela crée un nouveau fichier de projet prêt pour les tâches et les lignes de base.

**Q : Quelle est la différence entre `BaselineType.Baseline` et les autres types de lignes de base ?**  
R : `BaselineType.Baseline` fait référence à la ligne de base principale (Baseline 1). Aspose.Tasks prend également en charge Baseline 2‑10 pour des instantanés supplémentaires.

**Q : Puis‑je exporter les données de ligne de base vers Excel ou CSV ?**  
R : Oui, vous pouvez parcourir les objets `TaskBaseline` et écrire les valeurs dans un fichier CSV en utilisant les I/O Java standard.

**Q : Le fait de définir une ligne de base affecte‑t‑il les dates des tâches existantes ?**  
R : Définir une ligne de base capture les dates actuelles mais ne modifie pas le planning actif de la tâche. Vous pouvez toujours ajuster les dates de début/fin après la définition de la ligne de base.

**Q : Est‑il possible de comparer plusieurs lignes de base de façon programmatique ?**  
R : Absolument. Récupérez chaque ligne de base via `task.getBaselines().get(index)` et comparez leurs propriétés `Start`, `Finish` et `Duration`.

**Dernière mise à jour :** 2026-08-29  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose  

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Tutoriels associés

- [Créer une liste de tâches Java – ligne de base MS Project avec Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Comment définir la durée de la ligne de base dans Aspose.Tasks pour Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Créer un projet MPP Java – Modifier la progression des tâches avec Aspose.Tasks](/tasks/java/task-properties/change-progress/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}