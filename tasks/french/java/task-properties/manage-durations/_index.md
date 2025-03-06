---
title: Gérer la durée des tâches dans Aspose.Tasks
linktitle: Gérer la durée des tâches dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explorez Aspose.Tasks pour Java et apprenez à gérer la durée des tâches sans effort. Suivez notre guide étape par étape pour une planification et une exécution efficaces du projet.
weight: 20
url: /fr/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gérer la durée des tâches dans Aspose.Tasks

## Introduction
Aspose.Tasks for Java fournit une solution robuste pour gérer efficacement les tâches et la durée des projets. Dans ce didacticiel, nous explorerons comment gérer la durée des tâches à l'aide d'Aspose.Tasks, en vous guidant à chaque étape. Que vous soyez un développeur chevronné ou un débutant, ce guide vous aidera à comprendre l'essentiel du travail avec les durées de tâches dans vos projets.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre ordinateur. Vous pouvez le télécharger[ici](https://www.oracle.com/java/technologies/javase-downloads.html).
- Bibliothèque Aspose.Tasks : téléchargez et incluez la bibliothèque Aspose.Tasks dans votre projet. Vous pouvez trouver la bibliothèque[ici](https://releases.aspose.com/tasks/java/).
## Importer des packages
Dans votre projet Java, importez les packages nécessaires pour travailler avec Aspose.Tasks :
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Étape 1 : Configurez votre projet
```java
// Créer un nouveau projet
Project project = new Project();
```
## Étape 2 : ajouter une nouvelle tâche
```java
// Ajouter une nouvelle tâche au projet
Task task = project.getRootTask().getChildren().add("Task");
```
## Étape 3 : Obtenir et convertir la durée de la tâche
```java
// Obtenir la durée de la tâche en jours (unité de temps par défaut)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convertir la durée en heures, unité de temps
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Étape 4 : Mettre à jour la durée de la tâche à 1 semaine
```java
// Augmenter la durée de la tâche à 1 semaine
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Étape 5 : diminuer la durée de la tâche
```java
// Diminuer la durée de la tâche
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
En suivant ces étapes, vous avez réussi à gérer la durée des tâches dans votre projet Aspose.Tasks for Java.
## Conclusion
Dans ce didacticiel, nous avons couvert les bases de la gestion de la durée des tâches à l'aide d'Aspose.Tasks pour Java. Vous pouvez désormais intégrer ces techniques en toute confiance dans vos projets pour une gestion efficace de la durée des tâches.
## FAQ
### Aspose.Tasks est-il compatible avec toutes les versions de Java ?
Aspose.Tasks est compatible avec Java 6 et les versions ultérieures.
### Puis-je utiliser Aspose.Tasks pour des projets commerciaux ?
 Oui, vous pouvez utiliser Aspose.Tasks pour des projets personnels et commerciaux. Visite[ici](https://purchase.aspose.com/buy) pour les détails de la licence.
### Où puis-je trouver une assistance et des ressources supplémentaires ?
 Visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien et les discussions de la communauté.
### Comment puis-je obtenir une licence temporaire à des fins de test ?
 Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/) pour les tests et l'évaluation.
### Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?
 Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/) pour explorer Aspose.Tasks avant de faire un achat.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
