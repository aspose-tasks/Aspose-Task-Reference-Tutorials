---
title: Travailler avec des périodes de disponibilité dans Aspose.Tasks
linktitle: Travailler avec des périodes de disponibilité dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les périodes de disponibilité des ressources à l'aide d'Aspose.Tasks pour .NET. Ce didacticiel fournit un guide étape par étape pour utiliser les périodes de disponibilité dans vos projets .NET.
type: docs
weight: 17
url: /fr/net/advanced-features/working-with-availability-periods/
---
## Introduction

Dans ce didacticiel, nous verrons comment utiliser les périodes de disponibilité dans Aspose.Tasks pour .NET. Les périodes de disponibilité sont cruciales pour gérer efficacement les ressources dans les scénarios de gestion de projet. Nous vous guiderons étape par étape tout au long du processus.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des prérequis suivants :

1. Visual Studio : installez Visual Studio ou tout autre IDE préféré pour le développement .NET.
2.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Compréhension de base de la programmation C# : Une connaissance des bases du langage de programmation C# sera utile.

## Importer des espaces de noms

Avant de plonger dans le code, assurez-vous d'importer les espaces de noms nécessaires :

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Décomposons l'exemple de code en plusieurs étapes :

## Étape 1 : Créer une nouvelle instance de projet

```csharp
var project = new Project();
```

Cette ligne initialise une nouvelle instance de la classe Project, qui représente un projet dans Aspose.Tasks.

## Étape 2 : ajouter une ressource

```csharp
var resource = project.Resources.Add("Work Resource");
```

Ici, nous ajoutons une nouvelle ressource au projet avec le nom « Work Resource ».

## Étape 3 : Définir les périodes de disponibilité

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Nous appelons le`GetPeriods()` méthode pour récupérer une collection de périodes de disponibilité.

## Étape 4 : ajouter des périodes de disponibilité à la ressource

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Nous parcourons la collection de périodes de disponibilité obtenues à l’étape précédente et les ajoutons à la ressource.

## Étape 5 : Afficher les détails de la période de disponibilité

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Enfin, nous parcourons les périodes de disponibilité associées à la ressource et imprimons leurs détails, y compris la date de début, la date de fin et les unités disponibles.

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser les périodes de disponibilité dans Aspose.Tasks pour .NET. En suivant le guide étape par étape, vous pouvez gérer efficacement la disponibilité des ressources dans vos applications de gestion de projet.

## FAQ

### Q1 : Puis-je utiliser Aspose.Tasks pour .NET dans des projets commerciaux ?

 A1 : Oui, Aspose.Tasks pour .NET peut être utilisé dans des projets commerciaux. Vous pouvez acheter une licence[ici](https://purchase.aspose.com/buy).

### Q2 : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?

A2 : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks pour .NET[ici](https://releases.aspose.com/).

### Q3 : Où puis-je trouver la documentation pour Aspose.Tasks pour .NET ?

 A3 : Vous pouvez trouver la documentation[ici](https://reference.aspose.com/tasks/net/).

### Q4 : Comment puis-je obtenir de l'assistance pour Aspose.Tasks pour .NET ?

 A4 : Vous pouvez obtenir de l'aide auprès du forum communautaire[ici](https://forum.aspose.com/c/tasks/15).

### Q5 : Proposez-vous des licences temporaires pour Aspose.Tasks pour .NET ?

 A5 : Oui, des licences temporaires sont disponibles[ici](https://purchase.aspose.com/temporary-license/).