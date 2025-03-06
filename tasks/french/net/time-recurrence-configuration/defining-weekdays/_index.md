---
title: Maîtriser les jours de la semaine dans Aspose.Tasks pour .NET
linktitle: Définir les jours de la semaine dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez la puissance de la définition des jours de la semaine dans Aspose.Tasks .NET. Suivez notre didacticiel détaillé pour gérer efficacement les calendriers de projets, personnaliser les temps de travail et bien plus encore.
weight: 10
url: /fr/net/time-recurrence-configuration/defining-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser les jours de la semaine dans Aspose.Tasks pour .NET

## Introduction
Si vous plongez dans le monde de la gestion de projet en utilisant Aspose.Tasks pour .NET, comprendre et manipuler les jours de la semaine est un aspect crucial. La gestion et la personnalisation efficaces des jours de la semaine dans le calendrier de votre projet peuvent avoir un impact significatif sur les délais du projet. Dans ce didacticiel, nous vous guiderons tout au long du processus de définition des jours de la semaine à l'aide d'Aspose.Tasks, en fournissant des instructions étape par étape et des exemples pour une meilleure clarté.
## Conditions préalables
Avant de vous lancer dans cette aventure, assurez-vous de disposer des prérequis suivants :
- Compréhension de base du langage de programmation C#.
-  Aspose.Tasks pour la bibliothèque .NET installée. Sinon, téléchargez-le depuis[ici](https://releases.aspose.com/tasks/net/).
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Vérifiez l'égalité des jours de semaine
```csharp
// Votre répertoire de documents
String DataDir = "Your Document Directory";
// Charger le fichier de projet
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Accès en semaine
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Vérifier l'égalité en fonction de diverses propriétés
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Ajoutez des instructions de sortie similaires pour DayWorking, FromDate, ToDate et WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Cloner un jour de la semaine
```csharp
// Charger le fichier de projet
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Créer une copie complète du jour de la semaine
var weekDay2 = weekDay1.Clone();
// Propriétés de sortie des deux jours de la semaine
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Ajoutez des instructions de sortie similaires pour DayWorking, FromDate, ToDate et WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Obtenez le code de hachage d'un jour de la semaine
```csharp
// Charger le fichier de projet
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Propriétés de sortie des deux jours de la semaine
// Ajoutez des instructions de sortie similaires pour DayWorking, FromDate, ToDate et WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Créez un nouveau calendrier avec des jours de semaine définis
```csharp
// Créer un nouveau projet
var project = new Project();
// Définir un calendrier
var calendar = project.Calendars.Add("Calendar1");
// Ajouter des jours ouvrables et un jour d'exception
// Ajouter des instructions de sortie similaires pour FromDate et ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Fixer les horaires de travail pour le vendredi
// Ajoutez des instructions de sortie similaires pour DayWorking, FromDate, ToDate et WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Définir le temps de travail par défaut pour une journée
```csharp
// Créer un nouveau projet
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Ajouter des horaires de travail par défaut du lundi au vendredi
// Ajoutez des instructions de sortie similaires pour DayWorking, FromDate, ToDate et WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Répéter pour mardi, mercredi, jeudi et vendredi
// Définir les jours non ouvrés pour le samedi et le dimanche
// Ajoutez des instructions de sortie similaires pour DayWorking, FromDate, ToDate et WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Conclusion
Dans ce didacticiel, nous avons abordé les aspects essentiels de la définition des jours de la semaine dans Aspose.Tasks pour .NET. La manipulation des jours de la semaine est une compétence clé pour une gestion de projet efficace. Expérimentez avec les exemples fournis, adaptez-les aux besoins de votre projet et libérez tout le potentiel d'Aspose.Tasks.
## FAQ
### Puis-je définir des horaires de travail personnalisés pour chaque jour ?
Oui, vous pouvez définir des horaires de travail personnalisés pour des jours de semaine spécifiques à l'aide des exemples fournis.
### Est-il possible d'ajouter plusieurs jours d'exception au calendrier ?
Absolument. Modifiez le code du quatrième exemple pour inclure des jours d'exception supplémentaires.
### Comment puis-je supprimer un jour de la semaine spécifique du calendrier ?
Utilisez les méthodes appropriées fournies par la bibliothèque Aspose.Tasks pour supprimer les jours de la semaine si nécessaire.
### Les modifications apportées aux jours de la semaine sont-elles persistantes dans le fichier projet ?
Oui, toute modification apportée aux jours de la semaine est reflétée dans le fichier de projet lors de son enregistrement.
### Puis-je utiliser Aspose.Tasks avec d’autres langages de programmation ?
Aspose.Tasks prend en charge divers langages de programmation, mais les exemples ici sont spécifiquement destinés à .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
