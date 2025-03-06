---
title: Obtenez les heures de travail du calendrier à l'aide d'Aspose.Tasks
linktitle: Obtenez les heures de travail du calendrier à l'aide d'Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Extrayez facilement les heures de travail des calendriers MS Project avec Aspose.Tasks pour Java. Simplifiez les tâches de gestion de projet.
type: docs
weight: 13
url: /fr/java/calendars/working-hours/
---
## Introduction
La gestion des calendriers de projet et l’extraction des heures de travail sont essentielles pour une gestion de projet efficace. Aspose.Tasks for Java fournit des fonctionnalités robustes pour récupérer sans effort les heures de travail des calendriers MS Project. Dans ce tutoriel, nous vous guiderons pas à pas tout au long du processus.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour Java téléchargée et ajoutée à votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/java/).
3. Compréhension de base du langage de programmation Java.
## Importer des packages
Tout d’abord, importez les packages nécessaires pour travailler avec Aspose.Tasks for Java :
```java
import com.aspose.tasks.*;
```
## Étape 1 : Charger le fichier de projet
Commencez par charger votre fichier MS Project :
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Étape 2 : Récupérer les informations sur les tâches et le calendrier
Extrayez les détails des tâches et du calendrier du projet :
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Étape 3 : Définir les dates de début et de fin
Définissez les dates de début et de fin de la tâche :
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Étape 4 : Parcourir les dates
Parcourez les dates pendant la durée de la tâche :
```java
java.util.Calendar tempDate = calStartDate;
```
## Étape 5 : Calculer la durée
Calculez la durée en minutes, heures et jours :
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Conclusion
Dans ce didacticiel, nous avons expliqué comment récupérer les heures de travail d'un calendrier MS Project à l'aide d'Aspose.Tasks pour Java. En suivant ces étapes, vous pouvez gérer efficacement les calendriers de projet et calculer facilement la durée des tâches.
## FAQ
### Q : Aspose.Tasks pour Java peut-il gérer des structures de projet complexes ?
R : Oui, Aspose.Tasks for Java fournit une prise en charge complète pour la gestion des structures de projet complexes, notamment les tâches, les ressources et les calendriers.
### Q : Aspose.Tasks pour Java est-il compatible avec différentes versions de MS Project ?
R : Absolument, Aspose.Tasks for Java prend en charge différentes versions de MS Project, garantissant ainsi la compatibilité entre différents environnements.
### Q : Puis-je personnaliser les heures de travail et les jours fériés dans les calendriers de projet ?
R : Oui, vous pouvez facilement personnaliser les heures de travail et les jours fériés en fonction des exigences de votre projet à l'aide des API Aspose.Tasks pour Java.
### Q : Aspose.Tasks pour Java propose-t-il une assistance et une documentation ?
: Oui, Aspose.Tasks for Java fournit une documentation complète et des forums d'assistance dédiés pour aider les développeurs à utiliser efficacement ses fonctionnalités.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour Java ?
 R : Oui, vous pouvez accéder à une version d'essai gratuite d'Aspose.Tasks for Java à partir de[ici](https://releases.aspose.com/).