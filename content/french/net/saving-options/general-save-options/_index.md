---
title: Maîtriser les options de sauvegarde de MS Project pour Aspose.Tasks
linktitle: Options générales d'enregistrement pour Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à enregistrer efficacement des fichiers MS Project à l'aide d'Aspose.Tasks pour .NET. Personnalisez facilement les options de sortie pour vos projets.
type: docs
weight: 17
url: /fr/net/saving-options/general-save-options/
---
## Introduction
Aspose.Tasks for .NET offre des fonctionnalités puissantes pour manipuler les fichiers Microsoft Project par programme. Dans ce didacticiel, nous aborderons les subtilités de l'enregistrement des fichiers MS Project à l'aide de diverses options fournies par Aspose.Tasks. Plus précisément, nous nous concentrerons sur les options de sauvegarde générales disponibles pour Aspose.Tasks, vous permettant d'adapter la sortie à vos besoins spécifiques.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des prérequis suivants :
1.  Installation d'Aspose.Tasks for .NET : Téléchargez et installez Aspose.Tasks for .NET à partir du[lien de téléchargement](https://releases.aspose.com/tasks/net/).
2. Compréhension de base de .NET Framework : une connaissance des concepts de programmation .NET est bénéfique.

## Importation d'espaces de noms
Avant de plonger dans le code, assurez-vous d'importer les espaces de noms nécessaires :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Étape 1 : Charger le fichier de projet
Tout d'abord, vous devez charger le fichier MS Project à l'aide d'Aspose.Tasks :
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Étape 2 : définir les options d'enregistrement
 Définissez les options de sauvegarde en fonction de vos besoins. Dans cet exemple, nous utilisons`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Étape 3 : Personnaliser les colonnes d'affichage
Vous pouvez personnaliser les colonnes d'affichage telles que le diagramme de Gantt, l'affichage des ressources et l'affichage des affectations. Voici comment ajouter des colonnes à chacune :
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Étape 4 : Enregistrez le projet avec les options
Enfin, enregistrez le projet avec les options spécifiées :
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusion
La maîtrise des options générales de sauvegarde de MS Project avec Aspose.Tasks pour .NET vous permet de personnaliser efficacement le format de sortie en fonction des besoins de votre projet.
## FAQ
### Q : Aspose.Tasks est-il compatible avec différentes versions de fichiers MS Project ?
R : Oui, Aspose.Tasks prend en charge différentes versions de fichiers MS Project, garantissant ainsi la compatibilité entre différents environnements.
### Q : Puis-je essayer Aspose.Tasks avant d'acheter ?
 R : Oui, vous pouvez explorer Aspose.Tasks avec un essai gratuit disponible[ici](https://releases.aspose.com/).
### Q : Où puis-je trouver de la documentation pour Aspose.Tasks ?
 R : Une documentation détaillée peut être trouvée[ici](https://reference.aspose.com/tasks/net/), fournissant des conseils complets sur l’utilisation des fonctionnalités d’Aspose.Tasks.
### Q : Comment puis-je obtenir des licences temporaires pour Aspose.Tasks ?
 R : Des licences temporaires sont disponibles à des fins d'évaluation[ici](https://purchase.aspose.com/temporary-license/).
### Q : Où puis-je demander de l'aide pour les requêtes liées à Aspose.Tasks ?
 R : Vous pouvez rejoindre le forum de la communauté Aspose.Tasks.[ici](https://forum.aspose.com/c/tasks/15)pour obtenir l'aide d'experts et d'autres développeurs.