---
title: Fractionner la date de fin de la tâche dans Aspose.Tasks
linktitle: Fractionner la date de fin de la tâche dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Apprenez à diviser les dates de fin des tâches sans effort à l'aide d'Aspose.Tasks pour Java. Améliorez la gestion de projet avec des délais précis.
weight: 28
url: /fr/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fractionner la date de fin de la tâche dans Aspose.Tasks

## Introduction
En gestion de projet, comprendre les délais des tâches est crucial pour la réussite du projet. Aspose.Tasks for Java fournit des fonctionnalités puissantes pour manipuler efficacement les tâches du projet. Dans ce didacticiel, nous aborderons le fractionnement des dates de fin des tâches à l'aide d'Aspose.Tasks, vous aidant ainsi à gérer efficacement les délais du projet.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Connaissance de base de la programmation Java.
-  Aspose.Tasks pour la bibliothèque Java installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/java/).
- Un environnement de développement Java mis en place.
## Importer des packages
Commencez par inclure les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.*;
```
## Étape 1 : Rechercher une tâche fractionnée
Localisez la tâche que vous souhaitez diviser au sein du projet :
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Lire le projet
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Étape 2 : Trouver le calendrier du projet
Récupérez le calendrier du projet pour des calculs de dates précis :
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Étape 3 : Calculer la date de fin de la tâche avec différentes durées
Calculez maintenant la date de fin de la tâche pour différentes durées :
## Étape 3.1 : Durée de 8 heures
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Répétez le code ci-dessus pour différentes durées, en ajustant les heures en conséquence.
## Conclusion
Maîtriser l’art de manipuler les dates de fin des tâches est essentiel pour une gestion de projet efficace. Aspose.Tasks for Java simplifie ce processus, vous permettant de rationaliser les délais de votre projet sans effort.
## FAQ
### Q1 : Comment puis-je télécharger Aspose.Tasks pour Java ?
 A1 : Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/java/).
### Q2 : Où puis-je trouver de la documentation pour Aspose.Tasks ?
 A2 : Se référer à la documentation[ici](https://reference.aspose.com/tasks/java/).
### Q3 : Comment puis-je obtenir une licence temporaire pour Aspose.Tasks ?
 A3 : Obtenir un permis temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Q4 : Où puis-je demander de l'aide pour Aspose.Tasks ?
 A4 : Visitez le forum d'assistance[ici](https://forum.aspose.com/c/tasks/15).
### Q5 : Puis-je acheter Aspose.Tasks ?
 A5 : Oui, vous pouvez l'acheter[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
