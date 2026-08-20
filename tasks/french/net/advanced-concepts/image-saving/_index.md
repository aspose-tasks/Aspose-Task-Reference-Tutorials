---
date: 2026-03-05
description: Apprenez comment enregistrer des images, générer du HTML avec des images
  et personnaliser l’exportation d’images à l’aide d’Aspose.Tasks pour .NET. Guide
  étape par étape pour enregistrer le projet au format HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Comment enregistrer des images avec Aspose.Tasks pour .NET
url: /fr/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment enregistrer des images avec Aspose.Tasks pour .NET

## Introduction

Dans ce tutoriel, vous découvrirez **comment enregistrer des images** à partir de fichiers Microsoft Project en utilisant l'API Aspose.Tasks pour .NET. Que vous ayez besoin d'intégrer des graphiques dans des rapports, de générer des pages HTML contenant des visuels de projet, ou simplement d'exporter des ressources diagrammatiques, les étapes ci‑dessous vous guideront à travers le processus complet — depuis la configuration de l'objet projet jusqu'à la personnalisation des rappels d'exportation d'images.

## Quick Answers
- **Que signifie “how to save images” dans Aspose.Tasks ?**  
  Cela fait référence à l’utilisation de l’interface `IImageSavingCallback` pour contrôler où et comment les ressources visuelles sont écrites sur le disque.
- **Puis‑je enregistrer un projet au format HTML avec des images intégrées ?**  
  Oui, en utilisant `HtmlSaveOptions` conjointement avec les callbacks d’enregistrement d’images, vous pouvez **enregistrer le projet au format HTML** qui inclut toutes les images générées.
- **Ai‑je besoin d’une licence pour l’exportation d’images ?**  
  Une licence d’évaluation temporaire suffit pour les tests ; une licence complète est requise pour la production.
- **Quelles versions de .NET sont prises en charge ?**  
  Aspose.Tasks pour .NET prend en charge .NET Framework 4.5+, .NET Core 3.1+ et .NET 5/6+.
- **Est‑il possible de personnaliser l’exportation d’images (format, dossier, nommage) ?**  
  Absolument – le callback vous donne un contrôle total sur le nom de fichier, le format et la destination.

## Qu’est‑ce que “how to save images” dans le contexte d’Aspose.Tasks ?

Enregistrer des images signifie extraire les éléments visuels (graphes, barres de Gantt, graphiques de ressources) d’un fichier Project et les écrire dans des fichiers image (PNG, JPEG, etc.). Aspose.Tasks offre un mécanisme de rappel flexible qui vous permet de choisir l’emplacement exact, la convention de nommage, et même le format de l’image.

## Pourquoi utiliser Aspose.Tasks pour enregistrer des images ?

- **Contrôle programmatique complet** – aucune interaction manuelle avec l’interface utilisateur n’est requise.  
- **Cross‑platform** – fonctionne sous Windows, Linux et macOS via .NET Core.  
- **Rendu haute fidélité** – les images conservent la même qualité que la vue originale du projet.  
- **Génération HTML facile** – combinez `HtmlSaveOptions` avec les callbacks d’image pour **générer automatiquement du HTML avec des images**.

## Prérequis

Avant de commencer, assurez‑vous d’avoir les éléments suivants :

1. Visual Studio installé sur votre machine de développement.  
2. Aspose.Tasks pour .NET téléchargé depuis [ici](https://releases.aspose.com/tasks/net/).  
3. Familiarité de base avec C# et la structure d’un projet .NET.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis dans votre fichier source :

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Étape 1 : Créer un objet Project

Chargez le fichier Microsoft Project avec lequel vous souhaitez travailler :

```csharp
var project = new Project("Project1.mpp");
```

## Étape 2 : Définir les options d’enregistrement

Créez les options d’enregistrement HTML qui contiendront également nos callbacks d’enregistrement d’images :

```csharp
var options = GetSaveOptions(1);
```

## Étape 3 : Enregistrer le projet au format HTML (save project as html)

Exportez maintenant le projet vers un fichier HTML. Les images référencées dans le HTML seront générées par le callback que nous définirons ensuite :

```csharp
project.Save("document_out.html", options);
```

## Étape 4 : Implémenter le callback d’enregistrement d’image (customize image export)

Implémentez l’interface `IImageSavingCallback`. C’est ici que vous **personnalisez le comportement d’exportation d’image** :

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Étape 5 : Enregistrer les images dans le répertoire spécifié

Dans la méthode `ImageSaving`, décidez où chaque image doit être stockée. L’exemple ci‑dessous différencie les ressources PNG des autres formats :

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Étape 6 : Spécifier les options d’enregistrement (including callbacks)

Configurez les callbacks pour les polices, le CSS et les images. Cela garantit que chaque élément visuel est traité de manière cohérente :

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Problèmes courants et solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| Les images n’apparaissent pas dans le HTML généré | Le callback n’attribue pas un chemin de fichier valide | Assurez‑vous que `args.Path` pointe vers un dossier accessible en écriture et que `args.ImageStream` est correctement défini. |
| Les fichiers PNG sont enregistrés avec une mauvaise extension | La logique conditionnelle ne vérifie que le suffixe “png” | Utilisez `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` pour une détection robuste. |
| Les références HTML sont cassées après le déplacement des fichiers | Les chemins relatifs ont changé après le déplacement du dossier de sortie | Conservez les dossiers HTML et image ensemble ou mettez à jour `options.ImageFolder` en conséquence. |

## Conclusion

En suivant ces étapes, vous savez maintenant **comment enregistrer des images** à partir d’un fichier Project, **enregistrer le projet au format HTML**, et **personnaliser l’exportation d’image** pour s’adapter à la structure de dossiers de votre application. Cette approche vous permet de **générer du HTML avec des images** qui peuvent être intégrées de façon transparente dans des rapports, des portails de documentation ou des tableaux de bord web.

## Questions fréquentes

**Q1 : Puis‑je utiliser Aspose.Tasks pour manipuler des fichiers projet dans d’autres formats que le HTML ?**  
R1 : Oui, Aspose.Tasks prend en charge divers formats tels que PDF, XLSX et MPP.

**Q2 : Aspose.Tasks propose‑t‑il une prise en charge de l’intégration avec le stockage cloud ?**  
R2 : Oui, Aspose.Tasks offre des API pour travailler avec des services de stockage cloud populaires comme Amazon S3 et Google Drive.

**Q3 : Aspose.Tasks est‑il compatible avec .NET Core ?**  
R3 : Oui, Aspose.Tasks est compatible avec .NET Core, vous permettant de développer des applications multiplateformes.

**Q4 : Puis‑je personnaliser l’apparence des images enregistrées ?**  
R4 : Oui, vous pouvez personnaliser l’apparence des images enregistrées en modifiant la logique d’enregistrement d’image dans les méthodes de callback.

**Q5 : Aspose.Tasks propose‑t‑il des versions d’essai à des fins d’évaluation ?**  
R5 : Oui, vous pouvez obtenir un essai gratuit d’Aspose.Tasks depuis [ici](https://releases.aspose.com/).

---

**Dernière mise à jour :** 2026-03-05  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}