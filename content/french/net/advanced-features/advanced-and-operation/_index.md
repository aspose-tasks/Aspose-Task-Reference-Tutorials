---
title: Opération ET avancée dans Aspose.Tasks
linktitle: Opération ET avancée dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment effectuer des opérations ET avancées dans Aspose.Tasks pour .NET afin de filtrer efficacement les tâches de projet en fonction de plusieurs critères.
type: docs
weight: 10
url: /fr/net/advanced-features/advanced-and-operation/
---
## Introduction

 Dans ce didacticiel, nous aborderons l'opération ET avancée dans Aspose.Tasks for .NET, un outil puissant de gestion de tâches et de projets. Nous explorerons comment filtrer les tâches d'un projet en fonction de plusieurs conditions à l'aide de l'outil`Util.And` classe.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Connaissance de base du langage de programmation C#.
2.  Aspose.Tasks installé pour .NET. Sinon, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
3. Environnement de développement intégré (IDE) tel que Visual Studio.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires dans notre projet C# :

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Étape 1 : initialiser le projet et collecter les tâches

Commencez par initialiser un nouveau projet Aspose.Tasks et en collectant toutes les tâches qu'il contient :

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Étape 2 : Définir les conditions de filtre

Ensuite, définissez les conditions de filtre. Pour cet exemple, nous allons créer deux conditions : une pour filtrer les tâches récapitulatives et une autre pour filtrer les tâches non nulles :

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Étape 3 : Combiner les conditions avec l’opération AND

 Maintenant, combinez les conditions en utilisant le`Util.And` classe pour créer une condition composite :

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Étape 4 : appliquer la condition et filtrer les tâches

Appliquez la condition combinée aux tâches collectées et filtrez-les en conséquence :

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Étape 5 : Tâches filtrées en sortie

Enfin, affichez les tâches filtrées :

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Un traitement supplémentaire peut être effectué ici
}
```

## Conclusion

 Dans ce didacticiel, nous avons appris à effectuer des opérations ET avancées dans Aspose.Tasks pour .NET. En combinant les conditions à l'aide du`Util.And` classe, nous pouvons filtrer efficacement les tâches en fonction de plusieurs critères.

## FAQ

### Q1 : Qu'est-ce qu'Aspose.Tasks pour .NET ?

R : Aspose.Tasks for .NET est une API robuste qui permet aux développeurs de manipuler les fichiers Microsoft Project par programmation dans les applications .NET.

### Q2 : Puis-je appliquer plus de deux conditions à l’aide de Util.And ?

R : Oui, Util.And peut être utilisé pour combiner un certain nombre de conditions afin de créer des critères de filtrage complexes.

### Q3 : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?

 R : Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).

### Q4 : Où puis-je trouver la documentation pour Aspose.Tasks pour .NET ?

 R : Vous pouvez trouver la documentation[ici](https://reference.aspose.com/tasks/net/).

### Q5 : Comment puis-je obtenir de l'assistance pour Aspose.Tasks pour .NET ?

 R : Vous pouvez obtenir de l'aide sur le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).