---
title: Définitions de gestion du code de plan MS Project dans Aspose.Tasks
linktitle: Gestion des définitions de code hiérarchique dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer les définitions de code hiérarchique MS Project à l'aide d'Aspose.Tasks pour .NET, renforçant ainsi vos applications de gestion de projet.
weight: 12
url: /fr/net/outline-code-page-settings/outline-code-definitions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définitions de gestion du code de plan MS Project dans Aspose.Tasks

## Introduction
Microsoft Project est un outil puissant pour gérer des projets et Aspose.Tasks pour .NET fournit une prise en charge complète pour la manipulation des fichiers de projet par programme. Un aspect essentiel de la gestion de projet consiste à organiser les tâches à l’aide de codes hiérarchiques. Dans ce didacticiel, nous explorerons comment gérer les définitions de code hiérarchique MS Project à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de nous lancer dans la mise en œuvre, assurez-vous de disposer des conditions préalables suivantes :
### 1. Installation d'Aspose.Tasks pour .NET
 Assurez-vous d'avoir installé Aspose.Tasks pour .NET dans votre environnement de développement. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
### 2. Compréhension de base de C# et .NET Framework
Familiarisez-vous avec le langage de programmation C# et le framework .NET car ce didacticiel nécessite des connaissances C# de niveau intermédiaire.
### 3. Environnement de développement intégré (IDE)
Installez un IDE tel que Visual Studio sur votre système pour le codage et le débogage.
## Importer des espaces de noms
Avant de commencer le codage, importons les espaces de noms nécessaires pour travailler avec Aspose.Tasks pour .NET.
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Maintenant, décomposons l'exemple fourni en plusieurs étapes pour une compréhension claire.
## Étape 1 : Charger le fichier de projet
Tout d'abord, nous devons charger le fichier MS Project dans notre application.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Étape 2 : Créer une définition de code hiérarchique
Créons maintenant une nouvelle définition de code hiérarchique.
```csharp
var outline = new OutlineCodeDefinition();
```
## Étape 3 : Définir le numéro et le nom du champ
Définissez le numéro de champ et le nom du code hiérarchique.
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## Étape 4 : définir le GUID et d’autres propriétés
Définissez le GUID et d’autres propriétés du code hiérarchique.
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## Étape 5 : Ajouter un masque de contour
Ajoutez un masque de plan au code de plan.
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## Étape 6 : définir d'autres propriétés
Définissez des propriétés supplémentaires du code hiérarchique.
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## Étape 7 : ajouter une valeur de plan
Enfin, ajoutons une valeur hiérarchique au code hiérarchique.
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## Conclusion
Dans ce didacticiel, nous avons appris à gérer les définitions de code hiérarchique MS Project à l'aide d'Aspose.Tasks pour .NET. En suivant le guide étape par étape, vous pouvez manipuler efficacement les codes hiérarchiques dans vos fichiers de projet par programme.
## FAQ
### Q1 : Puis-je utiliser Aspose.Tasks pour .NET avec différentes versions de fichiers MS Project ?
: Oui, Aspose.Tasks pour .NET prend en charge différentes versions de fichiers MS Project, notamment les formats MPP et XML.
### Q2 : Aspose.Tasks pour .NET est-il compatible avec .NET Core ?
R : Oui, Aspose.Tasks for .NET est compatible avec .NET Core, vous permettant de développer des applications multiplateformes.
### Q3 : Puis-je manipuler les affectations de ressources à l’aide d’Aspose.Tasks pour .NET ?
R : Oui, Aspose.Tasks pour .NET fournit des fonctionnalités étendues pour manipuler les affectations de ressources, notamment l'ajout, la mise à jour et la suppression d'affectations.
### Q4 : Aspose.Tasks pour .NET prend-il en charge la lecture des champs personnalisés à partir de fichiers MS Project ?
R : Absolument, Aspose.Tasks pour .NET prend en charge la lecture et l'écriture de champs personnalisés, y compris les codes hiérarchiques, à partir de fichiers MS Project.
### Q5 : Existe-t-il un forum communautaire pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez rejoindre le forum communautaire pour Aspose.Tasks pour .NET.[ici](https://forum.aspose.com/c/tasks/15) pour poser des questions, partager des connaissances et collaborer avec d'autres développeurs.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
