---
title: Gestion des exceptions de calendrier dans Aspose.Tasks
linktitle: Gestion des exceptions de calendrier dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les exceptions de calendrier dans Aspose.Tasks pour .NET avec des didacticiels et des exemples étape par étape.
type: docs
weight: 12
url: /fr/net/calendar-scheduling/calendar-exceptions/
---
## Introduction

Dans ce didacticiel, nous verrons comment gérer les exceptions de calendrier dans Aspose.Tasks à l'aide du framework .NET. Les exceptions de calendrier nous permettent de définir des dates ou des périodes spéciales dans le calendrier d'un projet où l'horaire de travail régulier est modifié, comme les jours fériés ou les fermetures temporaires. Nous aborderons étape par étape diverses méthodes pour gérer les exceptions de calendrier, à l’aide d’Aspose.Tasks pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des prérequis suivants :
- Connaissance de base du langage de programmation C#.
- Visual Studio installé sur votre système.
- Aspose.Tasks pour la bibliothèque .NET ajoutée à votre projet.

## Importer des espaces de noms

Tout d'abord, importons les espaces de noms nécessaires à notre projet :

```csharp
using Aspose.Tasks;
using System;


```

## Étape 1 : suppression d'une exception de calendrier

Pour supprimer une exception de calendrier, procédez comme suit :

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Afficher les informations du calendrier
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Supprimer la première exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Étape 2 : Obtenir le temps de travail d'une exception de calendrier

Pour récupérer le temps de travail d'une exception de calendrier, procédez comme suit :

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Afficher les informations sur le calendrier et les exceptions
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Obtenez le temps de travail et affichez les détails
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Étape 3 : Définition des exceptions de calendrier

Pour ajouter ou supprimer des exceptions de calendrier, procédez comme suit :

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Créer une nouvelle exception de calendrier
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Définir les détails de l'exception
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Vérifiez si une date est une exception
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Ajouter l'exception au calendrier
    calendar.Exceptions.Add(exception);

    // Supprimer une exception si elle existe
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Ajouter une nouvelle exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Exceptions d'impression
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Conclusion

Dans cet article, nous avons abordé divers aspects de la gestion des exceptions de calendrier dans Aspose.Tasks pour .NET. En suivant les étapes fournies, vous pouvez gérer efficacement les exceptions dans les calendriers de votre projet, garantissant ainsi une représentation précise des heures de travail et des événements spéciaux.

## FAQ

### Q1 : Puis-je ajouter plusieurs exceptions à un seul calendrier ?

A1 : Oui, vous pouvez ajouter plusieurs exceptions à un calendrier pour tenir compte de diverses dates ou périodes spéciales.

### Q2 : Comment puis-je vérifier si une date spécifique constitue une exception ?

 A2 : Vous pouvez utiliser le`CheckException()` méthode pour vérifier si une date particulière relève d’une exception.

### Q3 : Est-il possible de supprimer une exception existante d’un calendrier ?

 A3 : Oui, vous pouvez supprimer des exceptions en accédant au`Exceptions` collecte du calendrier et utilisation du`Remove()` méthode.

### Q4 : Quels types d’exceptions de calendrier sont pris en charge ?

A4 : Aspose.Tasks prend en charge différents types d'exceptions, notamment les exceptions quotidiennes, hebdomadaires, mensuelles et annuelles, offrant ainsi une flexibilité dans la définition des règles d'exception.

### Q5 : Puis-je personnaliser les heures de travail pour des dates d'exception spécifiques ?

A5 : Oui, vous pouvez définir des horaires de travail personnalisés pour des dates d'exception individuelles en utilisant les méthodes appropriées fournies par Aspose.Tasks.