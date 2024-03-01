---
title: Configuration des options d'affichage de MS Project dans Aspose.Tasks
linktitle: Configuration des options d'affichage du projet dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment configurer les options d'affichage de MS Project par programme à l'aide d'Aspose.Tasks pour .NET. Personnalisez l'apparence de votre projet sans effort.
type: docs
weight: 17
url: /fr/net/project-management-integration/project-display-options/
---
## Introduction
Microsoft Project propose une multitude d'options d'affichage pour personnaliser l'apparence de votre projet. Aspose.Tasks for .NET fournit un cadre robuste pour manipuler ces options par programme. Dans ce didacticiel, nous explorerons comment configurer les options d'affichage de MS Project à l'aide d'Aspose.Tasks.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
1.  Aspose.Tasks pour .NET : téléchargez et installez la bibliothèque à partir de[ici](https://releases.aspose.com/tasks/net/).
2. Fichier Microsoft Project : disposez d'un fichier MS Project valide (.mpp) prêt à appliquer les options d'affichage.
3. Connaissance de base de C# : Une connaissance du langage de programmation C# est requise.

## Importation d'espaces de noms
Tout d’abord, assurez-vous d’importer les espaces de noms nécessaires dans votre code C# :
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Étape 1 : Charger le fichier de projet
 Chargez le fichier MS Project à l'aide du`Project` classe fournie par Aspose.Tasks :
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Étape 2 : configurer les options d'affichage
Maintenant, configurons les différentes options d'affichage disponibles dans MS Project :
### Désactiver les avertissements de planification des tâches
Pour désactiver les avertissements en cas de conflits de planification avec des tâches planifiées manuellement (disponible pour Project 2010 et versions ultérieures) :
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Ajouter un espace avant l'étiquette
Définir pour ajouter un espace avant la valeur numérique et l'abréviation de l'heure :
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Configurer l'affichage des étiquettes pour les unités de temps
Personnalisez l'affichage des différentes unités de temps :
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Afficher la tâche récapitulative du projet
Afficher des informations récapitulatives sur l'ensemble du projet sur une seule ligne :
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Activer les suggestions de planification des tâches
Autoriser l'affichage de suggestions pour les conflits de planification avec les tâches planifiées manuellement :
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Souligner les hyperliens
Définir pour souligner les hyperliens au sein du projet :
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Étape 3 : Enregistrez le projet
Enfin, enregistrez le projet avec les options d'affichage appliquées :
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Conclusion
Dans ce didacticiel, nous avons appris à configurer les options d'affichage de MS Project à l'aide d'Aspose.Tasks pour .NET. Grâce à ces fonctionnalités, vous pouvez personnaliser efficacement l'apparence de vos fichiers de projet par programme.
## FAQ
### Q : Puis-je appliquer ces options d'affichage à des tâches spécifiques uniquement ?
R : Oui, vous pouvez appliquer de manière sélective des options d'affichage à des tâches individuelles à l'aide de l'API Aspose.Tasks.
### Q : Ces options d'affichage affectent-elles les données du projet sous-jacentes ?
: Non, ces options modifient uniquement la représentation visuelle du projet et n'altèrent pas les données sous-jacentes.
### Q : Ces options d'affichage sont-elles compatibles avec toutes les versions de Microsoft Project ?
R : Non, certaines options peuvent être spécifiques à certaines versions de MS Project. Reportez-vous à la documentation pour plus de détails sur la compatibilité.
### Q : Puis-je rétablir les options d'affichage aux paramètres par défaut ?
R : Oui, vous pouvez réinitialiser les options d'affichage à leurs valeurs par défaut à l'aide de l'API Aspose.Tasks.
### Q : Existe-t-il des limites à la personnalisation des options d'affichage par programmation ?
R : Bien qu'Aspose.Tasks offre des capacités de personnalisation étendues, certaines options d'affichage peuvent ne pas être accessibles par programme en raison des limitations du format de fichier MS Project.