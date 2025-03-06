---
title: Mettre à jour et replanifier MS Project dans Aspose.Tasks
linktitle: Mettre à jour le projet et replanifier le travail inachevé dans Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment mettre à jour et replanifier des fichiers MS Project par programme à l'aide d'Aspose.Tasks pour Java.
weight: 23
url: /fr/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mettre à jour et replanifier MS Project dans Aspose.Tasks

## Introduction
Microsoft Project est un logiciel de gestion de projet largement utilisé qui permet aux utilisateurs de gérer efficacement les tâches, les ressources et les délais. Aspose.Tasks for Java fournit un ensemble puissant d'API pour manipuler les fichiers Microsoft Project par programme. Dans ce didacticiel, nous apprendrons comment mettre à jour les fichiers MS Project et replanifier les travaux inachevés à l'aide d'Aspose.Tasks pour Java.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2.  Aspose.Tasks pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
3. Compréhension de base du langage de programmation Java.

## Importer des packages
Tout d'abord, importez les packages nécessaires dans votre code Java :
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Étape 1 : Configurer le projet
Initialisez un nouvel objet Projet et définissez-y des tâches ainsi que leurs durées et dépendances.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Définir les tâches et leurs durées
// ...
// Définir les dépendances des tâches
// ...
// Enregistrer l'état initial du projet
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Étape 2 : Mettre à jour le travail du projet
Mettez à jour le travail du projet pour le marquer comme terminé jusqu'à une certaine date.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Enregistrez le projet mis à jour
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Étape 3 : Replanifier le travail inachevé
Replanifiez tout travail inachevé pour qu'il commence après une date spécifiée.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Enregistrez le projet reprogrammé
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusion
Dans ce didacticiel, nous avons appris comment mettre à jour les fichiers MS Project et replanifier les travaux inachevés à l'aide d'Aspose.Tasks pour Java. Cela peut être particulièrement utile dans les scénarios où les délais du projet doivent être ajustés en fonction des progrès ou de l'évolution des priorités.

## FAQ
### Q : Aspose.Tasks pour Java peut-il gérer des structures de projet complexes ?
R : Oui, Aspose.Tasks for Java fournit des API robustes pour gérer efficacement les tâches, les dépendances, les ressources et d'autres éléments du projet.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez bénéficier d'un essai gratuit auprès de[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir de l'assistance pour Aspose.Tasks pour Java ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute aide ou question.
### Q : Puis-je acheter une licence temporaire pour Aspose.Tasks pour Java ?
 R : Oui, des licences temporaires sont disponibles à l'achat[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je trouver une documentation détaillée pour Aspose.Tasks pour Java ?
 R : Vous pouvez vous référer à la documentation[ici](https://reference.aspose.com/tasks/java/) pour des guides complets et des références API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
