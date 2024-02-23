---
title: Maîtriser les masques de code WBS avec Aspose.Tasks pour .NET
linktitle: Collection de masques de code WBS dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Améliorez la gestion de projet avec Aspose.Tasks pour .NET. Apprenez à créer, gérer et transférer des masques de code WBS sans effort dans ce didacticiel complet.
type: docs
weight: 15
url: /fr/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Introduction
Dans le monde dynamique de la gestion de projet, organiser efficacement les tâches est crucial. Aspose.Tasks pour .NET fournit une solution puissante pour gérer sans effort les codes de structure de répartition du travail (WBS) du projet. Dans ce didacticiel, nous approfondirons la collection de masques de code WBS, en explorant comment les implémenter et les manipuler à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de nous lancer dans ce voyage de codage, assurez-vous d'avoir les conditions préalables suivantes en place :
- Une connaissance pratique du langage de programmation C#.
-  Aspose.Tasks pour .NET installé dans votre environnement de développement. Sinon, téléchargez-le[ici](https://releases.aspose.com/tasks/net/).
- Un éditeur de code comme Visual Studio pour une expérience de codage transparente.
## Importer des espaces de noms
Pour commencer, importons les espaces de noms nécessaires :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Initialiser la définition du projet et du code WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Définir les masques de code WBS
Effacez tous les masques de code existants et ajoutez-en de nouveaux :
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Afficher les informations sur les masques de code
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Ajouter des tâches au projet
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Récupérer les informations sur la tâche
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipuler les masques de code
Supprimez un masque de code et assurez-vous qu'il est supprimé :
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Copier les masques de code vers un autre projet
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Afficher les masques de code dans un autre projet
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Ajouter des tâches à l'autre projet
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Afficher les codes WBS dans l'autre projet
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Conclusion
Avec Aspose.Tasks pour .NET, la gestion des codes WBS devient une tâche sans effort. Ce didacticiel a couvert la création, la manipulation et le transfert de masques de code WBS, vous fournissant un guide complet pour améliorer votre expérience de gestion de projet.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour .NET avec d’autres langages de programmation ?
R : Aspose.Tasks prend principalement en charge les langages .NET, mais vous pouvez explorer les options d'interopérabilité avec d'autres langages.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez télécharger la version d'essai.[ici](https://releases.aspose.com/).
### Q : Comment puis-je demander de l'aide ou signaler des problèmes avec Aspose.Tasks pour .NET ?
 R : Visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour du soutien et des discussions.
### Q : A quoi servent les codes WBS dans la gestion de projet ?
R : Les codes WBS aident à organiser et à structurer les tâches du projet de manière hiérarchique, offrant ainsi une approche systématique de la planification du projet.
### Q : Puis-je personnaliser le format des codes WBS dans Aspose.Tasks pour .NET ?
: Absolument, vous avez un contrôle total sur le format et la structure des codes WBS à l'aide d'Aspose.Tasks pour .NET.