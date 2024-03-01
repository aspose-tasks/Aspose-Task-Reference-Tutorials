---
title: Maîtriser les données de projet avec Aspose.Tasks
linktitle: Travailler avec des données de projet dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment manipuler les données Microsoft Project à l'aide d'Aspose.Tasks dans .NET. Créez des tâches, ajoutez des ressources et enregistrez facilement des projets.
type: docs
weight: 16
url: /fr/net/project-management-integration/project-data/
---
## Introduction
Dans ce didacticiel, nous explorerons comment utiliser les données Microsoft Project à l'aide de la bibliothèque Aspose.Tasks pour .NET. Aspose.Tasks fournit des fonctionnalités puissantes pour manipuler les fichiers de projet, notamment la création de tâches, l'ajout de ressources, la définition de propriétés et l'enregistrement de projets dans différents formats.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Installation de la bibliothèque Aspose.Tasks : téléchargez et installez la bibliothèque Aspose.Tasks à partir de[ici](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : assurez-vous d'avoir configuré un environnement de développement .NET.
3. Connaissance de base de C# : Une connaissance du langage de programmation C# sera bénéfique.

## Importer des espaces de noms
Avant de travailler avec Aspose.Tasks, importez les espaces de noms nécessaires dans votre projet :
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Étape 1 : initialiser l'objet du projet
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Cette ligne initialise une nouvelle instance du`Project` classe, qui représente un fichier Microsoft Project.
## Étape 2 : définir les propriétés du projet
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Ces lignes montrent comment définir les propriétés du projet telles que le format de travail et le mode de création de tâches.
## Étape 3 : ajout de tâches
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Ici, une nouvelle tâche nommée « Tâche 1 » est ajoutée à la tâche racine du projet.
## Étape 4 : Définition des propriétés de la tâche
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Ces lignes définissent la date de début, la durée et la date de fin de la « Tâche 1 ».
## Étape 5 : Ajouter des ressources
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Cette partie montre comment ajouter une ressource de travail au projet.
## Étape 6 : attribution de ressources aux tâches
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Ces lignes montrent comment affecter la ressource de travail précédemment ajoutée à la « Tâche 1 » avec des dates de début, de travail et de fin spécifiques.
## Étape 7 : Sauvegarde du projet
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Enfin, le projet est enregistré au format de fichier Microsoft Project XML.

## Conclusion
Dans ce didacticiel, nous avons appris à utiliser les données Microsoft Project à l'aide de la bibliothèque Aspose.Tasks dans .NET. En suivant le guide étape par étape, vous pouvez manipuler des fichiers de projet, ajouter des tâches, des ressources, attribuer des ressources aux tâches et enregistrer des projets dans différents formats.
## FAQ
### Q : Aspose.Tasks peut-il gérer des structures de projet complexes ?
R : Oui, Aspose.Tasks fournit une prise en charge complète des structures de projets complexes, vous permettant de gérer efficacement les tâches, les ressources et les affectations.
### Q : Aspose.Tasks est-il compatible avec différentes versions de Microsoft Project ?
: Aspose.Tasks prend en charge une large gamme de versions de Microsoft Project, garantissant ainsi la compatibilité entre différents environnements.
### Q : Puis-je intégrer Aspose.Tasks à d’autres bibliothèques .NET ?
R : Absolument, Aspose.Tasks s'intègre de manière transparente à d'autres bibliothèques .NET, offrant ainsi une flexibilité dans vos projets de développement.
### Q : Aspose.Tasks offre-t-il une prise en charge des algorithmes de planification de projet ?
R : Oui, Aspose.Tasks inclut des algorithmes de planification avancés pour vous aider à optimiser les délais de projet et l'utilisation des ressources.
### Q : Existe-t-il un forum communautaire pour les utilisateurs d'Aspose.Tasks ?
 R : Oui, vous pouvez trouver des ressources utiles et interagir avec d'autres utilisateurs d'Aspose.Tasks sur le site Web.[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).