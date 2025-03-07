---
title: Collection de périodes de disponibilité dans Aspose.Tasks
linktitle: Collection de périodes de disponibilité dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les périodes de disponibilité des ressources dans Aspose.Tasks pour .NET. Ce didacticiel étape par étape vous guide dans l'ajout, la mise à jour et la suppression de périodes de disponibilité, garantissant ainsi une planification efficace des ressources du projet.
weight: 18
url: /fr/net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Collection de périodes de disponibilité dans Aspose.Tasks

## Introduction

Dans ce didacticiel, nous allons explorer comment utiliser la collection de périodes de disponibilité d'une ressource dans Aspose.Tasks pour .NET. La gestion des périodes de disponibilité est cruciale pour la gestion de projet, nous permettant de définir quand les ressources sont disponibles pour les tâches d'un projet.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système.
2.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Compréhension de base : Familiarité avec le framework C# et .NET.

## Importer des espaces de noms

Tout d’abord, nous devons importer les espaces de noms nécessaires dans notre projet :

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Décomposons l'exemple de code en plusieurs étapes et comprenons chaque partie :

## Étape 1 : initialiser le projet et la ressource

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Ici, nous chargeons un fichier de projet et obtenons une ressource spécifique par son ID.

## Étape 2 : Effacer les périodes de disponibilité existantes

```csharp
resource.AvailabilityPeriods.Clear();
```

Nous supprimons toutes les périodes de disponibilité existantes associées à la ressource.

## Étape 3 : ajouter des périodes de disponibilité

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Nous parcourons une collection de périodes de disponibilité et les ajoutons à la ressource.

## Étape 4 : Insérer une nouvelle période de disponibilité

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Nous créons une nouvelle période de disponibilité pour l'année 2013 et l'insérons dans la collection.

## Étape 5 : Afficher les périodes de disponibilité

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Nous imprimons le décompte et le détail de chaque période de disponibilité associée à la ressource.

## Étape 6 : copier les périodes de disponibilité vers une autre ressource

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Nous copions les périodes de disponibilité d'une ressource à une autre.

## Étape 7 : mettre à jour et supprimer les périodes de disponibilité

```csharp
// Mettre à jour les unités disponibles pour une période spécifique
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Supprimer une période spécifique
otherResource.AvailabilityPeriods.Remove(period2013);
```

Nous mettons à jour les unités disponibles pour une période et supprimons des périodes spécifiques de la collection.

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser les collections de périodes de disponibilité dans Aspose.Tasks pour .NET. La gestion de la disponibilité des ressources est essentielle pour une planification et une exécution efficaces du projet.

## FAQ

### Q1 : Puis-je ajouter des champs personnalisés aux périodes de disponibilité ?

A1 : Non, les périodes de disponibilité dans Aspose.Tasks pour .NET ne prennent pas en charge les champs personnalisés.

### Q2 : Les périodes de disponibilité sont-elles liées à des tâches spécifiques ?

A2 : Non, les périodes de disponibilité sont associées aux ressources et définissent quand elles sont disponibles pour les tâches en général.

### Q3 : Puis-je importer des périodes de disponibilité à partir de sources externes ?

A3 : Oui, vous pouvez importer des périodes de disponibilité à partir de diverses sources de données à l'aide d'Aspose.Tasks pour les API .NET.

### Q4 : Comment gérer les périodes de disponibilité qui se chevauchent ?

A4 : Aspose.Tasks pour .NET ne fournit pas de mécanismes intégrés pour gérer les périodes qui se chevauchent. Vous devrez peut-être implémenter une logique personnalisée pour gérer de tels scénarios.

### Q5 : Y a-t-il une limite au nombre de périodes de disponibilité qu'une ressource peut avoir ?

A5 : Il n'y a pas de limite prédéfinie quant au nombre de périodes de disponibilité qu'une ressource peut avoir, mais les performances peuvent se dégrader avec un grand nombre de périodes.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
