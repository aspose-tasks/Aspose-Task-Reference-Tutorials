---
title: Gestion des tâches dans Aspose.Tasks
linktitle: Gestion des tâches dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explorez le guide complet sur la gestion des tâches avec Aspose.Tasks pour .NET. Apprenez à ajouter, afficher des pièces divisées, déplacer, obtenir/définir des propriétés, etc.
weight: 15
url: /fr/net/task-table-management/managing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestion des tâches dans Aspose.Tasks

## Introduction
Si vous êtes un développeur .NET cherchant à gérer efficacement les tâches au sein de vos projets, Aspose.Tasks for .NET fournit une solution robuste. Ce didacticiel vous guidera à travers différents aspects de la gestion des tâches à l'aide d'Aspose.Tasks, en vous proposant des instructions étape par étape et des exemples de code. Que vous ajoutiez des tâches, affichiez des parties fractionnées, déplaciez des tâches sous le même parent, obteniez/définissiez des propriétés de tâche, parcouriez les affectations de tâches, lisiez les lignes de base des tâches ou supprimiez des tâches, ce guide est là pour vous.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1. Bibliothèque Aspose.Tasks pour .NET : assurez-vous que la bibliothèque Aspose.Tasks pour .NET est installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/net/).
2. Répertoire de documents : configurez un répertoire dans lequel les documents de votre projet seront stockés.
## Importer des espaces de noms
Dans votre projet .NET, incluez les espaces de noms nécessaires pour travailler avec Aspose.Tasks :
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Ajouter une tâche à un projet
```csharp
// Créer un nouveau projet
var project = new Project();
// Ajouter une tâche
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Enregistrez le projet
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Affichage des parties fractionnées de la tâche
```csharp
// Charger un projet avec des tâches fractionnées
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Accéder à une tâche
var task = project.RootTask.Children.GetById(4);
// Afficher les pièces divisées
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Déplacer une tâche sous le même parent
```csharp
try
{
    // Charger un projet
    var project = new Project(DataDir + "MoveTask.mpp");
    // Déplacer les tâches avec l'ID 5 avant la tâche avec l'ID 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Enregistrez le projet modifié
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Obtenir/définir les propriétés de la tâche
```csharp
// Créer un nouveau projet
var project = new Project();
// Ajouter une tâche et définir les propriétés
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Collecter et afficher les propriétés des tâches
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Itérer sur les affectations des tâches
```csharp
// Charger un projet avec des devoirs
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Collecter et afficher les affectations de tâches
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Lecture des lignes de base de la tâche
```csharp
// Créer un nouveau projet
var project = new Project();
// Ajouter une tâche et définir une référence
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Afficher la durée de référence de la tâche
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Supprimer une tâche
```csharp
// Créer un nouveau projet
var project = new Project();
// Ajouter une tâche
var task = project.RootTask.Children.Add("Task");
//Afficher le nombre de tâches avant et après suppression
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Supprimer la tâche
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Conclusion
La gestion des tâches dans Aspose.Tasks pour .NET est un processus transparent avec les exemples fournis. Que vous soyez un développeur chevronné ou que vous débutiez tout juste, l'intégration de ces techniques améliorera vos capacités de gestion de projet.
## Questions fréquemment posées
### Q : Aspose.Tasks est-il compatible avec tous les frameworks .NET ?
R : Oui, Aspose.Tasks prend en charge divers frameworks .NET, garantissant ainsi la compatibilité avec votre environnement de développement.
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Tasks ?
 R : Vous pouvez obtenir une licence temporaire de 30 jours auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Q : Existe-t-il des limitations lorsque vous travaillez avec des tâches fractionnées dans Aspose.Tasks ?
 R : Les tâches fractionnées sont une fonctionnalité puissante et une documentation détaillée peut être trouvée[ici](https://reference.aspose.com/tasks/net/).
### Q : Puis-je personnaliser les propriétés de la tâche au-delà de ce qui est indiqué dans les exemples ?
R : Absolument ! Aspose.Tasks fournit des options de personnalisation étendues pour les propriétés des tâches. Consultez la documentation pour plus de détails.
### Q : Comment puis-je obtenir de l'aide pour Aspose.Tasks ?
 R : Visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien et les discussions de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
