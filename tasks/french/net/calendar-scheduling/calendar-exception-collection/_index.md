---
date: 2026-04-09
description: Apprenez à définir le calendrier standard et à gérer les jours fériés
  du projet dans vos projets .NET en utilisant Aspose.Tasks pour une planification
  précise.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Définir le calendrier standard et gérer les exceptions dans Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Définir le calendrier standard et gérer les exceptions dans Aspose.Tasks
url: /fr/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir le calendrier standard et gérer les exceptions dans Aspose.Tasks

## Introduction

Une planification précise est la colonne vertébrale de tout projet réussi, et les plans du monde réel doivent souvent s’écarter du calendrier de travail par défaut en raison de jours fériés, d’événements spéciaux ou d’arrêts inattendus. Aspose.Tasks pour .NET facilite la **définition d’un calendrier standard** et l’ajout d’exceptions personnalisées par-dessus. Dans ce tutoriel, vous apprendrez comment charger le calendrier d’un projet, définir un calendrier standard et gérer les jours fériés du projet grâce à la fonctionnalité Calendar Exception Collection.

## Réponses rapides
- **Que fait « set standard calendar » ?** Il réinitialise un calendrier aux heures de travail par défaut (9 h‑17 h, du lundi au vendredi) avant d’ajouter des exceptions personnalisées.  
- **Quelle méthode supprime les exceptions existantes ?** `Calendar.Exceptions.Clear()` supprime toutes les exceptions précédemment définies.  
- **Comment ajouter un jour férié ?** Créez un `CalendarException` avec `DayWorking = false` et ajoutez‑le à la collection.  
- **Dois‑je recharger le projet après les modifications ?** Non, les modifications sont appliquées directement à l’objet `Project` en mémoire.  
- **Quelles bibliothèques sont requises ?** Aspose.Tasks pour .NET (toute version .NET prise en charge) et les espaces de noms `System`.

## Prérequis

Avant de plonger dans le code, assurez‑vous d’avoir :

1. **Aspose.Tasks pour .NET** – téléchargez‑le [ici](https://releases.aspose.com/tasks/net/).  
2. Connaissances de base en **C#** – vous écrirez quelques courts extraits.  
3. Un environnement de développement tel que **Visual Studio** ou **JetBrains Rider**.

## Importer les espaces de noms

Ces directives `using` vous donnent accès aux classes nécessaires à la manipulation du calendrier.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Qu’est‑ce qu’une exception de calendrier ?

Une *exception de calendrier* représente une période pendant laquelle le planning de travail habituel est modifié – par exemple, un jour férié d’entreprise ou un planning d’heures supplémentaires temporaire. En ajoutant des exceptions à un calendrier, vous pouvez modéliser des contraintes du monde réel sans modifier le calendrier de base.

## Comment définir le calendrier standard dans Aspose.Tasks

La première étape consiste à charger votre fichier de projet et à récupérer le calendrier avec lequel vous souhaitez travailler.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Étape 1 : Supprimer les exceptions existantes et réinitialiser à un calendrier standard

Avant d’ajouter de nouvelles règles, il est recommandé de supprimer les anciennes exceptions et de **définir le calendrier standard**. Cela garantit une base propre.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Étape 2 : Définir une exception de temps de travail

Parfois, vous devez créer un planning temporaire (par ex., des heures prolongées pour le lancement d’un produit). L’extrait suivant définit une exception de temps de travail qui s’étend sur plusieurs jours et comprend deux périodes de travail quotidiennes.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Étape 3 : Ajouter des exceptions de temps non travaillé (jours fériés)

Pour **gérer les jours fériés du projet**, créez des exceptions où `DayWorking` est `false`. L’exemple ci‑dessous ajoute un bloc de deux jours fériés.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Étape 4 : Afficher les exceptions du calendrier (vérification)

Après avoir ajouté des exceptions, vous souhaiterez souvent vérifier qu’elles ont été correctement enregistrées. La boucle suivante imprime les détails de chaque exception dans la console.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Étape 5 : Supprimer toutes les exceptions (nettoyage)

Si vous devez rétablir le calendrier à son état d’origine, vous pouvez supprimer chaque exception de façon programmatique.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| Les exceptions n’apparaissent pas après l’enregistrement | Projet non enregistré après modifications | Appelez `project.Save("output.mpp")` après avoir effectué les modifications. |
| Des exceptions qui se chevauchent provoquent des heures de travail inattendues | Aspose.Tasks utilise la dernière exception ajoutée pour les périodes qui se chevauchent | Ordonnez soigneusement vos appels `Add` ou ajustez les priorités manuellement. |
| `MakeStandardCalendar` réinitialise les temps de travail personnalisés | Il supprime intentionnellement les temps personnalisés ; ré‑ajoutez‑les après l’appel si nécessaire. | Ajoutez vos objets `WorkingTime` personnalisés après avoir invoqué `MakeStandardCalendar`. |

## Questions fréquentes

**Q : Puis‑je ajouter plusieurs exceptions à un même calendrier ?**  
**R :** Oui, vous pouvez ajouter plusieurs exceptions à un calendrier en utilisant la méthode `AddRange`.

**Q : Comment gérer les exceptions récurrentes, comme les jours fériés hebdomadaires ?**  
**R :** Vous pouvez calculer programmatiquement les exceptions récurrentes et les ajouter au calendrier à l’aide d’une logique personnalisée.

**Q : Est‑il possible d’importer des exceptions de calendrier depuis des sources externes ?**  
**R :** Oui, vous pouvez lire les exceptions de calendrier depuis des sources externes comme des bases de données ou des fichiers CSV et les intégrer à votre projet.

**Q : Que se passe‑t‑il s’il y a des exceptions qui se chevauchent dans le calendrier ?**  
**R :** Aspose.Tasks pour .NET vous permet de gérer les exceptions qui se chevauchent en définissant des priorités ou en résolvant les conflits selon les exigences de votre projet.

**Q : Puis‑je personnaliser les temps de travail pour chaque jour au sein d’une exception ?**  
**R :** Oui, vous pouvez spécifier des temps de travail personnalisés pour chaque jour au sein d’une exception afin de répondre à des besoins de planification spécifiques.

## Conclusion

En **définissant d’abord un calendrier standard** puis en superposant des exceptions personnalisées, vous obtenez un contrôle total sur la planification du projet, ce qui facilite la **gestion des jours fériés du projet** et toute autre chronologie particulière. La Calendar Exception Collection dans Aspose.Tasks offre une méthode propre et programmatique pour modéliser les calendriers du monde réel directement dans vos applications .NET.

---

**Dernière mise à jour :** 2026-04-09  
**Testé avec :** Aspose.Tasks 24.12 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}