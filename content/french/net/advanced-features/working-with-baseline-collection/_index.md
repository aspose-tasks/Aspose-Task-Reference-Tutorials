---
title: Travailler avec la collection de référence dans Aspose.Tasks
linktitle: Travailler avec la collection de référence dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les lignes de base dans Aspose.Tasks pour .NET. Suivez notre didacticiel complet pour des conseils étape par étape.
type: docs
weight: 20
url: /fr/net/advanced-features/working-with-baseline-collection/
---
## Introduction

Aspose.Tasks for .NET est une bibliothèque puissante qui permet aux développeurs de travailler de manière transparente avec les fichiers Microsoft Project dans leurs applications .NET. Parmi ses nombreuses fonctionnalités, il offre un support robuste pour la gestion des références au sein des projets. Les références sont essentielles pour la gestion de projet car elles vous permettent de comparer le plan de projet original avec l'état actuel, permettant ainsi un meilleur suivi et une meilleure analyse de l'avancement du projet.

## Conditions préalables

Avant de commencer à travailler avec les collections de base dans Aspose.Tasks, assurez-vous que les conditions préalables suivantes sont en place :

1. Visual Studio : installez Visual Studio IDE sur votre système.
2.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[lien de téléchargement](https://releases.aspose.com/tasks/net/).
3. Compréhension de base de C# : Familiarisez-vous avec le langage de programmation C#.
4. Fichier Microsoft Project : préparez un fichier Microsoft Project (.mpp) à des fins de test.

## Importer des espaces de noms

Pour commencer à travailler avec des collections de base dans Aspose.Tasks, vous devez importer les espaces de noms suivants :

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Maintenant, décomposons chaque exemple en plusieurs étapes :

## Étape 1 : Charger le fichier de projet

Tout d’abord, chargez le fichier Microsoft Project à l’aide d’Aspose.Tasks :

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Étape 2 : Obtenir des ressources

Ensuite, récupérez la ressource souhaitée dans le projet :

```csharp
var resource = project.Resources.GetByUid(1);
```

## Étape 3 : Afficher les informations de base

Maintenant, affichez les informations sur les lignes de base associées à la ressource :

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Étape 4 : Parcourir les lignes de base

Parcourez chaque référence associée à la ressource et imprimez les informations pertinentes :

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Étape 5 : Supprimer les lignes de base

Supprimez toutes les lignes de base associées à la ressource :

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Conclusion

Dans ce didacticiel, nous avons exploré comment utiliser les collections de base dans Aspose.Tasks pour .NET. En suivant le guide étape par étape, vous pouvez facilement gérer les références au sein de vos applications .NET, permettant ainsi un suivi et une analyse efficaces des projets.

## FAQ

### Q1 : Aspose.Tasks peut-il gérer des fichiers de projet volumineux ?

A1 : Oui, Aspose.Tasks est optimisé pour gérer efficacement les fichiers de projet volumineux, garantissant ainsi des performances fluides.

### Q2 : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?

A2 : Aspose.Tasks prend en charge différentes versions de Microsoft Project, garantissant la compatibilité entre différents environnements.

### Q3 : Puis-je personnaliser les lignes de base dans Aspose.Tasks ?

A3 : Oui, vous pouvez personnaliser les lignes de base en fonction des exigences de votre projet à l'aide d'Aspose.Tasks pour .NET.

### Q4 : Aspose.Tasks offre-t-il une prise en charge des plates-formes cloud ?

A4 : Oui, Aspose.Tasks prend en charge l'intégration avec les plates-formes cloud populaires, offrant une flexibilité de déploiement.

### Q5 : Existe-t-il un forum communautaire permettant aux utilisateurs d'Aspose.Tasks de demander de l'aide et de partager leurs connaissances ?

 A5 : Oui, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour interagir avec la communauté et obtenir l’aide d’experts.