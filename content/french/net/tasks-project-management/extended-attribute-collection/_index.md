---
title: Gérer la collection d'attributs MS Project dans Aspose.Tasks
linktitle: Gestion de la collection d'attributs étendus dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer efficacement les attributs étendus de MS Project à l'aide d'Aspose.Tasks pour .NET. Manipulez en toute transparence les attributs des tâches grâce à des conseils étape par étape.
type: docs
weight: 12
url: /fr/net/tasks-project-management/extended-attribute-collection/
---
## Introduction
Cherchez-vous à gérer efficacement les attributs étendus de MS Project à l’aide d’Aspose.Tasks pour .NET ? Dans ce didacticiel, nous vous guiderons étape par étape tout au long du processus. Allons-y !
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Visual Studio : installez Visual Studio sur votre système.
2.  Aspose.Tasks pour .NET : téléchargez et installez Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Connaissance de base de C# : Familiarisez-vous avec les bases du langage de programmation C#.

## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet :
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Étape 1 : Charger le fichier de projet
Tout d’abord, chargez le fichier MS Project à l’aide de l’extrait de code suivant :
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Étape 2 : accéder à la tâche et aux attributs étendus
Accédez à une tâche spécifique et à ses attributs étendus :
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Étape 3 : Effacer les attributs étendus
Effacez les attributs étendus existants si nécessaire :
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Étape 4 : Créer des définitions d'attribut étendues
Créez des définitions pour les nouveaux attributs étendus :
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Étape 5 : Itérer sur les attributs étendus de la tâche
Parcourez les attributs étendus de la tâche :
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Étape 6 : ajouter des attributs étendus
Ajoutez de nouveaux attributs étendus à la tâche :
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Étape 7 : Travailler avec des attributs étendus
Effectuez des opérations sur les attributs étendus selon les besoins.
## Étape 8 : Supprimer les attributs étendus
Supprimez les attributs étendus par index ou conditionnellement :
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Étape 9 : copier les attributs vers une autre tâche
Copiez les attributs vers une autre tâche au sein du même projet ou d'un projet différent :
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Conclusion
La gestion des collections d'attributs étendus MS Project devient transparente avec Aspose.Tasks pour .NET. En suivant les étapes décrites dans ce didacticiel, vous pouvez gérer efficacement les attributs étendus, améliorant ainsi vos capacités de gestion de projet.
## FAQ
### Q : Puis-je manipuler des attributs étendus sur plusieurs projets ?
R : Oui, vous pouvez copier des attributs étendus entre des tâches dans différents projets à l'aide d'Aspose.Tasks pour .NET.
### Q : Existe-t-il des limites sur le nombre d'attributs étendus par tâche ?
R : Aspose.Tasks pour .NET n'impose aucune limitation inhérente sur le nombre d'attributs étendus par tâche.
### Q : Puis-je créer des champs d'attributs étendus personnalisés ?
R : Absolument ! Aspose.Tasks for .NET vous permet de définir des champs d'attributs étendus personnalisés adaptés aux exigences de votre projet.
### Q : Aspose.Tasks pour .NET prend-il en charge la lecture et l'écriture dans des fichiers MS Project de différentes versions ?
R : Oui, Aspose.Tasks pour .NET prend en charge les formats de fichiers MS Project dans différentes versions.
### Q : Existe-t-il une version d'essai disponible pour Aspose.Tasks pour .NET ?
 R : Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).