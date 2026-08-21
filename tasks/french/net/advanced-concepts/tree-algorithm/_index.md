---
date: 2026-03-19
description: Apprenez comment ajouter une ressource au projet, calculer la durée des
  tâches en utilisant l'algorithme d'arbre d'Aspose.Tasks, et affecter des ressources
  aux tâches en .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ajouter une ressource au projet avec l'algorithme d'arbre dans Aspose.Tasks
url: /fr/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une ressource au projet avec l'algorithme d'arbre dans Aspose.Tasks

## Introduction

Dans ce tutoriel, vous découvrirez **comment ajouter une ressource au projet** en tirant parti du puissant algorithme d'arbre fourni par Aspose.Tasks pour .NET. Nous parcourrons la création d'une hiérarchie de tâches, le calcul de la durée des tâches et l'affectation de ressources aux tâches — le tout de manière claire, étape par étape, que vous pouvez copier dans votre propre solution.

## Quick Answers
- **Que fait l'algorithme d'arbre ?** Il parcourt une hiérarchie de tâches pour agréger les valeurs de travail de manière efficace.  
- **Quelle opération principale ce guide couvre-t-il ?** Ajouter une ressource à un projet et mettre à jour les totaux de travail.  
- **Ai-je besoin d'une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production.  
- **Puis-je l'utiliser avec .NET Core ?** Oui, Aspose.Tasks prend en charge .NET Framework et .NET Core.  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un fichier de projet basique.

## What is “add resource to project” in Aspose.Tasks?

Ajouter une ressource à un projet signifie créer un objet `Resource`, définir son type (par ex., work), et le lier à une ou plusieurs tâches via `ResourceAssignments`. Cela permet au planificateur de calculer l'effort, le coût et la durée globale du projet.

## Why use the Tree Algorithm for resource work calculations?

L'algorithme d'arbre parcourt l'arbre des tâches une seule fois, en accumulant le travail des tâches feuilles jusqu'à leurs tâches récapitulatives. Cette approche est bien plus efficace que d'itérer sur chaque tâche individuellement, surtout dans les grands projets avec des hiérarchies profondes. Elle garantit également que les valeurs de travail récapitulatives restent synchronisées avec leurs enfants.

## Prerequisites

Avant de commencer, assurez-vous de disposer de ce qui suit :

1. **Visual Studio** – toute édition récente (2019, 2022 ou ultérieure).  
2. **Aspose.Tasks for .NET** – téléchargez-le depuis [here](https://releases.aspose.com/tasks/net/).  
3. **Connaissances de base en C#** – vous devez être à l'aise avec les classes, les objets et le LINQ simple.

## Import Namespaces

Dans votre projet C#, importez les espaces de noms nécessaires pour travailler avec les fonctionnalités d'Aspose.Tasks :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Maintenant, décomposons chaque exemple en plusieurs étapes :

## Step 1: Load Project File

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Chargez le fichier de projet en mémoire en utilisant la classe `Project`.

## Step 2: Define Task Hierarchy

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Définissez la hiérarchie des tâches en ajoutant des tâches parentes et enfants.

## Step 3: Set Task Properties (including **calculate task duration**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Ici, nous **calculons la durée de la tâche** en convertissant les heures de travail en un objet `Duration`, puis en déduisant la date de fin.

## Step 4: Add Resource (**assign resources to tasks**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Cet extrait **ajoute une ressource au projet** et **assigne des ressources aux tâches** afin que le planificateur sache qui est responsable du travail.

## Step 5: Apply Tree Algorithm

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Initialisez la classe `WorkAccumulator` et appliquez l'algorithme d'arbre pour rassembler le travail commun à travers la hiérarchie.

## Step 6: Update Task Work

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Mettez à jour les valeurs de travail des tâches en fonction des informations recueillies.

## Common Issues & Tips

- **Paramètres de calendrier manquants :** Si la date de fin semble incorrecte, assurez-vous que le calendrier du projet est correctement configuré avant d'appeler `GetFinishDateByStartAndWork`.  
- **Incohérence du type de ressource :** Toujours définir `Rsc.Type` sur `ResourceType.Work` pour les ressources basées sur l'effort ; sinon, l'accumulation du travail peut renvoyer zéro.  
- **Astuce pro :** Après la mise à jour du travail, appelez `project.Save("UpdatedProject.mpp")` pour enregistrer les modifications.

## Conclusion

En suivant ces étapes, vous savez maintenant comment **ajouter une ressource au projet**, **calculer la durée d'une tâche** et **assigner des ressources aux tâches** en utilisant l'algorithme d'arbre d'Aspose.Tasks. Cette méthode simplifie la gestion de la hiérarchie et maintient les valeurs de travail récapitulatives précises avec un code minimal.

## FAQ's

### Q1: What is Aspose.Tasks for .NET?

A1: Aspose.Tasks for .NET est une API puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project de manière programmatique en utilisant C#.

### Q2: Can I download a free trial of Aspose.Tasks for .NET?

A2: Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks for .NET depuis [here](https://releases.aspose.com/).

### Q3: Where can I find documentation for Aspose.Tasks for .NET?

A3: Vous pouvez trouver la documentation d'Aspose.Tasks for .NET [here](https://reference.aspose.com/tasks/net/).

### Q4: How can I get support for Aspose.Tasks for .NET?

A4: Pour obtenir de l'aide concernant Aspose.Tasks for .NET, vous pouvez visiter le [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Is there a temporary license available for testing purposes?

A5: Oui, vous pouvez obtenir une licence temporaire à des fins de test depuis [here](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q : Puis-je utiliser cette approche avec un fichier de projet volumineux existant ?**  
R : Absolument. L'algorithme d'arbre fonctionne sur n'importe quelle instance `Project`, quelle que soit sa taille.

**Q : L'algorithme met-il également à jour les valeurs de coût ?**  
R : L'exemple se concentre sur le travail, mais vous pouvez l'étendre aux coûts en accumulant `Tsk.Cost` de manière similaire.

**Q : Quelles versions de .NET sont prises en charge ?**  
R : Aspose.Tasks prend en charge .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ et .NET 6+.

**Q : Comment gérer plusieurs ressources par tâche ?**  
R : Ajoutez chaque ressource avec `project.ResourceAssignments.Add(task, resource)` ; l'accumulateur additionnera automatiquement leur travail.

---

**Dernière mise à jour :** 2026-03-19  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}