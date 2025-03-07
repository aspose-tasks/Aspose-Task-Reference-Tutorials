---
title: Collection d'exceptions de calendrier dans Aspose.Tasks
linktitle: Collection d'exceptions de calendrier dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer efficacement les exceptions de calendrier dans vos projets .NET à l'aide d'Aspose.Tasks, garantissant ainsi une planification et une gestion précises des ressources.
weight: 13
url: /fr/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Collection d'exceptions de calendrier dans Aspose.Tasks

## Introduction

En gestion de projet, une planification précise est essentielle au succès. Cependant, les scénarios réels nécessitent souvent des écarts par rapport aux horaires standards en raison de vacances, d'événements spéciaux ou d'autres facteurs. Aspose.Tasks for .NET fournit une solution robuste pour gérer de telles exceptions grâce à sa fonctionnalité de collecte d'exceptions de calendrier. Ce didacticiel vous guidera étape par étape tout au long du processus d'utilisation de cette fonctionnalité.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :

1.  Aspose.Tasks pour .NET : assurez-vous que la bibliothèque est installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/net/).
2. Connaissance de base de C# : Une connaissance du langage de programmation C# sera utile pour comprendre les exemples.
3. Environnement de développement : configurez votre environnement de développement préféré, tel que Visual Studio ou JetBrains Rider.

## Importer des espaces de noms

Avant de commencer à travailler avec Aspose.Tasks pour .NET, vous devez importer les espaces de noms requis dans votre projet. Cette étape permet d'accéder aux classes et méthodes nécessaires à la gestion des exceptions de calendrier.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Maintenant, décomposons l'exemple fourni en plusieurs étapes :

## Étape 1 : Charger le projet et récupérer le calendrier

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

Dans cette étape, nous chargeons un fichier projet et récupérons le calendrier souhaité par son UID.

## Étape 2 : Supprimer les exceptions existantes et définir un calendrier standard

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Cette étape efface toutes les exceptions existantes du calendrier et le définit sur une configuration standard.

## Étape 3 : Définir et ajouter une exception de temps de travail

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Cette étape définit une exception de temps de travail avec des dates de début et de fin spécifiques, ainsi que des heures de travail comprises dans ces dates, et l'ajoute au calendrier.

## Étape 4 : Définir et ajouter des exceptions de temps chômé

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Ajoutez plus d'exceptions si nécessaire

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Cette étape définit les exceptions de temps chômé, telles que les jours fériés, et les ajoute au calendrier.

## Étape 5 : Afficher les exceptions du calendrier

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

Cette étape affiche les exceptions de calendrier ajoutées ainsi que leurs détails.

## Étape 6 : Supprimer toutes les exceptions

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Enfin, cette étape supprime toutes les exceptions du calendrier.

## Conclusion

La gestion des exceptions de calendrier est cruciale pour une planification précise des projets. Aspose.Tasks for .NET simplifie cette tâche en fournissant un ensemble complet de fonctionnalités, notamment la collection d'exceptions de calendrier. En suivant les étapes décrites dans ce didacticiel, vous pouvez gérer efficacement divers scénarios de planification au sein de vos projets.

## FAQ

### Q1 : Puis-je ajouter plusieurs exceptions à un seul calendrier ?

 A1 : Oui, vous pouvez ajouter plusieurs exceptions à un calendrier à l'aide de l'outil`AddRange` méthode.

### Q2 : Comment gérer les exceptions récurrentes, telles que les jours fériés hebdomadaires ?

A2 : Vous pouvez calculer par programme les exceptions récurrentes et les ajouter au calendrier à l’aide d’une logique personnalisée.

### Q3 : Est-il possible d'importer des exceptions de calendrier à partir de sources externes ?

A3 : Oui, vous pouvez lire les exceptions de calendrier à partir de sources externes telles que des bases de données ou des fichiers CSV et les intégrer dans votre projet.

### Q4 : Que se passe-t-il s'il y a des exceptions qui se chevauchent dans le calendrier ?

A4 : Aspose.Tasks for .NET vous permet de gérer les exceptions qui se chevauchent en définissant des priorités ou en résolvant les conflits en fonction des exigences de votre projet.

### Q5 : Puis-je personnaliser les horaires de travail pour chaque jour dans le cadre d'une exception ?

A5 : Oui, vous pouvez spécifier des horaires de travail personnalisés pour des jours individuels dans le cadre d'une exception afin de répondre à des besoins de planification spécifiques.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
