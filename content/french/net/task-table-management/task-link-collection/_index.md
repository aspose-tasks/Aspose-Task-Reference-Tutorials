---
title: Gestion des liens de tâches dans Aspose.Tasks
linktitle: Gestion des liens de tâches dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez la puissance d'Aspose.Tasks pour .NET dans la gestion efficace des liens entre les tâches du projet. Suivez notre guide étape par étape pour améliorer votre expérience de gestion de projet.
type: docs
weight: 19
url: /fr/net/task-table-management/task-link-collection/
---
## Introduction
Bienvenue dans le guide étape par étape sur la gestion des liens de tâches dans Aspose.Tasks pour .NET ! Les liens de tâches jouent un rôle crucial dans la gestion de projet, vous permettant d'établir des relations entre les tâches et de créer des dépendances. Dans ce didacticiel, nous vous guiderons tout au long du processus d'utilisation des collections de liens de tâches à l'aide d'Aspose.Tasks.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Aspose.Tasks pour la bibliothèque .NET : téléchargez et installez la bibliothèque Aspose.Tasks. Vous pouvez trouver la bibliothèque[ici](https://releases.aspose.com/tasks/net/).
2. Exemple de fichier de projet : préparez un exemple de fichier de projet (par exemple, "SampleProject.mpp") à suivre avec les exemples.
Maintenant, commençons !
## Importer des espaces de noms
Dans votre projet .NET, assurez-vous d'importer les espaces de noms nécessaires pour travailler avec Aspose.Tasks :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Étape 1 : charger le projet et accéder aux tâches
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
// Charger le projet
var project = new Project(DataDir + "SampleProject.mpp");
// Accéder aux tâches par ID
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Étape 2 : Créer des liens de tâches
Reliez les tâches entre elles pour établir des dépendances :
```csharp
// Lier des tâches à l'aide de la dépendance FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Étape 3 : Imprimer les liens des tâches
Imprimez les liens de tâches pour le projet :
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
// Parcourir les liens de tâches
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Étape 4 : Modifier le lien de tâche
Modifier un lien de tâche par accès à l'index :
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Étape 5 : Supprimer les liens de tâches
Supprimez tous les liens de tâches du projet :
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment gérer les liens de tâches dans Aspose.Tasks pour .NET. Ce guide complet couvre le chargement d'un projet, la création de liens de tâches, l'impression de liens, la modification de liens et la suppression de liens de tâches.
N'hésitez pas à explorer davantage de fonctionnalités et de fonctionnalités offertes par Aspose.Tasks pour améliorer votre expérience de gestion de projet.
## FAQ
### Aspose.Tasks est-il compatible avec toutes les versions de .NET ?
Oui, Aspose.Tasks est conçu pour fonctionner de manière transparente avec toutes les versions de .NET.
### Puis-je créer des types de liens de tâches personnalisés à l’aide d’Aspose.Tasks ?
Actuellement, Aspose.Tasks prend en charge les types de liens de tâches standard et les types de liens personnalisés ne sont pas disponibles.
### Comment puis-je appliquer des contraintes aux tâches dans Aspose.Tasks ?
 Vous pouvez appliquer des contraintes à l'aide de l'outil`ConstraintType` propriété du`Task` classe dans Aspose.Tasks.
### Existe-t-il des limitations sur la taille des fichiers de projet qu'Aspose.Tasks peut gérer ?
Aspose.Tasks peut gérer efficacement des fichiers de projet volumineux avec un impact minimal sur les performances.
### Existe-t-il un forum communautaire pour le support d'Aspose.Tasks ?
 Oui, vous pouvez trouver du soutien et interagir avec la communauté sur le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).