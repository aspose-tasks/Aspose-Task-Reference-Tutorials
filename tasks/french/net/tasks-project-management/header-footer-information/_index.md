---
title: Extraire les informations d'en-tête et de pied de page avec Aspose.Tasks
linktitle: Informations d’en-tête et de pied de page dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à extraire les informations d'en-tête et de pied de page des fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. Solution simple, efficace et conviviale pour les développeurs.
weight: 29
url: /fr/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraire les informations d'en-tête et de pied de page avec Aspose.Tasks

## Introduction
Aspose.Tasks for .NET est une bibliothèque puissante qui permet aux développeurs de manipuler facilement les fichiers Microsoft Project. Dans ce didacticiel, nous apprendrons comment récupérer les informations d'en-tête et de pied de page des fichiers MS Project à l'aide d'Aspose.Tasks.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1. Visual Studio : installez Visual Studio sur votre système.
2.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Connaissance de base de C# : Familiarité avec le langage de programmation C#.

## Importer des espaces de noms
Tout d’abord, vous devez importer les espaces de noms nécessaires dans votre projet C#. Cela vous permettra d'accéder aux classes et méthodes fournies par la bibliothèque Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Étape 1 : initialiser l'objet du projet
 Pour commencer, vous devez initialiser un`Project` objet en chargeant un fichier MS Project existant.
```csharp
// Le chemin d'accès au répertoire des documents.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Étape 2 : Récupérer les informations d’en-tête et de pied de page
 Une fois que vous avez chargé le fichier projet, vous pouvez récupérer les informations d'en-tête et de pied de page à l'aide du`PageInfo` propriété.
```csharp
var info = project.DefaultView.PageInfo;
// Informations d'en-tête
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Informations sur le pied de page
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
En suivant ces étapes simples, vous pouvez facilement récupérer les informations d'en-tête et de pied de page des fichiers MS Project à l'aide d'Aspose.Tasks pour .NET.

## Conclusion
Dans ce didacticiel, nous avons exploré comment extraire les informations d'en-tête et de pied de page des fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. Cette puissante bibliothèque simplifie la tâche de travail avec les fichiers de projet dans les applications C#, fournissant aux développeurs des outils de manipulation robustes.
### FAQ
### Puis-je modifier les informations d’en-tête et de pied de page à l’aide d’Aspose.Tasks ?
Oui, vous pouvez modifier les informations d'en-tête et de pied de page par programme à l'aide d'Aspose.Tasks pour .NET.
### Aspose.Tasks prend-il en charge d'autres formats de fichiers de projet en plus de MS Project ?
Oui, Aspose.Tasks prend en charge divers formats de fichiers de projet, notamment MPP, XML et MPX.
### Existe-t-il un essai gratuit disponible pour Aspose.Tasks ?
 Oui, vous pouvez télécharger un essai gratuit d’Aspose.Tasks à partir de[ici](https://releases.aspose.com/).
### Où puis-je trouver de la documentation pour Aspose.Tasks ?
 Vous pouvez trouver la documentation pour Aspose.Tasks[ici](https://reference.aspose.com/tasks/net/).
### Comment puis-je obtenir de l'aide pour Aspose.Tasks ?
 Vous pouvez obtenir de l'aide pour Aspose.Tasks en visitant le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
