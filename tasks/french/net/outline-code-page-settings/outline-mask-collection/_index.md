---
title: Maîtrisez les masques de plan MS Project avec Aspose.Tasks
linktitle: Collection de masques de contour dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à manipuler les masques de plan de collection MS Project à l'aide d'Aspose.Tasks pour .NET. Améliorez la productivité avec ce didacticiel complet.
weight: 15
url: /fr/net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtrisez les masques de plan MS Project avec Aspose.Tasks

## Introduction
Cherchez-vous à exploiter la puissance des masques de plan de Microsoft Project à l’aide d’Aspose.Tasks pour .NET ? Vous êtes arrivé au bon endroit! Dans ce didacticiel complet, nous vous guiderons étape par étape tout au long du processus, vous assurant ainsi de bien comprendre comment manipuler efficacement les masques de contour dans vos projets. Que vous soyez un développeur chevronné ou que vous débutiez tout juste, ce guide vous fournira les connaissances et les compétences nécessaires pour optimiser votre flux de travail.
## Conditions préalables
Avant de vous lancer dans ce didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
### 1. Installation d'Aspose.Tasks pour .NET
Assurez-vous que Aspose.Tasks pour .NET est installé dans votre environnement de développement. Vous pouvez télécharger la bibliothèque depuis le site Web d'Aspose[ici](https://releases.aspose.com/tasks/net/).
### 2. Connaissance de base de C# et .NET Framework
Familiarisez-vous avec le langage de programmation C# et le .NET Framework, car ce didacticiel utilisera les deux.
### 3. Fichier de projet Microsoft
Préparez un fichier Microsoft Project (MPP) à des fins de test. Vous pouvez utiliser un fichier existant ou en créer un nouveau à des fins d'expérimentation.
## Importer des espaces de noms
Commençons par importer les espaces de noms nécessaires dans votre projet C#. Cette étape garantit que vous avez accès aux classes et fonctionnalités requises fournies par Aspose.Tasks for .NET.

Ajoutez les espaces de noms suivants au début de votre fichier de code :
```csharp
    using Aspose.Tasks;
    using System;
    
```
Maintenant, décomposons l'exemple fourni en plusieurs étapes et expliquons chaque étape en détail :
## Étape 1 : initialiser l'objet du projet
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Ici, nous créons une nouvelle instance du`Project` classe et chargez un fichier Microsoft Project existant nommé « OutlineValues2010.mpp ».
## Étape 2 : accéder aux codes hiérarchiques
```csharp
var outline = project.OutlineCodes[0];
```
Nous accédons aux codes hiérarchiques du projet. Les codes hiérarchiques sont des champs personnalisés dans Microsoft Project qui vous permettent de catégoriser et d'organiser les tâches.
## Étape 3 : Effacer les masques de contour
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Cette étape garantit que tous les masques de contour existants sont effacés avant de continuer.
## Étape 4 : Créer des masques de contour
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Nous créons de nouveaux masques de contour et spécifions leurs types. Dans cet exemple, nous créons un masque de contour valide et un mauvais.
## Étape 5 : Insérer et modifier des masques
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Ici, nous insérons un mauvais masque dans la collection et modifions la longueur d'un masque en utilisant son index.
## Étape 6 : Supprimer les masques
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Nous supprimons le mauvais masque de la collection en fonction de son index.
## Étape 7 : Itérer sur les masques
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Cette boucle parcourt chaque masque de contour de la collection et imprime ses propriétés telles que la longueur, le niveau, le séparateur et le type.
## Étape 8 : copier des masques vers un autre projet
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Enfin, nous copions les masques de contour d'un projet à un autre, garantissant ainsi la cohérence entre les différents projets.
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès à manipuler les masques de plan de collection MS Project à l'aide d'Aspose.Tasks pour .NET. En suivant ce didacticiel, vous disposez désormais des compétences nécessaires pour gérer efficacement les masques de plan dans vos projets, améliorant ainsi votre productivité et votre flux de travail.
## FAQ
### Q1 : Puis-je utiliser Aspose.Tasks pour .NET avec différentes versions de fichiers Microsoft Project ?
R : Oui, Aspose.Tasks pour .NET prend en charge différentes versions de fichiers Microsoft Project, notamment les formats MPP, MPT et XML.
### Q2 : Aspose.Tasks pour .NET est-il compatible avec .NET Core ?
R : Oui, Aspose.Tasks for .NET est compatible avec .NET Core, vous permettant de l'utiliser dans des applications multiplateformes.
### Q3 : Puis-je personnaliser les propriétés des masques de contour en fonction des exigences de mon projet ?
R : Absolument ! Vous pouvez personnaliser les masques de contour en ajustant leur longueur, leur niveau, leur séparateur et leur type en fonction des besoins spécifiques de votre projet.
### Q4 : Aspose.Tasks pour .NET fournit-il de la documentation et une assistance ?
 : Oui, Aspose.Tasks for .NET propose une documentation complète et une assistance dédiée via son site Web et[forums](https://forum.aspose.com/c/tasks/15).
### Q5 : Existe-t-il un essai gratuit disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez accéder à un essai gratuit d'Aspose.Tasks pour .NET depuis leur[site web](https://releases.aspose.com/tasks/net/). pour explorer ses caractéristiques et fonctionnalités avant de faire un achat.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
