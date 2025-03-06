---
title: Collecter MS Project de pièces divisées dans Aspose.Tasks
linktitle: Collection de pièces divisées dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment collecter des parties fractionnées dans MS Project à l'aide d'Aspose.Tasks pour .NET. Ce didacticiel complet vous guide tout au long du processus, étape par étape.
type: docs
weight: 19
url: /fr/net/rate-recurring-tasks/split-part-collection/
---
## Introduction
Dans ce didacticiel, nous verrons comment collecter des parties fractionnées dans MS Project à l'aide d'Aspose.Tasks pour .NET. La division des tâches en parties peut être un aspect crucial de la gestion de projet, et Aspose.Tasks fournit des méthodes pratiques pour gérer cela efficacement.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1. Installation d'Aspose.Tasks pour .NET : assurez-vous d'avoir installé Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
2. Connaissance de base de C# : Une connaissance du langage de programmation C# sera bénéfique car nous écrirons des extraits de code en C#.

## Importer des espaces de noms
Dans votre projet C#, incluez les espaces de noms nécessaires :
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Étape 1 : Configurez votre projet
Tout d’abord, créez un nouveau projet dans votre IDE préféré et assurez-vous qu’Aspose.Tasks for .NET est correctement référencé.
## Étape 2 : initialiser l'objet du projet
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Initialisez un nouvel objet Project avec le chemin d'accès à votre fichier MS Project.
## Étape 3 : Récupérer la tâche et parcourir les parties fractionnées
```csharp
var task = project.RootTask.Children.GetById(1);
// Itérer sur des pièces divisées
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Récupérez la tâche du projet et parcourez ses parties divisées, en imprimant leurs dates de début et de fin.
## Étape 4 : Obtenir une partie divisée par index
```csharp
// Récupérer la pièce par index
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Récupérez une partie fractionnée spécifique par index et imprimez sa date de début.

## Conclusion
La gestion des parties fractionnées dans les fichiers MS Project peut améliorer considérablement l'efficacité de la gestion de projet. Aspose.Tasks for .NET simplifie ce processus en fournissant des API intuitives pour gérer les tâches fractionnées de manière transparente.
## FAQ
### Q : Puis-je diviser les tâches de manière dynamique pendant l'exécution ?
R : Oui, vous pouvez diviser les tâches par programme à l'aide d'Aspose.Tasks pour .NET.
### Q : Aspose.Tasks prend-il en charge toutes les versions des fichiers MS Project ?
R : Aspose.Tasks prend en charge différentes versions de fichiers MS Project, garantissant ainsi la compatibilité entre différentes plates-formes.
### Q : Existe-t-il une version d'essai disponible à des fins de test ?
 R : Oui, vous pouvez obtenir une version d'essai gratuite auprès de[ici](https://releases.aspose.com/) pour évaluation.
### Q : Comment puis-je obtenir des licences temporaires pour mes projets ?
 R : Les licences temporaires peuvent être acquises auprès de[ici](https://purchase.aspose.com/temporary-license/) pour une utilisation à court terme.
### Q : Où puis-je demander de l'aide ou de l'assistance concernant Aspose.Tasks ?
 R : Vous pouvez visiter le forum Aspose.Tasks[ici](https://forum.aspose.com/c/tasks/15)pour demander de l'aide à la communauté ou à l'équipe d'assistance Aspose.