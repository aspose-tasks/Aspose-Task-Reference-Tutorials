---
title: Maîtrisez les tarifs MS Project avec Aspose.Tasks
linktitle: Collecte des tarifs dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les tarifs dans les fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. Tutoriel étape par étape pour une gestion efficace des ressources.
weight: 11
url: /fr/net/rate-recurring-tasks/rate-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtrisez les tarifs MS Project avec Aspose.Tasks

## Introduction
Bienvenue dans notre tutoriel sur la gestion des tarifs dans MS Project à l'aide d'Aspose.Tasks pour .NET ! Dans ce guide, nous vous guiderons tout au long du processus d'utilisation des taux dans vos fichiers MS Project à l'aide d'Aspose.Tasks. Que vous soyez un développeur chevronné ou que vous débutiez tout juste dans le développement .NET, ce didacticiel vous fournira des instructions étape par étape pour gérer efficacement les tarifs au sein de vos projets.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
### 1. Visual Studio installé
Assurez-vous que Visual Studio est installé sur votre système. Vous pouvez le télécharger depuis le site Web si ce n’est pas déjà fait.
### 2. Aspose.Tasks pour .NET
 Téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[site web](https://releases.aspose.com/tasks/net/).
### 3. Connaissance de base de C# et .NET
Familiarisez-vous avec le langage de programmation C# et les bases du framework .NET pour mieux comprendre les exemples de code fournis dans ce didacticiel.
## Importer des espaces de noms
Dans votre projet C#, importez les espaces de noms nécessaires pour utiliser les fonctionnalités Aspose.Tasks :
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Maintenant, décomposons chaque exemple en plusieurs étapes :
## Étape 1 : Charger un fichier MS Project
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Ici, nous créons un nouveau`Project` objet en chargeant un fichier MS Project existant.
## Étape 2 : ajouter une ressource et définir le travail et les tarifs
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Nous ajoutons une nouvelle ressource au projet, définissons son type comme travail, montant du travail et taux standard.
## Étape 3 : ajouter des tarifs à la ressource
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Nous ajoutons des tarifs à la ressource en spécifiant les dates de début et de fin, le tarif standard et le format du tarif.
## Étape 4 : Imprimer les informations sur les tarifs
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Cette étape imprime des informations sur les tarifs associés à la ressource.
## Étape 5 : Mettre à jour un tarif
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Nous mettons à jour la date de fin d'un tarif spécifique.
## Étape 6 : Supprimer les tarifs
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Cette étape supprime tous les tarifs d'un type spécifique.
## Étape 7 : Itérer sur les taux restants
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Enfin, nous parcourons les taux restants après la suppression.
## Conclusion
En conclusion, ce didacticiel vous a fourni un guide complet sur la gestion des tarifs dans les fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. En suivant les instructions étape par étape décrites dans ce didacticiel, vous pouvez gérer efficacement les tarifs au sein de vos projets, garantissant ainsi une gestion précise des ressources.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour .NET avec d’autres logiciels de gestion de projet ?
: Oui, Aspose.Tasks pour .NET prend en charge l'intégration avec divers logiciels de gestion de projet, notamment MS Project, Primavera, etc.
### Q : Aspose.Tasks pour .NET est-il compatible avec différentes versions de fichiers MS Project ?
R : Absolument, Aspose.Tasks pour .NET prend en charge l'utilisation de fichiers MS Project de différentes versions, garantissant ainsi flexibilité et compatibilité.
### Q : Aspose.Tasks pour .NET propose-t-il une documentation et une assistance ?
 R : Oui, vous pouvez trouver une documentation complète et accéder aux forums d'assistance sur Aspose.Tasks.[site web](https://reference.aspose.com/tasks/net/).
### Q : Puis-je essayer Aspose.Tasks pour .NET avant d'acheter ?
R : Oui, vous pouvez bénéficier d'un essai gratuit d'Aspose.Tasks pour .NET pour évaluer ses fonctionnalités et sa compatibilité avec vos besoins.
### Q : Comment puis-je acheter une licence pour Aspose.Tasks pour .NET ?
 R : Vous pouvez acheter une licence pour Aspose.Tasks pour .NET auprès du[site web](https://purchase.aspose.com/temporary-license/)qui offre des options de licence flexibles adaptées à vos besoins.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
