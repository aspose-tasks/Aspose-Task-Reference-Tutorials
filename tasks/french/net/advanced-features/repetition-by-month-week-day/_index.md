---
title: Répétition par mois semaine jour dans Aspose.Tasks
linktitle: Répétition par mois semaine jour dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment configurer des répétitions par mois, semaine et jour dans Aspose.Tasks pour .NET afin d'automatiser efficacement les tâches récurrentes.
type: docs
weight: 26
url: /fr/net/advanced-features/repetition-by-month-week-day/
---
## Introduction

Dans le domaine du développement de logiciels, en particulier dans les applications de gestion de projet, la capacité à gérer efficacement les tâches récurrentes est primordiale. Aspose.Tasks for .NET est une bibliothèque puissante conçue pour rationaliser la création et la gestion des tâches de projet, y compris les tâches récurrentes. L'une de ces fonctionnalités fournies par Aspose.Tasks est la possibilité de configurer des répétitions par mois, semaine et jour, garantissant que les tâches sont exécutées dans les délais sans intervention manuelle.

## Conditions préalables

Avant de plonger dans les subtilités de la configuration des répétitions par mois, semaine et jour à l'aide d'Aspose.Tasks pour .NET, assurez-vous d'avoir les conditions préalables suivantes en place :

1. Compréhension de base de C# : La connaissance du langage de programmation C# est essentielle pour comprendre et mettre en œuvre les exemples de code fournis.
   
2.  Installation d'Aspose.Tasks pour .NET : assurez-vous d'avoir téléchargé et installé la bibliothèque Aspose.Tasks pour .NET. Vous pouvez obtenir la bibliothèque auprès du[page de téléchargement](https://releases.aspose.com/tasks/net/).

3. Accès à un fichier de projet .mpp : préparez un fichier Microsoft Project (.mpp), car nous l'utiliserons pour démontrer la mise en œuvre des répétitions par mois, semaine et jour.

## Importer des espaces de noms

Pour commencer à utiliser Aspose.Tasks pour .NET dans votre application C#, vous devez importer les espaces de noms nécessaires. Voici comment procéder :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Décomposons l'extrait de code fourni en plusieurs étapes pour bien comprendre chaque partie.

## Étape 1 : Charger le fichier de projet

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Cette étape implique la création d'une nouvelle instance du`Project` classe et en chargeant un fichier Microsoft Project existant (`Project1.mpp`) à partir du répertoire spécifié.

## Étape 2 : Définir les paramètres des tâches récurrentes

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Dans cette étape, nous définissons les paramètres d'une tâche récurrente. Nous spécifions le nom de la tâche, la durée, le modèle de répétition (mensuel) et la plage de récurrence (terminée par une date spécifique).

## Étape 3 : Ajouter une tâche récurrente au projet

```csharp
project.RootTask.Children.Add(parameters);
```

Ici, nous ajoutons les paramètres de tâche récurrente définis à la tâche racine du projet.

## Étape 4 : Enregistrer le fichier de projet

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Enfin, nous sauvegardons le fichier projet modifié avec la tâche récurrente ajoutée.

## Conclusion

En conclusion, la configuration des répétitions par mois, semaine et jour dans Aspose.Tasks pour .NET est un processus simple qui permet aux développeurs d'automatiser efficacement la gestion des tâches récurrentes au sein de leurs projets. En suivant les étapes décrites dans ce didacticiel, vous pouvez intégrer de manière transparente cette fonctionnalité dans vos applications C#, économisant ainsi du temps et des efforts dans la gestion de projet.

## FAQ

###Q1 : Puis-je personnaliser le modèle de récurrence au-delà des exemples fournis ?

A1 : Oui, Aspose.Tasks for .NET offre des options de personnalisation étendues pour les modèles de récurrence, vous permettant de les adapter à vos besoins spécifiques.

###Q2 : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour .NET ?

 A2 : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks pour .NET à partir du[page des versions](https://releases.aspose.com/).

###Q3 : Comment puis-je obtenir une assistance pour Aspose.Tasks pour .NET ?

 A3 : Vous pouvez demander de l'aide et dialoguer avec la communauté sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

###Q4 : Des licences temporaires sont-elles disponibles pour Aspose.Tasks pour .NET ?

 A4 : Oui, vous pouvez acquérir des licences temporaires auprès du[page d'achat](https://purchase.aspose.com/temporary-license/) à des fins de tests et d’évaluation.

###Q5 : Où puis-je trouver une documentation complète pour Aspose.Tasks pour .NET ?

 A5 : Vous pouvez vous référer au détail[Documentation](https://reference.aspose.com/tasks/net/) disponible sur le site Web d'Aspose pour des conseils détaillés sur l'utilisation de la bibliothèque.