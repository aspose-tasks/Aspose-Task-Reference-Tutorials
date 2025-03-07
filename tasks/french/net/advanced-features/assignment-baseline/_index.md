---
title: Gestion de la ligne de base des affectations dans Aspose.Tasks
linktitle: Gestion de la ligne de base des affectations dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer efficacement les références d'affectation avec Aspose.Tasks pour .NET, garantissant un suivi précis de l'avancement et des performances du projet.
weight: 14
url: /fr/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestion de la ligne de base des affectations dans Aspose.Tasks

## Introduction

Lorsque vous travaillez sur des tâches de gestion de projet, la gestion des références d’affectation est cruciale pour suivre avec précision les progrès. Aspose.Tasks for .NET fournit un ensemble complet d'outils pour gérer efficacement les références d'affectation. Dans ce didacticiel, nous aborderons étape par étape le processus de gestion des références d’affectation.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des prérequis suivants :

- Connaissance de base du langage de programmation C#.
- Visual Studio installé sur votre système.
- Aspose.Tasks pour la bibliothèque .NET ajoutée à votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
- Accès à un fichier projet au format MPP.

## Importer des espaces de noms

Pour commencer à travailler avec Aspose.Tasks, vous devez importer les espaces de noms nécessaires dans votre projet C#. Ajoutez les espaces de noms suivants au début de votre fichier C# :

```csharp
using Aspose.Tasks;
using System;


```

## Étape 1 : charger le projet et définir la référence

 Tout d'abord, chargez le fichier du projet à l'aide du`Project` classe d’Aspose.Tasks. Ensuite, définissez le type de référence pour le projet à l'aide du`SetBaseline` méthode.

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Étape 2 : Lire les informations de base sur l'affectation

Parcourez chaque affectation de ressources du projet et récupérez les informations de base pour chaque affectation.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Étape 3 : Vérifier l'égalité de base

Comparez les informations de base pour différentes missions à l'aide de diverses méthodes de comparaison fournies par Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Vérifier l'égalité de base
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Vérifier la comparaison de base
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Afficher les hashcodes de base
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Conclusion

La gestion des références d'affectation fait partie intégrante de la gestion de projet, permettant un suivi précis des progrès et des performances. Avec Aspose.Tasks pour .NET, la gestion des références d'affectation devient rationalisée et efficace, offrant aux développeurs des outils puissants pour améliorer les flux de travail de gestion de projet.

## FAQ

### Q1 : Aspose.Tasks peut-il gérer plusieurs lignes de base pour une seule affectation ?

A1 : Oui, Aspose.Tasks prend en charge plusieurs références pour chaque mission, permettant un suivi complet de l'avancement du projet au fil du temps.

### Q2 : Aspose.Tasks est-il compatible avec divers formats de fichiers de projet autres que MPP ?

A2 : Oui, Aspose.Tasks prend en charge un large éventail de formats de fichiers de projet, notamment XML, MPX et MPP, garantissant la compatibilité avec divers outils de gestion de projet.

### Q3 : Puis-je modifier les informations de base par programmation à l’aide d’Aspose.Tasks ?

A3 : Absolument, Aspose.Tasks fournit des API complètes pour modifier dynamiquement les informations de base en fonction des exigences du projet, offrant ainsi flexibilité et contrôle sur les processus de gestion de projet.

### Q4 : Aspose.Tasks propose-t-il de la documentation et des ressources d'assistance aux développeurs ?

A4 : Oui, les développeurs peuvent accéder à une documentation complète, des didacticiels et des forums sur le site Web Aspose.Tasks, facilitant ainsi une intégration et un dépannage fluides.

### Q5 : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour .NET ?

 A5 : Oui, les développeurs peuvent obtenir une version d'essai gratuite d'Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/), leur permettant d'évaluer ses caractéristiques et capacités avant de prendre une décision d'achat.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
