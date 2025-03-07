---
title: Gestion des parties fractionnées MS Project dans Aspose.Tasks
linktitle: Gestion des pièces divisées dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer efficacement les parties fractionnées de MS Project avec Aspose.Tasks pour .NET. Améliorez votre flux de travail de gestion de projet.
weight: 18
url: /fr/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestion des parties fractionnées MS Project dans Aspose.Tasks


## Introduction
La gestion des parties fractionnées de MS Project peut être un aspect crucial de la gestion de projet lors de l'utilisation d'Aspose.Tasks pour .NET. Dans ce didacticiel, nous explorerons comment gérer efficacement les pièces divisées à l'aide de conseils étape par étape.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :
1.  Installation d'Aspose.Tasks for .NET : Téléchargez et installez Aspose.Tasks for .NET à partir du[site web](https://releases.aspose.com/tasks/net/).
   
2. Compréhension de base de C# : Une connaissance du langage de programmation C# sera bénéfique.

## Importer des espaces de noms
Dans votre code C#, assurez-vous d'importer les espaces de noms nécessaires :
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Étape 1 : Création d'une instance de projet
```csharp
var project = new Project();
```
 Créez une nouvelle instance du`Project` classe.
## Étape 2 : Définition des dates de début et de fin du projet
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Fixez les dates de début et de fin du projet.
## Étape 3 : Ajouter une tâche
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Ajoutez une nouvelle tâche au projet.
## Étape 4 : Définition des propriétés de la tâche
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Définissez des propriétés telles que le statut manuel, la date de début et la durée de la tâche.
## Étape 5 : Ajout d'affectations de ressources
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Ajoutez des affectations de ressources à la tâche.
## Étape 6 : Définition des propriétés d'affectation
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Définissez des propriétés telles que la date de début, la date de travail et la date de fin de la mission.
## Étape 7 : Générer des données chronologiques
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Générez des données chronologiques pour la mission en fonction du calendrier du projet.
## Étape 8 : diviser la tâche
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Divisez la tâche en plusieurs parties dans le délai spécifié.
## Étape 9 : Itérer sur des parties divisées
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Parcourez les parties fractionnées de la tâche et imprimez leurs dates de début et de fin.

## Conclusion
La gestion efficace des parties fractionnées de MS Project dans Aspose.Tasks pour .NET est cruciale pour l'efficacité de la gestion de projet. En suivant les étapes décrites dans ce didacticiel, vous pouvez gérer de manière transparente les tâches fractionnées et améliorer votre flux de travail de gestion de projet.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour .NET avec d’autres frameworks .NET ?
R : Oui, Aspose.Tasks pour .NET est compatible avec divers frameworks .NET, notamment .NET Core et .NET Standard.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez obtenir un essai gratuit auprès de[ici](https://releases.aspose.com/).
### Q : Aspose.Tasks pour .NET prend-il en charge la gestion des ressources ?
: Oui, Aspose.Tasks for .NET vous permet de gérer efficacement les ressources du projet.
### Q : Puis-je personnaliser les calendriers de projet à l’aide d’Aspose.Tasks pour .NET ?
R : Absolument, vous pouvez personnaliser les calendriers de projet en fonction des exigences de votre projet.
### Q : Où puis-je trouver de l'assistance pour Aspose.Tasks pour .NET ?
 R : Vous pouvez trouver du soutien et de l'assistance sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
