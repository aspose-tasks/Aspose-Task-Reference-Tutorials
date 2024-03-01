---
title: Colonne d'affichage des affectations personnalisées dans Aspose.Tasks
linktitle: Colonne d'affichage des affectations personnalisées dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment ajouter des colonnes d'affichage d'affectation personnalisées dans Aspose.Tasks pour .NET afin d'améliorer les capacités de gestion de projet.
type: docs
weight: 16
url: /fr/net/advanced-features/assignment-view-column/
---
## Introduction

Dans ce didacticiel, nous allons explorer comment ajouter des colonnes personnalisées pour les vues d'affectation à l'aide d'Aspose.Tasks pour .NET. Les colonnes personnalisées offrent de la flexibilité et vous permettent d'afficher des informations supplémentaires pertinentes pour vos besoins en matière de gestion de projet.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Connaissance de base du langage de programmation C#.
2.  Aspose.Tasks pour la bibliothèque .NET installée. Sinon, vous pouvez le télécharger[ici](https://releases.aspose.com/tasks/net/).
3. Un environnement de développement intégré (IDE) tel que Visual Studio.

## Importer des espaces de noms

Tout d'abord, importons les espaces de noms nécessaires pour accéder aux classes et méthodes requises pour créer des colonnes de vue d'affectation personnalisée :

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Étape 1 : Charger le projet

 Pour commencer, chargez votre fichier de projet à l'aide du`Project` classe:

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Étape 2 : Créer des options d'enregistrement dans une feuille de calcul

 Ensuite, créez une instance de`Spreadsheet2003SaveOptions` ce qui nous permet de personnaliser les colonnes de la vue des affectations :

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Étape 3 : Définir une colonne personnalisée

 Maintenant, définissez votre colonne personnalisée en créant une instance de`AssignmentViewColumn`. Cette classe nécessite le nom de la colonne, sa largeur et une fonction déléguée pour convertir les données d'affectation en texte de colonne :

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Étape 4 : ajouter une colonne personnalisée aux options

Ajoutez la colonne personnalisée à la collection de colonnes d'affichage des affectations des options d'enregistrement :

```csharp
options.AssignmentView.Columns.Add(column);
```

## Étape 5 : Parcourir les affectations

Parcourez chaque affectation de ressource dans le projet et affichez le texte de la colonne personnalisée :

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Étape 6 : Enregistrez le projet avec des colonnes personnalisées

Enfin, enregistrez le projet avec les colonnes de la vue des affectations personnalisées :

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusion

Dans ce didacticiel, nous avons appris à ajouter des colonnes d'affichage d'affectation personnalisées à l'aide d'Aspose.Tasks pour .NET. Les colonnes personnalisées offrent une flexibilité dans l'affichage d'informations supplémentaires adaptées aux exigences de votre projet, améliorant ainsi les capacités de gestion de projet.

## FAQ

### Q1 : Puis-je ajouter plusieurs colonnes personnalisées à la vue des affectations ?

 A1 : Oui, vous pouvez ajouter plusieurs colonnes personnalisées en créant des instances supplémentaires de`AssignmentViewColumn` et en les ajoutant au`Columns` collection.

### Q2 : Existe-t-il des convertisseurs prédéfinis disponibles pour les champs d'affectation courants ?

A2 : Oui, Aspose.Tasks fournit des convertisseurs prédéfinis pour les champs d'affectation courants, facilitant ainsi l'extraction de données pour les colonnes personnalisées.

### Q3 : Puis-je personnaliser l'apparence des colonnes personnalisées, comme le formatage du texte ou l'application de styles ?

A3 : Oui, vous pouvez personnaliser l'apparence des colonnes personnalisées en modifiant les propriétés telles que la largeur, la police et l'alignement.

### Q4 : Est-il possible de supprimer les colonnes par défaut de la vue des affectations ?

 A4 : Oui, vous pouvez supprimer les colonnes par défaut en les excluant du`Columns` collection ou en mettant leur largeur à zéro.

### Q5 : Aspose.Tasks prend-il en charge l'exportation de projets vers d'autres formats que les feuilles de calcul avec des colonnes personnalisées ?

A5 : Oui, Aspose.Tasks prend en charge l'exportation de projets vers divers formats tels que PDF, HTML et XML, permettant des options de reporting de projet polyvalentes.