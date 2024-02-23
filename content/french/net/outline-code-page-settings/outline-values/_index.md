---
title: Maîtriser les valeurs générales de MS Project avec Aspose.Tasks
linktitle: Gestion des valeurs de plan dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer efficacement les valeurs de plan MS Project à l'aide d'Aspose.Tasks pour .NET. Personnalisez facilement les grandes lignes du projet.
type: docs
weight: 16
url: /fr/net/outline-code-page-settings/outline-values/
---
## Introduction
Dans ce didacticiel, nous explorerons comment gérer les valeurs vectorielles de Microsoft Project à l'aide de la bibliothèque Aspose.Tasks pour .NET. Avec Aspose.Tasks, vous pouvez facilement manipuler les codes hiérarchiques, créer de nouvelles valeurs hiérarchiques et personnaliser les contours du projet en fonction de vos besoins.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Installation d'Aspose.Tasks for .NET : Téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : assurez-vous d'avoir configuré un environnement de développement, tel que Visual Studio, avec la compatibilité du framework .NET.
3. Compréhension de base de la programmation C# : Familiarisez-vous avec les bases du langage de programmation C#, car nous utiliserons C# pour travailler avec la bibliothèque Aspose.Tasks.

## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre code C# :
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Étape 1 : Charger le fichier de projet
```csharp
// Le chemin d'accès au répertoire des documents.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Cette étape initialise un nouvel objet Project et charge le fichier Microsoft Project à partir du répertoire spécifié.
## Étape 2 : Définir les définitions du code hiérarchique
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Ici, nous définissons deux objets OutlineCodeDefinition et les ajoutons à la collection OutlineCodes du projet.
## Étape 3 : Définir le masque de contour
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Cette étape configure un OutlineMask pour la définition du code hiérarchique.
## Étape 4 : Créer des valeurs de plan
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
Dans cette étape, nous créons deux objets OutlineValue et définissons leurs propriétés telles que la valeur, l'ID de valeur, le type, la description et l'état de réduction.

## Conclusion
La gestion des valeurs vectorielles MS Project à l'aide d'Aspose.Tasks pour .NET est simple grâce aux fonctionnalités fournies. En suivant les étapes décrites dans ce didacticiel, vous pouvez manipuler efficacement les codes hiérarchiques et les valeurs pour personnaliser les contours du projet en fonction de vos besoins.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks avec d’autres frameworks .NET ?
: Oui, Aspose.Tasks est compatible avec divers frameworks .NET, garantissant ainsi la flexibilité de votre environnement de développement.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks ?
 R : Oui, vous pouvez accéder à une version d'essai gratuite d'Aspose.Tasks à partir de[ici](https://releases.aspose.com/).
### Q : Comment puis-je obtenir de l'aide pour Aspose.Tasks ?
 R : Pour obtenir de l'aide et de l'aide, vous pouvez visiter le forum Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
### Q : Puis-je acheter une licence temporaire pour Aspose.Tasks ?
 R : Oui, vous pouvez acheter une licence temporaire pour Aspose.Tasks auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je trouver une documentation détaillée pour Aspose.Tasks ?
 R : Vous pouvez vous référer à la documentation complète disponible[ici](https://reference.aspose.com/tasks/net/).