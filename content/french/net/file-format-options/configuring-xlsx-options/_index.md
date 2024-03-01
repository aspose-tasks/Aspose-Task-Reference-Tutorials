---
title: Configurer les options MS Project XLSX dans Aspose.Tasks pour .NET
linktitle: Configuration des options XLSX dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment configurer les options MS Project XLSX dans Aspose.Tasks pour .NET. Personnalisez les colonnes, l'encodage et bien plus encore sans effort.
type: docs
weight: 11
url: /fr/net/file-format-options/configuring-xlsx-options/
---
## Introduction
Microsoft Project (MS Project) est un outil puissant pour la gestion de projet, et Aspose.Tasks pour .NET offre une intégration transparente pour travailler avec les fichiers MS Project par programme. Dans ce didacticiel, nous passerons en revue le processus de configuration des options de MS Project XLSX à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
### 1. Aspose.Tasks pour .NET installé
 Assurez-vous que Aspose.Tasks pour .NET est installé dans votre environnement de développement. Sinon, vous pouvez le télécharger depuis le[Aspose.Tasks pour la page de téléchargement .NET](https://releases.aspose.com/tasks/net/).
### 2. Compréhension de base de C# et .NET Framework
Une connaissance du langage de programmation C# et du framework .NET est requise pour suivre ce didacticiel.
### 3. Fichier de projet Microsoft
Préparez un fichier Microsoft Project (MPP) que vous souhaitez configurer et enregistrer en tant que fichier XLSX.

## Importation d'espaces de noms
Pour commencer, importez les espaces de noms nécessaires :
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Étape 1 : Charger le projet
```csharp
var project = new Project("YourProjectFile.mpp");
```
Chargez le fichier Microsoft Project que vous souhaitez configurer.
## Étape 2 : définir XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Créer une instance de`XlsxOptions` pour configurer les paramètres d'enregistrement au format XLSX.
## Étape 3 : Ajouter des colonnes au diagramme de Gantt
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Ajoutez les colonnes du diagramme de Gantt souhaitées aux options.
## Étape 4 : ajouter des colonnes d'affichage des ressources
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Incluez les colonnes souhaitées pour la vue des ressources dans les options.
## Étape 5 : ajouter des colonnes de vue d'affectation
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Ajoutez les colonnes souhaitées pour la vue des affectations dans les options.
## Étape 6 : Définir l'encodage
```csharp
options.Encoding = Encoding.Unicode;
```
Définissez l'encodage du fichier de sortie.
## Étape 7 : Enregistrez le projet au format XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Enregistrez le projet avec les options configurées sous forme de fichier XLSX.

## Conclusion
Dans ce didacticiel, nous avons appris à configurer les options de MS Project XLSX à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez personnaliser le format de sortie en fonction de vos besoins, améliorant ainsi la flexibilité et la convivialité de votre flux de travail de gestion de projet.
## FAQ

### Q : Puis-je configurer séparément différentes colonnes pour le diagramme de Gantt, la vue des ressources et la vue des affectations ?

R : Oui, vous pouvez personnaliser les colonnes indépendamment pour chaque vue à l'aide d'Aspose.Tasks for .NET.

### Q : Existe-t-il une version d'essai disponible avant d'acheter Aspose.Tasks pour .NET ?

 R : Oui, vous pouvez télécharger un essai gratuit à partir du[Page Aspose.Tasks pour les versions .NET](https://releases.aspose.com/).

### Q : Comment puis-je obtenir de l'aide si je rencontre des problèmes ou si j'ai des questions lors de la mise en œuvre ?

 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir l’aide de la communauté et de l’équipe d’assistance Aspose.

### Q : Puis-je générer des fichiers XLSX avec Aspose.Tasks pour .NET sur des plates-formes non Windows ?

R : Aspose.Tasks for .NET est principalement conçu pour les plates-formes Windows, mais vous pouvez explorer les options de compatibilité pour d'autres plates-formes.

### Q : Existe-t-il des options de licence temporaire disponibles à des fins de test ?

 R : Oui, vous pouvez obtenir une licence temporaire auprès du[Page de licence temporaire Aspose.Tasks](https://purchase.aspose.com/temporary-license/).