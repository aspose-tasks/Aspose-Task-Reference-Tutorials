---
title: Extraction des informations sur les tâches récurrentes dans Aspose.Tasks
linktitle: Extraction des informations sur les tâches récurrentes dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment extraire des informations sur les tâches récurrentes à partir de fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. Intégration facile pour les développeurs .NET.
weight: 13
url: /fr/net/rate-recurring-tasks/recurring-task-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraction des informations sur les tâches récurrentes dans Aspose.Tasks

## Introduction
Aspose.Tasks for .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers Microsoft Project dans leurs applications .NET. Dans ce didacticiel, nous explorerons comment extraire des informations sur les tâches récurrentes à partir de fichiers MS Project à l'aide d'Aspose.Tasks.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1. Compréhension de base du langage de programmation C#.
2. Visual Studio installé sur votre système.
3.  Aspose.Tasks pour la bibliothèque .NET installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
## Importer des espaces de noms
Pour commencer, importez les espaces de noms nécessaires dans votre code C# :
```csharp
    using Aspose.Tasks;
    using System;
    
```
Maintenant, décomposons l'exemple en plusieurs étapes :
## Étape 1 : Configurer le chemin du fichier du projet
```csharp
String DataDir = "Your Document Directory";
```
 Remplacer`"Your Document Directory"` avec le chemin d'accès à votre fichier MS Project.
## Étape 2 : Chargez le fichier MS Project
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Cette ligne initialise un nouveau`Project` objet en chargeant le fichier MS Project spécifié par le chemin.
## Étape 3 : Lire les informations récurrentes des tâches
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Accéder et afficher les informations sur les tâches récurrentes
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Continuer à afficher d'autres informations sur les tâches récurrentes si nécessaire
}
```
Cette boucle parcourt toutes les tâches du projet et vérifie si chaque tâche est associée à des informations récurrentes. Si c'est le cas, il récupère et affiche diverses propriétés de la tâche récurrente, telles que la date de début, la durée, la date de fin, etc.
## Conclusion
Dans ce didacticiel, nous avons appris à extraire des informations sur les tâches récurrentes à partir de fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. Grâce à ces connaissances, vous pouvez désormais intégrer cette fonctionnalité dans vos applications .NET pour travailler plus efficacement sur les tâches récurrentes.
## FAQ
### Q : Puis-je modifier les informations sur les tâches récurrentes à l’aide d’Aspose.Tasks pour .NET ?
R : Oui, vous pouvez modifier les informations sur les tâches récurrentes par programme à l'aide des API fournies.
### Q : Aspose.Tasks prend-il en charge d'autres formats de fichiers de projet que MS Project ?
R : Oui, Aspose.Tasks prend en charge divers formats de fichiers de projet tels que MPP, XML et CSV.
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver de la documentation pour Aspose.Tasks pour .NET ?
 R : Vous pouvez trouver la documentation[ici](https://reference.aspose.com/tasks/net/).
### Q : Comment puis-je obtenir une assistance technique pour Aspose.Tasks pour .NET ?
 R : Vous pouvez obtenir une assistance technique sur le forum Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
