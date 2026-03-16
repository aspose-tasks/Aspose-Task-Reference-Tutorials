---
date: 2026-03-16
description: Apprenez à implémenter le callback d’enregistrement de page dans Aspose.Tasks
  pour .NET, permettant une gestion personnalisée des flux de sortie de documents
  multi‑pages.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Implémenter le rappel de sauvegarde de page dans Aspose.Tasks
url: /fr/net/advanced-concepts/page-saving-callback/
weight: 12
---

 keep.

Then closing shortcodes.

Also need to translate "## Quick Answers" to "## Réponses rapides". Ensure bullet list formatting same.

Now produce final content with all translations, preserving shortcodes and code placeholders.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implémenter le rappel d'enregistrement de page dans Aspose.Tasks

## Introduction

Dans ce tutoriel, vous apprendrez comment **implémenter le rappel d'enregistrement de page** dans Aspose.Tasks pour .NET. Cette fonctionnalité puissante vous permet de diriger chaque page d'un document multipage vers un flux de votre choix, vous offrant un contrôle total sur la façon dont la sortie est stockée ou traitée davantage.

## Réponses rapides
- **Que fait le rappel d'enregistrement de page ?** Il capture chaque page rendue dans un flux séparé afin que vous puissiez les gérer individuellement.  
- **Quel format puis‑je exporter ?** Tout format pris en charge par `ImageSaveOptions`, par ex., PNG, JPEG, PDF.  
- **Ai‑je besoin d'une licence ?** Une licence valide d'Aspose.Tasks est requise pour une utilisation en production.  
- **Puis‑je l'utiliser avec .NET Core ?** Oui, Aspose.Tasks prend pleinement en charge .NET Core et .NET 5/6+.  
- **Le rappel est‑il thread‑safe ?** Le rappel s'exécute sur le même thread qui effectue le rendu, donc les règles normales de sécurité des threads s'appliquent.

## Qu'est‑ce que **implémenter le rappel d'enregistrement de page** ?
Le modèle **implémenter le rappel d'enregistrement de page** vous permet d'insérer une logique personnalisée dans le pipeline d'enregistrement d'Aspose.Tasks. Au lieu d'écrire directement dans un fichier, vous recevez un objet `Stream` pour chaque page, ce qui vous permet de le stocker en mémoire, de le télécharger vers un stockage cloud ou d'appliquer un traitement supplémentaire.

## Pourquoi exporter le projet en PNG avec un rappel ?
Exporter un projet en PNG vous fournit une image raster de chaque page du diagramme de Gantt, ce qui est idéal pour les rapports, les e‑mails ou l'intégration dans des pages web. Utiliser un rappel signifie que vous pouvez conserver chaque page dans un `MemoryStream` séparé sans créer de fichiers temporaires sur le disque.

## Prérequis

1. **Connaissances en C#** – familiarité de base avec les classes, les interfaces et les flux.  
2. **Aspose.Tasks pour .NET** – téléchargez et installez depuis [here](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider ou tout éditeur compatible .NET.

## Importer les espaces de noms

Pour commencer, importez les espaces de noms requis :

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Étape 1 : créer un objet Project

Chargez un fichier MPP existant dans une instance `Project` :

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Étape 2 : configurer les options d'enregistrement d'image

Configurez `ImageSaveOptions` pour une sortie PNG et attachez le rappel personnalisé :

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Astuce :** Définir `RenderToSinglePage = false` garantit que chaque page du diagramme de Gantt est rendue séparément, ce qui est essentiel pour que le rappel reçoive des flux distincts.

## Étape 3 : enregistrer le projet avec le rappel

Appelez la méthode `Save`, en passant `Stream.Null` car les flux réels sont fournis par le rappel :

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Étape 4 : traiter les flux de pages enregistrées

Une fois l'opération d'enregistrement terminée, le rappel détient une collection d'objets `MemoryStream` — un par page. Vous pouvez maintenant les parcourir :

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Étape 5 : implémenter un rappel d'enregistrement de page personnalisé

Créez une classe scellée qui implémente `IPageSavingCallback`. Cette classe capture le flux de chaque page et le stocke dans une liste pour une utilisation ultérieure.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Pièges courants et dépannage

| Problème | Raison | Solution |
|----------|--------|----------|
| **Aucune page n'est retournée** | `RenderToSinglePage` laissé à `true`. | Définissez `RenderToSinglePage = false` pour générer des pages séparées. |
| **Les flux sont vides** | `KeepStreamOpen` mis à `true` sans libération ultérieure. | Laissez-le à `false` (par défaut) et laissez le rappel fermer les flux automatiquement. |
| **Erreurs de mémoire insuffisante** | Les très gros projets génèrent de nombreux PNG haute résolution. | Traitez les flux un par un ou augmentez les limites de mémoire de la VM. |

## Questions fréquentes

**Q1 : Qu'est‑ce qu'un rappel d'enregistrement de page dans Aspose.Tasks ?**  
R : Un rappel d'enregistrement de page vous permet d'intercepter le processus d'enregistrement pour chaque page d'un document multipage, en fournissant un `Stream` personnalisé pour cette page.

**Q2 : Puis‑je utiliser différents formats pour enregistrer les pages avec ce rappel ?**  
R : Oui. En modifiant `SaveFileFormat` vous pouvez exporter en PNG, JPEG, PDF, SVG, etc.

**Q3 : Aspose.Tasks est‑il compatible avec .NET Core ?**  
R : Absolument. Aspose.Tasks prend en charge .NET Core, .NET 5 et .NET 6.

**Q4 : Comment gérer les erreurs pendant le processus d'enregistrement de page ?**  
R : Enveloppez la logique du rappel dans des blocs `try/catch` et consignez les exceptions. La méthode `OnFinish` est un bon endroit pour le nettoyage final.

**Q5 : Où puis‑je trouver plus de ressources et d'assistance pour Aspose.Tasks ?**  
R : Vous pouvez visiter le [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir de l'aide, accéder à la documentation [ici](https://reference.aspose.com/tasks/net/), ou explorer des fonctionnalités supplémentaires et les options de licence sur le site [Aspose.Tasks](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-03-16  
**Testé avec :** Aspose.Tasks 24.12 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}