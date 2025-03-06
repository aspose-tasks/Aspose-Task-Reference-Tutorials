---
title: Utilisation de l'algorithme d'arborescence dans Aspose.Tasks
linktitle: Utilisation de l'algorithme d'arborescence dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à manipuler efficacement les hiérarchies de tâches dans vos projets .NET à l'aide de l'algorithme d'arborescence d'Aspose.Tasks.
type: docs
weight: 13
url: /fr/net/advanced-concepts/tree-algorithm/
---
## Introduction

Aspose.Tasks for .NET fournit des fonctionnalités puissantes pour travailler avec des tâches, des ressources et des calendriers de gestion de projet. L'une de ces fonctionnalités est l'algorithme d'arborescence, qui permet aux utilisateurs de manipuler efficacement les hiérarchies de tâches. Dans ce didacticiel, nous explorerons comment utiliser l'algorithme d'arborescence dans Aspose.Tasks pour .NET pour rassembler le travail commun et mettre à jour les valeurs de travail au sein d'un projet.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système.
2.  Aspose.Tasks pour .NET : téléchargez et installez Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Compréhension de base de C# : une connaissance du langage de programmation C# est requise pour suivre les exemples.

## Importer des espaces de noms

Dans votre projet C#, importez les espaces de noms nécessaires pour utiliser les fonctionnalités Aspose.Tasks :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Maintenant, décomposons chaque exemple en plusieurs étapes :

## Étape 1 : Charger le fichier de projet

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Chargez le fichier de projet en mémoire à l'aide du`Project` classe.

## Étape 2 : Définir la hiérarchie des tâches

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Définissez la hiérarchie des tâches en ajoutant des tâches parent et enfant.

## Étape 3 : Définir les propriétés de la tâche

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Définissez des propriétés telles que la date de début, la durée et la date de fin des tâches.

## Étape 4 : ajouter une ressource

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Ajoutez des ressources au projet et affectez-les aux tâches selon vos besoins.

## Étape 5 : Appliquer l’algorithme d’arborescence

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Initialisez le`WorkAccumulator` classe et appliquer l’algorithme d’arbre pour rassembler le travail commun.

## Étape 6 : Mettre à jour le travail de la tâche

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Mettez à jour les valeurs de travail pour les tâches en fonction des informations recueillies.

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser l'algorithme d'arborescence dans Aspose.Tasks pour .NET pour manipuler efficacement les hiérarchies de tâches. En suivant le guide étape par étape, vous pouvez gérer efficacement les tâches et les ressources au sein de vos projets.

## FAQ

### Q1 : Qu'est-ce qu'Aspose.Tasks pour .NET ?

A1 : Aspose.Tasks for .NET est une API puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project par programme à l'aide de C#.

### Q2 : Puis-je télécharger un essai gratuit d’Aspose.Tasks pour .NET ?

 A2 : Oui, vous pouvez télécharger un essai gratuit d'Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/).

### Q3 : Où puis-je trouver la documentation pour Aspose.Tasks pour .NET ?

 A3 : Vous pouvez trouver la documentation pour Aspose.Tasks pour .NET[ici](https://reference.aspose.com/tasks/net/).

### Q4 : Comment puis-je obtenir de l'assistance pour Aspose.Tasks pour .NET ?

 A4 : Pour obtenir une assistance relative à Aspose.Tasks pour .NET, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5 : Existe-t-il une licence temporaire disponible à des fins de test ?

 A5 : Oui, vous pouvez obtenir une licence temporaire à des fins de test auprès de[ici](https://purchase.aspose.com/temporary-license/).