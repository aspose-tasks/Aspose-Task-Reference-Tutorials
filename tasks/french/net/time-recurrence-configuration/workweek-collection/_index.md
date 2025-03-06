---
title: Personnaliser les semaines de travail dans Aspose.Tasks
linktitle: Collection de semaines de travail dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment personnaliser les semaines de travail dans Aspose.Tasks pour .NET. Guide étape par étape pour créer des calendriers de projet personnalisés. Télécharger maintenant!
weight: 17
url: /fr/net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personnaliser les semaines de travail dans Aspose.Tasks

## Introduction
Bienvenue dans notre tutoriel sur la création d'une semaine de travail personnalisée à l'aide d'Aspose.Tasks pour .NET ! Dans ce guide étape par étape, nous vous guiderons tout au long du processus de définition d'une semaine de travail personnalisée pour un calendrier de votre projet. Aspose.Tasks est une bibliothèque puissante qui permet aux développeurs de travailler efficacement avec les documents Microsoft Project dans leurs applications .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
1. Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur.
2.  Aspose.Tasks pour .NET : téléchargez et installez la bibliothèque Aspose.Tasks. Vous pouvez trouver le lien de téléchargement[ici](https://releases.aspose.com/tasks/net/).
3. Connaissance de base de C# : Familiarisez-vous avec les bases du langage de programmation C#.
## Importer des espaces de noms
Dans votre projet C#, assurez-vous d'importer les espaces de noms nécessaires :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Étape 1 : Créer un projet et un calendrier
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Étape 2 : Définir une semaine de travail personnalisée
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Étape 3 : Définir les jours ouvrables
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Étape 4 : Afficher les informations sur les semaines de travail
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Ce guide complet vous permet de créer et de gérer efficacement des semaines de travail personnalisées à l'aide d'Aspose.Tasks pour .NET.
## Conclusion
En conclusion, Aspose.Tasks for .NET fournit une solution robuste pour gérer les calendriers de projet avec des semaines de travail personnalisées. En suivant ce didacticiel, vous avez appris à créer et afficher des informations sur les semaines de travail personnalisées dans votre projet.
## FAQ
### Puis-je avoir plusieurs semaines de travail personnalisées dans un seul projet ?
Oui, vous pouvez ajouter plusieurs semaines de travail personnalisées à un calendrier de projet.
### Comment puis-je modifier les semaines de travail existantes ?
 Utilisez le`WorkWeek`propriétés et méthodes pour modifier les semaines de travail existantes.
### Aspose.Tasks est-il compatible avec .NET Core ?
Oui, Aspose.Tasks prend en charge .NET Core.
### Puis-je exporter le projet avec des semaines de travail personnalisées au format de fichier Microsoft Project ?
Absolument, Aspose.Tasks vous permet de sauvegarder votre projet dans différents formats, dont Microsoft Project.
### Où puis-je demander de l'aide pour les requêtes liées à Aspose.Tasks ?
 Visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour tout soutien ou assistance.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
