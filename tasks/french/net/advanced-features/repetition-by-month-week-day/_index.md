---
date: 2026-04-01
description: Apprenez à définir la récurrence dans Aspose.Tasks pour .NET, à ajouter
  une tâche récurrente et à automatiser les tâches récurrentes par mois, semaine et
  jour.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Répétition par mois, semaine, jour dans Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Comment définir la récurrence dans Aspose.Tasks (Mois, Semaine, Jour)
url: /fr/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la récurrence dans Aspose.Tasks (Mois, Semaine, Jour)

## Introduction

Si vous devez **how to set recurrence** pour des tâches dans un projet, Aspose.Tasks for .NET vous offre une méthode propre et programmatique pour ajouter des définitions de tâches récurrentes qui s’exécutent par mois, semaine ou jour. Dans ce tutoriel, nous parcourrons un exemple réel qui vous montre comment **add recurring task** des entrées, **automate recurring tasks**, et les gérer directement depuis le code C#. À la fin, vous serez prêt à intégrer cette fonctionnalité dans toute solution de planification ou de gestion de projet.

## Réponses rapides
- **What does “recurrence” mean in Aspose.Tasks?** Il définit un modèle (quotidien, hebdomadaire, mensuel) qui crée automatiquement des instances de tâches sur une plage de dates.  
- **Which primary method creates the recurrence?** `RecurringTaskParameters` combiné avec un `RecurrencePattern` spécifique.  
- **Do I need a license to run this code?** Un essai fonctionne pour l’évaluation ; une licence commerciale est requise pour la production.  
- **Can I schedule weekly tasks instead of monthly?** Oui – remplacez `MonthlyRecurrencePattern` par `WeeklyRecurrencePattern`.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 et versions ultérieures.

## Qu’est‑ce que la récurrence dans Aspose.Tasks ?

La récurrence est un ensemble de règles qui indique à Aspose.Tasks de générer des instances de tâches à intervalles réguliers—quotidiennement, chaque semaine ou chaque mois—sans les dupliquer manuellement. Cette fonctionnalité est essentielle pour les projets contenant des activités récurrentes telles que des réunions de suivi, des inspections ou des travaux de maintenance.

## Pourquoi utiliser les fonctionnalités de récurrence ?

- **Save time:** Aucun besoin de copier‑coller les tâches manuellement.  
- **Reduce errors:** La bibliothèque garantit des dates et des durées cohérentes.  
- **Flexibility:** Combinez des modèles (p. ex., « premier dimanche de chaque 2 mois »).  
- **Automation:** Idéal pour générer des plannings dans les pipelines CI ou les outils de reporting.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

1. **Basic Understanding of C#** – vous écrirez quelques lignes de code C#.  
2. **Aspose.Tasks for .NET installed** – téléchargez‑le depuis la [page de téléchargement](https://releases.aspose.com/tasks/net/).  
3. **A .mpp project file** – nous utiliserons `Project1.mpp` comme fichier source.

## Importer les espaces de noms

To begin, import the required Aspose.Tasks namespaces:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Étape 1 : Charger le fichier de projet

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Nous créons une instance `Project` qui pointe vers un fichier Microsoft Project existant.

### Étape 2 : Définir les paramètres de tâche récurrente

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Ici nous **create recurring task** les paramètres :

- **TaskName** – le nom de la tâche générée.  
- **Duration** – la durée de chaque occurrence.  
- **RecurrencePattern** – un modèle mensuel qui se répète tous les 2 mois le premier dimanche.  
- **RecurrenceRange** – les dates de début et de fin qui délimitent le planning.

### Étape 3 : Ajouter la tâche récurrente au projet

```csharp
project.RootTask.Children.Add(parameters);
```

Cette ligne **adds the recurring task** à la racine de la hiérarchie du projet.

### Étape 4 : Enregistrer le projet mis à jour

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Le projet est enregistré sous un nouveau fichier `.mpp` qui contient désormais le planning automatisé.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Task not appearing** | La plage de récurrence est en dehors des dates du projet. | Vérifiez que les valeurs `Start` et `Finish` sont dans le calendrier du projet. |
| **Wrong weekday** | Incohérence de l’énumération `WeekDay`. | Utilisez `DayOfWeek.Monday` … `DayOfWeek.Sunday` selon les besoins. |
| **License exception** | Exécution sans licence valide en production. | Appliquez une licence temporaire ou complète avant l’enregistrement. |

## Questions fréquemment posées

### Q1 : Puis‑je personnaliser le modèle de récurrence au‑delà des exemples fournis ?

R1 : Oui, Aspose.Tasks for .NET offre de vastes options de personnalisation des modèles de récurrence, vous permettant de les adapter à vos besoins spécifiques.

### Q2 : Existe‑t‑il une version d’essai disponible pour Aspose.Tasks for .NET ?

R2 : Oui, vous pouvez obtenir un essai gratuit d’Aspose.Tasks for .NET depuis la [page des versions](https://releases.aspose.com/).

### Q3 : Comment puis‑je obtenir du support pour Aspose.Tasks for .NET ?

R3 : Vous pouvez demander de l’aide et interagir avec la communauté sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q4 : Des licences temporaires sont‑elles disponibles pour Aspose.Tasks for .NET ?

R4 : Oui, vous pouvez acquérir des licences temporaires depuis la [page d’achat](https://purchase.aspose.com/temporary-license/) à des fins de test et d’évaluation.

### Q5 : Où puis‑je trouver une documentation complète pour Aspose.Tasks for .NET ?

R5 : Vous pouvez consulter la [documentation](https://reference.aspose.com/tasks/net/) détaillée disponible sur le site Aspose pour des instructions approfondies sur l’utilisation de la bibliothèque.

---

**Dernière mise à jour :** 2026-04-01  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}