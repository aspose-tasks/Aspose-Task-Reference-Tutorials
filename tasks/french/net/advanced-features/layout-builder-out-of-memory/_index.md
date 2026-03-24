---
date: 2026-03-24
description: Apprenez la gestion des erreurs de mémoire insuffisante et comment enregistrer
  l’image du projet à l’aide d’Aspose.Tasks Layout Builder en .NET. Guide étape par
  étape avec des exemples de code.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Gestion du manque de mémoire avec le Layout Builder d'Aspose.Tasks (C#)
url: /fr/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestion du manque de mémoire avec Aspose.Tasks Layout Builder

## Introduction

La gestion du manque de mémoire est une partie critique de la création d’applications .NET fiables qui manipulent de gros fichiers de projet. Lorsque vous générez des visualisations avec Aspose.Tasks Layout Builder, vous pouvez rapidement rencontrer des exceptions liées à la mémoire, notamment sur des diagrammes de Gantt complexes. Dans ce tutoriel, nous vous expliquerons comment **gérer les exceptions de mémoire**, **personnaliser la vue Gantt** et **enregistrer l’image du projet** en toute sécurité, afin que votre application reste réactive même avec des plannings massifs.

## Réponses rapides
- **Qu'est-ce que la gestion du manque de mémoire ?** Gestion de l’utilisation de la mémoire et capture des erreurs de type `OutOfMemoryException` lors du traitement de gros volumes de données.
- **Quelle API aide ?** Aspose.Tasks Layout Builder pour .NET.
- **Scénario typique ?** Rendu d’un diagramme de Gantt haute résolution au format PNG.
- **Pré‑requis clé ?** .NET (Framework 4.5+ ou .NET 6) avec Aspose.Tasks installé.
- **Comment attraper les erreurs ?** Utilisez des blocs `try…catch` pour `ApsLayoutBuilderOutOfMemoryException` et les exceptions associées.

## Prérequis

Avant de plonger dans le code, assurez‑vous d’avoir :

1. **Bases C#** – vous devez être à l’aise avec la syntaxe standard de C#.
2. **Aspose.Tasks pour .NET** installé. Si vous ne l’avez pas encore ajouté, téléchargez‑le [ici](https://releases.aspose.com/tasks/net/).
3. **Un IDE** tel que Visual Studio (ou VS Code avec l’extension C#) pour compiler et exécuter l’exemple.

## Importer les espaces de noms

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Guide étape par étape

### Étape 1 : Charger le projet

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Cette ligne charge **Blank2010.mpp** dans une instance `Project`, la préparant pour la visualisation.

### Étape 2 : Personnaliser la vue du diagramme de Gantt

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Ici nous **personnalisons la vue Gantt** en ajustant les niveaux de l’échelle de temps du milieu et du bas. Modifier ces niveaux réduit la quantité de données rendues en une fois, ce qui peut aider à atténuer la pression sur la mémoire.

### Étape 3 : Configurer les options d’enregistrement d’image

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` indique à Aspose.Tasks comment rendre le diagramme. Nous choisissons PNG comme format de sortie et associons l’échelle de temps à la vue que nous venons de personnaliser.

### Étape 4 : Enregistrer le projet en tant qu’image

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

L’appel `Save` **enregistre l’image du projet** en utilisant les options définies ci‑dessus. Si le projet est très volumineux, c’est à ce moment‑là qu’une condition de manque de mémoire est la plus susceptible de se produire.

### Étape 5 : Gérer les exceptions

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

En capturant `ApsLayoutBuilderOutOfMemoryException` vous **gérez l’exception de mémoire** de façon élégante, en affichant un message clair au lieu de faire planter l’application. Le second `catch` traite les problèmes de taille de bitmap qui peuvent également survenir lors du rendu de diagrammes très grands.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| **OutOfMemoryException** | Le rendu d’une image très haute résolution consomme plus de RAM que le processus ne peut en allouer. | Réduisez les dimensions de l’image, simplifiez les niveaux d’échelle de temps, ou divisez le diagramme en plusieurs images. |
| **BitmapInvalidSizeException** | La taille de bitmap demandée dépasse le maximum autorisé par la plateforme. | Limitez la largeur/hauteur dans `ImageSaveOptions` ou rendez le diagramme par segments. |
| **Slow performance** | Les gros fichiers de projet nécessitent beaucoup de traitement. | Activez `project.Set(Prj.SaveToCache, true)` avant le rendu, ou utilisez un thread d’arrière‑plan. |

## FAQ

### Q1 : Qu'est‑ce qu'Aspose.Tasks pour .NET ?

A1 : Aspose.Tasks pour .NET est une API puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project de façon programmatique dans les applications .NET.

### Q2 : Comment obtenir une licence temporaire pour Aspose.Tasks ?

A2 : Vous pouvez obtenir une licence temporaire pour Aspose.Tasks en visitant [ce lien](https://purchase.aspose.com/temporary-license/).

### Q3 : Aspose.Tasks est‑il adapté à la gestion de gros fichiers de projet ?

A3 : Oui, Aspose.Tasks propose des fonctionnalités et des optimisations pour gérer efficacement de gros fichiers de projet, mais les développeurs doivent tout de même envisager des stratégies de gestion de la mémoire.

### Q4 : Puis‑je personnaliser l'apparence des diagrammes de Gantt avec Aspose.Tasks ?

A4 : Absolument ! Aspose.Tasks offre de vastes possibilités de personnalisation de l’apparence et de la mise en page des diagrammes de Gantt selon vos besoins.

### Q5 : Où puis‑je trouver plus d'aide et de support pour Aspose.Tasks ?

A5 : Vous pouvez trouver plus d’aide et de support, ainsi que rejoindre la communauté, sur le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Questions fréquemment posées

**Q : Comment réduire l'utilisation de la mémoire lors de l'enregistrement d'une image de projet ?**  
A : Diminuez la résolution de l'image, limitez la plage de l’échelle de temps, ou enregistrez le diagramme en plusieurs segments plus petits.

**Q : Est‑il possible de diffuser l'image directement dans une réponse web ?**  
A : Oui, vous pouvez utiliser `project.Save(stream, options)` et écrire le flux dans la réponse HTTP.

**Q : Aspose.Tasks prend‑il en charge .NET Core et .NET 5/6 ?**  
A : La bibliothèque est entièrement compatible avec .NET Core, .NET 5 et .NET 6.

**Q : Que faire si je rencontre toujours une erreur de manque de mémoire après optimisation ?**  
A : Envisagez de traiter le projet sur une machine disposant de plus de RAM ou de déléguer le rendu à un service d’arrière‑plan.

**Q : Puis‑je exporter le diagramme de Gantt vers d'autres formats que PNG ?**  
A : Oui, `ImageSaveOptions` prend en charge JPEG, BMP et TIFF en plus de PNG.

---

**Dernière mise à jour** : 2026-03-24  
**Testé avec** : Aspose.Tasks 24.11 pour .NET  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}