---
title: Gestion de la collection de types de jours dans Aspose.Tasks
linktitle: Gestion de la collection de types de jours dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les collections de type jour dans Aspose.Tasks pour .NET. Créez, modifiez et manipulez facilement les exceptions de calendrier.
weight: 28
url: /fr/net/calendar-scheduling/day-type-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestion de la collection de types de jours dans Aspose.Tasks

## Introduction

 Aspose.Tasks for .NET fournit des fonctionnalités robustes pour gérer les collections de types de jours, cruciales pour définir des exceptions de calendrier hebdomadaire dans les applications de gestion de projet. Dans ce didacticiel, nous explorerons comment utiliser le`DayTypeCollection` classe efficacement. 

## Conditions préalables

Avant de poursuivre le didacticiel, assurez-vous de disposer des prérequis suivants :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système.
2.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Connaissance de base de C# : Familiarité avec le langage de programmation C# et les concepts du framework .NET.

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet C# :

```csharp
using Aspose.Tasks;
using System;


```

Maintenant, décomposons l'exemple fourni en plusieurs étapes :

## Étape 1 : Charger le projet et accéder au calendrier

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Cette étape initialise une nouvelle instance de projet et récupère le calendrier par son UID.

## Étape 2 : Parcourir les exceptions du calendrier

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Ici, nous parcourons chaque exception du calendrier et imprimons son nom et les types de jours associés.

## Étape 3 : Modifier les exceptions du calendrier

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Cette étape montre comment modifier les exceptions du calendrier en ajoutant, supprimant ou mettant à jour des types de jours.

## Étape 4 : Créer et gérer de nouvelles exceptions de calendrier

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

Dans cette dernière étape, nous créons de nouvelles exceptions de calendrier et les manipulons en ajoutant et en copiant des types de jours.

## Conclusion

 En conclusion, la gestion des collections de types de jours dans Aspose.Tasks pour .NET est essentielle pour définir et modifier les exceptions de calendrier hebdomadaire dans les applications de gestion de projet. En suivant le guide étape par étape fourni dans ce didacticiel, vous pouvez utiliser efficacement le`DayTypeCollection` classe pour gérer diverses opérations de calendrier.

## FAQ

### Q1 : Aspose.Tasks pour .NET peut-il être utilisé pour créer des diagrammes de Gantt par programme ?

A1 : Oui, Aspose.Tasks pour .NET fournit des API pour créer et manipuler des diagrammes de Gantt dans les applications .NET.

### Q2 : Aspose.Tasks pour .NET est-il compatible avec .NET Core et .NET Framework ?

A2 : Oui, Aspose.Tasks pour .NET prend en charge à la fois .NET Core et .NET Framework.

### Q3 : Comment puis-je obtenir de l'assistance pour Aspose.Tasks pour .NET ?

 A3 : Vous pouvez obtenir de l'aide en visitant le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) où vous pouvez poser des questions et interagir avec d’autres utilisateurs.

### Q4 : Aspose.Tasks pour .NET propose-t-il un essai gratuit ?

 A4 : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/).

### Q5 : Puis-je acheter une licence temporaire pour Aspose.Tasks pour .NET ?

 R5 : Oui, des licences temporaires sont disponibles à l'achat auprès du[Site Aspose](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
