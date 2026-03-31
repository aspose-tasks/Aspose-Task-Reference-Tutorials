---
date: 2026-03-19
description: Apprenez à lire les lignes de base et à gérer efficacement les lignes
  de base de gestion de projet avec Aspose.Tasks pour .NET.
linktitle: Project Management Baselines using Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Repères de gestion de projet avec Aspose.Tasks
url: /fr/net/advanced-features/assignment-baseline-collection/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bases de référence de la gestion de projet avec Aspose.Tasks

## Introduction

Dans la gestion de projet, les bases de référence sont les points de repère qui vous permettent de comparer les performances prévues aux performances réelles. Gérer les **bases de référence de la gestion de projet**—en particulier les bases de référence d’affectation—aide à maintenir les plannings sur la bonne voie et assure la responsabilité. Aspose.Tasks pour .NET fournit une API puissante pour créer, lire, mettre à jour et supprimer ces bases de référence de manière programmatique. Dans ce tutoriel, nous allons parcourir comment travailler avec les collections de bases de référence d’affectation à l’aide d’Aspose.Tasks pour .NET.

## Quick Answers
- **Quel est le but principal des bases de référence d’affectation ?** Capturer les dates de début/fin prévues pour chaque affectation de ressource.  
- **Quelle méthode API lit les bases de référence ?** La collection `Assignment.Baselines`.  
- **Les bases de référence peuvent‑elles être supprimées programmatique ?** Oui, en retirant les éléments de la collection `Assignment.Baselines`.  
- **Ai‑je besoin d’une licence pour utiliser ces fonctionnalités ?** Une licence valide d’Aspose.Tasks est requise pour une utilisation en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Qu’est‑ce que les bases de référence de la gestion de projet ?
Les bases de référence de la gestion de projet sont des instantanés des données de planning, de coût et de périmètre prises à un moment donné. Elles servent de référence pour mesurer la performance du projet et identifier les écarts tout au long du cycle de vie du projet.

## Pourquoi utiliser Aspose.Tasks pour les bases de référence de la gestion de projet ?
- **Contrôle total :** Accédez et manipulez les données de base de référence sans ouvrir le projet dans Microsoft Project.  
- **Prêt pour l’automatisation :** Intégrez la gestion des bases de référence dans les pipelines CI/CD ou les outils de reporting.  
- **Prise en charge multi‑format :** Fonctionne avec les fichiers MPP, XML et MPX, garantissant une flexibilité entre différents formats de fichiers de projet.  

## Prérequis

Avant de poursuivre ce tutoriel, assurez‑vous d’avoir les prérequis suivants :

1. Connaissances de base du langage de programmation C#.  
2. Visual Studio installé sur votre système.  
3. Bibliothèque Aspose.Tasks pour .NET installée. Vous pouvez la télécharger [ici](https://releases.aspose.com/tasks/net/).

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;
```

## Step 1: Load the Project File

Tout d’abord, nous devons charger le fichier de projet qui contient les bases de référence d’affectation.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## How to read baselines?

Ensuite, nous parcourons chaque affectation de ressource dans le projet pour accéder à leurs bases de référence respectives.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## Step 3: Delete Assignment Baselines

Dans cette étape, nous montrons comment supprimer toutes les bases de référence d’affectation du projet.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Baselines appear empty** | Assurez‑vous que le fichier de projet contient réellement des bases de référence enregistrées ; elles ne sont pas créées automatiquement. |
| **`NullReferenceException` when accessing `baselines.ParentAssignment`** | Vérifiez que l’objet d’affectation n’est pas nul et que les bases de référence ont été initialisées. |
| **Performance slowdown on large projects** | Traitez les affectations par lots ou filtrez par `Assignment.Id` pour limiter la portée. |

## Conclusion

Une gestion efficace des bases de référence d’affectation est primordiale dans la gestion de projet, garantissant le respect des plannings et le suivi précis de l’avancement du projet. Avec Aspose.Tasks pour .NET, la manipulation des bases de référence d’affectation devient fluide, offrant aux développeurs les outils nécessaires pour rationaliser les processus de gestion de projet.

## FAQ's

### Q1 : Aspose.Tasks peut‑il gérer les bases de référence d’affectation pour différents formats de fichiers de projet ?

R1 : Oui, Aspose.Tasks prend en charge divers formats de fichiers de projet, notamment MPP, XML et MPX, vous permettant de gérer les bases de référence d’affectation à travers différents types de fichiers sans effort.

### Q2 : Aspose.Tasks est‑il compatible avec toutes les versions du .NET Framework ?

R2 : Aspose.Tasks pour .NET est compatible avec plusieurs versions du .NET Framework, assurant compatibilité et flexibilité pour les développeurs dans différents environnements.

### Q3 : Puis‑je manipuler les bases de référence d’affectation de façon programmatique avec Aspose.Tasks ?

R3 : Absolument, Aspose.Tasks fournit une API complète qui permet aux développeurs de créer, lire, mettre à jour et supprimer les bases de référence d’affectation selon les exigences du projet.

### Q4 : Aspose.Tasks offre‑t‑il un support technique pour les développeurs ?

R4 : Oui, Aspose.Tasks propose un support technique solide via son forum communautaire, où les développeurs peuvent demander de l’aide, partager leurs connaissances et collaborer avec leurs pairs.

### Q5 : Puis‑je essayer Aspose.Tasks avant d’effectuer un achat ?

R5 : Oui, Aspose.Tasks propose une version d’essai gratuite, permettant aux développeurs d’explorer ses fonctionnalités avant de prendre une décision d’achat.

## Frequently Asked Questions

**Q : Comment lire les bases de référence pour une affectation spécifique ?**  
R : Accédez à la collection `Assignment.Baselines` de cette affectation et parcourez‑la comme illustré dans la section « How to read baselines? ».

**Q : Est‑il possible d’ajouter une nouvelle base de référence à une affectation existante ?**  
R : Oui, vous pouvez créer un objet `AssignmentBaseline`, définir ses valeurs `Start` et `Finish`, puis l’ajouter à la collection `Assignment.Baselines`.

**Q : La suppression des bases de référence affectera‑t‑elle le planning original ?**  
R : La suppression des bases de référence ne fait que retirer les instantanés enregistrés ; le planning actuel (dates réelles) reste inchangé.

**Q : Puis‑je exporter les données de base de référence au format CSV ?**  
R : Bien qu’Aspose.Tasks ne propose pas d’exportation CSV directe pour les bases de référence, vous pouvez parcourir la collection et écrire les valeurs dans un fichier CSV à l’aide des classes I/O standard de .NET.

**Q : Aspose.Tasks prend‑il en charge les rapports de comparaison de bases de référence ?**  
R : Oui, vous pouvez comparer les dates de base de référence avec les dates réelles de façon programmatique et générer des rapports personnalisés en utilisant n’importe quelle bibliothèque de reporting de votre choix.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}