---
date: 2026-04-06
description: Apprenez à supprimer toutes les lignes de base et à gérer les collections
  de lignes de base dans Aspose.Tasks pour .NET avec des exemples de code étape par
  étape.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Supprimer toutes les lignes de base avec la collection de lignes de base
  Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Supprimer toutes les lignes de base avec la collection de lignes de base Aspose.Tasks
url: /fr/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Supprimer toutes les lignes de base avec la collection Baseline d'Aspose.Tasks

## Introduction

Aspose.Tasks for .NET vous permet de manipuler les fichiers Microsoft Project directement depuis vos applications .NET. L’une des fonctionnalités les plus puissantes est la capacité de **supprimer toutes les lignes de base** pour une ressource, ce qui est essentiel lorsque vous devez réinitialiser les données de suivi d’un projet ou démarrer une nouvelle période de ligne de base. Dans ce tutoriel, nous parcourrons l’ensemble du processus — du chargement d’un fichier de projet à la suppression de chaque ligne de base attachée à une ressource spécifique — en utilisant des explications claires et conversationnelles ainsi qu’un code C# prêt à l’exécution.

## Quick Answers
- **Que fait « supprimer toutes les lignes de base » ?** Il supprime chaque enregistrement de ligne de base stocké pour la ressource sélectionnée, effaçant les données historiques de coût et de travail.  
- **Pourquoi aurais‑je besoin de cela ?** Pour réinitialiser le suivi après un changement majeur du projet ou lorsque les lignes de base d’origine ne sont plus pertinentes.  
- **Quelle bibliothèque fournit cette fonctionnalité ?** Aspose.Tasks for .NET.  
- **Ai‑je besoin d’une licence ?** Une licence valide d’Aspose.Tasks est requise pour une utilisation en production ; un essai gratuit est disponible.  
- **Le code est‑il compatible avec .NET 6+ ?** Oui, l’API fonctionne avec .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6.

## What Is a Baseline and Why Delete All Baselines?

Une ligne de base capture le plan original des coûts, du travail et du calendrier à un moment donné. Au cours de la vie d’un projet, vous pouvez créer plusieurs lignes de base (Baseline 1, Baseline 2, etc.) pour comparer l’avancement réel à différents instantanés de planification. Cependant, il existe des scénarios — comme un re‑cadrage du projet ou un nouveau départ — où conserver ces lignes de base historiques devient source de confusion. Supprimer toutes les lignes de base vous donne une ardoise propre, vous permettant de définir de nouvelles lignes de base qui reflètent la réalité actuelle.

## Prerequisites

Avant de plonger dans le code, assurez‑vous d’avoir :

1. **Visual Studio** – toute édition récente (Community, Professional ou Enterprise).  
2. **Aspose.Tasks for .NET** – téléchargez‑le depuis le [download link](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – vous devez être à l’aise avec les variables, les boucles et la sortie console.  
4. **A Microsoft Project file** (`.mpp`) – un fichier d’exemple nommé *WorkWithBaselineCollection.mpp* sera utilisé dans les exemples.

## Import Namespaces

Tout d’abord, importez les espaces de noms nécessaires afin que le compilateur sache où trouver les classes que nous allons utiliser.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Step 1: Load the Project File

Nous commençons par charger un fichier Project existant. Ajustez `DataDir` pour qu’il pointe vers le dossier contenant votre fichier `.mpp`.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Step 2: Get the Target Resource

À titre de démonstration, nous récupérons la ressource dont l’UID = 1. Dans un scénario réel, vous localiseriez la ressource par son nom ou un autre identifiant.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Step 3: Display Existing Baseline Information

Avant de supprimer quoi que ce soit, il est utile de voir quelles lignes de base sont actuellement attachées à la ressource. Cela vous assure que vous supprimez les bonnes données.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Step 4: Iterate Through All Baselines

Ici, nous parcourons chaque ligne de base, affichant les métriques clés telles que le coût, le travail et la valeur acquise (BCWP/BCWS). Cette étape est facultative mais utile pour la journalisation ou les besoins d’audit.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Delete All Baselines

Nous effectuons maintenant l’action principale : **supprimer toutes les lignes de base** pour la ressource sélectionnée. Nous copions d’abord la collection dans une liste afin d’éviter de modifier la collection pendant l’itération, puis nous supprimons chaque ligne de base une par une.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Après l’exécution de ce bloc, `resource.Baselines.Count` sera `0`, confirmant que tous les enregistrements de lignes de base ont été effacés.

## Common Issues and Tips

- **NullReferenceException** – Assurez‑vous que le fichier projet contient réellement la ressource que vous ciblez ; sinon `GetByUid` renverra `null`.  
- **Licensing** – Sans licence valide d’Aspose.Tasks, vous verrez un filigrane dans la sortie et des fonctionnalités limitées.  
- **Performance** – Pour des projets très volumineux, envisagez d’itérer avec `Parallel.ForEach` pour accélérer le processus de suppression, mais rappelez‑vous que la collection sous‑jacente n’est pas thread‑safe.

## Frequently Asked Questions

**Q : Aspose.Tasks peut‑il gérer de gros fichiers de projet ?**  
**R :** Oui, Aspose.Tasks est optimisé pour les performances et peut traiter efficacement des fichiers `.mpp` de plusieurs gigaoctets.

**Q : La bibliothèque est‑elle compatible avec toutes les versions de Microsoft Project ?**  
**R :** Aspose.Tasks prend en charge Project 2000 à Project 2024, couvrant à la fois les anciens formats `.mpp` et les fichiers plus récents basés sur XML.

**Q : Puis‑je personnaliser les lignes de base avant de les supprimer ?**  
**R :** Absolument. Vous pouvez lire ou modifier n’importe quelle propriété d’une ligne de base (coût, travail, dates) avant de décider de la supprimer.

**Q : Aspose.Tasks fonctionne‑t‑il sur les plateformes cloud ?**  
**R :** Oui, l’API s’exécute sur tout environnement compatible .NET, y compris Azure App Service, AWS Lambda (via .NET Core) et les conteneurs Docker.

**Q : Où puis‑je demander de l’aide à la communauté ?**  
**R :** Consultez le [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pour entrer en contact avec d’autres développeurs et le personnel d’Aspose.

## Conclusion

Dans ce guide, nous avons démontré comment **supprimer toutes les lignes de base** d’une ressource en utilisant Aspose.Tasks for .NET. En suivant le code étape par étape, vous pouvez réinitialiser les données de lignes de base, garder le suivi de votre projet propre et préparer votre planning à un nouveau cycle de planification. N’hésitez pas à expérimenter la création de nouvelles lignes de base après la suppression pour voir comment la bibliothèque met à jour le fichier de projet.

---

**Dernière mise à jour:** 2026-04-06  
**Testé avec:** Aspose.Tasks 24.12 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}