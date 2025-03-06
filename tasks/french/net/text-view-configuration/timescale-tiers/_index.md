---
title: Configuration des niveaux d'échelle de temps du diagramme de Gantt dans Aspose.Tasks
linktitle: Configuration des niveaux d'échelle de temps dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explorez Aspose.Tasks pour .NET pour configurer les niveaux d'échelle de temps dans votre vue Diagramme de Gantt pour une visualisation précise de la chronologie du projet. #Aspose.Tasks #MS Project
weight: 16
url: /fr/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuration des niveaux d'échelle de temps du diagramme de Gantt dans Aspose.Tasks

## Introduction
Dans le paysage dynamique de la gestion de projet, une visualisation efficace est cruciale pour comprendre les délais et les délais. Aspose.Tasks for .NET fournit un ensemble d'outils puissants et, dans ce didacticiel, nous explorerons comment configurer les niveaux d'échelle de temps pour une représentation optimale dans la vue Diagramme de Gantt. Suivez ces instructions étape par étape pour améliorer la visualisation de votre projet.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
- Connaissance de base de C# et .NET.
-  Aspose.Tasks pour la bibliothèque .NET installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/net/).
- Un environnement de développement configuré pour le développement d'applications .NET.
## Importer des espaces de noms
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Maintenant, décomposons chaque étape de l'exemple fourni.
## Étape 1 : initialiser le projet et ajouter des liens de tâches
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Ici, nous créons un projet et établissons des liens de tâches entre la « Tâche 1 » et la « Tâche 2 ».
## Étape 2 : configurer la vue du diagramme de Gantt
```csharp
var view = (GanttChartView)project.DefaultView;
```
Accédez à la vue Diagramme de Gantt pour la personnalisation.
## Étape 3 : Ajuster le niveau d’échelle de temps intermédiaire
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Personnalisez le niveau intermédiaire de l’échelle de temps pour afficher les semaines avec des étiquettes et un alignement spécifiques.
## Étape 4 : Ajouter le niveau supérieur d'échelle de temps
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Ajoutez un niveau d'échelle de temps supérieur pour représenter les mois.
## Étape 5 : Personnaliser les dates du niveau intermédiaire
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Personnalisez les étiquettes du mois pour une meilleure visualisation.
## Étape 6 : Définir le calendrier du projet
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Définissez l’échelle de temps du projet pour contrôler le calendrier global.
## Étape 7 : Enregistrez le projet avec une échelle de temps personnalisée
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Enregistrez le projet avec les paramètres d'échelle de temps définis.
## Conclusion
En conclusion, la configuration des niveaux d'échelle de temps dans Aspose.Tasks pour .NET permet une représentation plus personnalisée et visuellement attrayante des délais de projet. Ces étapes vous permettent de créer une vue Diagramme de Gantt qui répond précisément à vos besoins en matière de gestion de projet.
## FAQ
### Puis-je utiliser Aspose.Tasks avec d’autres bibliothèques .NET ?
Oui, Aspose.Tasks s'intègre de manière transparente à d'autres bibliothèques .NET, offrant une flexibilité dans votre pile de développement.
### Une licence temporaire est-elle disponible à des fins de test ?
 Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/) pour évaluation.
### Existe-t-il des options de personnalisation supplémentaires pour la vue Diagramme de Gantt ?
Absolument, Aspose.Tasks fournit des options de personnalisation étendues pour la vue Diagramme de Gantt afin de répondre aux diverses exigences du projet.
### Puis-je restituer les échelles de temps dans différents formats ?
Certes, vous pouvez explorer différents formats et styles de représentation d'échelle de temps afin de mieux s'adapter au contexte de votre projet.
### Existe-t-il un forum communautaire pour le support d'Aspose.Tasks ?
 Oui, visitez le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien et les discussions de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
