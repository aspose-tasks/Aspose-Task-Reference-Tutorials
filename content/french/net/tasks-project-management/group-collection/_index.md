---
title: Gestion des collections de projets dans Aspose.Tasks
linktitle: Gestion de la collecte de groupe dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer efficacement les collections MS Project à l'aide d'Aspose.Tasks pour .NET. Suivez notre guide étape par étape.
type: docs
weight: 26
url: /fr/net/tasks-project-management/group-collection/
---
## Introduction
Dans ce didacticiel, nous explorerons comment gérer les collections de groupe MS Project à l'aide d'Aspose.Tasks pour .NET. La gestion des collections de groupe est cruciale pour organiser et manipuler efficacement les tâches et les ressources au sein de votre projet.
## Conditions préalables
Avant de poursuivre ce didacticiel, assurez-vous de disposer des prérequis suivants :
1.  Bibliothèque Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[lien de téléchargement](https://releases.aspose.com/tasks/net/).
2. Connaissance de base de C# : Familiarisez-vous avec les bases du langage de programmation C#, car ce didacticiel implique le codage en C#.
3. Environnement de développement : configurez un environnement de développement tel que Visual Studio ou tout autre IDE prenant en charge le développement .NET.

## Importer des espaces de noms
Tout d’abord, importons les espaces de noms nécessaires pour utiliser les fonctionnalités Aspose.Tasks dans notre code C#.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Étape 1 : Charger le projet
```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Cette étape consiste à charger le fichier MS Project dans l'objet projet Aspose.Tasks, nous permettant d'effectuer des opérations dessus.
## Étape 2 : Itérer sur les groupes de tâches
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Ici, nous parcourons les groupes de tâches au sein du projet, en imprimant des détails tels que l'index, le nom et la visibilité dans le menu de chaque groupe.
## Étape 3 : Itérer sur les groupes de ressources
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
De même, cette étape parcourt les groupes de ressources, affichant leur index, leur nom et leur visibilité dans le menu.
## Étape 4 : Effacer et copier des groupes vers un autre projet
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Effacer les groupes d'autres projets
otherProject.TaskGroups.Clear();
// Copier les groupes vers un autre projet
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Ici, nous effaçons les groupes d'un autre projet, puis y copions les groupes du projet d'origine.
## Étape 5 : ajouter un groupe de tâches personnalisé
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
Dans cette étape, nous créons un groupe de tâches personnalisé et l'ajoutons à l'autre projet s'il n'est pas déjà présent.
## Étape 6 : Supprimer tous les groupes
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Enfin, nous supprimons tous les groupes de l'autre projet.

## Conclusion
La gestion des collections de groupe MS Project dans Aspose.Tasks pour .NET est essentielle pour organiser et manipuler efficacement les données du projet. En suivant les étapes décrites dans ce didacticiel, vous pouvez gérer efficacement les groupes de tâches et de ressources au sein de vos projets, améliorant ainsi la gestion globale du projet.
## FAQ
### Aspose.Tasks pour .NET est-il compatible avec toutes les versions de MS Project ?
Aspose.Tasks for .NET prend en charge différentes versions de Microsoft Project, notamment 2003, 2007, 2010, 2013, 2016 et 2019.
### Puis-je personnaliser les propriétés du groupe à l’aide d’Aspose.Tasks pour .NET ?
Oui, vous pouvez personnaliser les propriétés du groupe telles que le nom et la visibilité à l'aide d'Aspose.Tasks pour .NET.
### Aspose.Tasks pour .NET offre-t-il une compatibilité multiplateforme ?
Aspose.Tasks for .NET cible principalement le framework .NET, mais il peut être utilisé dans des scénarios multiplateformes avec .NET Core et .NET Standard.
### Comment puis-je obtenir de l’assistance pour Aspose.Tasks pour .NET ?
 Vous pouvez obtenir une assistance pour Aspose.Tasks pour .NET via le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Existe-t-il une version d’essai disponible pour Aspose.Tasks pour .NET ?
 Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks pour .NET à partir du[site web](https://releases.aspose.com/).