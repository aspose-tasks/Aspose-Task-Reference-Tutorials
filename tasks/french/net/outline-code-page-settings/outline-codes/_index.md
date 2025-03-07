---
title: Gérer les codes hiérarchiques du projet dans Aspose.Tasks pour .NET
linktitle: Gestion des codes hiérarchiques dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Apprenez à gérer les codes hiérarchiques MS Project avec Aspose.Tasks pour .NET. Simplifiez l’organisation du projet sans effort.
weight: 10
url: /fr/net/outline-code-page-settings/outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gérer les codes hiérarchiques du projet dans Aspose.Tasks pour .NET

## Introduction
Dans ce didacticiel, nous explorerons comment gérer les codes hiérarchiques Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Les codes hiérarchiques sont des champs personnalisés dans Microsoft Project qui permettent aux utilisateurs de catégoriser et d'organiser les tâches selon des critères spécifiques. Aspose.Tasks simplifie le processus de lecture et de manipulation de ces codes hiérarchiques par programme.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Bibliothèque Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[site web](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : configurez un environnement de développement approprié pour la programmation .NET, tel que Visual Studio.
3. Connaissance de base de C# : La connaissance du langage de programmation C# sera bénéfique pour comprendre les exemples de code.

## Importation d'espaces de noms
Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet C#. Cela vous permet d'accéder aux classes et méthodes fournies par la bibliothèque Aspose.Tasks.
1. Ouvrez Visual Studio : lancez votre IDE Visual Studio.
2. Créer un nouveau projet : démarrez un nouveau projet C# ou ouvrez-en un existant dans lequel vous avez l'intention d'utiliser Aspose.Tasks.
3. Ajouter une référence Aspose.Tasks : cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions, sélectionnez "Gérer les packages NuGet", recherchez "Aspose.Tasks" et installez la dernière version.
4. Importer l'espace de noms Aspose.Tasks : en haut de votre fichier C#, ajoutez la directive using suivante :
```csharp
using Aspose.Tasks;
using System;

```
## Étape 1 : Définir le répertoire des documents
Tout d’abord, définissez le chemin d’accès au répertoire contenant votre fichier MS Project.
```csharp
String DataDir = "Your Document Directory";
```
 Remplacer`"Your Document Directory"` avec le chemin réel de votre fichier de projet.
## Étape 2 : charger le fichier de projet
 Instancier un nouveau`Project` objet en chargeant le fichier MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Cela initialise l'objet du projet avec le fichier spécifié.
## Étape 3 : Lire les codes de plan
Parcourez toutes les tâches du projet et récupérez leurs codes hiérarchiques.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Cet extrait de code parcourt chaque tâche, vérifie si elle comporte des codes hiérarchiques et imprime des détails tels que l'ID de champ, le guide de valeur et l'ID de valeur pour chaque code hiérarchique associé à la tâche.

## Conclusion
En conclusion, Aspose.Tasks pour .NET offre de puissantes fonctionnalités pour gérer les codes hiérarchiques de Microsoft Project par programmation. En suivant les étapes décrites dans ce didacticiel, vous pouvez lire et manipuler efficacement les codes hiérarchiques dans vos fichiers MS Project à l'aide de C#.
## FAQ
### Q : Puis-je modifier les codes hiérarchiques à l’aide d’Aspose.Tasks ?
R : Oui, vous pouvez modifier les codes hiérarchiques par programme à l'aide d'Aspose.Tasks pour .NET. Accédez simplement aux codes hiérarchiques des tâches et mettez à jour leurs valeurs si nécessaire.
### Q : Aspose.Tasks est-il compatible avec toutes les versions de Microsoft Project ?
R : Aspose.Tasks prend en charge un large éventail de versions de Microsoft Project, notamment 2003, 2007, 2010, 2013, 2016 et 2019.
### Q : Aspose.Tasks nécessite-t-il une licence pour une utilisation commerciale ?
R : Oui, une licence valide est requise pour une utilisation commerciale d’Aspose.Tasks. Vous pouvez obtenir une licence sur le site Web Aspose.
### Q : Puis-je essayer Aspose.Tasks avant d'acheter ?
: Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Tasks à partir du site Web pour évaluer ses fonctionnalités et capacités.
### Q : Où puis-je obtenir de l'aide pour Aspose.Tasks ?
 R : Vous pouvez obtenir de l'aide pour Aspose.Tasks en visitant le forum à l'adresse[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Code source complet
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
