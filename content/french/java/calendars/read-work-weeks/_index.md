---
title: Lire les semaines de travail à partir du calendrier MS Project avec Aspose.Tasks
linktitle: Lire les semaines de travail à partir du calendrier avec Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Apprenez à lire les semaines de travail à partir du calendrier MS Project à l'aide d'Aspose.Tasks pour Java. Obtenez des instructions étape par étape dans ce didacticiel complet.
type: docs
weight: 15
url: /fr/java/calendars/read-work-weeks/
---
## Introduction
Dans ce didacticiel, nous verrons comment utiliser Aspose.Tasks pour Java pour lire les informations sur les semaines de travail à partir d'un calendrier Microsoft Project. Aspose.Tasks est une puissante bibliothèque Java qui vous permet de manipuler et de gérer les documents Microsoft Project par programme.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2.  Aspose.Tasks pour la bibliothèque Java téléchargée et installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
## Importer des packages
Tout d’abord, importons les packages nécessaires pour démarrer avec notre code :
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## Étape 1 : Configurez votre répertoire de données
Configurez le chemin du répertoire où se trouve votre fichier MS Project :
```java
String dataDir = "Your Data Directory";
```
## Étape 2 : Créer une instance de projet et accéder au calendrier
Créez une nouvelle instance de la classe Project et accédez à la collection de calendriers et de semaines de travail :
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## Étape 3 : Parcourir les semaines de travail
Parcourez la collection de semaines de travail et affichez leurs informations :
```java
for (WorkWeek workWeek : collection) {
    // Afficher le nom de la semaine de travail, les dates de début et de fin
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Accédez aux jours de la semaine et aux horaires de travail
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Traiter davantage les temps de travail si nécessaire
    }
}
```
## Conclusion
Dans ce didacticiel, nous avons appris à lire les informations sur les semaines de travail à partir d'un calendrier Microsoft Project à l'aide d'Aspose.Tasks pour Java. Cette puissante bibliothèque permet une manipulation transparente des fichiers de projet, permettant aux développeurs d'automatiser efficacement diverses tâches.
## FAQ
### Puis-je modifier les informations sur les semaines de travail à l'aide d'Aspose.Tasks pour Java ?
Oui, Aspose.Tasks fournit des API pour modifier, ajouter ou supprimer des semaines de travail et leurs informations associées.
### Aspose.Tasks est-il compatible avec différentes versions des fichiers Microsoft Project ?
Oui, Aspose.Tasks prend en charge différentes versions de fichiers Microsoft Project, notamment les formats MPP et XML.
### Puis-je intégrer Aspose.Tasks à d’autres frameworks Java ?
Absolument, Aspose.Tasks peut être intégré de manière transparente à d'autres frameworks et bibliothèques Java pour des fonctionnalités améliorées.
### Existe-t-il une version d’essai disponible pour Aspose.Tasks ?
 Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks à partir de[ici](https://releases.aspose.com/).
### Où puis-je trouver de l’assistance pour Aspose.Tasks ?
Vous pouvez trouver du support et de l'assistance sur le forum Aspose.Tasks[ici](https://forum.aspose.com/c/tasks/15).