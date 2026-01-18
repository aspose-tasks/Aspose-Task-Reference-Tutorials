---
date: 2026-01-18
description: Apprenez à planifier une ligne de base de gestion de projet avec Aspose.Tasks
  pour Java, ce qui vous permet de gérer les lignes de base du projet et de comparer
  l'avancement prévu à l'avancement réel.
linktitle: Baseline Task Scheduling in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ligne de base de la gestion de projet – Planification des tâches avec Aspose.Tasks
url: /fr/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Base de référence de gestion de projet – Planification des tâches avec Aspose.Tasks

## Introduction à la base de référence de gestion de projet
Gérer une **base de référence de gestion de projet** est une pierre angulaire d’une gestion de projet efficace. Elle vous permet de capturer le plan original et de comparer plus tard **le planifié vs le réel** afin de repérer les écarts tôt. Dans ce tutoriel, nous allons parcourir comment planifier les bases de référence des tâches en utilisant Aspose.Tasks for Java, vous donnant les outils pour **gérer les bases de référence de projet** en toute confiance et maintenir vos projets sur la bonne voie.

## Réponses rapides
- **Que représente une base de référence de gestion de projet ?**  
  La base de référence enregistre le calendrier, le coût et le périmètre originaux pour une analyse des écarts ultérieure.  
- **Quelle bibliothèque gère la planification des bases de référence en Java ?**  
  Aspose.Tasks for Java fournit une API robuste pour créer et gérer les bases de référence.  
- **Ai-je besoin d’une licence pour exécuter le code ?**  
  Un essai gratuit fonctionne pour les tests ; une licence commerciale est requise pour une utilisation en production.  
- **Quels sont les prérequis principaux ?**  
  Java Development Kit (JDK) et la bibliothèque Aspose.Tasks for Java.  
- **Puis-je consulter les dates de la base de référence après les avoir définies ?**  
  Oui — utilisez l’objet `TaskBaseline` pour lire les valeurs de début, de fin et de durée.

## Qu’est‑ce qu’une base de référence de gestion de projet ?
Une base de référence de gestion de projet capture la version approuvée du calendrier, du budget et du périmètre du projet au début de l’exécution. Elle sert de point de référence pour mesurer la performance et identifier les écarts tout au long du cycle de vie du projet.

## Pourquoi utiliser Aspose.Tasks pour la planification des bases de référence ?
Aspose.Tasks propose une API pure‑Java qui fonctionne sans Microsoft Project installé. Elle vous permet de **créer une instance de projet**, de définir des tâches, de définir des bases de référence et de récupérer les informations de base de référence de manière programmatique — idéal pour les rapports automatisés ou l’intégration dans des outils de gestion de projet personnalisés.

## Prérequis

Avant de commencer, assurez‑vous d’avoir les éléments suivants en place :

### Environnement de développement Java
Assurez‑vous d’avoir le Java Development Kit (JDK) installé sur votre système. Vous pouvez télécharger et installer le JDK depuis le [site web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Bibliothèque Aspose.Tasks for Java
Téléchargez la bibliothèque Aspose.Tasks for Java depuis la [page de téléchargement](https://releases.aspose.com/tasks/java/) et incluez‑la dans votre projet Java.

## Import Packages
Commencez par importer les packages nécessaires dans votre projet Java :

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

Maintenant, décomposons l’exemple fourni en plusieurs étapes :

## Étape 1 : Créer une nouvelle instance de projet
```java
Project project = new Project();
```

## Étape 2 : Définir une tâche et définir la base de référence
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Étape 3 : Accéder aux informations de la base de référence
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Étape 4 : Afficher la durée de la base de référence
```java
System.out.println(baseline.getDuration().toString());
```

## Étape 5 : Afficher la date de début de la base de référence
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Étape 6 : Afficher la date de fin de la base de référence
```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

En suivant ces étapes, vous pouvez exploiter efficacement Aspose.Tasks for Java pour **gérer les bases de référence de projet** au sein de vos projets.

## Problèmes courants et solutions
- **Base de référence non définie :** Assurez‑vous d’appeler `project.setBaseline(BaselineType.Baseline)` **après** avoir ajouté les tâches ; sinon la collection de bases de référence sera vide.  
- **Valeurs nulles :** Si `task.getBaselines()` renvoie une liste vide, vérifiez que la tâche a été ajoutée à la hiérarchie du projet avant de définir la base de référence.  
- **Format de date :** Les méthodes `getStart()` et `getFinish()` renvoient des objets `Date`. Utilisez un formateur si vous avez besoin d’un format d’affichage personnalisé.

## FAQ
### Aspose.Tasks for Java peut‑il gérer des structures de projet complexes ?
Oui, Aspose.Tasks for Java offre des capacités robustes pour gérer efficacement des projets de complexité variable.

### Aspose.Tasks for Java est‑il compatible avec d’autres bibliothèques Java ?
Absolument, Aspose.Tasks for Java s’intègre parfaitement avec d’autres bibliothèques Java, améliorant vos capacités de gestion de projet.

### Puis‑je personnaliser les bases de référence des tâches avec Aspose.Tasks for Java ?
Certainement, Aspose.Tasks for Java offre des fonctionnalités étendues pour personnaliser et gérer les bases de référence des tâches selon les exigences de votre projet.

### Existe‑t‑il une version d’essai d’Aspose.Tasks for Java ?
Oui, vous pouvez accéder à une version d’essai gratuite d’Aspose.Tasks for Java depuis la [page de diffusion](https://releases.aspose.com/).

### Où puis‑je trouver du support pour Aspose.Tasks for Java ?
Pour toute question ou assistance, vous pouvez visiter le forum Aspose.Tasks [ici](https://forum.aspose.com/c/tasks/15).

## Questions fréquemment posées

**Q : Comment créer une nouvelle instance de projet dans Aspose.Tasks ?**  
A : Instanciez la classe `Project` (`Project project = new Project();`). Cela crée un nouveau fichier de projet prêt pour les tâches et les bases de référence.

**Q : Quelle est la différence entre `BaselineType.Baseline` et les autres types de base de référence ?**  
A : `BaselineType.Baseline` fait référence à la base de référence principale (Baseline 1). Aspose.Tasks prend également en charge les Baselines 2‑10 pour des instantanés supplémentaires.

**Q : Puis‑je exporter les données de base de référence vers Excel ou CSV ?**  
A : Oui, vous pouvez parcourir les objets `TaskBaseline` et écrire les valeurs dans un fichier CSV en utilisant les I/O Java standard.

**Q : La définition d’une base de référence affecte‑t‑elle les dates des tâches existantes ?**  
A : Définir une base de référence capture les dates actuelles mais ne modifie pas le planning actif de la tâche. Vous pouvez toujours ajuster les dates de début/fin après la création de base de référence.

**Q : Est‑il possible de comparer plusieurs bases de référence de manière programmatique ?**  
A : Absolument. Récupérez chaque base de référence via `task.getBaselines().get(index)` et comparez leurs propriétés `Start`, `Finish` et `Duration`.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-18  
**Testé avec :** Aspose.Tasks for Java 24.12  
**Auteur :** Aspose