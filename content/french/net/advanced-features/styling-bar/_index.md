---
title: Barre de style dans Aspose.Tasks
linktitle: Barre de style dans Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Découvrez comment styliser les barres dans Aspose.Tasks pour .NET pour améliorer la visualisation du projet.
type: docs
weight: 19
url: /fr/net/advanced-features/styling-bar/
---
## Introduction

Les barres de style dans Aspose.Tasks sont un aspect essentiel de la création de plans de projet visuellement attrayants. Grâce à la flexibilité offerte par l'API Aspose.Tasks, les développeurs peuvent personnaliser divers aspects des barres, tels que la couleur, la forme et le style du texte, pour améliorer la visualisation du projet. Dans ce didacticiel, nous allons explorer comment styliser les barres à l'aide d'Aspose.Tasks pour .NET, en décomposant chaque exemple en étapes gérables.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Bibliothèque Aspose.Tasks for .NET : téléchargez et installez la bibliothèque Aspose.Tasks for .NET à partir du[page de téléchargement](https://releases.aspose.com/tasks/net/).
2. Environnement de développement : configurez un environnement de développement avec la prise en charge du framework .NET.
3. Compréhension de base de C# : Une connaissance du langage de programmation C# sera bénéfique.

## Importer des espaces de noms

Tout d'abord, importons les espaces de noms nécessaires pour accéder aux classes et méthodes Aspose.Tasks :

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Étape 1 : Charger le projet

Pour commencer, chargez le fichier projet à l'aide de l'API Aspose.Tasks :

```csharp
// Le chemin d'accès au répertoire des documents.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Étape 2 : configurer les options d'enregistrement

Définissez les options d'enregistrement en précisant les styles de barres à appliquer :

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Étape 3 : Définir le style de barre

Créez un nouveau style de barre et personnalisez ses propriétés :

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Définir le type d'élément de barre
style.BarColor = Color.Green; // Définir la couleur de la barre
style.BarShape = BarShape.HalfHeight; // Définir la forme de la barre
style.StartShape = Shape.LeftBracket; // Définir la forme au début de la barre
style.StartShapeColor = Color.Aqua; // Définir la couleur de la forme de départ
style.EndShape = Shape.RightBracket; // Définir la forme au bout de la barre
style.EndShapeColor = Color.Aquamarine; // Définir la couleur de la forme finale
style.TextStyle = new TextStyle(); // Définir le style du texte
style.TextStyle.BackgroundColor = Color.Black; // Définir la couleur d'arrière-plan du texte
```

## Étape 4 : Personnaliser le convertisseur de texte

Vous pouvez éventuellement personnaliser le convertisseur de texte pour modifier le rendu du texte :

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Étape 5 : ajouter un style de barre aux options

Ajoutez le style de barre configuré aux options d'enregistrement :

```csharp
options.BarStyles.Add(style);
```

## Étape 6 : Enregistrez le projet

Enfin, enregistrez le projet avec les styles de barres appliqués :

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Conclusion

La personnalisation des styles de barres dans Aspose.Tasks pour .NET offre aux développeurs la possibilité de créer des plans de projet visuellement attrayants. En suivant les étapes décrites dans ce didacticiel, vous pouvez styliser efficacement les barres pour répondre aux exigences spécifiques de visualisation du projet.

## FAQ

### Q1 : Puis-je appliquer plusieurs styles de barres à un seul projet ?

A1 : Oui, vous pouvez définir et appliquer plusieurs styles de barres à différents types de tâches au sein du même projet.
   
### Q2 : Est-il possible de modifier dynamiquement les styles de barres pendant l'exécution ?

A2 : Oui, vous pouvez modifier dynamiquement les styles de barres en fonction de certaines conditions ou préférences utilisateur au sein de votre application.
   
### Q3 : Aspose.Tasks prend-il en charge l'exportation de projets avec des barres stylisées vers différents formats de fichiers ?

A3 : Oui, Aspose.Tasks prend en charge l'exportation de projets avec des barres stylisées vers différents formats tels que PDF, XLSX et HTML.
   
### Q4 : Existe-t-il des styles de barre prédéfinis disponibles dans Aspose.Tasks ?

A4 : Bien qu'Aspose.Tasks fournisse des styles de barre par défaut, les développeurs peuvent également créer des styles de barre personnalisés adaptés aux exigences de leur projet.
   
### Q5 : Puis-je récupérer et modifier les styles de barres existants dans un projet à l'aide de l'API ?

A5 : Oui, vous pouvez récupérer et modifier les styles de barres existants par programme à l'aide d'Aspose.Tasks pour l'API .NET.