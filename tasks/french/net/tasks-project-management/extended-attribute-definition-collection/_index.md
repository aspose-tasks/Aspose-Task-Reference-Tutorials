---
title: Maître des définitions d'attributs étendus MS Project dans Aspose.Tasks
linktitle: Collection de définitions d'attributs étendues dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment gérer les définitions d'attributs étendus dans Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Personnalisez et améliorez les données de votre projet sans effort.
type: docs
weight: 14
url: /fr/net/tasks-project-management/extended-attribute-definition-collection/
---
## Introduction
Dans ce didacticiel, nous explorerons comment utiliser les définitions d'attributs étendus dans Microsoft Project à l'aide d'Aspose.Tasks pour .NET. Les attributs étendus offrent un moyen flexible de personnaliser et d'améliorer les données du projet, permettant aux utilisateurs d'ajouter des champs supplémentaires au-delà de ceux standard fournis par défaut. Avec Aspose.Tasks, vous pouvez gérer sans effort ces attributs étendus pour adapter vos besoins en matière de gestion de projet.
## Conditions préalables
Avant de continuer, assurez-vous que les prérequis suivants sont installés :
- [Cadre .NET](https://dotnet.microsoft.com/download)
-  Aspose.Tasks pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/tasks/net/).

## Importer des espaces de noms
Tout d’abord, vous devez importer les espaces de noms nécessaires pour accéder aux classes et méthodes Aspose.Tasks dans votre projet .NET. Suivez ces étapes:
## Étape 1 : Ouvrez votre projet .NET
Ouvrez votre projet .NET dans votre IDE préféré, tel que Visual Studio.
## Étape 2 : Ajouter un espace de noms Aspose.Tasks
Ajoutez la ligne suivante au début de votre fichier de code pour importer l'espace de noms Aspose.Tasks :
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Maintenant, décomposons les exemples de code fournis en plusieurs étapes pour une compréhension globale :
## Étape 1 : Charger le fichier du projet
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Étape 2 : Effacer les définitions d'attributs étendus existantes (facultatif)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Étape 3 : Créer et ajouter une définition d'attribut étendue pour une tâche
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Étape 4 : Parcourir les attributs étendus de la tâche
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Étape 5 : Créer et ajouter une définition d'attribut étendue pour une ressource
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Étape 6 : Insérer une définition d'attribut étendu de ressource
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Étape 7 : Supprimer un attribut étendu par index
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Conclusion
Dans ce didacticiel, nous avons couvert les bases de l'utilisation des définitions d'attributs étendus dans Microsoft Project à l'aide d'Aspose.Tasks pour .NET. En suivant ces étapes, vous pouvez gérer et personnaliser efficacement les attributs étendus pour répondre à vos exigences de gestion de projet.
## FAQ
### Q : Puis-je modifier les définitions d'attributs étendus existantes ?
R : Oui, vous pouvez modifier les définitions d'attributs étendus existantes ou en créer de nouvelles en fonction de vos besoins.
### Q : Les attributs étendus sont-ils pris en charge dans toutes les versions de Microsoft Project ?
R : Oui, les attributs étendus sont pris en charge dans la plupart des versions de Microsoft Project, y compris les plus récentes.
### Q : Puis-je utiliser des attributs étendus pour calculer des champs personnalisés ?
R : Absolument, les attributs étendus peuvent être utilisés pour calculer des champs personnalisés en fonction de critères spécifiques que vous définissez.
### Q : Aspose.Tasks est-il compatible avec d'autres frameworks .NET ?
R : Aspose.Tasks est compatible avec divers frameworks .NET, garantissant flexibilité et facilité d'intégration.
### Q : Où puis-je trouver plus de ressources et d'assistance pour Aspose.Tasks ?
 R : Vous pouvez visiter le[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pour obtenir de l'aide et explorer la documentation[ici](https://reference.aspose.com/tasks/net/).