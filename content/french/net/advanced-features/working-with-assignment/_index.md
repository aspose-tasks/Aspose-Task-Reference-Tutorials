---
title: Travailler avec l'affectation dans Aspose.Tasks
linktitle: Travailler avec l'affectation dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les affectations de projets dans .NET à l'aide d'Aspose.Tasks. Explorez différents contours pour la planification des ressources.
type: docs
weight: 13
url: /fr/net/advanced-features/working-with-assignment/
---
## Introduction

Dans ce didacticiel, nous verrons comment utiliser les affectations dans Aspose.Tasks pour .NET. Les affectations sont cruciales dans la gestion de projet car elles allouent des ressources aux tâches, aidant ainsi à planifier et à suivre les progrès. Nous nous concentrerons sur la génération de données chronologiques d’affectation de ressources avec différents contours à l’aide d’Aspose.Tasks.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des prérequis suivants :

1.  Installation d'Aspose.Tasks for .NET : Téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[lien de téléchargement](https://releases.aspose.com/tasks/net/).
2. Compréhension de base de C# et du .NET Framework : Une familiarité avec le langage de programmation C# et les concepts du framework .NET est nécessaire pour suivre.

## Importer des espaces de noms

Assurez-vous d'importer les espaces de noms nécessaires dans votre projet C# :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Étape 1 : Créer un projet et une tâche

Commençons par créer un nouveau projet et y ajouter une tâche. Définissez la date de début, la durée et la date de fin de la tâche :

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Étape 2 : ajouter une ressource et l'attribuer à une tâche

Ensuite, ajoutez une ressource au projet et affectez-la à la tâche précédemment créée :

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Étape 3 : générer des données chronologiques avec différents contours

Maintenant, générons des données chronologiques avec différents contours pour l'affectation des ressources :

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Étape 4 : modifier les contours et générer des données

Nous pouvons modifier le type de contour et générer des données chronologiques en conséquence. Voici quelques exemples:

```csharp
// Changer de contour
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Générer des données chronologiques et imprimer
// Répétez cette étape pour d'autres types de contours
```

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser les affectations dans Aspose.Tasks pour .NET. Nous avons exploré la génération de données chronologiques d'affectation de ressources avec différents contours. Ces connaissances peuvent être extrêmement utiles dans les scénarios de gestion de projet.

## FAQ

### Q1 : Puis-je utiliser Aspose.Tasks pour planifier des tâches dans mon application .NET ?

A1 : Oui, Aspose.Tasks fournit des API complètes pour la planification et la gestion des tâches dans les applications .NET.

### Q2 : Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?

 A2 : Oui, vous pouvez bénéficier d'un essai gratuit auprès de[ici](https://releases.aspose.com/).

### Q3 : Existe-t-il des limitations sur le nombre de tâches ou de ressources dans Aspose.Tasks ?

A3 : Aspose.Tasks n'impose aucune limitation sur le nombre de tâches ou de ressources que vous pouvez gérer dans vos projets.

### Q4 : Puis-je personnaliser les contours des affectations de ressources dans Aspose.Tasks ?

A4 : Oui, comme démontré dans ce didacticiel, vous pouvez définir différents contours tels que tortue, cloche, pic, etc., en fonction des exigences de votre projet.

### Q5 : Où puis-je trouver de l'aide pour les requêtes liées à Aspose.Tasks ?

A5 : Vous pouvez trouver de l'aide sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) où les experts et les membres de la communauté participent activement aux discussions.