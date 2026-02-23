---
date: 2026-02-23
description: Apprenez à définir la date de début du projet, à définir la durée des
  tâches et à enregistrer le projet au format MPP à l'aide d'Aspose.Tasks pour Java.
  Gérez efficacement les tâches parent et enfant.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Définir la date de début du projet et gérer les tâches parentes et enfants
  dans Aspose.Tasks
url: /fr/java/task-properties/parent-child-tasks/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir la date de début du projet et gérer les tâches parent et enfant dans Aspose.Tasks

## Introduction
L'organisation efficace des tâches est la colonne vertébrale d'une gestion de projet réussie, et **définir correctement la date de début du projet** est la première étape vers un planning bien structuré. Dans ce tutoriel, vous verrez comment **définir la date de début du projet**, configurer les durées des tâches et gérer les relations parent‑enfant à l'aide d'Aspose.Tasks pour Java. À la fin, vous serez prêt à **enregistrer le projet au format MPP**, mettre à jour les pourcentages d'achèvement des tâches et personnaliser les propriétés des tâches pour tout scénario réel.

## Quick Answers
- **Comment définir la date de début du projet ?** Utilisez `proj.set(Prj.START_DATE, startDate);` après avoir initialisé l'objet `Project`.  
- **Puis-je ajouter des tâches enfants sous une tâche parent ?** Oui – appelez `parentTask.getChildren().add("Child Task")`.  
- **Dans quel format Aspose.Tasks enregistre-t-il le fichier ?** Utilisez `SaveFileFormat.Mpp` pour **enregistrer le projet au format MPP**.  
- **Comment mettre à jour l'avancement d'une tâche ?** Définissez `Tsk.PERCENT_COMPLETE` sur l'objet tâche.  
- **Où puis-je obtenir une licence temporaire ?** Consultez la page de licence temporaire liée dans la FAQ.

## Prerequisites
Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants :
- Compréhension de base de la programmation Java.  
- Bibliothèque Aspose.Tasks pour Java installée. Vous pouvez la télécharger [ici](https://releases.aspose.com/tasks/java/).  
- Un environnement de développement intégré (IDE) Java configuré sur votre système.

## Import Packages
Pour commencer, importez les packages nécessaires dans votre projet Java. Ces packages facilitent une intégration transparente avec les fonctionnalités d'Aspose.Tasks pour Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
### Étape 1 : Définir la date de début du projet
Commencez par définir la date de début du projet ainsi que d'autres paramètres pertinents.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Step 2: Add Parent Task (Task 1)
### Étape 2 : Ajouter une tâche parent (Tâche 1)
Créez une tâche parent nommée "Task 1" et configurez ses propriétés, y compris **définir la durée de la tâche**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Step 3: Add Parent Task (Task 2) with Child Tasks
### Étape 3 : Ajouter une tâche parent (Tâche 2) avec des tâches enfants
Ajoutez maintenant une autre tâche parent nommée "Task 2" et incluez des tâches enfants (Tâche 3 et Tâche 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Step 4: Configure Child Tasks
### Étape 4 : Configurer les tâches enfants
Spécifiez les dates de début, les durées et les contraintes pour les Tâches 3 et 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Step 5: Update Task Completion Percentage
### Étape 5 : Mettre à jour le pourcentage d'achèvement de la tâche
Ajustez le pourcentage d'achèvement pour les Tâches 3 et 4 – c'est ainsi que vous **mettez à jour l'avancement de la tâche**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Step 6: Save the Project
### Étape 6 : Enregistrer le projet
Enfin, **enregistrez le projet au format MPP** avec les modifications appliquées.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Ce guide étape par étape montre comment gérer efficacement les tâches parent et enfant à l'aide d'Aspose.Tasks pour Java. Expérimentez différentes configurations pour répondre aux exigences de votre projet.

## Why Customize Task Properties?
### Pourquoi personnaliser les propriétés des tâches ?
Personnaliser les propriétés des tâches telles que les dates de début, les durées, les contraintes et les pourcentages d'achèvement vous donne un contrôle granulaire sur le comportement du planning. Que vous deviez aligner les tâches avec la disponibilité des ressources ou appliquer des règles métier, Aspose.Tasks vous permet de **personnaliser les propriétés des tâches** par programmation.

## Common Issues and Solutions
| Problème | Solution |
|----------|----------|
| **Date de début non appliquée** | Assurez‑vous d’appeler `proj.set(Prj.START_DATE, …)` **après** la création de l’objet `Project` et avant d’ajouter des tâches. |
| **Les tâches enfants héritent de contraintes incorrectes** | Définissez explicitement le `ConstraintType` et le `ConstraintDate` de chaque enfant, comme indiqué à l’étape 4. |
| **Le fichier enregistré ne peut pas être ouvert dans MS Project** | Vérifiez que vous utilisez la dernière version d’Aspose.Tasks et enregistrez avec `SaveFileFormat.Mpp`. |
| **Le pourcentage ne se reflète pas dans l'interface** | Après avoir défini `Tsk.PERCENT_COMPLETE`, appelez `proj.calculateTaskSchedule()` si vous avez besoin de dates recalculées. |

## FAQs
### Aspose.Tasks pour Java est‑il compatible avec différents formats de fichiers de projet ?
Oui, Aspose.Tasks pour Java prend en charge divers formats de fichiers de projet, y compris MPP et XML.

### Puis‑je personnaliser les propriétés des tâches au‑delà de ce qui est couvert dans ce tutoriel ?
Absolument ! Aspose.Tasks pour Java offre de nombreuses options de personnalisation des propriétés des tâches.

### Existe‑t‑il un forum communautaire pour Aspose.Tasks où je peux obtenir de l’aide ?
Oui, vous pouvez visiter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir du soutien de la communauté.

### Comment obtenir une licence temporaire pour Aspose.Tasks pour Java ?
Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Où puis‑je trouver la documentation complète pour Aspose.Tasks pour Java ?
La documentation est disponible [ici](https://reference.aspose.com/tasks/java/).

**Additional Q&A**
**Q : Comment obtenir programmétiquement une licence temporaire ?**  
R : Chargez le fichier de licence temporaire avec `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q : Puis‑je changer l’unité de durée par défaut d’une tâche ?**  
R : Oui – modifiez l’argument `TimeUnitType` dans `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q : Quelle version d’Aspose.Tasks est requise pour utiliser `SaveFileFormat.Mpp` ?**  
R : Toutes les versions récentes (2022‑2026) supportent l’enregistrement au format MPP ; consultez les notes de version pour d’éventuels changements majeurs.

**Dernière mise à jour** : 2026-02-23  
**Testé avec** : Aspose.Tasks pour Java 24.11  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}