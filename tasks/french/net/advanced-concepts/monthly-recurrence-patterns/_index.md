---
date: 2026-03-08
description: Apprenez à créer une tâche récurrente mensuelle dans Aspose.Tasks pour
  .NET avec ce tutoriel étape par étape.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Comment créer une tâche récurrente mensuelle dans Aspose.Tasks
url: /fr/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une tâche récurrente mensuelle avec Aspose.Tasks

## Introduction

Aspose.Tasks for .NET vous permet de manipuler programmatiquement les fichiers Microsoft Project, et l’un des besoins réels les plus courants est de **créer une tâche récurrente mensuelle**. Que vous construisiez un outil de suivi de projet, automatisiez l’allocation des ressources, ou génériez des éléments de maintenance récurrents, ce tutoriel vous guide pas à pas pour ajouter un modèle de récurrence mensuelle à une tâche.

Dans les sections suivantes, vous verrez comment configurer le projet, définir les paramètres de récurrence, puis enregistrer le fichier mis à jour — le tout avec des explications claires et des conseils pratiques.

## Quick Answers
- **Que signifie « tâche récurrente mensuelle » ?** Une tâche qui se répète selon un modèle jour‑ou‑semaine défini chaque mois.  
- **Quelle classe API gère la récurrence ?** `RecurringTaskParameters` avec `MonthlyRecurrencePattern`.  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Un essai gratuit suffit pour l’évaluation ; une licence est requise en production.  
- **Puis‑je modifier l’intervalle ?** Oui – définissez `RepetitionInterval` au nombre de mois entre les occurrences.  
- **Quels formats de fichiers sont pris en charge ?** Les fichiers Project `.mpp` et `.xml` peuvent être chargés et enregistrés.

## What is a Monthly Recurrence Pattern?

Un modèle de récurrence mensuelle indique à Microsoft Project (et à Aspose.Tasks) à quelle fréquence une tâche doit se répéter chaque mois. Vous pouvez spécifier un jour fixe du mois (par ex., le 1ᵉʳ) ou une position relative (par ex., le dernier vendredi). L’API traduit ces règles dans la structure sous‑jacente du fichier Project.

## Why use Aspose.Tasks for this?

- **Full control** – No UI limitations; you define every aspect of the pattern in code.  
- **Cross‑platform** – Works on .NET Framework, .NET Core, and .NET 5/6+.  
- **No Microsoft Project required** – Generate or modify files on a server or CI pipeline.  

## Prerequisites

Avant de commencer, assurez‑vous d’avoir :

- .NET 6 (ou .NET 5/Framework 4.7+) installé.  
- Le package NuGet Aspose.Tasks for .NET ajouté à votre projet.  
- Un fichier Project d’exemple (`Project1.mpp`) placé dans un dossier connu (`DataDir`).  

## Import Namespaces

Tout d’abord, importez les espaces de noms requis pour travailler avec les tâches et enregistrer les projets :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Step 1: Initialize the Project

Créez une instance `Project` qui pointe vers votre fichier `.mpp` existant. Cela charge le fichier en mémoire afin que vous puissiez le modifier.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Pro tip:** Si le fichier n’existe pas, Aspose.Tasks créera automatiquement un nouveau projet vierge.

## Step 2: Set Recurring Task Parameters

Définissez les détails de la tâche récurrente, y compris son nom, sa durée et le modèle mensuel que vous souhaitez appliquer.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` signifie que la tâche se produit le **premier jour** du mois.  
- `RepetitionInterval = 2` fait que la tâche se répète **tous les deux mois**.  
- `Start` et `Finish` définissent la fenêtre globale pendant laquelle la récurrence est active.

## Step 3: Add Parameters to the Project

Attachez l’objet `RecurringTaskParameters` à la collection des enfants de la tâche racine. Cela crée effectivement la tâche récurrente dans la hiérarchie du projet.

```csharp
project.RootTask.Children.Add(parameters);
```

## Step 4: Save the Project

Persistez les modifications en enregistrant le projet dans un nouveau fichier. Vous pouvez choisir n’importe quel format supporté ; ici nous utilisons le format natif `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Après l’exécution du code, ouvrez le fichier résultant dans Microsoft Project pour voir la tâche récurrente mensuelle que vous venez de créer.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| La tâche n’apparaît pas après l’enregistrement | Projet non rafraîchi dans l’UI | Ré‑ouvrez le fichier ou appelez `project.UpdateTaskLinks()` avant d’enregistrer. |
| Date de début incorrecte | `Start` fixé à un week‑end | Utilisez un `DateTime` qui tombe sur un jour ouvrable ou ajustez le calendrier. |
| Intervalle de récurrence ignoré | Utilisation de `ByMonthDayRepetition` avec `DayPosition` = 0 | Assurez‑vous que `DayPosition` est compris entre 1‑31. |

## Conclusion

En suivant ces étapes, vous savez maintenant comment **créer une tâche récurrente mensuelle** avec Aspose.Tasks pour .NET. L’API vous offre un contrôle granulaire sur les intervalles de récurrence, les plages de début/fin et le modèle de jour spécifique, vous permettant d’automatiser des scénarios de planification de projet complexes.

## FAQ's

### Q1 : Aspose.Tasks est‑il compatible avec toutes les versions des fichiers Microsoft Project ?

R1 : Aspose.Tasks prend en charge diverses versions des fichiers Microsoft Project, y compris MPP, MPT, XML et MPX.

### Q2 : Puis‑je personnaliser davantage le modèle de récurrence ?

R2 : Oui, Aspose.Tasks propose de nombreuses options pour personnaliser les modèles de récurrence, y compris quotidien, hebdomadaire, mensuel et annuel.

### Q3 : Existe‑t‑il un essai gratuit d’Aspose.Tasks ?

R3 : Oui, vous pouvez obtenir un essai gratuit d’Aspose.Tasks depuis le site web [ici](https://releases.aspose.com/).

### Q4 : Comment obtenir du support pour Aspose.Tasks ?

R4 : Vous pouvez demander de l’aide et participer aux discussions sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5 : Où puis‑je acheter une licence pour Aspose.Tasks ?

R5 : Vous pouvez acheter une licence pour Aspose.Tasks sur le site web [ici](https://purchase.aspose.com/buy)

## Frequently Asked Questions

**Q : Puis‑je utiliser ce code dans une application .NET Core ?**  
R : Absolument. Aspose.Tasks for .NET prend pleinement en charge .NET Core 3.1 et les versions ultérieures.

**Q : Comment changer la récurrence en « dernier jour ouvrable du mois » ?**  
R : Utilisez `ByMonthDayRepetition` avec `DayPosition = -1` (les valeurs négatives comptent depuis la fin du mois) et définissez `WeekDay` en conséquence.

**Q : Que se passe‑t‑il si la plage de récurrence dépasse le calendrier du projet ?**  
R : L’API respecte le calendrier du projet ; les occurrences tombant sur des jours non ouvrés sont soit ignorées, soit déplacées selon les paramètres du calendrier.

**Q : Est‑il possible de supprimer une occurrence spécifique d’une tâche récurrente ?**  
R : Oui. Après avoir ajouté la tâche récurrente, vous pouvez récupérer les occurrences individuelles via `Task.GetOccurrences()` et supprimer celles dont vous n’avez pas besoin.

**Q : Aspose.Tasks gère‑t‑il automatiquement les différences de fuseau horaire ?**  
R : La bibliothèque stocke les dates en UTC ; vous pouvez les convertir en heure locale à l’aide des méthodes standard .NET `DateTime` si nécessaire.

---

**Dernière mise à jour :** 2026-03-08  
**Testé avec :** Aspose.Tasks 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}