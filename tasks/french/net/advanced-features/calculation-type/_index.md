---
date: 2026-03-24
description: Apprenez à configurer le calcul dans Aspose.Tasks pour .NET, avec des
  exemples pour calculer les valeurs récapitulatives, définir la formule de calcul
  et configurer le résumé de regroupement.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Comment définir le type de calcul dans Aspose.Tasks
url: /fr/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir le type de calcul dans Aspose.Tasks

## Introduction

Si vous devez **définir les règles de calcul** pour les tâches et les lignes de synthèse dans un fichier Microsoft Project, ce tutoriel vous montre exactement comment le faire en utilisant Aspose.Tasks pour .NET. Nous parcourrons un **exemple complet de type de calcul**, démontrerons comment **calculer les valeurs de synthèse**, et expliquerons comment **définir une formule de calcul** et **configurer le résumé de rollup** pour les attributs étendus. À la fin, vous serez capable d’ajouter une tâche à un projet, de définir une logique de calcul personnalisée et de contrôler le comportement de roll‑up en toute confiance.

## Réponses rapides
- **Quel est le but principal ?** Contrôler la façon dont les valeurs des tâches et des résumés sont calculées dans un fichier Project.  
- **Quelle classe API est utilisée ?** `ExtendedAttributeDefinition` avec `CalculationType` et `SummaryRowsCalculationType`.  
- **Puis-je utiliser une formule ?** Oui – définissez `CalculationType = CalculationType.Formula` et fournissez une chaîne de formule.  
- **Comment regrouper les valeurs de synthèse ?** Utilisez `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` et spécifiez un `RollupType` tel que `Average`.  
- **Ai-je besoin d’une licence ?** Une licence valide d’Aspose.Tasks est requise pour une utilisation en production.

## Qu'est-ce que le type de calcul et comment le définir ?

`CalculationType` indique à Aspose.Tasks comment calculer la valeur d’un attribut étendu. Vous pouvez choisir une valeur statique, une formule, ou laisser la bibliothèque regrouper les valeurs des tâches enfants. Définir correctement le calcul est essentiel lorsque vous souhaitez que le projet reflète des règles métier personnalisées sans mises à jour manuelles.

## Pourquoi utiliser le type de calcul pour calculer les valeurs de synthèse ?

Lorsqu’un projet contient des tâches de synthèse, vous avez souvent besoin que les lignes de synthèse affichent des données agrégées (par ex., coût total, durée moyenne). En configurant **calculer les valeurs de synthèse** via `SummaryRowsCalculationType` et `RollupType`, Aspose.Tasks peut automatiquement maintenir ces agrégats à jour lorsque vous modifiez les tâches individuelles.

## Prérequis

1. Connaissances de base en C# et du framework .NET.  
2. Visual Studio (toute version récente) installé sur votre machine.  
3. Bibliothèque Aspose.Tasks pour .NET installée – vous pouvez la télécharger depuis [ici](https://releases.aspose.com/tasks/net/).  
4. Accès à la documentation officielle d’Aspose.Tasks pour .NET pour référence, disponible [ici](https://reference.aspose.com/tasks/net/).

## Importer les espaces de noms

Before diving into the example, make sure to import the necessary namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Étape 1 : Créer un nouveau projet

Tout d'abord, nous créons un objet `Project` vide qui contiendra nos tâches et attributs personnalisés.

```csharp
var project = new Project();
```

## Étape 2 : Ajouter une tâche au projet

Nous **ajoutons des données de tâche au projet** en créant une tâche simple, en définissant sa date de début et en lui attribuant une durée d’un jour.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Étape 3 : Définir le type de calcul pour un attribut étendu (exemple de formule)

Ici nous créons une définition d’attribut étendu dont la valeur est calculée à partir d’une formule. Cela illustre un **exemple de type de calcul** et montre comment **définir une formule de calcul**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Étape 4 : Définir le type de calcul pour les lignes de synthèse (configurer le résumé de rollup)

Ensuite, nous créons une autre définition d’attribut étendu qui indique à Aspose.Tasks de **configurer le résumé de rollup** en utilisant le type de roll‑up *Average*. C’est la méthode typique pour **calculer les valeurs de synthèse** pour le coût, le travail ou les champs personnalisés.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Problèmes courants et dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| La formule renvoie `null` | Référence de champ incorrecte dans la formule | Vérifiez le nom du champ entre crochets (par ex., `[Start]` et non `[stARt]`). |
| Les lignes de synthèse affichent 0 | `SummaryRowsCalculationType` non défini ou `RollupType` incorrect | Assurez-vous que `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` et choisissez un `RollupType` approprié. |
| Le projet ne charge pas après l’ajout des attributs | Incohérence entre la définition de l’attribut et l’utilisation dans la tâche | Ajoutez la définition d’attribut **avant** de l’assigner à une tâche. |

## Conclusion

Dans ce tutoriel, nous avons couvert **comment définir les règles de calcul** dans Aspose.Tasks pour .NET, depuis la création d’une tâche simple jusqu’à la définition des types de calcul basés sur une formule et sur le roll‑up. En maîtrisant ces paramètres, vous obtenez un contrôle fin sur **le calcul des valeurs de synthèse**, permettant des analyses de projet plus riches sans travail manuel sur feuille de calcul.

## FAQ

### Q1 : Qu’est‑ce que le type de calcul dans Aspose.Tasks ?

R1 : Le type de calcul dans Aspose.Tasks détermine comment les valeurs sont calculées pour les tâches et les tâches de synthèse au sein d’un projet, offrant des options telles que Formula et Rollup.

### Q2 : Comment définir le type de calcul pour un attribut étendu ?

R2 : Vous pouvez définir le type de calcul pour un attribut étendu en définissant sa propriété CalculationType en conséquence.

### Q3 : Puis‑je personnaliser le type de calcul pour les lignes de synthèse dans un projet ?

R3 : Oui, Aspose.Tasks vous permet de spécifier le type de calcul pour les lignes de synthèse, vous permettant d’adapter le calcul des valeurs selon vos besoins.

### Q4 : Existe‑t‑il différents types de rollup disponibles pour le calcul des tâches de synthèse ?

R4 : Oui, Aspose.Tasks propose différents types de rollup tels que Average, Sum et Count pour calculer les valeurs des tâches de synthèse.

### Q5 : Où puis‑je trouver plus de ressources sur Aspose.Tasks pour .NET ?

R5 : Vous pouvez explorer la documentation et les forums de support communautaire disponibles sur le [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) pour des conseils complets et de l’assistance.

---

**Dernière mise à jour :** 2026-03-24  
**Testé avec :** Aspose.Tasks for .NET (latest release)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}