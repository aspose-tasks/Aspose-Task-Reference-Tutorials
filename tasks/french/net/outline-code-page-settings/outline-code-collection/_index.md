---
title: Collection MS Project de codes hiérarchiques dans Aspose.Tasks
linktitle: Collection de codes hiérarchiques dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment collecter les codes hiérarchiques Microsoft Project à l’aide d’Aspose.Tasks pour .NET. Ce didacticiel complet fournit des instructions étape par étape.
weight: 11
url: /fr/net/outline-code-page-settings/outline-code-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Collection MS Project de codes hiérarchiques dans Aspose.Tasks

## Introduction
Dans ce didacticiel, nous explorerons comment collecter les codes hiérarchiques Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Nous décomposerons le processus en instructions étape par étape pour garantir la clarté et la compréhension.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Visual Studio : installez Visual Studio sur votre système.
2.  Aspose.Tasks pour .NET : téléchargez et installez Aspose.Tasks pour .NET à partir de[ici](https://releases.aspose.com/tasks/net/).
3. Compréhension de base de la programmation C# : Une connaissance de C# sera bénéfique.

## Importer des espaces de noms
Tout d’abord, importez les espaces de noms nécessaires pour accéder à la fonctionnalité Aspose.Tasks dans votre projet C#.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Étape 1 : Charger le fichier de projet
 Commencez par charger le fichier Microsoft Project à l'aide du`Project` classe.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Étape 2 : Collecter les codes de plan
Créez un collecteur pour rassembler les codes hiérarchiques des tâches du projet.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Étape 3 : Parcourir les tâches et les codes hiérarchiques
Parcourez les tâches collectées et les codes hiérarchiques, en imprimant leurs détails.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Étape 4 : Ajouter une définition de code de plan personnalisé
Ajoutez une définition de code hiérarchique personnalisée au projet.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Étape 5 : Créer et insérer le code hiérarchique
Créez un code hiérarchique et insérez-le dans une tâche.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Étape 6 : Manipuler les codes hiérarchiques
Manipulez les codes hiérarchiques selon vos besoins, par exemple en les insérant, en les supprimant ou en les effaçant.
```csharp
// Exemple de manipulation
// ...
// Insérez le code avec 2 dans la bonne position
task.OutlineCodes.Insert(2, code2);
// Vérifiez si le code a été inséré
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Conclusion
Dans ce didacticiel, nous avons appris à collecter les codes hiérarchiques Microsoft Project à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez gérer efficacement les codes hiérarchiques au sein de vos projets, améliorant ainsi l'organisation et la clarté.
## FAQ
### Q : Puis-je utiliser Aspose.Tasks pour .NET avec d’autres langages de programmation ?
R : Oui, Aspose.Tasks for .NET cible principalement la plate-forme .NET, mais il prend également en charge d'autres langages de programmation via Aspose.Tasks for Cloud.
### Q : Existe-t-il des limitations sur la taille des fichiers de projet qu'Aspose.Tasks for .NET peut gérer ?
R : Aspose.Tasks pour .NET peut gérer efficacement des fichiers de projet volumineux, mais les performances peuvent varier en fonction de la complexité et de la taille du fichier.
### Q : Aspose.Tasks pour .NET est-il compatible avec les dernières versions de Microsoft Project ?
R : Oui, Aspose.Tasks for .NET prend en charge différentes versions de Microsoft Project, y compris les dernières.
### Q : Puis-je personnaliser le format de sortie lorsque je travaille avec Aspose.Tasks pour .NET ?
: Absolument, Aspose.Tasks pour .NET offre de nombreuses options pour personnaliser le format de sortie en fonction de vos besoins.
### Q : Où puis-je trouver une assistance ou des ressources supplémentaires pour Aspose.Tasks pour .NET ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour toute assistance ou question concernant Aspose.Tasks pour .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
