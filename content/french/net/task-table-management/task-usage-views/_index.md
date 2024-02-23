---
title: Maîtriser les vues d'utilisation des tâches dans Aspose.Tasks pour .NET
linktitle: Configurer les vues d'utilisation des tâches dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explorez Aspose.Tasks pour .NET et découvrez comment configurer les vues d'utilisation des tâches. Personnalisez les paramètres d’échelle de temps et améliorez les visuels de votre gestion de projet.
type: docs
weight: 24
url: /fr/net/task-table-management/task-usage-views/
---
## Introduction
Dans le domaine de la gestion de projet, la visualisation de l'utilisation des tâches est essentielle pour une planification et une exécution efficaces. Aspose.Tasks for .NET fournit une solution robuste pour le rendu des vues d'utilisation des tâches, vous permettant de personnaliser les paramètres d'échelle de temps et les formats de présentation. Dans ce didacticiel, nous passerons en revue les étapes de configuration des vues d'utilisation des tâches à l'aide d'Aspose.Tasks.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Aspose.Tasks pour .NET : assurez-vous que la bibliothèque Aspose.Tasks est intégrée à votre projet .NET. Vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/net/).
2. Environnement .NET : disposez d'un environnement .NET fonctionnel configuré sur votre ordinateur.
## Importer des espaces de noms
Dans votre projet .NET, importez les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Tasks. Ajoutez les lignes suivantes à votre code :
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Étape 1 : Définir le chemin du répertoire de documents
 Avant de travailler avec les fonctionnalités Aspose.Tasks, définissez le chemin d'accès à votre répertoire de documents. remplacer`"Your Document Directory"` avec le chemin réel.
```csharp
String DataDir = "Your Document Directory";
```
## Étape 2 : Charger le projet
 Initialiser les tâches Aspose.Tasks`Project` objet en chargeant votre fichier de projet (par exemple, TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Étape 3 : Définir les options de sauvegarde
 Créer un`SaveOptions`objet pour spécifier les options de rendu. Définissez l'échelle de temps sur « Jours » et le format de présentation sur « TaskUsage ».
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Étape 4 : Enregistrez avec l'échelle de temps en jours
Enregistrez le projet avec les paramètres d'échelle de temps prédéfinis de « Jours ».
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Étape 5 : Enregistrez avec l'échelle de temps ThirdsOfMonths
Modifiez les paramètres d'échelle de temps sur « ThirdsOfMonths » et enregistrez le projet.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Étape 6 : Économisez avec une échelle de temps de plusieurs mois
Définissez l'échelle de temps sur « Mois » et enregistrez le projet avec les paramètres mis à jour.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Conclusion
La configuration des vues d'utilisation des tâches avec Aspose.Tasks pour .NET est un processus simple. En personnalisant les paramètres d'échelle de temps, vous pouvez adapter la visualisation des tâches de votre projet en fonction de vos besoins spécifiques.
 N'hésitez pas à explorer plus de fonctionnalités et de fonctionnalités dans le[Documentation](https://reference.aspose.com/tasks/net/).
## Questions fréquemment posées
### Puis-je personnaliser l’échelle de temps au-delà des paramètres prédéfinis ?
Oui, vous pouvez définir une échelle de temps personnalisée en spécifiant les intervalles et les unités.
### Existe-t-il d'autres formats de présentation disponibles ?
Aspose.Tasks prend en charge divers formats de présentation, notamment GanttChart, ResourceUsage, etc.
### Aspose.Tasks est-il compatible avec différents formats de fichiers de projet ?
Oui, Aspose.Tasks prend en charge les formats de fichiers de projet populaires tels que MPP, XML et CSV.
### Puis-je appliquer différents paramètres d’échelle de temps à des tâches spécifiques ?
Absolument, vous pouvez personnaliser les paramètres d'échelle de temps pour des tâches individuelles au sein de votre projet.
### Comment puis-je obtenir de l'aide ou demander de l'aide pour Aspose.Tasks ?
 visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour le soutien et les conseils de la communauté.