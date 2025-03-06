---
title: Fractionner les tâches dans Aspose.Tasks
linktitle: Fractionner les tâches dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Maîtrisez la gestion des tâches en Java avec Aspose.Tasks ! Apprenez à répartir efficacement les tâches pour optimiser les délais de projet. Télécharger maintenant!
weight: 29
url: /fr/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fractionner les tâches dans Aspose.Tasks

## Introduction
Avez-vous des difficultés avec la gestion des tâches dans votre projet Java ? Aspose.Tasks for Java fournit une solution puissante pour diviser efficacement les tâches, améliorant ainsi les capacités de gestion de projet. Dans ce didacticiel, nous vous guiderons tout au long du processus de répartition des tâches à l'aide d'Aspose.Tasks for Java, vous aidant ainsi à optimiser les délais de votre projet et les allocations de ressources.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Kit de développement Java (JDK) installé sur votre machine.
-  Bibliothèque Aspose.Tasks pour Java téléchargée et ajoutée à votre projet. Vous pouvez le télécharger depuis le[Documentation Aspose.Tasks pour Java](https://reference.aspose.com/tasks/java/).
## Importer des packages
Commencez par importer les packages nécessaires dans votre projet Java :
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Étape 1 : Créer un nouveau projet
Commencez par créer un nouveau projet à l'aide de la bibliothèque Aspose.Tasks :
```java
// Créer un nouveau projet
Project splitTaskProject = new Project();
```
## Étape 2 : Définir le calendrier du projet
Définissez les paramètres du calendrier du projet pour établir la chronologie :
```java
// Obtenez un calendrier standard
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Définir les paramètres du calendrier du projet
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continuez avec l'exemple)
```
## Étape 3 : ajouter une tâche racine
Ajoutez une tâche racine à votre projet :
```java
// Tâche racine
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Étape 4 : Ajouter une nouvelle tâche à diviser
Ajoutez une nouvelle tâche à votre projet que vous souhaitez diviser :
```java
// Ajouter une nouvelle tâche
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Étape 5 : Créer une affectation de ressources
Créez une nouvelle affectation de ressource pour la tâche :
```java
// Créer une nouvelle affectation de ressource
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Étape 6 : générer des données chronologiques
Générez des données chronologiques d'affectation de ressources :
```java
// Générer des données chronologiques d'affectation de ressources
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Étape 7 : diviser la tâche
Divisez la tâche en plusieurs parties :
```java
// Divisez la tâche en 3 parties
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continuez avec l'exemple)
```
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment diviser les tâches à l'aide d'Aspose.Tasks pour Java. Cette puissante bibliothèque simplifie la gestion des tâches dans les projets Java, en fournissant des solutions efficaces pour optimiser les délais des projets et l'allocation des ressources.
## Questions fréquemment posées
### Puis-je diviser des tâches de durées différentes ?
Oui, vous pouvez ajuster la durée des tâches en fonction des exigences de votre projet.
### Aspose.Tasks for Java est-il compatible avec toutes les versions de Java ?
Aspose.Tasks for Java est conçu pour fonctionner de manière transparente avec différentes versions de Java, garantissant ainsi la compatibilité.
### Puis-je utiliser Aspose.Tasks pour Java gratuitement ?
Aspose.Tasks for Java propose un essai gratuit, vous permettant d'explorer ses fonctionnalités avant de faire un achat.
### Comment puis-je obtenir de l'aide pour Aspose.Tasks pour Java ?
 Visiter le[Forum de support Aspose.Tasks pour Java](https://forum.aspose.com/c/tasks/15) pour obtenir de l'aide et entrer en contact avec la communauté.
### Ai-je besoin d’une licence temporaire pour Aspose.Tasks pour Java ?
 Vous pouvez obtenir une licence temporaire auprès de[ce lien](https://purchase.aspose.com/temporary-license/) à des fins de tests et d’évaluation.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
