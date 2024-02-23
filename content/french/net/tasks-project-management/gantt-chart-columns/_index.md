---
title: Personnaliser les colonnes du diagramme de Gantt avec Aspose.Tasks
linktitle: Colonnes du diagramme de Gantt dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment personnaliser les colonnes du diagramme de Gantt dans Aspose.Tasks pour .NET pour afficher efficacement des informations sur des tâches spécifiques.
type: docs
weight: 21
url: /fr/net/tasks-project-management/gantt-chart-columns/
---
## Introduction
Les diagrammes de Gantt sont un outil fondamental dans la gestion de projet, fournissant une représentation visuelle des tâches, des délais et des ressources. Aspose.Tasks for .NET offre de puissantes fonctionnalités pour manipuler les diagrammes de Gantt, notamment la personnalisation des colonnes pour afficher des informations sur des tâches spécifiques. Dans ce didacticiel, nous verrons comment utiliser les colonnes du diagramme de Gantt à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Installation : Aspose.Tasks pour .NET installé sur votre système. Sinon, téléchargez-le et installez-le depuis[ici](https://releases.aspose.com/tasks/net/).
2. Environnement de développement .NET : une connaissance pratique de C# et du framework .NET.
3. Exemple de fichier de projet : disposez d'un exemple de fichier Microsoft Project (`.mpp`) pratique pour expérimenter. Si vous n'en avez pas, vous pouvez créer un projet simple dans MS Project et l'enregistrer.

## Importer des espaces de noms
Tout d’abord, vous devez importer les espaces de noms nécessaires pour travailler avec Aspose.Tasks for .NET :
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Étape 1 : Charger le fichier de projet
 Chargez le fichier de projet à l'aide du`Project` classe fournie par Aspose.Tasks :
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Étape 2 : Définir les colonnes du diagramme de Gantt
Définissez les colonnes que vous souhaitez afficher dans le diagramme de Gantt. Vous pouvez spécifier des champs intégrés ou en créer des personnalisés :
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Étape 3 : Itérer sur les colonnes
Parcourez les colonnes définies pour accéder à leurs propriétés et afficher les informations :
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Étape 4 : Enregistrer le diagramme de Gantt au format CSV
Enregistrez le diagramme de Gantt avec les colonnes définies dans un fichier CSV :
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
En suivant ces étapes, vous pouvez travailler efficacement avec les colonnes du diagramme de Gantt dans Aspose.Tasks pour .NET, vous permettant ainsi de personnaliser et d'afficher les informations sur les tâches selon vos besoins.

## Conclusion
Maîtriser la manipulation des colonnes du diagramme de Gantt dans Aspose.Tasks pour .NET ouvre des possibilités infinies pour adapter les visuels de gestion de projet à vos besoins spécifiques. En suivant les étapes décrites dans ce didacticiel, vous pouvez gérer efficacement les informations sur les tâches et améliorer la clarté et l'organisation du projet.
## FAQ
### Q : Puis-je créer des colonnes personnalisées dans Aspose.Tasks pour .NET ?
R : Oui, vous pouvez définir des colonnes personnalisées pour afficher des attributs de tâches spécifiques en fonction des exigences de votre projet.
### Q : Aspose.Tasks pour .NET est-il compatible avec toutes les versions des fichiers Microsoft Project ?
R : Aspose.Tasks for .NET prend en charge différentes versions de fichiers Microsoft Project, garantissant ainsi la compatibilité entre différents environnements de projet.
### Q : Comment puis-je gérer des structures de projet complexes avec Aspose.Tasks pour .NET ?
R : Aspose.Tasks for .NET fournit des API et des fonctionnalités complètes pour gérer des structures de projets complexes, offrant flexibilité et évolutivité.
### Q : Existe-t-il des limites au nombre de colonnes que je peux ajouter à un diagramme de Gantt ?
R : Aspose.Tasks pour .NET offre des options de personnalisation étendues, vous permettant d'ajouter un nombre important de colonnes aux diagrammes de Gantt sans limitations.
### Q : Où puis-je trouver une assistance et des ressources supplémentaires pour Aspose.Tasks pour .NET ?
R : Vous pouvez explorer la documentation, les forums communautaires et les canaux d'assistance fournis par Aspose.Tasks for .NET pour accéder à des ressources et à une assistance complètes.