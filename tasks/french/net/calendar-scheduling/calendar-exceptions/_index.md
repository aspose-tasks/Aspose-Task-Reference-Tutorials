---
date: 2026-04-13
description: Apprenez comment supprimer une exception de calendrier dans Aspose.Tasks
  pour .NET et vérifier la date d’exception lors de la gestion de la planification
  du calendrier ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Supprimer une exception de calendrier avec Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Supprimer une exception de calendrier avec Aspose.Tasks
url: /fr/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Supprimer une exception de calendrier avec Aspose.Tasks

## Introduction

Dans ce tutoriel, vous apprendrez comment **supprimer une exception de calendrier** et gérer d'autres exceptions de calendrier dans Aspose.Tasks en utilisant le framework .NET. Les exceptions de calendrier vous permettent de modéliser les jours fériés, les fermetures temporaires ou toute période spéciale où l'horaire de travail habituel change. Comprendre comment ajouter, interroger et supprimer ces exceptions est essentiel pour une planification de projet précise, notamment dans les scénarios de **planification de calendrier ASP.NET**.

## Réponses rapides
- **Quelle est la méthode principale pour supprimer une exception ?** Utilisez la méthode `Delete()` sur l'objet `CalendarException`.  
- **Quelle classe vérifie une date par rapport à une exception ?** `CalendarException.CheckException()` — utile pour **vérifier la date d'exception**.  
- **Ai-je besoin d'une licence pour exécuter le code ?** Oui, une licence valide d'Aspose.Tasks est requise pour une utilisation en production.  
- **Puis-je ajouter plusieurs exceptions à un même calendrier ?** Absolument ; la collection `Exceptions` prend en charge de nombreuses entrées.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu'est-ce qu'une exception de calendrier ?

Une **exception de calendrier** représente une déviation du calendrier de travail habituel — pensez-y comme une règle qui indique « à ces dates, les heures de travail sont différentes ou inexistantes ». Dans Aspose.Tasks, chaque exception peut avoir ses propres heures de travail, son modèle de récurrence et des indicateurs précisant si le jour est ouvrable.

## Pourquoi gérer les exceptions de calendrier dans la planification de calendrier ASP.NET ?

- **Chronologies précises** : les projets tiennent automatiquement compte des jours fériés et des fermetures spéciales, évitant ainsi des échéances irréalistes.  
- **Flexibilité** : vous pouvez définir des modèles quotidiens, hebdomadaires, mensuels ou annuels, correspondant aux calendriers d'entreprise du monde réel.  
- **Automatisation** : vérifier programmatique une date d'exception vous permet de créer une logique de planification dynamique dans les applications ASP.NET.

## Pré-requis

- Connaissances de base en programmation C#.  
- Visual Studio (toute version récente).  
- Bibliothèque Aspose.Tasks pour .NET ajoutée à votre projet (via NuGet ou référence manuelle).  

## Importer les espaces de noms

Tout d'abord, importez les espaces de noms dont vous aurez besoin :

```csharp
using Aspose.Tasks;
using System;
```

## Étape 1 : Supprimer une exception de calendrier

Supprimer une exception indésirable est simple. Le code suivant charge un projet, sélectionne le premier calendrier, affiche des informations de base, supprime la première exception, puis montre le nombre mis à jour.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Astuce :** Vérifiez toujours que l'index de l'exception existe avant d'appeler `Delete()` afin d'éviter une `IndexOutOfRangeException`.

## Étape 2 : Obtenir le temps de travail d'une exception de calendrier

Si vous devez inspecter les heures de travail définies pour une exception, utilisez `GetWorkingTime()`. Cet exemple montre également comment **vérifier la date d'exception** avec `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Étape 3 : Définir les exceptions de calendrier

Voici un exemple complet qui montre comment **ajouter**, **vérifier** et **supprimer** des exceptions de calendrier. Remarquez l'utilisation de `CheckException` pour **vérifier la date d'exception** à un moment précis.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Problèmes courants et astuces

| Problème | Raison | Solution |
|----------|--------|----------|
| **`IndexOutOfRangeException` lors de la suppression** | Tentative de suppression d'une exception qui n'existe pas. | Vérifiez que `calendar.Exceptions.Count` > index avant d'appeler `Delete()`. |
| **Heures de travail incorrectes** | Non définition correcte de `DayWorking` ou `WorkingTimes`. | Utilisez `exception.WorkingTimes.Add(new WorkingTime(...))` pour définir des périodes explicites. |
| **Exception non reconnue** | `CheckException` renvoie `false` parce que la date est en dehors de la plage définie. | Revérifiez `FromDate`/`ToDate` et le `Type` (Daily, Weekly, etc.). |

## Foire aux questions

**Q : Puis-je ajouter plusieurs exceptions à un même calendrier ?**  
R : Oui, vous pouvez ajouter autant d'exceptions que nécessaire pour représenter les jours fériés, les fenêtres de maintenance ou toute règle de planification spéciale.

**Q : Comment **vérifier la date d'exception** pour un jour spécifique ?**  
R : Utilisez la méthode `CheckException(DateTime date)` sur une instance de `CalendarException`. Elle renvoie `true` si la date fournie se situe dans la plage de l'exception.

**Q : Est-il possible de supprimer une exception existante d'un calendrier ?**  
R : Absolument. Accédez à la collection `Exceptions` et appelez `Remove()` ou invoquez `Delete()` sur l'objet `CalendarException` spécifique.

**Q : Quels types d'exceptions de calendrier sont pris en charge ?**  
R : Aspose.Tasks prend en charge les types d'exception Daily, Weekly, Monthly et Yearly, vous offrant la flexibilité de modéliser presque n'importe quel modèle de récurrence.

**Q : Puis-je personnaliser les heures de travail pour des dates d'exception spécifiques ?**  
R : Oui. Après avoir créé une exception, remplissez sa collection `WorkingTimes` avec des objets `WorkingTime` qui définissent les heures de début et de fin pour ce jour.

## Conclusion

Nous avons parcouru le cycle complet des opérations de **suppression d'exception de calendrier**, de l'inspection des exceptions existantes à l'ajout de nouvelles et à la vérification des dates. Maîtriser ces techniques garantit que vos plannings de projet respectent les calendriers du monde réel, rendant vos implémentations de planification de calendrier ASP.NET robustes et fiables.

---

**Dernière mise à jour :** 2026-04-13  
**Testé avec :** Aspose.Tasks pour .NET (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}