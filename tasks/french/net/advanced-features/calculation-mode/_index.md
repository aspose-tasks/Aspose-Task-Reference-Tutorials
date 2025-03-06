---
title: Mode de calcul dans Aspose.Tasks
linktitle: Mode de calcul dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les modes de calcul dans Aspose.Tasks pour .NET afin de rationaliser la planification des projets et les dépendances des tâches.
weight: 29
url: /fr/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mode de calcul dans Aspose.Tasks

## Introduction

Aspose.Tasks for .NET est une API puissante qui permet aux développeurs de travailler avec des fichiers Microsoft Project par programmation dans leurs applications .NET. Un aspect crucial du travail avec des fichiers de projet est la gestion des modes de calcul, qui dictent la manière dont les tâches et les calendriers de projet sont calculés et mis à jour. Dans ce didacticiel, nous examinerons les différents modes de calcul pris en charge par Aspose.Tasks pour .NET et montrerons comment les utiliser efficacement.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre système.
2.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Compréhension de base de la programmation C# : Familiarisez-vous avec les concepts de programmation C#.

## Importer des espaces de noms

Avant de commencer à travailler avec Aspose.Tasks pour .NET, importons les espaces de noms nécessaires :

```csharp
using Aspose.Tasks;
using System;


```

## Application du mode de calcul automatique

### Étape 1 : Créer une nouvelle instance de projet

 Initialiser un nouveau`Project` objet et définir son`CalculationMode` propriété à`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Étape 2 : Définir la date de début du projet et ajouter des tâches

Définissez la date de début du projet et ajoutez-y des tâches.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Étape 3 : Lier les tâches

Établir des dépendances entre les tâches.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Étape 4 : Vérifiez les dates recalculées

Vérifiez si les dates ont été recalculées automatiquement.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Ajoutez plus de vérifications si nécessaire
```

## Application du mode de calcul manuel

### Étape 1 : Créer une nouvelle instance de projet

 Initialiser un nouveau`Project` objet et définir son`CalculationMode` propriété à`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Étape 2 : Définir la date de début du projet et ajouter des tâches

Définissez la date de début du projet et ajoutez-y des tâches.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Étape 3 : Vérifier les propriétés de la tâche

Vérifiez si les propriétés de la tâche sont correctement définies en mode manuel.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Ajoutez plus de vérifications si nécessaire
```

### Étape 4 : Lier les tâches et vérifier les dates

Liez les tâches entre elles et vérifiez si leurs dates ne sont pas recalculées.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Application du mode de calcul Aucun

### Étape 1 : Créer une nouvelle instance de projet

 Initialiser un nouveau`Project` objet et définir son`CalculationMode` propriété à`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Étape 2 : Ajouter une nouvelle tâche

Ajoutez une nouvelle tâche au projet.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Étape 3 : Vérifier les propriétés de la tâche

Vérifiez si les propriétés de la tâche ne sont pas automatiquement calculées.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Ajoutez plus de vérifications si nécessaire
```

## Conclusion

Dans ce didacticiel, nous avons exploré les modes de calcul disponibles dans Aspose.Tasks pour .NET et appris à les appliquer dans des scénarios pratiques. Que vous ayez besoin d'un mode de calcul automatique, manuel ou sans calcul, Aspose.Tasks offre la flexibilité nécessaire pour répondre aux exigences de votre projet.

## FAQ

### Q1 : Puis-je modifier le mode de calcul de manière dynamique pendant l'exécution ?

A1 : Oui, vous pouvez changer le mode de calcul d'un projet à tout moment pendant l'exécution en modifiant le`CalculationMode` propriété.

### Q2 : Aspose.Tasks prend-il en charge d'autres formats de fichiers de gestion de projet en plus de Microsoft Project ?

A2 : Aspose.Tasks se concentre principalement sur les formats de fichiers Microsoft Project, mais il prend également en charge d'autres formats tels que Primavera P6 XML, Primavera DB et Asta Powerproject XML.

### Q3 : Aspose.Tasks est-il adapté aux projets à petite échelle et au niveau de l'entreprise ?

A3 : Absolument ! Aspose.Tasks est conçu pour répondre aux besoins des projets à petite échelle et au niveau de l'entreprise grâce à ses fonctionnalités complètes et ses API robustes.

### Q4 : Puis-je intégrer Aspose.Tasks à d’autres bibliothèques et frameworks .NET ?

A4 : Oui, vous pouvez intégrer de manière transparente Aspose.Tasks à d’autres bibliothèques et frameworks .NET pour améliorer les fonctionnalités de vos applications.

### Q5 : Existe-t-il un forum communautaire ou un canal d'assistance disponible pour les utilisateurs d'Aspose.Tasks ?

 A5 : Oui, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien et les discussions de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
