---
title: Gérer les tâches parents et enfants dans Aspose.Tasks
linktitle: Gérer les tâches parents et enfants dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Améliorez l'efficacité de la gestion de projet avec Aspose.Tasks pour Java. Apprenez à gérer les tâches des parents et des enfants étape par étape. Commencez maintenant!
weight: 24
url: /fr/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gérer les tâches parents et enfants dans Aspose.Tasks

## Introduction
Dans le domaine de la gestion de projet, une organisation efficace des tâches est cruciale. Aspose.Tasks for Java fournit une solution robuste pour gérer efficacement les tâches parents et enfants. Dans ce didacticiel, nous vous guiderons tout au long du processus d'utilisation d'Aspose.Tasks for Java pour rationaliser les tâches de votre projet.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Compréhension de base de la programmation Java.
-  Aspose.Tasks pour la bibliothèque Java installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/java/).
- Un environnement de développement intégré (IDE) Java installé sur votre système.
## Importer des packages
Pour commencer, importez les packages nécessaires dans votre projet Java. Ces packages facilitent une intégration transparente avec les fonctionnalités Aspose.Tasks for Java.
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
## Étape 1 : Définir la date de début du projet
Commencez par définir la date de début du projet et d’autres paramètres pertinents.
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Un code supplémentaire pour les importations de packages peut être ajouté ici
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Étape 2 : Ajouter une tâche parent (tâche 1)
Créez une tâche parent nommée « Tâche 1 » et configurez ses propriétés.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Étape 3 : Ajouter une tâche parent (tâche 2) avec des tâches enfants
Maintenant, ajoutez une autre tâche parent nommée « Tâche 2 » et incluez les tâches enfants (Tâche 3 et Tâche 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Ajouter des tâches enfants à la tâche 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Une configuration supplémentaire pour la tâche 3 et la tâche 4 peut être ajoutée ici
```
## Étape 4 : configurer les tâches enfants
Spécifiez les dates de début, les durées et les contraintes pour la tâche 3 et la tâche 4.
```java
// Configurer la tâche 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configurer la tâche 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Étape 5 : Mettre à jour le pourcentage d’achèvement des tâches
Ajustez le pourcentage d'achèvement pour la tâche 3 et la tâche 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Étape 6 : Enregistrez le projet
Enfin, enregistrez le projet avec les modifications appliquées.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Ce guide étape par étape montre comment gérer efficacement les tâches parents et enfants à l'aide d'Aspose.Tasks pour Java. Expérimentez avec différentes configurations pour répondre aux exigences de votre projet.
## Conclusion
En conclusion, Aspose.Tasks for Java permet aux développeurs de gérer efficacement les tâches du projet, garantissant une organisation et un suivi transparents. Mettez en œuvre les étapes décrites pour améliorer vos capacités de gestion de projet.
## FAQ
### Aspose.Tasks for Java est-il compatible avec différents formats de fichiers de projet ?
Oui, Aspose.Tasks for Java prend en charge divers formats de fichiers de projet, notamment MPP et XML.
### Puis-je personnaliser les propriétés des tâches au-delà de ce qui est couvert dans ce didacticiel ?
Absolument! Aspose.Tasks for Java fournit des options de personnalisation étendues pour les propriétés des tâches.
### Existe-t-il un forum communautaire pour Aspose.Tasks où je peux demander de l'aide ?
 Oui, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien de la communauté.
### Comment puis-je obtenir une licence temporaire pour Aspose.Tasks pour Java ?
 Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver une documentation complète pour Aspose.Tasks pour Java ?
 La documentation est disponible[ici](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
