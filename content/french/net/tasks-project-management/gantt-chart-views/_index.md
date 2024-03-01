---
title: Maîtriser les vues de diagramme de Gantt dans Aspose.Tasks
linktitle: Vues de diagramme de Gantt dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment personnaliser les vues de diagramme de Gantt dans les fichiers Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Guide étape par étape pour une gestion de projet efficace.
type: docs
weight: 22
url: /fr/net/tasks-project-management/gantt-chart-views/
---
## Introduction
Les diagrammes de Gantt sont des outils puissants utilisés dans la gestion de projet pour visualiser les tâches, les délais et les dépendances. Aspose.Tasks pour .NET offre des fonctionnalités robustes pour travailler avec des vues de diagramme de Gantt dans les fichiers Microsoft Project. Dans ce didacticiel, nous verrons comment utiliser Aspose.Tasks pour manipuler les vues de diagramme de Gantt, personnaliser leur apparence et les enregistrer sous forme de fichiers PDF.
## Conditions préalables
Avant de continuer, assurez-vous que les conditions préalables suivantes sont remplies :
### 1. Installation d'Aspose.Tasks pour .NET
 Assurez-vous d'avoir installé Aspose.Tasks pour .NET. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/tasks/net/) et suivez les instructions d'installation fournies dans la documentation[ici](https://reference.aspose.com/tasks/net/).
### 2. Fichier de projet Microsoft
Préparez un fichier Microsoft Project (`Project2.mpp`) que vous utiliserez pour travailler avec les vues de diagramme de Gantt.
### 3. Connaissance de base de C# et .NET Framework
Ce didacticiel suppose que vous possédez une compréhension de base du langage de programmation C# et du framework .NET.
## Importer des espaces de noms
Avant de commencer à travailler avec les vues de diagramme de Gantt dans Aspose.Tasks, vous devez importer les espaces de noms nécessaires dans votre code C#. Voici comment procéder :

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Décomposons l'exemple de code fourni en plusieurs étapes et expliquons chaque étape en détail :
## Étape 1 : Charger le fichier de projet
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Cette étape implique le chargement du fichier Microsoft Project (`Project2.mpp` ) dans une instance du`Project` classe.
## Étape 2 : définir la date d'état
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Ici, nous fixons la date d'état du projet à sa date de début.
## Étape 3 : accéder à la vue Diagramme de Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Nous accédons à la vue diagramme de Gantt depuis le projet. Aspose.Tasks permet d'accéder à des vues telles que le diagramme de Gantt, le diagramme de réseau et l'utilisation des tâches.
## Étape 4 : Personnaliser la vue du diagramme de Gantt
Maintenant, personnalisons différents aspects de la vue du diagramme de Gantt :
### Définir l'arrondi de la barre
```csharp
view.BarRounding = false;
```
Ceci définit si les barres du diagramme de Gantt seront arrondies au jour le plus proche.
### Définir la taille de la barre
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Cela détermine la hauteur des barres du Gantt dans le diagramme.
### Masquer les barres de rollup
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Spécifie si les barres de cumul seront masquées lors du développement des tâches récapitulatives.
### Définir la couleur du temps non travaillé
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Définit la couleur des temps chômés sur le diagramme de Gantt.
### Rouler les barres du Gantt
```csharp
view.RollUpGanttBars = true;
```
Spécifie si les barres du diagramme de Gantt doivent être cumulées.
### Afficher les divisions de barre
```csharp
view.ShowBarSplits = true;
```
Détermine si les répartitions de tâches sur le diagramme de Gantt doivent être affichées.
### Afficher les dessins
```csharp
view.ShowDrawings = true;
```
Spécifie si les dessins du diagramme de Gantt doivent être affichés.
### Pourcentage de taille d’échelle de temps
```csharp
view.TimescaleSizePercentage = 10;
```
Définit un pourcentage pour ajuster l’espacement entre les unités sur le niveau de l’échelle de temps.
## Étape 5 : Enregistrer la vue du diagramme de Gantt au format PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Enfin, nous enregistrons la vue personnalisée du diagramme de Gantt sous forme de fichier PDF.
## Conclusion
Dans ce didacticiel, nous avons appris à utiliser les vues de diagramme de Gantt dans Aspose.Tasks pour .NET. En suivant les étapes fournies, vous pouvez manipuler et personnaliser efficacement les diagrammes de Gantt en fonction des exigences de votre projet.
## FAQ
### Q : Puis-je personnaliser davantage l’apparence des barres du diagramme de Gantt ?
R : Oui, Aspose.Tasks propose de nombreuses options pour personnaliser l'apparence des barres du diagramme de Gantt, notamment les couleurs, les formes et les tailles.
### Q : Aspose.Tasks est-il compatible avec différentes versions des fichiers Microsoft Project ?
R : Oui, Aspose.Tasks prend en charge différentes versions de fichiers Microsoft Project, notamment les formats MPP, MPT et XML.
### Q : Puis-je exporter des vues de diagramme de Gantt vers des formats autres que PDF ?
R : Absolument, Aspose.Tasks prend en charge l'exportation de vues de diagramme de Gantt vers plusieurs formats, notamment PNG, JPEG et XPS.
### Q : Aspose.Tasks offre-t-il une prise en charge des algorithmes de planification de projets complexes ?
R : Oui, Aspose.Tasks fournit des algorithmes de planification avancés pour gérer efficacement les calendriers de projets complexes.
### Q : Existe-t-il un forum communautaire où je peux demander de l'aide ou partager mes expériences avec Aspose.Tasks ?
 R : Oui, vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour interagir avec d'autres utilisateurs, poser des questions et trouver des solutions à vos requêtes.