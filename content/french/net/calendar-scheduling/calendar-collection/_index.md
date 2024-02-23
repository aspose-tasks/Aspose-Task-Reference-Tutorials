---
title: Gestion de la collection de calendriers dans Aspose.Tasks
linktitle: Gestion de la collection de calendriers dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les collections de calendriers dans Aspose.Tasks pour .NET. Créez, modifiez et manipulez facilement des calendriers.
type: docs
weight: 11
url: /fr/net/calendar-scheduling/calendar-collection/
---
## Introduction

Dans ce didacticiel, nous verrons comment gérer les collections de calendriers dans Aspose.Tasks pour .NET. Les calendriers jouent un rôle crucial dans la gestion de projet, définissant les jours ouvrables, les jours fériés et les exceptions. Aspose.Tasks fournit des fonctionnalités robustes pour manipuler les calendriers au sein de vos projets.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Visual Studio : installez Visual Studio ou tout autre IDE compatible pour le développement .NET.
2.  Aspose.Tasks pour .NET : téléchargez et installez Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Compréhension de base de C# : Une connaissance du langage de programmation C# sera bénéfique.

## Importer des espaces de noms

Tout d'abord, importons les espaces de noms nécessaires pour travailler avec Aspose.Tasks :

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Créer un nouveau calendrier

###  Étape 1 : initialiser un nouveau`Project` object.
```csharp
var project = new Project();
```

### Étape 2 : ajoutez des calendriers à la collection de calendriers du projet.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Étape 3 : Parcourez les calendriers et affichez leurs noms.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Remplacement d'un calendrier par un nouveau calendrier

### Étape 1 : Chargez un projet existant.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Étape 2 : Supprimez le calendrier existant (s'il existe).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Étape 3 : Ajoutez un nouveau calendrier.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Obtenir le calendrier par nom ou identifiant

### Étape 1 : Chargez le projet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Étape 2 : Récupérez les calendriers par nom ou UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Étape 3 : Affichez les détails du calendrier.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Itérer sur des calendriers

### Étape 1 : Chargez le projet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Étape 2 : Récupérez le nombre de calendriers.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Étape 3 : Parcourez la collection de calendriers et les noms d'affichage.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Créer un calendrier standard

### Étape 1 : Initialisez un nouveau projet.
```csharp
var project = new Project();
```

### Étape 2 : Définir un nouveau calendrier et le rendre standard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Étape 3 : Enregistrez le projet.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Conclusion

La gestion des collections de calendriers dans Aspose.Tasks pour .NET est essentielle pour une gestion de projet efficace. Avec les fonctionnalités fournies, vous pouvez créer, modifier et manipuler efficacement des calendriers en fonction des exigences de votre projet.

## FAQ

### Q1 : Puis-je créer des jours de travail personnalisés dans Aspose.Tasks ?

A1 : Oui, vous pouvez créer des jours de travail personnalisés en ajoutant des exceptions aux calendriers.

### Q2 : Est-il possible d'importer des calendriers à partir de fichiers Microsoft Project ?

A2 : Absolument, Aspose.Tasks prend en charge l'importation de calendriers à partir de fichiers Microsoft Project.

### Q3 : Comment puis-je supprimer un calendrier spécifique d'un projet ?

A3 : Vous pouvez supprimer un calendrier en le récupérant de la collection, puis en appelant le`Remove` méthode.

### Q4 : Aspose.Tasks prend-il en charge l'exportation de calendriers vers différents formats ?

A4 : Oui, Aspose.Tasks permet d'exporter des calendriers vers différents formats comme XML, MPP, etc.

### Q5 : Puis-je personnaliser les heures de travail pour des jours spécifiques dans un calendrier ?

A5 : Vous pouvez certainement définir des heures de travail pour des jours individuels en utilisant des exceptions dans le calendrier.