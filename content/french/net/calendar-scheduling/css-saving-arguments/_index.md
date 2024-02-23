---
title: Arguments d’enregistrement CSS dans Aspose.Tasks
linktitle: Arguments d’enregistrement CSS dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment enregistrer les arguments CSS dans Aspose.Tasks for .NET pour personnaliser la sortie HTML. Améliorez la présentation avec des paramètres CSS personnalisés.
type: docs
weight: 20
url: /fr/net/calendar-scheduling/css-saving-arguments/
---
## Introduction

Dans ce didacticiel, nous aborderons le processus d'enregistrement des arguments CSS à l'aide d'Aspose.Tasks pour .NET. Les feuilles de style en cascade (CSS) sont cruciales pour définir la présentation des éléments HTML. Aspose.Tasks nous permet de manipuler et de sauvegarder efficacement ces attributs CSS.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Installation : assurez-vous d'avoir installé Aspose.Tasks pour .NET. Vous pouvez le télécharger depuis le[site web](https://releases.aspose.com/tasks/net/).

2. Connaissances de base : une connaissance de l'environnement de développement C# et .NET est recommandée.

## Importer des espaces de noms

Pour commencer, importez les espaces de noms nécessaires :

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Étape 1 : Définir les rappels d’enregistrement CSS

Tout d’abord, nous définissons les méthodes de rappel de sauvegarde CSS pour gérer la sauvegarde des fichiers CSS :

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implémentez votre logique de sauvegarde CSS ici
    }
}
```

## Étape 2 : implémenter les rappels d’enregistrement des polices et des images

Ensuite, implémentez les méthodes de rappel de sauvegarde des polices et des images de la même manière :

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implémentez votre logique de sauvegarde de police ici
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implémentez votre logique de sauvegarde d'image ici
}
```

## Étape 3 : Configurer les options d'enregistrement

Maintenant, configurez les options de sauvegarde HTML pour utiliser les rappels implémentés :

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configurer les options d'enregistrement HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Étape 4 : Enregistrez le projet avec du CSS personnalisé

Enfin, enregistrez votre projet avec les paramètres CSS personnalisés :

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment enregistrer les arguments CSS à l'aide d'Aspose.Tasks pour .NET. En définissant des rappels de sauvegarde CSS et en configurant les options de sauvegarde HTML, nous pouvons manipuler efficacement les attributs CSS en fonction de nos besoins.

## FAQ

### Q1 : Qu'est-ce qu'Aspose.Tasks pour .NET ?

A1 : Aspose.Tasks for .NET est une puissante API .NET qui permet aux développeurs de travailler avec des fichiers Microsoft Project par programme.

### Q2 : Puis-je personnaliser les attributs CSS lors de l'enregistrement de fichiers HTML avec Aspose.Tasks ?

A2 : Oui, vous pouvez définir des rappels de sauvegarde CSS pour personnaliser les attributs CSS en fonction de vos besoins.

### Q3 : Aspose.Tasks pour .NET est-il compatible avec toutes les versions des fichiers Microsoft Project ?

A3 : Aspose.Tasks pour .NET prend en charge différentes versions de fichiers Microsoft Project, garantissant ainsi la compatibilité entre différents environnements.

### Q4 : Où puis-je trouver une documentation complète pour Aspose.Tasks pour .NET ?

 A4 : Vous pouvez vous référer au[Documentation](https://reference.aspose.com/tasks/net/) pour des informations détaillées et des exemples.

### Q5 : Aspose.Tasks pour .NET offre-t-il une assistance aux développeurs ?

 A5 : Oui, vous pouvez obtenir l'assistance de la communauté Aspose.Tasks via le[forum](https://forum.aspose.com/c/tasks/15).