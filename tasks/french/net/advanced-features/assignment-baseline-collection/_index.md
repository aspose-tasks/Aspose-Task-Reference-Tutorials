---
title: Collection de lignes de base d’affectation dans Aspose.Tasks
linktitle: Collection de lignes de base d’affectation dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les références d'affectation dans la gestion de projet à l'aide d'Aspose.Tasks pour .NET. Améliorez la productivité et la précision.
type: docs
weight: 15
url: /fr/net/advanced-features/assignment-baseline-collection/
---
## Introduction

Dans le domaine de la gestion de projet, le suivi et la gestion des références des missions sont essentiels pour garantir le succès du projet et le respect des délais. Aspose.Tasks for .NET offre un ensemble robuste de fonctionnalités pour faciliter une gestion efficace des lignes de base d'affectation au sein des projets. Dans ce didacticiel, nous aborderons les subtilités de l'utilisation des collections de référence d'affectation à l'aide d'Aspose.Tasks pour .NET.

## Conditions préalables

Avant de poursuivre ce didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

1. Connaissance de base du langage de programmation C#.
2. Visual Studio installé sur votre système.
3.  Aspose.Tasks pour la bibliothèque .NET installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).

## Importer des espaces de noms

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;


```

## Étape 1 : Charger le fichier de projet

Tout d’abord, nous devons charger le fichier projet qui contient les lignes de base d’affectation.

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## Étape 2 : Lire les lignes de base des affectations

Ensuite, nous parcourons chaque affectation de ressources du projet pour accéder à leurs références respectives.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## Étape 3 : Supprimer les lignes de base d'affectation

Dans cette étape, nous montrons comment supprimer toutes les références d’affectation du projet.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## Conclusion

Une gestion efficace des références d'affectation est primordiale dans la gestion de projet, garantissant le respect des calendriers et le suivi précis de l'avancement du projet. Avec Aspose.Tasks pour .NET, la gestion des références d'affectation devient transparente, fournissant aux développeurs les outils nécessaires pour rationaliser les processus de gestion de projet.

## FAQ

### Q1 : Aspose.Tasks peut-il gérer les lignes de base d'affectation pour différents formats de fichiers de projet ?

A1 : Oui, Aspose.Tasks prend en charge divers formats de fichiers de projet, notamment MPP, XML et MPX, vous permettant de gérer sans effort les lignes de base d'affectation sur différents types de fichiers.

### Q2 : Aspose.Tasks est-il compatible avec toutes les versions de .NET Framework ?

A2 : Aspose.Tasks for .NET est compatible avec plusieurs versions du .NET Framework, garantissant ainsi la compatibilité et la flexibilité pour les développeurs dans différents environnements.

### Q3 : Puis-je manipuler les références d’affectation par programmation à l’aide d’Aspose.Tasks ?

A3 : Absolument, Aspose.Tasks fournit une API complète qui permet aux développeurs de créer, lire, mettre à jour et supprimer par programme des lignes de base d'affectation selon les exigences du projet.

### Q4 : Aspose.Tasks offre-t-il une assistance technique aux développeurs ?

A4 : Oui, Aspose.Tasks fournit un support technique solide via son forum communautaire, où les développeurs peuvent demander de l'aide, partager des connaissances et collaborer avec leurs pairs.

### Q5 : Puis-je essayer Aspose.Tasks avant de faire un achat ?

A5 : Oui, Aspose.Tasks propose une version d'essai gratuite, permettant aux développeurs d'explorer ses caractéristiques et fonctionnalités avant de prendre une décision d'achat.