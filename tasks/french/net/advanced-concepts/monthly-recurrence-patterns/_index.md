---
title: Gestion des modèles de récurrence mensuelle dans Aspose.Tasks
linktitle: Gestion des modèles de récurrence mensuelle dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les modèles de récurrence mensuelle dans Aspose.Tasks pour .NET avec ce didacticiel étape par étape.
type: docs
weight: 18
url: /fr/net/advanced-concepts/monthly-recurrence-patterns/
---
## Introduction

Aspose.Tasks for .NET est une API puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project par programme. L’une des fonctionnalités essentielles qu’il offre est la capacité de gérer efficacement les tâches récurrentes. Dans ce didacticiel, nous verrons comment utiliser les modèles de récurrence mensuelle à l'aide d'Aspose.Tasks, étape par étape.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont installées :

## Importer des espaces de noms

Tout d'abord, assurez-vous d'avoir importé les espaces de noms nécessaires dans votre projet .NET :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Maintenant, décomposons le processus de gestion des modèles de récurrence mensuelle en plusieurs étapes :

## Étape 1 : initialiser le projet

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Étape 2 : définir les paramètres des tâches récurrentes

Définissez les paramètres de la tâche récurrente, notamment le nom de la tâche, la durée et le modèle de récurrence :

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Étape 3 : Ajouter des paramètres au projet

```csharp
project.RootTask.Children.Add(parameters);
```

## Étape 4 : Enregistrez le projet

Enregistrez le projet modifié avec la tâche récurrente :

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Conclusion

La gestion des modèles de récurrence mensuelle dans Aspose.Tasks pour .NET est simple et efficace. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement créer des tâches récurrentes avec des intervalles mensuels et des plages de récurrence spécifiques.

## FAQ

### Q1 : Aspose.Tasks est-il compatible avec toutes les versions des fichiers Microsoft Project ?

A1 : Aspose.Tasks prend en charge différentes versions de fichiers Microsoft Project, notamment MPP, MPT, XML et MPX.

### Q2 : Puis-je personnaliser davantage le modèle de récurrence ?

A2 : Oui, Aspose.Tasks propose de nombreuses options pour personnaliser les modèles de récurrence, notamment quotidiens, hebdomadaires, mensuels et annuels.

### Q3 : Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?

 A3 : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks sur le site Web.[ici](https://releases.aspose.com/).

### Q4 : Comment puis-je obtenir de l'aide pour Aspose.Tasks ?

 A4 : Vous pouvez demander de l'aide et participer aux discussions sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5 : Où puis-je acheter une licence pour Aspose.Tasks ?

 A5 : Vous pouvez acheter une licence pour Aspose.Tasks sur le site Web[ici](https://purchase.aspose.com/buy)