---
title: Gestion de la collection de propriétés de projet personnalisées dans Aspose.Tasks
linktitle: Gestion de la collection de propriétés de projet personnalisées dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les propriétés de projet personnalisées dans Aspose.Tasks pour .NET, améliorant ainsi votre expérience de gestion de projet.
type: docs
weight: 24
url: /fr/net/calendar-scheduling/custom-project-property-collection/
---
## Introduction

Êtes-vous prêt à améliorer votre expérience de gestion de projet avec Aspose.Tasks pour .NET ? La gestion des propriétés de projet personnalisées est un aspect crucial de la gestion de projet, vous permettant d'ajouter des métadonnées spécifiques adaptées aux exigences de votre projet. Dans ce didacticiel, nous verrons comment travailler efficacement avec des collections de propriétés de projet personnalisées à l'aide d'Aspose.Tasks pour .NET.

## Conditions préalables

Avant de continuer, assurez-vous d'avoir configuré les conditions préalables suivantes :

1. Environnement Visual Studio : installez Visual Studio sur votre système.
2.  Aspose.Tasks for .NET : téléchargez et installez Aspose.Tasks for .NET à partir du[lien de téléchargement](https://releases.aspose.com/tasks/net/).
3. Connaissance de base de C# : Familiarisez-vous avec les bases du langage de programmation C#.

## Importer des espaces de noms

Commencez par importer les espaces de noms nécessaires pour travailler avec Aspose.Tasks for .NET :

```csharp
using Aspose.Tasks;
using System;


```

Décomposons l'exemple de code en plusieurs étapes pour une compréhension complète :

## Étape 1 : initialiser le projet

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

Cette étape initialise un nouveau projet à l'aide d'Aspose.Tasks.

## Étape 2 : Vérifier l'état de préparation de la collection de propriétés personnalisées

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

Ce code vérifie si la collection de propriétés personnalisées est en lecture seule.

## Étape 3 : ajouter des propriétés personnalisées

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

Ici, nous ajoutons des propriétés personnalisées au projet, prenant en charge les types Boolean, DateTime, Double et String.

## Étape 4 : accéder aux propriétés personnalisées

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

Cette boucle nous permet de parcourir les propriétés personnalisées et d'afficher leur type, leur nom et leur valeur.

## Étape 5 : Récupérer une valeur de propriété personnalisée

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

Ce code récupère la valeur d'une propriété personnalisée spécifique nommée « Nom personnalisé ».

## Étape 6 : Itérer sur les noms de propriétés personnalisées

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

Ici, nous parcourons les noms des propriétés personnalisées et les affichons.

## Étape 7 : Supprimer ou effacer les propriétés personnalisées

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

Vous pouvez supprimer une propriété personnalisée spécifique par son nom ou effacer toute la collection.

## Conclusion

La maîtrise des collections de propriétés de projet personnalisées dans Aspose.Tasks for .NET vous permet de gérer efficacement les métadonnées du projet. En suivant ce guide étape par étape, vous pouvez intégrer de manière transparente des propriétés personnalisées dans votre flux de travail de gestion de projet, améliorant ainsi l'organisation et l'efficacité.

## FAQ

### Q1 : Puis-je ajouter des propriétés personnalisées de n’importe quel type de données à mon projet à l’aide d’Aspose.Tasks pour .NET ?

A1 : Oui, vous pouvez ajouter des propriétés personnalisées prenant en charge les types Boolean, DateTime, Double et String.

### Q2 : Est-il possible de parcourir les noms de propriétés personnalisées dans Aspose.Tasks pour .NET ?

 A2 : Absolument, vous pouvez parcourir les noms de propriétés personnalisées à l'aide de l'outil`Names` propriété.

### Q3 : Comment puis-je supprimer une propriété personnalisée spécifique de mon projet ?

 A3 : Vous pouvez supprimer une propriété personnalisée par son nom à l'aide du`Remove` méthode.

### Q4 : Aspose.Tasks pour .NET prend-il en charge les licences temporaires ?

A4 : Oui, vous pouvez obtenir une licence temporaire sur le site Web Aspose à des fins d'évaluation.

### Q5 : Où puis-je trouver une assistance ou une assistance supplémentaire concernant Aspose.Tasks pour .NET ?

 A5 : Vous pouvez visiter le forum Aspose.Tasks[ici](https://forum.aspose.com/c/tasks/15) pour toute question ou assistance.