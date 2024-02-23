---
title: Gestion des lignes de progression de MS Project avec Aspose.Tasks
linktitle: Gestion des lignes de progression dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à manipuler les lignes de progression dans les fichiers MS Project à l'aide d'Aspose.Tasks pour .NET, améliorant ainsi la visualisation et la gestion du projet.
type: docs
weight: 15
url: /fr/net/project-management-integration/progress-lines/
---
## Introduction
Microsoft Project (MS Project) est un outil puissant de gestion de projet, permettant aux utilisateurs de suivre différents aspects de leurs projets. Une caractéristique cruciale de MS Project est la capacité de visualiser les lignes de progression, qui aident les parties prenantes à comprendre l'état et la trajectoire du projet. Dans ce didacticiel, nous explorerons comment gérer les lignes de progression dans MS Project à l'aide de la bibliothèque Aspose.Tasks pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Visual Studio : installez Visual Studio ou tout autre environnement de développement .NET préféré.
2.  Aspose.Tasks pour .NET : téléchargez et installez Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Connaissance de base de C# : Une connaissance du langage de programmation C# sera bénéfique.

## Importation d'espaces de noms
Pour commencer, importons les espaces de noms nécessaires :
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Maintenant, décomposons chaque étape de la gestion des lignes de progression :
## Étape 1 : Charger le fichier de projet
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Ici, nous chargeons le fichier MS Project`Project2.mpp` et définissez sa date de statut.
## Étape 2 : définir la vue du diagramme de Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Nous convertissons la vue du projet en vue de diagramme de Gantt pour une manipulation ultérieure.
## Étape 3 : Définir les lignes de progression
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Nous initialisons les lignes de progression pour la vue diagramme de Gantt.
## Étape 4 : Configurer les paramètres de la ligne de progression
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Ici, nous définissons diverses propriétés pour les lignes de progression, telles que la couleur de la ligne, le motif, la police, etc.
## Étape 5 : Vérifier la configuration des lignes de progression
```csharp
// Paramètres des lignes de progression de sortie
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Afficher d'autres paramètres...
```
Nous produisons les paramètres configurés des lignes de progression pour vérification.
## Étape 6 : Enregistrez le fichier de projet
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Enfin, nous sauvegardons le fichier projet modifié avec les lignes de progression.

## Conclusion
Dans ce didacticiel, nous avons appris à gérer les lignes de progression de MS Project à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez personnaliser et visualiser efficacement les lignes de progression dans vos fichiers MS Project par programme.
## FAQ
### Q : Puis-je personnaliser davantage l’apparence des lignes de progression ?
R : Oui, vous pouvez ajuster diverses propriétés telles que la couleur des lignes, le motif et la police en fonction de vos besoins.
### Q : Aspose.Tasks prend-il en charge d'autres fonctionnalités de gestion de projet ?
: Oui, Aspose.Tasks fournit une prise en charge étendue pour manipuler divers aspects des fichiers MS Project, notamment les tâches, les ressources et les calendriers.
### Q : Puis-je intégrer Aspose.Tasks à d’autres bibliothèques .NET ?
R : Absolument, Aspose.Tasks est conçu pour s'intégrer de manière transparente à d'autres bibliothèques .NET, vous permettant d'améliorer davantage vos applications de gestion de projet.
### Q : Existe-t-il un forum communautaire pour le support d'Aspose.Tasks ?
 R : Oui, vous pouvez trouver des ressources utiles et demander de l'aide sur le forum Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15).
### Q : Aspose.Tasks propose-t-il des licences temporaires à des fins d'évaluation ?
 R : Oui, vous pouvez obtenir une licence temporaire pour évaluation auprès de[ici](https://purchase.aspose.com/temporary-license/).