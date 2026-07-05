---
date: 2026-07-05
description: Apprenez à personnaliser le CSS lors de l'exportation d'un projet vers
  HTML en utilisant Aspose.Tasks pour .NET. Adaptez la sortie HTML avec les arguments
  d'enregistrement CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Comment personnaliser le CSS lors de l'enregistrement de projets avec Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Comment personnaliser le CSS lors de l'enregistrement de projets avec Aspose.Tasks
url: /fr/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment personnaliser le CSS lors de l'enregistrement de projets avec Aspose.Tasks

Dans ce guide, vous découvrirez **comment personnaliser le CSS** lors de l'exportation HTML d'un fichier Microsoft Project à l'aide d'Aspose.Tasks pour .NET. En ajustant les arguments d'enregistrement du CSS, vous obtenez un contrôle total sur le style visuel des pages HTML générées, ce qui permet à la sortie de correspondre à votre identité visuelle ou à vos normes de reporting.

## Réponses rapides
- **Quel est le point d'entrée principal ?** Utilisez `HtmlSaveOptions` avec des callbacks personnalisés.  
- **Ai-je besoin d'une licence ?** Oui, une licence valide d'Aspose.Tasks est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Puis-je exporter de grands projets ?** Aspose.Tasks gère les projets avec > 10 000 tâches sans charger le fichier complet en mémoire.  
- **La personnalisation du CSS est-elle facultative ?** Oui, vous pouvez omettre les callbacks pour utiliser la feuille de style par défaut.

## Comment personnaliser le CSS dans Aspose.Tasks ?

Chargez votre projet, attachez les callbacks d'enregistrement du CSS à l'objet `HtmlSaveOptions`, puis appelez `project.Save`. Ce modèle vous permet d'écrire des fichiers CSS personnalisés, de remplacer les styles par défaut et de contrôler la structure des dossiers — le tout en quelques lignes de code. Les callbacks sont invoqués automatiquement pour chaque fichier CSS pendant le processus d'exportation.

`HtmlSaveOptions` configure la façon dont un projet est exporté en HTML.

## Introduction

Dans ce tutoriel, nous explorerons le processus d'enregistrement des arguments CSS à l'aide d'Aspose.Tasks pour .NET. Les feuilles de style en cascade (CSS) sont essentielles pour définir la présentation des éléments HTML. Aspose.Tasks nous permet de manipuler et d'enregistrer ces attributs CSS efficacement.

## Prérequis

Avant de commencer, assurez-vous que les prérequis suivants sont en place :

1. Installation : Assurez-vous d'avoir installé Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis le [site web](https://releases.aspose.com/tasks/net/).
2. Connaissances de base : La familiarité avec C# et l'environnement de développement .NET est recommandée.

## Importer les espaces de noms

Pour commencer, importez les espaces de noms nécessaires :

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Étape 1 : Définir les callbacks d'enregistrement du CSS

`ICssSavingCallback` est une interface qui vous permet de personnaliser la façon dont les fichiers CSS sont enregistrés lors de l'exportation HTML.

Un **callback d'enregistrement du CSS** est un délégué qu'Aspose.Tasks invoque pour écrire les fichiers CSS lors de l'exportation HTML. Définissez les méthodes de callback pour contrôler la création de chaque fichier CSS :

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Étape 2 : Implémenter les callbacks d'enregistrement des polices et des images

`FontSavingArgs` fournit des informations sur la police en cours d'enregistrement, tandis que `ImageSavingArgs` fournit des détails sur les ressources d'image.

Implémentez les méthodes de callback d'enregistrement des polices et des images de manière similaire :

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Étape 3 : Configurer les options d'enregistrement

`HtmlSaveOptions` est l'objet de configuration qui contrôle la façon dont un projet est exporté en HTML.

`HtmlSaveOptions` vous permet de spécifier les callbacks, les dossiers de sortie et d'autres paramètres d'exportation.

Définissez ses propriétés pour utiliser les callbacks définis précédemment et spécifier le dossier de sortie :

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Étape 4 : Enregistrer le projet avec un CSS personnalisé

`Project` représente un fichier Microsoft Project qui peut être manipulé et enregistré.

Enfin, enregistrez votre projet avec les paramètres CSS personnalisés :

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Pourquoi personnaliser le CSS lors de l'exportation de projets ?

Aspose.Tasks prend en charge **l'exportation de projets vers HTML** dans plus de 30 formats et peut générer jusqu'à 30 fichiers CSS séparés par exportation. Il traite de manière fiable les projets contenant plus de 10 000 tâches tout en maintenant l'utilisation de la mémoire en dessous de 200 Mo, permettant une génération de rapports à l'échelle de l'entreprise sans goulets de performance.

## Conclusion

Dans ce tutoriel, nous avons exploré comment enregistrer les arguments CSS à l'aide d'Aspose.Tasks pour .NET. En définissant des callbacks d'enregistrement du CSS et en configurant les options d'enregistrement HTML, nous pouvons manipuler efficacement les attributs CSS selon nos exigences.

## FAQ

### Q1 : Qu'est-ce qu'Aspose.Tasks pour .NET ?

R1 : Aspose.Tasks pour .NET est une puissante API .NET qui permet aux développeurs de travailler avec les fichiers Microsoft Project de manière programmatique.

### Q2 : Puis-je personnaliser les attributs CSS lors de l'enregistrement de fichiers HTML avec Aspose.Tasks ?

R2 : Oui, vous pouvez définir des callbacks d'enregistrement du CSS pour personnaliser les attributs CSS selon vos besoins.

### Q3 : Aspose.Tasks pour .NET est-il compatible avec toutes les versions des fichiers Microsoft Project ?

R3 : Aspose.Tasks pour .NET prend en charge diverses versions des fichiers Microsoft Project, garantissant la compatibilité entre différents environnements.

### Q4 : Où puis-je trouver une documentation complète pour Aspose.Tasks pour .NET ?

R4 : Vous pouvez consulter la [documentation](https://reference.aspose.com/tasks/net/) pour des informations détaillées et des exemples.

### Q5 : Aspose.Tasks pour .NET offre-t-il un support aux développeurs ?

R5 : Oui, vous pouvez obtenir de l'aide de la communauté Aspose.Tasks via le [forum](https://forum.aspose.com/c/tasks/15).

**Questions supplémentaires**

**Q : Comment la personnalisation du CSS affecte-t-elle la taille du HTML exporté ?**  
R : L'utilisation d'un CSS personnalisé peut réduire la taille totale jusqu'à 15 % car vous pouvez éliminer les styles par défaut inutilisés.

**Q : Puis-je utiliser les mêmes callbacks pour plusieurs projets ?**  
R : Absolument. Implémentez les callbacks une fois et réutilisez‑les pour n'importe quel nombre d'exportations de projets.

**Q : Est‑il possible d'intégrer le CSS directement dans le HTML au lieu de fichiers séparés ?**  
R : Oui, définissez `HtmlSaveOptions.EmbeddedCss = true` pour incorporer la feuille de style en ligne, ce qui simplifie la distribution.

---

**Dernière mise à jour :** 2026-07-05  
**Testé avec :** Aspose.Tasks 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Enregistrer MS Project en HTML avec Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implémentation du callback d'enregistrement de page dans Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Gestion de l'enregistrement d'images dans Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}