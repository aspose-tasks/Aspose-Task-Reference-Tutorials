---
title: Gestion des affectations de ressources MS Project dans Aspose.Tasks
linktitle: Gestion des affectations de ressources dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer efficacement les affectations de ressources MS Project à l'aide d'Aspose.Tasks pour .NET. Ce document complet fournit des conseils étape par étape aux développeurs.
type: docs
weight: 11
url: /fr/net/resource-risk-analysis/resource-assignments/
---
## Introduction
Dans ce didacticiel, nous verrons comment gérer efficacement les affectations de ressources Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Aspose.Tasks est une API puissante qui permet aux développeurs de manipuler les fichiers Microsoft Project par programme. En suivant ces étapes, vous apprendrez à gérer efficacement les affectations de ressources au sein de vos applications .NET.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :

## Importer des espaces de noms
Tout d'abord, vous devez importer les espaces de noms nécessaires pour utiliser les fonctionnalités Aspose.Tasks dans votre projet .NET. Ceci comprend:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Décomposons maintenant l'exemple fourni en plusieurs étapes pour une compréhension complète de la façon de gérer les affectations de ressources MS Project à l'aide d'Aspose.Tasks.
## Étape 1 : Configurer les paramètres du projet et du calendrier
Pour commencer, créez une nouvelle instance de projet et configurez les paramètres de calendrier du projet :
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Étape 2 : ajouter une tâche au projet
Ensuite, ajoutez une nouvelle tâche à la tâche racine du projet :
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Étape 3 : Créer une affectation de ressources et générer des données chronologiques
Maintenant, créez une nouvelle affectation de ressources pour la tâche et générez des données chronologiques :
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Étape 4 : diviser la tâche
Divisez la tâche en plusieurs parties en indiquant les dates de début et de fin :
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Étape 5 : Définir le contour de travail
Définissez le type de contour de travail pour l'affectation :
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Étape 6 : Enregistrez le projet
Enfin, enregistrez le fichier projet avec les modifications apportées :
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Conclusion
En conclusion, la gestion des affectations de ressources Microsoft Project à l'aide d'Aspose.Tasks pour .NET est un processus simple. En suivant les étapes décrites dans ce didacticiel, vous pouvez gérer efficacement les affectations de ressources au sein de vos applications .NET.
## FAQ
### Aspose.Tasks peut-il gérer des structures de projet complexes ?
Oui, Aspose.Tasks fournit des fonctionnalités complètes pour gérer efficacement les structures de projets complexes.
### Aspose.Tasks est-il compatible avec différentes versions de Microsoft Project ?
Oui, Aspose.Tasks prend en charge différentes versions de Microsoft Project, garantissant la compatibilité entre différents environnements.
### Puis-je personnaliser les affectations de ressources en fonction d'exigences spécifiques ?
Absolument, Aspose.Tasks offre des options de personnalisation étendues pour les affectations de ressources afin de répondre aux besoins spécifiques du projet.
### Aspose.Tasks prend-il en charge l'exportation des données du projet vers d'autres formats ?
Oui, Aspose.Tasks permet d'exporter les données du projet vers différents formats tels que XML, PDF et HTML, entre autres.
### Le support technique est-il disponible pour les utilisateurs d'Aspose.Tasks ?
Oui, Aspose fournit une assistance technique dédiée via son forum et d'autres canaux pour aider les utilisateurs en cas de questions ou de problèmes.