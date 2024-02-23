---
title: Répétition du calendrier quotidien dans Aspose.Tasks
linktitle: Répétition du calendrier quotidien dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment créer des tâches récurrentes avec des répétitions de calendrier quotidiennes dans Aspose.Tasks pour .NET. Améliorez l’efficacité de la gestion de projet sans effort.
type: docs
weight: 25
url: /fr/net/calendar-scheduling/daily-calendar-repetition/
---
## Introduction

 Aspose.Tasks for .NET fournit un ensemble puissant d'outils pour gérer les tâches et les projets par programmation. L'une de ses caractéristiques notables est la capacité de gérer efficacement les répétitions quotidiennes du calendrier. Dans ce didacticiel, nous explorerons comment utiliser le`DailyCalendarRepetition` classe avec d'autres classes pertinentes pour créer des tâches récurrentes avec des répétitions quotidiennes basées sur un calendrier spécifié.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir la configuration suivante :

1.  Installation : assurez-vous que Aspose.Tasks pour .NET est installé. Sinon, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).

2. Importation d'espaces de noms : importez les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Étape 1 : initialiser le projet

Tout d'abord, nous devons charger un projet existant ou en créer un nouveau avec lequel travailler :

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Étape 2 : Définir le calendrier

Ensuite, nous créons un calendrier d'une durée de 24 heures et l'associons au projet :

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Étape 3 : Définir les paramètres des tâches récurrentes

Maintenant, définissons les paramètres de notre tâche récurrente. Nous définissons son nom, sa durée, son modèle de récurrence et sa plage :

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Étape 4 : Définir le calendrier pour la tâche

Associez le calendrier défini à la tâche :

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Étape 5 : ajouter une tâche au projet

Ajoutez la tâche avec les paramètres définis au projet :

```csharp
project.RootTask.Children.Add(parameters);
```

## Étape 6 : Enregistrez le projet

Enfin, enregistrez le projet avec la tâche récurrente ajoutée :

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Vous avez maintenant créé avec succès un projet avec une tâche récurrente définie pour se répéter quotidiennement sur la base d'un calendrier de 24 heures à l'aide d'Aspose.Tasks pour .NET !

## Conclusion

Dans ce didacticiel, nous avons montré comment utiliser Aspose.Tasks pour .NET pour gérer efficacement les répétitions quotidiennes du calendrier. En suivant ces étapes, vous pouvez intégrer de manière transparente des tâches récurrentes dans vos projets, améliorant ainsi la productivité et l'organisation.

## FAQ

### Q1 : Puis-je personnaliser la durée de chaque répétition ?

A1 : Oui, vous pouvez ajuster la durée de chaque répétition selon vos besoins en modifiant les paramètres dans le code.

### Q2 : Est-il possible de définir différents calendriers pour différentes tâches au sein du même projet ?

A2 : Absolument, Aspose.Tasks vous permet d'attribuer des calendriers spécifiques à des tâches individuelles, offrant ainsi une flexibilité de planification.

### Q3 : Aspose.Tasks prend-il en charge d'autres modèles de récurrence en dehors du quotidien ?

A3 : Oui, Aspose.Tasks propose un large éventail de modèles de récurrence tels que hebdomadaire, mensuel, annuel, etc., répondant aux divers besoins du projet.

### Q4 : Puis-je visualiser les tâches récurrentes créées à l'aide d'Aspose.Tasks ?

A4 : Certes, Aspose.Tasks propose des options de visualisation pour vous aider à analyser et suivre efficacement les tâches récurrentes.

### Q5 : Existe-t-il une version d’essai disponible pour Aspose.Tasks ?

 A5 : Oui, vous pouvez bénéficier d'un essai gratuit d'Aspose.Tasks à partir de[ici](https://releases.aspose.com/) pour explorer ses fonctionnalités avant de faire un achat.