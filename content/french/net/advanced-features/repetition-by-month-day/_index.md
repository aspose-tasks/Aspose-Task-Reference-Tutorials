---
title: Répétition par mois et jour dans Aspose.Tasks
linktitle: Répétition par mois et jour dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer les tâches récurrentes dans les projets .NET avec Aspose.Tasks. Guide étape par étape pour gérer la répétition par jour du mois.
type: docs
weight: 25
url: /fr/net/advanced-features/repetition-by-month-day/
---
## Introduction

Dans le domaine du développement .NET, Aspose.Tasks constitue un outil puissant pour gérer les tâches et les calendriers d'un projet. Il offre une multitude de fonctionnalités pour rationaliser les flux de travail de gestion de projet, notamment la gestion des tâches récurrentes. La répétition par jour du mois est une exigence courante dans la planification de projets, et Aspose.Tasks fournit une prise en charge robuste pour ce scénario.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :

1. Compréhension de base de C# : une familiarité avec le langage de programmation C# est nécessaire pour comprendre les concepts abordés dans ce didacticiel.
2. Installation d'Aspose.Tasks pour .NET : assurez-vous d'avoir installé Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
3. Environnement de développement intégré (IDE) : installez un IDE tel que Visual Studio sur votre système pour faciliter le codage.

## Importer des espaces de noms

Dans votre projet C#, importez les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Tasks :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Décomposons l'exemple de code fourni sous la forme d'un guide étape par étape :

## Étape 1 : Charger le fichier de projet

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Cette ligne de code initialise une nouvelle instance du`Project` classe, en chargeant le fichier projet nommé "Project1.mpp".

## Étape 2 : Définir les paramètres des tâches récurrentes

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

Cette section définit les paramètres de la tâche récurrente, notamment son nom, sa durée, son modèle de répétition et sa plage de récurrence.

## Étape 3 : ajouter une tâche au projet

```csharp
project.RootTask.Children.Add(parameters);
```

Ici, nous ajoutons les paramètres des tâches récurrentes au projet.

## Étape 4 : Enregistrer le fichier de projet

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Enfin, le projet modifié est enregistré avec la tâche récurrente ajoutée.

## Conclusion

Dans ce didacticiel, nous avons exploré comment gérer la répétition par jour du mois dans Aspose.Tasks pour .NET. En suivant les étapes fournies, vous pouvez gérer efficacement les tâches récurrentes dans les délais de votre projet.

## FAQ

### Q1 : Aspose.Tasks est-il compatible avec toutes les versions de .NET ?

A1 : Aspose.Tasks prend en charge différentes versions du framework .NET, garantissant la compatibilité entre différents environnements.

### Q2 : Puis-je personnaliser davantage le modèle de récurrence ?

A2 : Oui, Aspose.Tasks offre des options de personnalisation étendues pour définir des modèles de récurrence en fonction des exigences spécifiques du projet.

### Q3 : Aspose.Tasks prend-il en charge d'autres fonctionnalités de gestion de projet ?

A3 : Absolument, Aspose.Tasks offre un large éventail de fonctionnalités pour la gestion de projet, notamment le suivi des tâches, l'allocation des ressources et la génération de diagrammes de Gantt.

### Q4 : Existe-t-il une version d’essai disponible pour Aspose.Tasks ?

 A4 : Oui, vous pouvez bénéficier d'un essai gratuit auprès de[ici](https://releases.aspose.com/) pour explorer les capacités d'Aspose.Tasks avant de prendre une décision d'achat.

### Q5 : Où puis-je demander de l'aide si je rencontre des problèmes ou si j'ai des questions ?

 A5 : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour demander le soutien de la communauté ou de l’équipe Aspose.