---
title: Définition des paramètres de tâches récurrentes dans Aspose.Tasks
linktitle: Définition des paramètres de tâches récurrentes dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment définir les paramètres de tâches récurrentes dans Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Tutoriel complet avec guide étape par étape.
weight: 14
url: /fr/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définition des paramètres de tâches récurrentes dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus de définition des paramètres des tâches récurrentes de Microsoft Project à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Compréhension de base du langage de programmation C#.
2. Visual Studio installé ou tout autre IDE C#.
3. Aspose.Tasks pour la bibliothèque .NET installée et référencée dans votre projet.

## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires dans votre code C# :
```csharp
using Aspose.Tasks;
using System;

```
## Étape 1 : Définir le répertoire des documents
```csharp
String DataDir = "Your Document Directory";
```
 Remplacer`"Your Document Directory"` avec le chemin d'accès à votre répertoire de documents.
## Étape 2 : charger le fichier de projet
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Cette ligne de code charge le fichier Microsoft Project dans le`project` variable.
## Étape 3 : Définir les paramètres des tâches récurrentes
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Ici, vous définissez les paramètres de la tâche récurrente tels que le nom de la tâche, la durée, le modèle de récurrence, la plage de récurrence et s'il faut ignorer le calendrier des ressources.
## Étape 4 : Définir le calendrier pour les tâches récurrentes
```csharp
parameters.SetCalendar(project, "Standard");
```
Cette étape définit le calendrier de la tâche récurrente. Dans cet exemple, il définit le calendrier sur « Standard ».
## Étape 5 : ajouter des paramètres au projet
```csharp
project.RootTask.Children.Add(parameters);
```
Enfin, ajoutez les paramètres à la tâche racine du projet.

## Conclusion
Dans ce didacticiel, nous avons montré comment définir les paramètres des tâches récurrentes de Microsoft Project à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez gérer efficacement les tâches récurrentes dans vos projets.
## FAQ
### Puis-je personnaliser davantage le modèle de récurrence ?
Oui, Aspose.Tasks propose divers modèles et options de récurrence à personnaliser en fonction des exigences de votre projet.
### Existe-t-il une version d'essai disponible avant d'acheter ?
 Oui, vous pouvez télécharger un essai gratuit depuis Aspose.Tasks[site web](https://purchase.aspose.com/buy) pour évaluer les fonctionnalités de la bibliothèque.
### Aspose.Tasks prend-il en charge d'autres formats de fichiers de projet ?
Oui, Aspose.Tasks prend en charge divers formats de fichiers de projet, notamment MPP, XML, XLSX, etc.
### Puis-je obtenir de l’aide si je rencontre des problèmes lors de la mise en œuvre ?
Oui, vous pouvez visiter le forum Aspose.Tasks pour obtenir l'aide de la communauté ou contacter le support pour une aide directe.
### Comment puis-je obtenir une licence temporaire pour Aspose.Tasks ?
 Vous pouvez obtenir une licence temporaire auprès du[site web](https://purchase.aspose.com/temporary-license/) à des fins de tests.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
