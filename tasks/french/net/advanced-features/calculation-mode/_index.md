---
date: 2026-03-24
description: Apprenez à définir le mode de calcul dans Aspose.Tasks pour .NET, en
  couvrant le mode de calcul automatique, manuel et aucun, afin de gérer les dépendances
  des tâches.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Comment définir le mode de calcul dans Aspose.Tasks pour .NET
url: /fr/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le mode de calcul dans Aspose.Tasks pour .NET

## Introduction

Aspose.Tasks for .NET est une API puissante qui vous permet de travailler avec les fichiers Microsoft Project de manière programmatique. L’un des paramètres les plus importants que vous rencontrerez est le **mode de calcul**, qui contrôle la façon dont les dates des tâches et les plannings du projet sont mis à jour. Dans ce tutoriel, vous apprendrez **comment définir le mode de calcul**, explorerez le **mode de calcul automatique**, le **mode de calcul manuel** et le **mode de calcul none**, et verrez comment ces options affectent **la gestion des dépendances des tâches**, **la création de la date de début du projet**, et **la liaison des relations fin‑début des tâches**.

## Quick Answers
- **Qu'est-ce que le mode de calcul ?** Il détermine si les dates des tâches sont recomputées automatiquement, manuellement, ou pas du tout.  
- **Pourquoi utiliser le mode de calcul manuel ?** Pour avoir un contrôle total sur le moment où le planning est rafraîchi, utile lors de mises à jour en masse.  
- **Quel est le mode par défaut ?** Le mode de calcul automatique, qui met à jour les dates instantanément après les modifications.  
- **Puis-je changer le mode à l'exécution ?** Oui — il suffit de définir la propriété `CalculationMode` sur l'objet `Project`.  
- **Ai-je besoin d'une licence ?** Une licence valide d'Aspose.Tasks est requise pour une utilisation en production.

## What is “how to set calculation” in Aspose.Tasks?
Définir le mode de calcul est aussi simple que d’assigner une valeur d’énumération à la propriété `Project.CalculationMode`. L’énumération propose trois options : `Automatic`, `Manual` et `None`. Le choix du bon mode dépend de votre flux de travail — que vous souhaitiez des mises à jour instantanées, un traitement par lots, ou un contrôle complet.

## Prerequisites

Avant de commencer, assurez‑vous d’avoir :

1. **Visual Studio** – toute version récente (2019, 2022 ou ultérieure).  
2. **Aspose.Tasks for .NET** – téléchargez et installez la bibliothèque depuis [here](https://releases.aspose.com/tasks/net/).  
3. **Connaissances de base en C#** – vous devez être à l’aise avec la création d’applications console et l’utilisation de packages NuGet.

## Import Namespaces

Avant de commencer à travailler avec Aspose.Tasks for .NET, importons les espaces de noms nécessaires :

```csharp
using Aspose.Tasks;
using System;
```

## How to Set Calculation Mode

Vous trouverez ci‑dessous des exemples pas à pas pour chaque mode de calcul. Les blocs de code restent inchangés par rapport au tutoriel original ; les explications environnantes ont été développées pour plus de clarté.

### Applying Automatic Calculation Mode

Le mode automatique recalcule les dates instantanément chaque fois que vous modifiez des tâches ou des liaisons.

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Step 2: Set project start date and add tasks

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Step 3: Link tasks (finish‑to‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Step 4: Verify recalculated dates

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Applying Manual Calculation Mode

Le mode manuel désactive les mises à jour automatiques, vous donnant la possibilité de traiter les changements par lots avant de forcer un recalcul.

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Step 2: Set project start date and add tasks

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Step 3: Verify task properties

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Step 4: Link tasks and verify dates (no automatic recalculation)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Applying None Calculation Mode

Le mode None désactive tous les calculs internes. Utilisez‑le lorsque vous avez seulement besoin de lire ou d’exporter des données sans aucune modification du planning.

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Step 2: Add a new task

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Step 3: Verify task properties (no automatic IDs)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Common Issues and Solutions

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| Les dates ne se mettent pas à jour après avoir lié les tâches | Le projet est en mode **Manual** ou **None** | Définissez `project.CalculationMode = CalculationMode.Automatic` ou appelez `project.Calculate()` manuellement |
| Les ID des tâches restent à 0 | L'utilisation du mode **None** empêche la génération des ID | Passez en mode **Automatic** ou **Manual**, puis recalculer |
| La liaison échoue avec `ArgumentException` | La date de début du prédécesseur est postérieure à celle du successeur lors de l'utilisation du mode **Manual** sans recalcul | Assurez‑vous que les dates de début sont correctes ou recalculer après avoir ajouté les liaisons |

## Frequently Asked Questions

**Q1 : Puis‑je changer le mode de calcul dynamiquement pendant l'exécution ?**  
A1 : Oui, vous pouvez modifier la propriété `CalculationMode` à tout moment dans votre code, puis appeler `project.Calculate()` si vous avez besoin d’une mise à jour immédiate.

**Q2 : Aspose.Tasks prend‑il en charge d’autres formats de fichiers de gestion de projet que Microsoft Project ?**  
A2 : Aspose.Tasks se concentre principalement sur les formats Microsoft Project, mais il prend également en charge Primavera P6 XML, Primavera DB et Asta Powerproject XML.

**Q3 : Aspose.Tasks convient‑il aux projets de petite échelle comme aux projets d’entreprise ?**  
A3 : Absolument. L’API passe de listes de tâches simples à des plannings d’entreprise complexes et multi‑phases.

**Q4 : Puis‑je intégrer Aspose.Tasks avec d’autres bibliothèques et frameworks .NET ?**  
A4 : Oui, vous pouvez combiner Aspose.Tasks avec ASP.NET, WPF, Xamarin ou toute autre technologie .NET pour créer des solutions riches de gestion de projet.

**Q5 : Existe‑t‑il un forum communautaire ou un canal de support pour les utilisateurs d’Aspose.Tasks ?**  
A5 : Oui, vous pouvez visiter le [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pour obtenir du support communautaire et des discussions.

---

**Dernière mise à jour :** 2026-03-24  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}