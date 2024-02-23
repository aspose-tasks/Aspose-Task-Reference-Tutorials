---
title: Collection d'affectations de ressources dans Aspose.Tasks
linktitle: Collection d'affectations de ressources dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les affectations de ressources dans Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Tutoriel étape par étape avec des exemples de code.
type: docs
weight: 12
url: /fr/net/resource-risk-analysis/resource-assignment-collection/
---
## Introduction
Bienvenue dans ce didacticiel complet sur la gestion des affectations de ressources dans Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Dans ce didacticiel, nous aborderons le processus étape par étape, en veillant à ce que vous ayez une solide compréhension de la manière de manipuler efficacement les affectations de ressources. Que vous soyez un développeur chevronné ou un débutant, ce guide vous guidera à travers tout ce que vous devez savoir.
## Conditions préalables
Avant de plonger dans le code, assurez-vous d'avoir la configuration suivante :
1. Aspose.Tasks pour .NET installé : assurez-vous que Aspose.Tasks pour .NET est installé dans votre environnement de développement. Sinon, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
2. Connaissance de base de C# : ce didacticiel suppose que vous possédez une compréhension de base du langage de programmation C#.
3. Fichier Microsoft Project : préparez un fichier Microsoft Project à des fins de test. Si vous n'en avez pas, vous pouvez créer un exemple de fichier.

## Importer des espaces de noms
Commençons par importer les espaces de noms nécessaires :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Étape 1 : Charger le fichier de projet
Commencez par charger le fichier Microsoft Project :
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Étape 2 : ajouter une tâche et une ressource
Maintenant, ajoutons une tâche et une ressource au projet :
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Étape 3 : attribuer une ressource à une tâche
Ensuite, nous affecterons la ressource à la tâche :
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Étape 4 : Travailler avec différents types d'affectations
Vous pouvez également travailler avec des affectations impliquant des unités ou des coûts :
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Définissez les propriétés des affectations avec des unités et des coûts de la même manière, comme indiqué à l'étape 3.
```
## Étape 5 : Imprimer les devoirs
Imprimez les devoirs du projet :
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Imprimer les détails du devoir
}
```
## Étape 6 : Récupérer l'affectation par UID
Vous pouvez récupérer les affectations par UID :
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Étape 7 : Vérifier l'état en lecture seule
Vérifiez si la collection d'affectations de ressources est en lecture seule :
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Étape 8 : Convertir la collection en liste et itérer
Convertissez la collection en liste et parcourez-la :
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Conclusion
Toutes nos félicitations! Vous avez appris à gérer les affectations de ressources dans Microsoft Project à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez manipuler efficacement les tâches et les ressources, faisant ainsi de la gestion de projet un jeu d'enfant.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour .NET avec différentes versions de fichiers Microsoft Project ?
R : Oui, Aspose.Tasks pour .NET prend en charge différentes versions de fichiers Microsoft Project, notamment les formats MPP, MPT et XML.
### Q : Existe-t-il une version d'essai disponible avant d'acheter Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir de l'aide si je rencontre des problèmes lors de l'utilisation d'Aspose.Tasks pour .NET ?
 R : Vous pouvez demander de l'aide sur le forum Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
### Q : Puis-je utiliser des licences temporaires pour Aspose.Tasks pour .NET ?
 R : Oui, des licences temporaires sont disponibles à des fins d'évaluation. Vous pouvez en obtenir un auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je acheter une licence complète pour Aspose.Tasks pour .NET ?
 R : Vous pouvez acheter une licence complète sur la boutique en ligne Aspose.[ici](https://purchase.aspose.com/buy).