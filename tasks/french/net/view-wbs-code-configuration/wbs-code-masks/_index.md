---
title: Configuration du code WBS étape par étape dans Aspose.Tasks .NET
linktitle: Configuration des masques de code WBS dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explorez la configuration étape par étape des masques de code WBS dans les projets .NET à l'aide d'Aspose.Tasks. Améliorez les capacités de gestion de projet sans effort.
weight: 14
url: /fr/net/view-wbs-code-configuration/wbs-code-masks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuration du code WBS étape par étape dans Aspose.Tasks .NET

## Introduction
Aspose.Tasks for .NET est une bibliothèque puissante qui permet aux développeurs de manipuler efficacement les données de gestion de projet dans les applications .NET. Dans ce didacticiel, nous explorerons le processus de configuration des masques de code WBS (Work Breakdown Structure) à l'aide d'Aspose.Tasks.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.Tasks pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir de[Aspose.Tasks pour la documentation .NET](https://reference.aspose.com/tasks/net/).
- Environnement de développement : assurez-vous d'avoir configuré un environnement de développement .NET fonctionnel.
- Répertoire de documents : choisissez un répertoire sur votre système pour stocker les fichiers du projet.
## Importer des espaces de noms
Dans votre projet .NET, incluez les espaces de noms nécessaires pour travailler avec Aspose.Tasks :
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Étape 1 : Créer une instance de projet
Commencez par créer une nouvelle instance de projet :
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Étape 2 : Définir la définition du code WBS
Configurez la définition du code WBS pour votre projet :
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Étape 3 : ajouter des masques de code WBS
Définissez les masques de code WBS et ajoutez-les au projet :
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Étape 4 : Créer des tâches
Ajoutez des tâches au projet :
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Étape 5 : Recalculer
Recalculez le projet pour vous assurer que les codes WBS sont appliqués correctement :
```csharp
project.Recalculate();
```
## Étape 6 : Afficher les informations du masque WBS
Afficher des informations sur les masques WBS sur la console :
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Étape 7 : Enregistrez le projet
Enregistrez le projet avec les codes WBS ajoutés :
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Toutes nos félicitations! Vous avez configuré avec succès les masques de code WBS dans votre projet Aspose.Tasks.
## Conclusion
Dans ce didacticiel, nous avons exploré le processus étape par étape de configuration des masques de code WBS à l'aide d'Aspose.Tasks pour .NET. Cette puissante bibliothèque offre aux développeurs un moyen transparent d'améliorer les capacités de gestion de projet au sein de leurs applications .NET.

## FAQ
### Puis-je utiliser Aspose.Tasks gratuitement ?
 Aspose.Tasks propose un essai gratuit, que vous pouvez télécharger[ici](https://releases.aspose.com/).
### Où puis-je trouver une assistance supplémentaire ?
 Visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien de la communauté.
### Comment puis-je obtenir un permis temporaire ?
 Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Existe-t-il une documentation détaillée disponible ?
 Oui, la documentation complète est disponible[ici](https://reference.aspose.com/tasks/net/).
### Où puis-je acheter Aspose.Tasks ?
 Acheter Aspose.Tasks[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
