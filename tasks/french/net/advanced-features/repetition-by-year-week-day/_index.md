---
date: 2026-04-03
description: Apprenez à utiliser Aspose.Tasks pour ajouter un projet de tâches récurrentes
  et enregistrer le projet au format MPP. Ce guide montre la fonctionnalité Répétition
  par Année Semaine Jour étape par étape.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Répétition par année, semaine, jour dans Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Comment utiliser Aspose.Tasks – Répétition par année, semaine et jour
url: /fr/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Répétition par jour de semaine d'année dans Aspose.Tasks

## Introduction

Lorsque vous avez besoin de **how to use Aspose.Tasks** pour gérer des plannings récurrents complexes, la bibliothèque vous offre un contrôle fin sur les modèles annuels. Dans ce tutoriel, nous allons créer une tâche qui se répète un jour de la semaine spécifique d'un mois donné, sur plusieurs années. À la fin, vous pourrez **add recurring task project** et **save project as MPP** en quelques lignes de C#.

## Réponses rapides
- **What does “Repetition by Year Week Day” mean?** Cela répète une tâche un jour de la semaine choisi (par ex., le premier dimanche) d'un mois donné chaque année.  
- **Which .NET versions are supported?** Toutes les versions modernes de .NET Framework et .NET Core/5/6.  
- **Do I need a license to run the code?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Can I change the recurrence range?** Oui – vous pouvez définir une date de début, une date de fin, ou un nombre fixe d'occurrences.  
- **Is the output an MPP file?** Absolument – le projet est enregistré au format MPP prêt pour Microsoft Project.

## Qu’est-ce que la fonctionnalité “Repetition by Year Week Day” ?

Cette fonctionnalité vous permet de définir une récurrence annuelle qui cible un **day of the week** particulier (par ex., Sunday) et une **position** dans le mois (premier, deuxième, dernier, etc.). Elle est idéale pour des tâches comme les revues trimestrielles, les audits annuels, ou tout événement suivant un rythme basé sur le calendrier.

## Pourquoi utiliser Aspose.Tasks pour les tâches récurrentes ?

- **Precision** – Contrôle complet sur les mois, les jours de la semaine et les positions ordinales.  
- **Compatibility** – Génère des fichiers MPP natifs qui s'ouvrent parfaitement dans Microsoft Project.  
- **No COM interop** – API .NET pure, aucune installation Office requise.  
- **Scalability** – Fonctionne aussi bien pour de petits projets que pour des plannings d'entreprise.

## Prérequis

Avant de plonger dans le code, assurez-vous d'avoir :

1. **Basic .NET knowledge** – Familiarité avec C# et les concepts orientés objet.  
2. **Aspose.Tasks for .NET** – Téléchargez-le depuis le [download link](https://releases.aspose.com/tasks/net/) et ajoutez le DLL à votre projet.  
3. **Access to the official docs** – La [documentation](https://reference.aspose.com/tasks/net/) contient des détails exhaustifs sur toutes les classes.  
4. **A development IDE** – Visual Studio, Rider, ou tout éditeur .NET compatible.

Maintenant que tout est prêt, voyons l'implémentation.

## Comment utiliser Aspose.Tasks pour les tâches récurrentes

### Importation des espaces de noms nécessaires

Tout d'abord, importez les espaces de noms requis afin de pouvoir travailler avec les projets, les tâches et les options d'enregistrement.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Étape 1 : Initialiser le projet et les paramètres de tâche

Créez une nouvelle instance `Project`, puis définissez un objet `RecurringTaskParameters` qui décrit le modèle de récurrence.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Ajustez `Month`, `WeekDay` et `Position` pour correspondre à votre planning réel.

### Étape 2 : Ajouter les paramètres au projet

Insérez la définition de la tâche récurrente à la racine du projet.

```csharp
project.RootTask.Children.Add(parameters);
```

### Étape 3 : Enregistrer le projet au format MPP

Enfin, persistez le projet dans un fichier MPP afin qu'il puisse être ouvert dans Microsoft Project ou tout visualiseur compatible.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Ceci démontre **save project as mpp** en une seule ligne de code.

## Problèmes courants et solutions

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Aucune tâche n'apparaît après l'ouverture du fichier MPP | Les dates de la plage de récurrence sont en dehors du calendrier du projet | Vérifiez que les dates `Start` et `Finish` se situent dans le temps de travail du projet |
| Exception `ArgumentNullException` sur `Add` | `parameters` est nul ou pas entièrement initialisé | Assurez-vous que toutes les propriétés requises (TaskName, Duration, RecurrencePattern) sont définies |
| Jour de la semaine sélectionné incorrect | Valeur d'énumération `WeekDay` incohérente | Utilisez `DayOfWeek.Monday` … `DayOfWeek.Sunday` selon les besoins |

## Questions fréquemment posées

**Q : Puis-je personnaliser le modèle de récurrence au-delà de l'exemple fourni ?**  
A : Oui, Aspose.Tasks vous permet de combiner `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` ou même des objets `RecurrenceRange` personnalisés pour s'adapter à n'importe quel planning.

**Q : Aspose.Tasks pour .NET est-il compatible avec d'autres logiciels de gestion de projet ?**  
A : Absolument – la bibliothèque lit et écrit les formats MPP, XML et Primavera, permettant un échange de données fluide.

**Q : Comment gérer les exceptions ou les modifications des tâches récurrentes ?**  
A : Utilisez la classe `ExceptionTask` pour créer des remplacements pour des occurrences spécifiques, ou modifiez les `RecurringTaskParameters` et réenregistrez le projet.

**Q : Aspose.Tasks prend‑il en charge les solutions cloud ?**  
A : Oui, vous pouvez exécuter l'API dans Azure Functions, AWS Lambda, ou tout service cloud compatible .NET.

**Q : Existe‑t‑il une version d'essai disponible pour Aspose.Tasks pour .NET ?**  
A : Oui, vous pouvez accéder à un essai gratuit d'Aspose.Tasks pour .NET depuis le [website](https://releases.aspose.com/), vous permettant d'explorer ses fonctionnalités avant de prendre une décision d'achat.

**Q : Comment ajouter une tâche récurrente à un projet existant sans écraser les autres données ?**  
A : Chargez le projet existant avec `new Project("Existing.mpp")`, ajoutez les `RecurringTaskParameters` à `RootTask.Children`, puis `Save` le fichier.

## Conclusion

En maîtrisant **how to use Aspose.Tasks** pour le scénario **Repetition by Year Week Day**, vous obtenez la capacité d'**add recurring task project** des entrées qui s'alignent parfaitement avec les calendriers réels et **save project as MPP** pour une collaboration fluide. Intégrez ces extraits dans vos propres solutions pour améliorer la précision de la planification et réduire l'effort manuel.

---

**Dernière mise à jour :** 2026-04-03  
**Testé avec :** Aspose.Tasks 24.12 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}