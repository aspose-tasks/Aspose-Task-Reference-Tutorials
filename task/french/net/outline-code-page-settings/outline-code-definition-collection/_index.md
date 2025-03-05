---
title: Collection de définitions de code hiérarchique dans Aspose.Tasks .NET
linktitle: Collection de définitions de code hiérarchique dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment manipuler les définitions de code hiérarchique dans les documents Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Catégorisation des données de votre projet sans effort.
type: docs
weight: 13
url: /fr/net/outline-code-page-settings/outline-code-definition-collection/
---
## Introduction
Aspose.Tasks est une puissante bibliothèque .NET conçue pour manipuler les documents Microsoft Project avec facilité et efficacité. L'une de ses fonctionnalités clés est la possibilité de travailler avec des définitions de code hiérarchique, permettant aux utilisateurs d'organiser et de catégoriser efficacement les données du projet. Dans ce didacticiel, nous verrons comment utiliser les définitions de code hiérarchique à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
1. Compréhension de base de C# : Une connaissance du langage de programmation C# sera bénéfique.
2. Visual Studio : installez Visual Studio ou tout autre environnement de développement C# préféré.
3.  Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir de[ici](https://releases.aspose.com/tasks/net/).

## Importer des espaces de noms
Pour commencer, assurez-vous d'importer les espaces de noms nécessaires :
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Étape 1 : Charger un document Microsoft Project
Tout d'abord, chargez un document Microsoft Project pour commencer à travailler avec les définitions de code hiérarchique :
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Étape 2 : Accéder aux définitions du code hiérarchique
Passons maintenant aux définitions du code hiérarchique au sein du projet :
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Étape 3 : ajouter des définitions de code hiérarchique personnalisées
Vous pouvez ajouter des définitions de code hiérarchique personnalisées comme suit :
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Étape 4 : Modifier les définitions du code hiérarchique
Modifiez facilement les définitions de code hiérarchique existantes :
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Étape 5 : Supprimer les définitions de code hiérarchique
Supprimez les définitions de code hiérarchique lorsqu'elles ne sont plus nécessaires :
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Étape 6 : Enregistrer les modifications
Enfin, enregistrez vos modifications dans le document de projet :
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Conclusion
En conclusion, Aspose.Tasks pour .NET fournit des fonctionnalités complètes pour gérer les définitions de code hiérarchique dans les documents Microsoft Project. En suivant les étapes décrites dans ce didacticiel, vous pouvez manipuler efficacement les définitions de code hiérarchique pour organiser et catégoriser efficacement les données de votre projet.
## FAQ
### Q : Puis-je ajouter plusieurs définitions de code hiérarchique à un seul projet ?
 R : Oui, vous pouvez ajouter plusieurs définitions de code hiérarchique à un projet en fonction de vos besoins. Utilisez simplement le`Add` méthode pour chaque définition que vous souhaitez inclure.
### Q : Est-il possible de supprimer simultanément toutes les définitions de code hiérarchique d'un projet ?
 R : Oui, vous pouvez effacer toutes les définitions de code hiérarchique d'un projet à l'aide de l'outil`Clear` méthode.
### Q : Que se passe-t-il si j'essaie de modifier une définition de code hiérarchique en lecture seule ?
R : Si une définition de code hiérarchique est en lecture seule, vous ne pourrez pas la modifier directement. Vous devrez vérifier son statut en lecture seule avant de tenter toute modification.
### Q : Existe-t-il des limites quant au nombre de définitions de code hiérarchique que je peux ajouter à un projet ?
R : Aspose.Tasks pour .NET n'impose aucune limitation spécifique sur le nombre de définitions de code hiérarchique que vous pouvez ajouter à un projet. Cependant, tenez compte des implications en termes de performances lorsque vous travaillez avec un grand nombre de définitions.
### Q : Puis-je utiliser des définitions de code hiérarchique pour regrouper des tâches en fonction de critères personnalisés ?
R : Oui, les définitions de code hiérarchique vous permettent de catégoriser les tâches en fonction de critères personnalisés, offrant ainsi une flexibilité dans l'organisation des données du projet.## Code source complet