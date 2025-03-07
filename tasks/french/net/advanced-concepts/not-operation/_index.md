---
title: Travailler avec l'opération NOT dans Aspose.Tasks
linktitle: Travailler avec l'opération NOT dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment utiliser l'opération NOT dans Aspose.Tasks pour .NET pour filtrer efficacement les tâches. Améliorez dès maintenant vos capacités de gestion de projet.
weight: 20
url: /fr/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Travailler avec l'opération NOT dans Aspose.Tasks

## Introduction

Dans ce didacticiel, nous allons explorer comment utiliser l'opération NOT dans Aspose.Tasks pour .NET. L'opération NOT nous permet d'inverser une condition de filtre, nous permettant de sélectionner des éléments qui ne répondent pas à un critère spécifié.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Visual Studio : vous avez besoin d'une installation fonctionnelle de Visual Studio pour suivre les exemples de code.
2.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[site web](https://releases.aspose.com/tasks/net/).
3. Compréhension de base de C# : La connaissance du langage de programmation C# sera utile pour comprendre les exemples de code.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires pour notre code :

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Étape 1 : Configurer le projet et les tâches

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Nous commençons par charger un fichier projet nommé "Project2.mpp" à l'aide du`Project` classe fournie par Aspose.Tasks. Assurez-vous que le fichier projet existe dans le répertoire spécifié.

## Étape 2 : Collecter les tâches du projet

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Ici, nous créons un`ChildTasksCollector` objet pour rassembler toutes les tâches du projet. On utilise alors`TaskUtils.Apply` méthode pour parcourir la hiérarchie des tâches du projet et collecter toutes les tâches enfants.

## Étape 3 : Définir la condition du filtre

```csharp
var filter = new NullCondition();
```

 Nous définissons une condition de filtre à l'aide d'une classe personnalisée nommée`NullCondition`. Cette condition sélectionne les tâches qui ont une valeur nulle.

## Étape 4 : Appliquer l’opération NOT

```csharp
var condition = new Not<Task>(filter);
```

 Nous appliquons l’opération NOT à la condition de filtre en utilisant la`Not<T>`classe fournie par Aspose.Tasks. Cela inversera la condition de filtre, en sélectionnant les tâches qui n'ont pas de valeur nulle.

## Étape 5 : filtrer les tâches

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Nous filtrons les tâches collectées en fonction de la condition appliquée à l'aide d'un filtre personnalisé`Filter` méthode. Cette méthode prend une collection énumérable de tâches et une condition de filtre comme paramètres d'entrée, et renvoie une liste de tâches qui satisfont à la condition.

## Étape 6 : Traiter les tâches filtrées

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Travailler avec d'autres propriétés...
}
```

Enfin, nous parcourons les tâches filtrées et effectuons toutes les opérations souhaitées. Dans cet exemple, nous imprimons simplement les noms des tâches sur la console.

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser l'opération NOT dans Aspose.Tasks pour .NET. En inversant les conditions de filtrage, nous pouvons choisir de manière sélective les éléments qui ne répondent pas aux critères spécifiés, améliorant ainsi notre flexibilité dans la manipulation des tâches au sein des projets.

## FAQ

### Q1 : Puis-je utiliser Aspose.Tasks avec d’autres frameworks .NET ?

: Oui, Aspose.Tasks prend en charge divers frameworks .NET, notamment .NET Core, .NET Standard et .NET Framework.

### Q2 : Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?

 R : Oui, vous pouvez télécharger un essai gratuit à partir du[site web](https://releases.aspose.com/).

### Q3 : Comment puis-je obtenir de l'aide pour Aspose.Tasks ?

 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute question d’assistance ou d’assistance technique.

### Q4 : Puis-je acheter une licence temporaire pour Aspose.Tasks ?

 R : Oui, vous pouvez acheter une licence temporaire auprès du[page d'achat](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis-je trouver une documentation complète pour Aspose.Tasks ?

 R : Vous pouvez accéder à la documentation complète sur le[Page de documentation Aspose.Tasks](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
