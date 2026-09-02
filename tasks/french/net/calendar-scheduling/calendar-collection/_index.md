---
date: 2026-04-13
description: Apprenez à définir les heures de travail et à gérer les collections de
  calendriers dans Aspose.Tasks pour .NET. Importez les calendriers Microsoft Project,
  supprimez le calendrier d’un projet et récupérez un calendrier par son nom facilement.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Gestion de la collection de calendriers dans Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Définir les heures de travail dans la collection de calendriers Aspose.Tasks
url: /fr/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir les heures de travail dans la collection de calendriers Aspose.Tasks

Dans ce tutoriel, vous apprendrez comment **définir les heures de travail** et gérer les collections de calendriers à l'aide d'Aspose.Tasks pour .NET. Les calendriers définissent les jours ouvrés, les jours fériés et les exceptions, ainsi les maîtriser vous permet de contrôler les plannings de projet avec précision. Nous vous montrerons également comment importer des calendriers depuis Microsoft Project, supprimer un calendrier d'un projet et obtenir un calendrier par son nom.

## Réponses rapides
- **Quelle est la classe principale pour les calendriers ?** Collection `Project.Calendars`.
- **Comment définir les heures de travail ?** Créez ou modifiez un objet `Calendar` et définissez son `WorkingTime`.
- **Puis-je importer des calendriers depuis Microsoft Project ?** Oui – chargez un fichier MPP et accédez à ses calendriers.
- **Comment supprimer un calendrier d'un projet ?** Utilisez `Project.Calendars.Remove(calendar)`.
- **Comment récupérer un calendrier par son nom ?** Appelez `Project.Calendars.GetByName("YourCalendar")`.

## Prérequis

Avant de commencer, assurez-vous de disposer de ce qui suit :

1. Visual Studio : Installez Visual Studio ou tout autre IDE compatible avec le développement .NET.  
2. Aspose.Tasks pour .NET : Téléchargez et installez Aspose.Tasks pour .NET depuis [here](https://releases.aspose.com/tasks/net/).  
3. Connaissances de base en C# : Une familiarité avec le langage de programmation C# sera bénéfique.

## Importer les espaces de noms

Tout d'abord, importons les espaces de noms nécessaires pour travailler avec Aspose.Tasks :

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Créer un nouveau calendrier

### Étape 1 : Initialiser un nouvel objet `Project`.
```csharp
var project = new Project();
```

### Étape 2 : Ajouter des calendriers à la collection de calendriers du projet.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Étape 3 : Parcourir les calendriers et afficher leurs noms.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Comment définir les heures de travail pour un calendrier ?

Pour **définir les heures de travail**, vous modifiez la collection `WorkingTime` d'un `Calendar`.  
Par exemple, vous pouvez définir une journée de travail standard de 9 h à 17 h ou ajouter des exceptions personnalisées.  
Le code pour cela est identique aux exemples présentés plus tard lorsque nous créons un calendrier standard.

## Remplacer un calendrier par un nouveau calendrier

### Étape 1 : Charger un projet existant.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Étape 2 : Supprimer le calendrier existant (s'il existe).  
Cela illustre le scénario de **suppression de calendrier du projet**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Étape 3 : Ajouter un nouveau calendrier.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Récupérer un calendrier par nom ou ID

### Étape 1 : Charger le projet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Étape 2 : Récupérer les calendriers par nom ou UID.  
Cela illustre l'opération **get calendar by name**.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Étape 3 : Afficher les détails du calendrier.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Parcourir les calendriers

### Étape 1 : Charger le projet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Étape 2 : Récupérer le nombre de calendriers.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Étape 3 : Parcourir la collection de calendriers et afficher les noms.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Créer un calendrier standard

### Étape 1 : Initialiser un nouveau projet.
```csharp
var project = new Project();
```

### Étape 2 : Définir un nouveau calendrier et le rendre standard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Étape 3 : Enregistrer le projet.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Problèmes courants et solutions

- **Calendrier non trouvé lors de l'utilisation de `GetByName`** – Assurez‑vous que le nom exact correspond à la casse utilisée lors de l'ajout du calendrier.  
- **Heures de travail non appliquées** – Après avoir défini `WorkingTime`, n'oubliez pas d'enregistrer le projet ; sinon les modifications restent uniquement en mémoire.  
- **L'importation de calendriers depuis un fichier MPP échoue** – Vérifiez que le fichier source est un fichier Microsoft Project valide et que vous disposez des permissions de lecture.

## FAQ

### Q1 : Puis-je créer des jours ouvrés personnalisés dans Aspose.Tasks ?
R1 : Oui, vous pouvez créer des jours ouvrés personnalisés en ajoutant des exceptions aux calendriers.

### Q2 : Est‑il possible d'importer des calendriers depuis des fichiers Microsoft Project ?
R2 : Absolument, Aspose.Tasks prend en charge l'importation de calendriers depuis des fichiers Microsoft Project.

### Q3 : Comment puis‑je supprimer un calendrier spécifique d'un projet ?
R3 : Vous pouvez supprimer un calendrier en le récupérant depuis la collection puis en appelant la méthode `Remove`.

### Q4 : Aspose.Tasks prend‑il en charge l'exportation des calendriers vers différents formats ?
R4 : Oui, Aspose.Tasks permet d'exporter les calendriers vers divers formats tels que XML, MPP, etc.

### Q5 : Puis‑je personnaliser les heures de travail pour des jours spécifiques dans un calendrier ?
R5 : Bien sûr, vous pouvez définir les heures de travail pour des jours individuels en utilisant des exceptions dans le calendrier.

## Questions fréquemment posées

**Q : Quelle est la meilleure façon de définir un calendrier de quart de 24 heures ?**  
R : Créez un nouveau calendrier, videz les entrées `WorkingTime` existantes, puis ajoutez une seule plage `WorkingTime` de 00 h00 à 24 h00 pour chaque jour de la semaine.

**Q : Puis‑je copier un calendrier d'un projet à un autre ?**  
R : Oui—exportez le calendrier au format XML avec `project.Save` puis importez‑le dans un autre projet avec `new Project(xmlPath)`.

**Q : Comment importer programmétiquement des calendriers depuis Microsoft Project ?**  
R : Chargez le fichier MPP avec `new Project("source.mpp")` ; les calendriers sont alors accessibles via `project.Calendars`.

**Q : Existe‑t‑il une limite au nombre de calendriers dans un projet ?**  
R : Pratiquement non ; la collection peut contenir autant de calendriers que la mémoire le permet, mais il est recommandé de garder la liste gérable pour des raisons de performance.

**Q : Les modifications d'un calendrier mettent‑elles automatiquement à jour les tâches qui l'utilisent ?**  
R : Oui—les tâches liées à un calendrier reflètent les heures de travail mises à jour après l'enregistrement du projet.

---

**Dernière mise à jour :** 2026-04-13  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}