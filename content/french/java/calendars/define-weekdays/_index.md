---
title: Définir les jours de la semaine dans le calendrier avec Aspose.Tasks
linktitle: Définir les jours de la semaine dans le calendrier avec Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Découvrez comment définir les jours de la semaine dans le calendrier MS Project à l'aide d'Aspose.Tasks pour Java. Personnalisez les jours et les horaires de travail sans effort.
type: docs
weight: 12
url: /fr/java/calendars/define-weekdays/
---
## Introduction
Dans ce didacticiel, nous allons parcourir le processus de définition des jours de la semaine dans un calendrier MS Project à l'aide d'Aspose.Tasks pour Java. Aspose.Tasks est une puissante bibliothèque Java qui permet aux développeurs de manipuler les fichiers Microsoft Project par programme.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système. Vous pouvez le télécharger depuis le[Site Web d'Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) si ce n'est pas déjà fait.
2.  Bibliothèque Aspose.Tasks for Java : téléchargez et installez la bibliothèque Aspose.Tasks for Java à partir du[page de téléchargement](https://releases.aspose.com/tasks/java/). Suivez les instructions d'installation fournies dans la documentation.

## Importer des packages
Pour commencer, importez les packages nécessaires pour travailler avec Aspose.Tasks dans votre projet Java :
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Étape 1 : Créer une instance de projet
Instanciez un objet Project, qui représente le fichier MS Project avec lequel vous allez travailler :
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Étape 2 : Définir le calendrier
Créez une nouvelle instance de calendrier et ajoutez-la au projet :
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Étape 3 : ajouter des jours ouvrables
Définissez les jours ouvrables en ajoutant du lundi au jeudi avec des horaires par défaut :
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Étape 4 : Définir un jour ouvrable personnalisé
Définissez le samedi et le dimanche comme jours ouvrables :
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Étape 5 : Définir une journée de travail courte
Définissez le vendredi comme une journée de travail courte avec des horaires de travail personnalisés :
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## Étape 6 : Enregistrez le projet
Enregistrez le projet modifié dans un fichier XML :
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Conclusion
Toutes nos félicitations! Vous avez défini avec succès les jours de la semaine dans un calendrier MS Project à l'aide d'Aspose.Tasks pour Java. Vous pouvez désormais intégrer cette fonctionnalité dans vos applications Java pour manipuler les fichiers MS Project par programme.
## FAQ
### Q1 : Puis-je définir des jours non ouvrés personnalisés à l’aide d’Aspose.Tasks pour Java ?
 R : Oui, vous pouvez définir des jours non ouvrés personnalisés en définissant le`DayWorking` propriété à`false` pour le jour de la semaine concerné.
### Q2 : Comment puis-je ajouter des jours fériés au calendrier ?
 R : Vous pouvez ajouter des jours fériés en créant des instances de`CalendarExceptions`et en précisant les dates non travaillées.
### Q3 : Aspose.Tasks est-il compatible avec différentes versions de fichiers MS Project ?
R : Oui, Aspose.Tasks prend en charge différentes versions de fichiers MS Project, notamment les formats MPP, MPT et XML.
### Q4 : Puis-je modifier les calendriers existants dans un fichier MS Project ?
R : Oui, vous pouvez charger un projet existant avec des calendriers, apporter des modifications, puis enregistrer les modifications dans le fichier d'origine.
### Q5 : Aspose.Tasks prend-il en charge les tâches récurrentes ?
R : Oui, Aspose.Tasks vous permet de travailler avec des tâches récurrentes, notamment en définissant leurs modèles de récurrence et leurs durées.