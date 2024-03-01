---
title: Répétition par jour de l'année dans Aspose.Tasks
linktitle: Répétition par jour de l'année dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les répétitions de jours d’année dans Aspose.Tasks pour .NET afin de rationaliser efficacement la gestion des tâches récurrentes.
type: docs
weight: 27
url: /fr/net/advanced-features/repetition-by-year-day/
---
## Introduction

Dans le domaine de la gestion de projet, une planification efficace des tâches et leur récurrence jouent un rôle essentiel pour garantir une exécution rapide et un flux de travail fluide. Aspose.Tasks for .NET offre une solution robuste permettant aux développeurs de gérer sans effort les tâches récurrentes au sein de leurs applications. Dans ce didacticiel, nous approfondissons les subtilités du travail avec les répétitions des jours de l'année à l'aide d'Aspose.Tasks, fournissant un guide complet pour créer des tâches récurrentes basées sur des modèles annuels.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Bibliothèque Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[site web](https://releases.aspose.com/tasks/net/).
   
2. Environnement de développement : configurez un environnement de développement approprié avec Visual Studio ou tout autre IDE préféré pour le développement .NET.

3. Connaissance de base de C# : Familiarisez-vous avec les principes fondamentaux du langage de programmation C# à suivre avec les exemples de code.

4. Concepts de gestion de projet : la compréhension des concepts de gestion de projet et de planification des tâches aidera à comprendre efficacement les concepts du didacticiel.

## Importer des espaces de noms

Avant de commencer le codage, importons les espaces de noms nécessaires pour faciliter la manipulation de nos tâches à l'aide d'Aspose.Tasks pour .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Maintenant, décomposons l'exemple fourni en plusieurs étapes et expliquons chaque étape en détail.

## Étape 1 : Charger le fichier de projet

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Ici, nous initialisons un nouveau`Project` objet et chargez un fichier de projet existant nommé "Project1.mpp".

## Étape 2 : Définir les paramètres des tâches récurrentes

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

 Dans cette étape, nous définissons les paramètres de notre tâche récurrente. Nous spécifions le nom de la tâche, la durée et le modèle de récurrence. Pour la récurrence annuelle, nous utilisons le`YearlyRecurrencePattern` et définissez la répétition pour qu'elle se produise le 1er juillet en utilisant`ByYearDayRepetition`. De plus, nous définissons la plage de récurrence du 1er juillet 2018 au 1er juillet 2019.

## Étape 3 : ajouter une tâche au projet

```csharp
project.RootTask.Children.Add(parameters);
```

Ici, nous ajoutons les paramètres de tâche récurrente définis à la tâche racine du projet.

## Étape 4 : Enregistrer le projet

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Enfin, nous sauvegardons le fichier projet modifié avec la tâche récurrente ajoutée.

## Conclusion

Dans ce didacticiel, nous avons exploré le processus de travail avec les répétitions de jours d'année dans Aspose.Tasks pour .NET. En suivant les étapes fournies, les développeurs peuvent intégrer de manière transparente la fonctionnalité de tâches récurrentes dans leurs applications, améliorant ainsi les capacités de gestion de projet.

## FAQ

### Q1 : Aspose.Tasks peut-il gérer des modèles de récurrence complexes ?

A1 : Oui, Aspose.Tasks fournit une prise en charge complète de divers modèles de récurrence, y compris les plus complexes comme les répétitions annuelles, mensuelles, hebdomadaires et quotidiennes.

### Q2 : Aspose.Tasks est-il compatible avec différents formats de fichiers de projet ?

A2 : Absolument, Aspose.Tasks prend en charge les formats de fichiers de projet populaires tels que MPP, XML et CSV, garantissant ainsi la compatibilité entre différents outils de gestion de projet.

### Q3 : Aspose.Tasks propose-t-il une documentation et une assistance aux développeurs ?

A3 : Oui, les développeurs peuvent accéder à une documentation complète et demander de l'aide sur les forums de la communauté Aspose.Tasks pour toute question ou problème qu'ils rencontrent.

### Q4 : Puis-je personnaliser les propriétés des tâches telles que la durée et la date de début à l'aide d'Aspose.Tasks ?

A4 : Certes, Aspose.Tasks fournit des API robustes pour manipuler les propriétés des tâches de manière dynamique, permettant aux développeurs de personnaliser les durées, les dates de début, les dépendances, etc.

### Q5 : Aspose.Tasks est-il adapté aux projets à petite échelle et au niveau de l'entreprise ?

A5 : En effet, Aspose.Tasks est conçu pour répondre aux besoins des développeurs travaillant sur des projets de toutes tailles, des tâches individuelles aux projets d'entreprise à grande échelle.