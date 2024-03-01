---
title: Gestion de la durée dans Aspose.Tasks
linktitle: Gestion de la durée dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer efficacement les durées dans Aspose.Tasks pour .NET avec des didacticiels étape par étape.
type: docs
weight: 30
url: /fr/net/calendar-scheduling/duration-handling/
---
## Introduction

La gestion efficace des durées est cruciale dans les applications de gestion de projet. Aspose.Tasks for .NET fournit des fonctionnalités robustes pour gérer efficacement les durées. Dans ce didacticiel, nous explorerons différents aspects de la gestion de la durée à l'aide d'Aspose.Tasks pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :

1. Connaissance de base de C# : La connaissance du langage de programmation C# est essentielle pour comprendre et mettre en œuvre les exemples.
2. Visual Studio : installez Visual Studio IDE pour créer et exécuter des applications .NET.
3.  Aspose.Tasks pour .NET : téléchargez et installez la bibliothèque Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).

## Importer des espaces de noms

Tout d'abord, importons les espaces de noms nécessaires pour utiliser les fonctionnalités d'Aspose.Tasks :

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Décomposons chaque exemple en plusieurs étapes dans un format de guide étape par étape :

## Mise à jour des durées des tâches

### Étape 1 : Charger le fichier de projet

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Étape 2 : Obtenez la tâche et la durée

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Étape 3 : Durée de la mise à jour

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Étape 4 : Afficher la durée mise à jour

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Soustraire les durées des tâches

### Étape 1 : Charger le fichier de projet

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Étape 2 : Obtenez la tâche et la durée

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Étape 3 : Soustraire la durée

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Étape 4 : Afficher la durée mise à jour

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Conversion de la durée en TimeSpan

### Étape 1 : Charger le fichier de projet

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Étape 2 : Obtenez la tâche et la durée

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Étape 3 : Convertir la durée en TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Conversion de la durée en chaîne

### Étape 1 : Charger le fichier de projet

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Étape 2 : Obtenez la tâche et la durée

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Étape 3 : Convertir la durée en chaîne

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Conclusion

Dans ce didacticiel, nous avons abordé divers aspects de la gestion de la durée dans Aspose.Tasks pour .NET. Comprendre et gérer efficacement les durées est essentiel pour une gestion de projet réussie. Aspose.Tasks fournit des fonctionnalités complètes pour simplifier les tâches de gestion de durée dans vos applications .NET.

## FAQ

### Q1 : Qu'est-ce qu'Aspose.Tasks pour .NET ?

A1 : Aspose.Tasks for .NET est une bibliothèque puissante permettant de travailler avec des fichiers Microsoft Project dans des applications .NET.

### Q2 : Aspose.Tasks peut-il gérer des structures de projet complexes ?

A2 : Oui, Aspose.Tasks peut gérer facilement des structures de projet complexes, en fournissant des API étendues pour la manipulation.

### Q3 : Aspose.Tasks pour .NET est-il compatible avec .NET Core ?

A3 : Oui, Aspose.Tasks for .NET est compatible avec .NET Core, vous permettant de l'utiliser dans des applications multiplateformes.

### Q4 : Aspose.Tasks prend-il en charge la lecture et l'écriture de fichiers Microsoft Project ?

A4 : Oui, Aspose.Tasks prend en charge la lecture et l'écriture de fichiers Microsoft Project dans différents formats, notamment MPP, XML et MPX.

### Q5 : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour .NET ?

A5 : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/).