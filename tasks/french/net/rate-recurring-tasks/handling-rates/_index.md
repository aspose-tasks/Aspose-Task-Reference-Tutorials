---
title: Gestion des tarifs MS Project avec Aspose.Tasks pour .NET
linktitle: Gestion des taux dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Maîtrisez facilement la gestion des tarifs MS Project à l’aide d’Aspose.Tasks pour .NET. Automatisez efficacement les tâches pour des flux de travail de projet plus fluides.
weight: 10
url: /fr/net/rate-recurring-tasks/handling-rates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestion des tarifs MS Project avec Aspose.Tasks pour .NET

## Introduction
Bienvenue dans notre didacticiel sur la gestion des taux MS Project à l'aide d'Aspose.Tasks pour .NET ! Dans ce guide, nous vous guiderons pas à pas tout au long du processus, afin que vous puissiez gérer efficacement les tarifs dans vos documents MS Project. Aspose.Tasks for .NET fournit des fonctionnalités puissantes pour manipuler les fichiers MS Project par programme, vous permettant de rationaliser vos tâches de gestion de projet sans effort.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1. Visual Studio installé : assurez-vous que Visual Studio est installé sur votre système.
2.  Bibliothèque Aspose.Tasks pour .NET : téléchargez et installez la bibliothèque Aspose.Tasks pour .NET. Vous pouvez trouver le lien de téléchargement[ici](https://releases.aspose.com/tasks/net/).
3. Compréhension de base de C# : Familiarisez-vous avec les principes fondamentaux du langage de programmation C#.
## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires dans votre projet C#. Ces espaces de noms donneront accès aux classes et méthodes requises pour gérer les taux MS Project.
## Étape 1 : Importer l’espace de noms Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
Maintenant, décomposons l'exemple fourni en plusieurs étapes et comprenons soigneusement chaque étape.
## Étape 1 : Charger le fichier de projet
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Dans cette étape, nous chargeons un fichier MS Project existant nommé "Project1.mpp" à l'aide du`Project` classe fournie par Aspose.Tasks.
## Étape 2 : Ajouter une ressource et définir le travail
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Ici, nous ajoutons une nouvelle ressource nommée « Ressource 1 » au projet et définissons son type sur « Travail ». Nous définissons également la durée de travail de cette ressource.
## Étape 3 : Définir le tarif standard
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
Au cours de cette étape, nous fixons le tarif standard de la ressource à 20 $ de l'heure.
## Étape 4 : Définir les périodes tarifaires
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Ici, nous définissons les périodes tarifaires pour la ressource. Le taux 1 est fixé du 1er janvier 2019 au 11 novembre 2019, avec des taux standard et des heures supplémentaires spécifiés.
## Étape 5 : Ajouter une autre période tarifaire
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
Dans cette dernière étape, nous ajoutons une autre période tarifaire allant du 12 novembre 2019 au 31 décembre 2019, avec un tarif standard et un coût par utilisation différents définis.
Toutes nos félicitations! Vous avez géré avec succès les tarifs MS Project à l’aide d’Aspose.Tasks pour .NET.
## Conclusion
La gestion des taux MS Project par programmation peut améliorer considérablement votre flux de travail de gestion de projet. Avec Aspose.Tasks pour .NET, vous avez le pouvoir d'automatiser efficacement les tâches de gestion des tarifs, économisant ainsi du temps et des ressources.
## FAQ
### Q : Aspose.Tasks peut-il gérer des structures de projet complexes ?
R : Oui, Aspose.Tasks fournit des fonctionnalités robustes pour gérer facilement des structures de projets complexes.
### Q : Aspose.Tasks est-il compatible avec toutes les versions des fichiers MS Project ?
R : Aspose.Tasks prend en charge différentes versions de fichiers MS Project, garantissant ainsi la compatibilité entre différentes plates-formes.
### Q : Puis-je modifier les tarifs existants dans un fichier MS Project à l'aide d'Aspose.Tasks ?
R : Absolument ! Aspose.Tasks vous permet de modifier les tarifs existants, d'ajouter de nouveaux tarifs et de les gérer dynamiquement.
### Q : Aspose.Tasks offre-t-il une prise en charge des calculs de taux personnalisés ?
R : Oui, vous pouvez mettre en œuvre des calculs de taux personnalisés à l'aide d'Aspose.Tasks pour répondre aux exigences spécifiques du projet.
### Q : Existe-t-il un forum communautaire ou une assistance disponible pour les utilisateurs d'Aspose.Tasks ?
 R : Oui, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)pour demander de l’aide et interagir avec d’autres utilisateurs.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
