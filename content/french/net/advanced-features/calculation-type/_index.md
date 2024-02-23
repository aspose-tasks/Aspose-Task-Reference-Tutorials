---
title: Type de calcul dans Aspose.Tasks
linktitle: Type de calcul dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment personnaliser les calculs de valeurs dans les projets .NET avec Calculation Type dans la bibliothèque Aspose.Tasks.
type: docs
weight: 30
url: /fr/net/advanced-features/calculation-type/
---
## Introduction

Dans ce didacticiel, nous explorerons la fonctionnalité Type de calcul dans Aspose.Tasks pour .NET. Aspose.Tasks est une bibliothèque puissante qui permet aux développeurs .NET de travailler avec des fichiers Microsoft Project sans avoir besoin d'installer Microsoft Project sur leurs systèmes. Le type de calcul nous permet de définir la manière dont les valeurs sont calculées pour les tâches et les tâches récapitulatives au sein d'un projet.

## Conditions préalables

Avant de commencer, assurez-vous que vous disposez des prérequis suivants :

1. Connaissance de base de C# et du framework .NET.
2. Visual Studio installé sur votre système.
3.  Aspose.Tasks pour la bibliothèque .NET installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).
4.  Accès à la documentation Aspose.Tasks pour .NET pour référence, disponible[ici](https://reference.aspose.com/tasks/net/).

## Importer des espaces de noms

Avant de plonger dans l'exemple, assurez-vous d'importer les espaces de noms nécessaires :

```csharp
using Aspose.Tasks;
using System;


```

## Étape 1 : Créer un nouveau projet

Tout d'abord, créons un nouvel objet projet :

```csharp
var project = new Project();
```

## Étape 2 : Ajouter une tâche

Maintenant, ajoutons une tâche à notre projet :

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Étape 3 : Définir le type de calcul pour un attribut étendu

Nous allons créer une définition d'attribut étendue avec le type de calcul défini sur Formule :

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Étape 4 : Définir le type de calcul pour les lignes récapitulatives

Ensuite, nous allons créer une autre définition d'attribut étendue dans laquelle les valeurs des tâches récapitulatives sont calculées à l'aide du type de cumul Moyenne :

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment utiliser le type de calcul dans Aspose.Tasks pour .NET. En définissant des types de calcul pour les attributs étendus, nous pouvons personnaliser la façon dont les valeurs sont calculées pour les tâches et les tâches récapitulatives au sein d'un projet, offrant ainsi une plus grande flexibilité et un plus grand contrôle.

## FAQ

### Q1 : Qu'est-ce que le type de calcul dans Aspose.Tasks ?

A1 : Type de calcul dans Aspose.Tasks détermine la manière dont les valeurs sont calculées pour les tâches et les tâches récapitulatives au sein d'un projet, offrant des options telles que la formule et le cumul.

### Q2 : Comment définir le type de calcul pour un attribut étendu ?

A2 : Vous pouvez définir le type de calcul pour un attribut étendu en définissant sa propriété CalculationType en conséquence.

### Q3 : Puis-je personnaliser le type de calcul pour les lignes récapitulatives d'un projet ?

A3 : Oui, Aspose.Tasks vous permet de spécifier le type de calcul pour les lignes récapitulatives, vous permettant d'adapter les calculs de valeur en fonction de vos besoins.

### Q4 : Existe-t-il différents types de cumul disponibles pour les calculs de tâches récapitulatives ?

A4 : Oui, Aspose.Tasks propose différents types de cumul tels que Moyenne, Somme et Nombre pour calculer les valeurs des tâches récapitulatives.

### Q5 : Où puis-je trouver plus de ressources sur Aspose.Tasks pour .NET ?

 A5 : Vous pouvez explorer la documentation et les forums de support communautaire disponibles sur le[Aspose.Tasks pour .NET](https://reference.aspose.com/tasks/net/) pour des conseils et une assistance complets.