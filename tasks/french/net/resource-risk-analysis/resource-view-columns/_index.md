---
title: Personnaliser les colonnes d'affichage des ressources MS Project dans Aspose.Tasks
linktitle: Personnalisation des colonnes d'affichage des ressources dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment personnaliser efficacement les colonnes de la vue des ressources MS Project à l'aide d'Aspose.Tasks pour .NET. Créez des vues personnalisées pour une meilleure gestion de projet.
weight: 17
url: /fr/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personnaliser les colonnes d'affichage des ressources MS Project dans Aspose.Tasks

## Introduction
Aspose.Tasks for .NET est une API puissante qui permet aux développeurs de travailler avec des fichiers Microsoft Project par programme. Une tâche courante dans la gestion de projet consiste à personnaliser les vues pour afficher des informations spécifiques. Dans ce didacticiel, nous explorerons comment personnaliser les colonnes de la vue des ressources MS Project à l'aide d'Aspose.Tasks pour .NET.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Aspose.Tasks pour la bibliothèque .NET : vous pouvez le télécharger à partir de[ici](https://releases.aspose.com/tasks/net/).
2. Fichier Microsoft Project : ayez un exemple de fichier MS Project à portée de main pour les tests.
3. Environnement de développement : un environnement de développement mis en place avec le framework .NET.
## Importer des espaces de noms
Tout d'abord, importons les espaces de noms nécessaires dans notre projet :
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Étape 1 : Charger le fichier de projet
Chargez le fichier MS Project à l'aide de l'API Aspose.Tasks :
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Étape 2 : obtenir des ressources et définir des options
Ensuite, récupérez la ressource dont vous souhaitez personnaliser les colonnes d'affichage et définissez les options d'enregistrement PDF :
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Étape 3 : Définir des colonnes personnalisées
Maintenant, définissez des colonnes personnalisées pour la vue des ressources. Vous pouvez spécifier différents champs et même utiliser des délégués pour des calculs personnalisés :
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Étape 4 : Itérer sur les colonnes
Parcourez les colonnes définies et affichez leurs propriétés :
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Étape 5 : Enregistrez la vue personnalisée
Enfin, définissez la vue personnalisée et enregistrez-la sous forme de fichier PDF :
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
En suivant ces étapes, vous pouvez personnaliser efficacement les colonnes d'affichage des ressources MS Project à l'aide d'Aspose.Tasks pour .NET.
## Conclusion
La personnalisation des colonnes d'affichage des ressources MS Project est essentielle pour afficher des informations pertinentes adaptées aux besoins de votre projet. Avec Aspose.Tasks pour .NET, cette tâche devient simple et efficace, vous permettant de créer des vues personnalisées sans effort.
## FAQ
### Puis-je personnaliser les vues pour d’autres éléments que les ressources ?
Oui, Aspose.Tasks permet également la personnalisation des tâches, des affectations et d'autres éléments du projet.
### Aspose.Tasks prend-il en charge l'enregistrement des vues dans des formats autres que PDF ?
Oui, vous pouvez enregistrer des vues dans différents formats tels que XLSX, HTML et images.
### Est-il possible d'appliquer un formatage à la vue personnalisée ?
Absolument, Aspose.Tasks propose des options de formatage étendues pour améliorer l'apparence de vos vues personnalisées.
### Puis-je mettre à jour dynamiquement la vue personnalisée en fonction de la modification des données du projet ?
Oui, vous pouvez mettre à jour et régénérer la vue personnalisée chaque fois que les données du projet sous-jacent changent.
### Aspose.Tasks prend-il en charge le développement multiplateforme ?
Aspose.Tasks pour .NET cible principalement les plates-formes .NET, mais il existe également des versions disponibles pour Java et d'autres plates-formes.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
