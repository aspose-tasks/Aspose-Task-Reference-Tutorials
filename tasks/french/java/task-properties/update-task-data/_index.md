---
title: Mettre à jour les données de tâche au format MPP dans Aspose.Tasks
linktitle: Mettre à jour les données de tâche au format MPP dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment mettre à jour les données de tâches au format MPP à l'aide d'Aspose.Tasks pour Java. Suivez notre guide étape par étape pour une gestion de projet efficace.
weight: 35
url: /fr/java/task-properties/update-task-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mettre à jour les données de tâche au format MPP dans Aspose.Tasks

## Introduction
Bienvenue dans notre guide étape par étape sur la mise à jour des données de tâches au format MPP à l'aide d'Aspose.Tasks pour Java. Dans ce didacticiel, nous vous guiderons tout au long du processus, en veillant à ce que vous compreniez chaque étape avec clarté. Aspose.Tasks for Java fournit une solution robuste pour travailler avec les fichiers Microsoft Project, et à la fin de ce guide, vous serez en mesure de mettre à jour efficacement les données de tâches au format MPP.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.Tasks pour Java : assurez-vous que la bibliothèque Aspose.Tasks est installée. Vous pouvez le télécharger depuis le[page de sortie](https://releases.aspose.com/tasks/java/).
- Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système.
- Environnement de développement intégré (IDE) : utilisez un IDE de votre choix pour le développement Java.
## Importer des packages
Commencez par importer les packages nécessaires dans votre projet Java. L'extrait suivant montre comment importer des packages :
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Créer et configurer la tâche initiale
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continuer avec le reste du code)
```
## 2. Définir la date de début et la durée
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continuer avec le reste du code)
```
## 3. Créez une tâche récapitulative
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continuer avec le reste du code)
```
## 4. Définir la date limite et les notes de tâches
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continuer avec le reste du code)
```
## 5. Configurer les contraintes de tâches
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continuer avec le reste du code)
```
## 6. Créer des tâches supplémentaires
```java
//Créer 10 nouvelles tâches
for (int i = 0; i < 10; i++) {
    //... (Continuer avec le reste du code)
}
//... (Continuer avec le reste du code)
```
## 7. Enregistrez le projet
```java
// Enregistrez le projet
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
En suivant ces étapes, vous avez réussi à mettre à jour les données de tâches au format MPP à l'aide d'Aspose.Tasks pour Java.
## Conclusion
Toutes nos félicitations! Vous avez terminé un guide complet sur la mise à jour des données de tâches au format MPP à l'aide d'Aspose.Tasks pour Java. Cette puissante bibliothèque simplifie les tâches de gestion de projet, ce qui en fait un outil précieux pour les développeurs Java.
## FAQ
### Q : Où puis-je trouver la documentation Aspose.Tasks pour Java ?
 R : La documentation est disponible[ici](https://reference.aspose.com/tasks/java/).
### Q : Comment puis-je télécharger Aspose.Tasks pour Java ?
 R : Vous pouvez le télécharger à partir du[page de sortie](https://releases.aspose.com/tasks/java/).
### Q : Existe-t-il un essai gratuit ?
 R : Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks pour Java ?
 R : Visitez le forum d'assistance[ici](https://forum.aspose.com/c/tasks/15).
### Q : Proposez-vous des licences temporaires à des fins de test ?
 R : Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
