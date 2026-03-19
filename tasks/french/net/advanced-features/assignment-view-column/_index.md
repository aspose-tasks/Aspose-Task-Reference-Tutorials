---
date: 2026-03-19
description: Apprenez comment ajouter plusieurs colonnes personnalisées et formater
  la largeur des colonnes personnalisées lors de l'exportation d'un projet au format
  XML à l'aide d'Aspose.Tasks pour .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ajouter plusieurs colonnes personnalisées à la vue des affectations dans Aspose.Tasks
url: /fr/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter plusieurs colonnes personnalisées à la vue d'affectation dans Aspose.Tasks

## Introduction

Dans ce tutoriel, vous découvrirez **comment ajouter plusieurs colonnes personnalisées** à une vue d'affectation avec Aspose.Tasks pour .NET. Les colonnes personnalisées vous permettent d'afficher des données supplémentaires — telles que des notes, des coûts ou des indicateurs personnalisés — directement dans les rapports exportés. À la fin du guide, vous serez capable de définir la largeur d'une colonne personnalisée, d'exporter le projet au format XML et d'adapter la vue à vos besoins en gestion de projet.

## Quick Answers
- **What can I achieve?** Afficher n'importe quelle donnée d'affectation dans des colonnes personnalisées et contrôler leur apparence.  
- **Which format supports it?** Exporter le projet au format XML (ou d'autres formats) en utilisant `Spreadsheet2003SaveOptions`.  
- **Do I need a license?** Oui, une licence valide d'Aspose.Tasks est requise pour une utilisation en production.  
- **Which .NET versions work?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **How many columns can I add?** Illimité – il suffit de créer des instances supplémentaires de `AssignmentViewColumn`.

## What are multiple custom columns?
Les multiples colonnes personnalisées sont des champs définis par l'utilisateur qui apparaissent aux côtés des colonnes d'affectation par défaut lorsqu'un projet est enregistré ou exporté. Elles offrent la flexibilité d'exposer n'importe quelle propriété d'un objet `ResourceAssignment`, comme des notes personnalisées, des codes de coût ou des valeurs calculées.

## Why add multiple custom columns to the assignment view?
- **Enhanced reporting:** Inclure des informations spécifiques au projet qui ne sont pas couvertes par les colonnes intégrées.  
- **Better decision‑making:** Les parties prenantes peuvent voir exactement les données dont elles ont besoin sans fouiller dans les fichiers bruts.  
- **Consistent formatting:** Contrôler la largeur des colonnes et la conversion du texte pour obtenir une sortie propre et lisible.  

## Prerequisites

Avant de commencer, assurez‑vous d'avoir :

1. Des connaissances de base en langage de programmation C#.  
2. La bibliothèque Aspose.Tasks pour .NET installée. Si ce n'est pas le cas, vous pouvez la télécharger **[ici](https://releases.aspose.com/tasks/net/)**.  
3. Un environnement de développement intégré (IDE) tel que Visual Studio.  

## Step-by-Step Guide

### Step 1: Import Namespaces
Tout d'abord, importez les espaces de noms qui fournissent les classes nécessaires pour travailler avec les projets et les visualisations.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Step 2: Load the Project
Créez une instance `Project` et chargez un fichier MPP existant.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Step 3: Create Spreadsheet Save Options
Instanciez `Spreadsheet2003SaveOptions` – cet objet nous permet de personnaliser la vue d'affectation avant l'exportation.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Step 4: Define Custom Column
Créez un `AssignmentViewColumn` pour chaque donnée que vous souhaitez afficher. Ci‑dessous, nous ajoutons une colonne **Notes** avec une largeur de 200 points.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tip:** Pour ajouter *plusieurs* colonnes personnalisées, répétez cette étape avec des noms de champ différents et une logique de délégué, puis ajoutez chaque instance à `options.AssignmentView.Columns`.

### Step 5: Add Custom Column to Options
Ajoutez la colonne (ou les colonnes) à la collection `Columns` de la vue d'affectation.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Step 6: Iterate Through Assignments (Optional Debugging)
Vous pouvez parcourir les affectations pour vérifier que le texte de la colonne personnalisée est généré correctement.

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

### Step 7: Save the Project with Custom Columns
Enfin, enregistrez le projet. L'exemple sauvegarde au format XML, mais vous pouvez choisir n'importe quel format pris en charge.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## How to export project to XML with custom columns?
Lorsque vous appelez `project.Save` avec les `Spreadsheet2003SaveOptions` configurés, Aspose.Tasks écrit les données du projet — y compris toutes les **multiples colonnes personnalisées** — dans le fichier XML choisi. Cela facilite le partage d'informations de projet enrichies avec d'autres systèmes ou parties prenantes.

## Format custom column width for better readability
Le deuxième paramètre du constructeur `AssignmentViewColumn` contrôle la largeur de la colonne (mesurée en points). Ajustez cette valeur en fonction de la quantité de texte attendue. Par exemple, une largeur de **300** convient bien aux notes longues, tandis que **100** suffit pour de courts indicateurs.

## Common Issues and Solutions
- **Column text appears blank:** Assurez‑vous que le délégué renvoie une chaîne et que la propriété d'affectation sous‑jacente (par ex., `Asn.NotesText`) est remplie.  
- **Columns are not visible in the exported file:** Vérifiez que `options.AssignmentView.Columns` contient vos colonnes personnalisées avant d'appeler `Save`.  
- **Width seems ignored:** Certains formats d'exportation ont leurs propres règles de mise en page ; XML respecte la largeur, mais PDF/HTML peuvent nécessiter un style supplémentaire.

## Frequently Asked Questions

### Q1: Can I add multiple custom columns to the assignment view?
**A:** Oui, il suffit de créer des objets `AssignmentViewColumn` supplémentaires et de les ajouter à `options.AssignmentView.Columns`.

### Q2: Are there predefined converters available for common assignment fields?
**A:** Oui, Aspose.Tasks fournit des convertisseurs intégrés pour de nombreux champs standards, ce qui facilite l'extraction des données sans écrire de délégués personnalisés.

### Q3: Can I customize the appearance of custom columns, such as formatting text or applying styles?
**A:** Absolument. En plus de définir la largeur, vous pouvez modifier la police, l'alignement et d'autres propriétés visuelles via les options de style de la colonne.

### Q4: Is it possible to remove default columns from the assignment view?
**A:** Vous pouvez exclure les colonnes par défaut en les retirant de la collection `Columns` ou en définissant leur largeur à zéro.

### Q5: Does Aspose.Tasks support exporting projects to other formats besides spreadsheets with custom columns?
**A:** Oui, Aspose.Tasks peut exporter vers PDF, HTML, XML et de nombreux autres formats tout en conservant les définitions des colonnes personnalisées.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}