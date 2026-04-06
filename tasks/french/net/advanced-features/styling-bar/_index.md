---
date: 2026-04-06
description: Apprenez à modifier le style des barres et à personnaliser les couleurs
  des barres dans Aspose.Tasks pour .NET afin d'améliorer la visualisation du projet.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Barre de style dans Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Comment changer le style des barres dans Aspose.Tasks
url: /fr/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment modifier le style des barres dans Aspose.Tasks

## Introduction

Si vous devez **modifier l'apparence des barres** dans un fichier Microsoft Project, Aspose.Tasks pour .NET vous donne un contrôle complet sur les couleurs des barres, les formes et les styles de texte. En personnalisant les couleurs des barres et d’autres attributs visuels, vous pouvez rendre les plans de projet beaucoup plus faciles à lire et mieux alignés avec l’image de marque de votre organisation. Dans ce tutoriel, nous parcourrons un exemple complet, étape par étape, qui montre comment changer le style des barres, depuis le chargement d’un projet jusqu’à son exportation avec les nouvelles règles visuelles appliquées.

## Réponses rapides
- **Que puis‑je styliser ?** Barres, jalons et texte des tâches dans les diagrammes de Gantt.  
- **Quel format prend en charge les barres stylisées ?** PDF, XLSX, HTML et MPP natif lorsqu'il est enregistré avec `PdfSaveOptions`.  
- **Ai‑je besoin d’une licence ?** Une licence commerciale est requise pour une utilisation en production ; un essai gratuit suffit pour les tests.  
- **Puis‑je appliquer plusieurs styles ?** Oui – ajoutez autant d’objets `BarStyle` que nécessaire.  
- **Est‑il compatible .NET Core ?** Absolument – fonctionne avec .NET Framework et .NET Core/5/6+.

## Qu’est‑ce que le style des barres dans Aspose.Tasks ?

Le style des barres vous permet de définir des règles visuelles que le moteur Aspose.Tasks applique lors du rendu des diagrammes de Gantt. Chaque règle (un **BarStyle**) cible un type d’élément spécifique — tâches, jalons ou tâches récapitulatives — et vous laisse définir les couleurs, les formes et même du texte personnalisé.

## Pourquoi personnaliser les couleurs des barres ?

Personnaliser les couleurs des barres aide les parties prenantes à identifier instantanément les chemins critiques, les tâches en retard ou les jalons. Cela vous permet également d’harmoniser les rapports avec les palettes de couleurs de l’entreprise, donnant ainsi un aspect professionnel et conforme à la marque.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

1. **Aspose.Tasks for .NET** – téléchargez‑le depuis la [page de téléchargement](https://releases.aspose.com/tasks/net/).  
2. Un environnement de développement qui prend en charge .NET (Framework 4.6+, .NET Core 3.1+ ou version ultérieure).  
3. Une connaissance de base du C# – les exemples utilisent du code simple et autonome.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms contenant les classes que nous allons utiliser :

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Étape 1 : Charger le projet

Chargez un fichier MPP existant (ou créez‑en un nouveau) afin d’obtenir un objet projet avec lequel travailler :

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Étape 2 : Configurer les options d’enregistrement

Créez une instance de `PdfSaveOptions` et initialisez la collection `BarStyles` où nous stockerons nos styles personnalisés :

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Étape 3 : Définir le style de la barre

Nous construisons maintenant un objet `BarStyle` et définissons les propriétés qui contrôlent l’apparence de la barre. C’est ici que nous **personnalisons les couleurs et les formes des barres** :

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Étape 4 : Personnaliser le convertisseur de texte (facultatif)

Si vous souhaitez ajuster le texte affiché sur la barre, vous pouvez attribuer un convertisseur personnalisé. L’exemple préfixe les noms de tâches qui ne commencent pas déjà par « T » :

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

## Étape 5 : Ajouter le style de barre aux options

Ajoutez le style entièrement configuré à la collection `BarStyles` des options d’enregistrement :

```csharp
options.BarStyles.Add(style);
```

## Étape 6 : Enregistrer le projet

Enfin, exportez le projet. Le PDF (ou autre format) rendra le diagramme de Gantt en utilisant le style de barre que nous avons défini :

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Le style de barre n’est pas appliqué** | La collection `BarStyles` était vide ou n’était pas attachée aux options d’enregistrement. | Assurez‑vous d’ajouter le `BarStyle` à `options.BarStyles` avant d’appeler `Save`. |
| **Les couleurs apparaissent différemment dans le PDF** | Le rendu PDF peut utiliser un profil couleur différent. | Utilisez les valeurs standard `System.Drawing.Color` ou définissez des couleurs ARGB personnalisées. |
| **Le convertisseur de texte génère une référence nulle** | La propriété de tâche `Tsk.Name` est nulle pour certaines tâches. | Ajoutez une vérification de null avant d’accéder à `task.Get(Tsk.Name)`. |

## FAQ

### Q1 : Puis‑je appliquer plusieurs styles de barre à un même projet ?

R1 : Oui, vous pouvez définir et appliquer plusieurs styles de barre à différents types de tâches dans le même projet.

### Q2 : Est‑il possible de modifier dynamiquement les styles de barre pendant l’exécution ?

R2 : Oui, vous pouvez modifier dynamiquement les styles de barre en fonction de certaines conditions ou préférences utilisateur dans votre application.

### Q3 : Aspose.Tasks prend‑il en charge l’exportation de projets avec des barres stylisées vers différents formats de fichier ?

R3 : Oui, Aspose.Tasks prend en charge l’exportation de projets avec des barres stylisées vers divers formats tels que PDF, XLSX et HTML.

### Q4 : Existe‑t‑il des styles de barre prédéfinis dans Aspose.Tasks ?

R4 : Bien qu’Aspose.Tasks propose des styles de barre par défaut, les développeurs peuvent également créer des styles de barre personnalisés adaptés aux exigences de leur projet.

### Q5 : Puis‑je récupérer et modifier les styles de barre existants dans un projet via l’API ?

R5 : Oui, vous pouvez récupérer et modifier les styles de barre existants de façon programmatique en utilisant l’API Aspose.Tasks pour .NET.

## Questions fréquemment posées

**Q : Comment changer la couleur de la barre pour les tâches normales au lieu des jalons ?**  
R : Définissez `style.ItemType = BarItemType.Task;` et assignez `style.BarColor` à la `Color` souhaitée.

**Q : Puis‑je utiliser cette approche pour styliser les barres lors de l’exportation en HTML ?**  
R : Oui. Utilisez `HtmlSaveOptions` et remplissez sa collection `BarStyles` de la même manière.

**Q : Y a‑t‑il une limite au nombre de styles de barre que je peux définir ?**  
R : Pratiquement non ; vous pouvez en ajouter autant que nécessaire, mais gardez à l’esprit les performances pour des collections très volumineuses.

**Q : Dois‑je appeler `project.Calculate()` après avoir modifié les styles ?**  
R : Non, les styles sont appliqués lors de l’opération d’enregistrement ; le recalcul n’est nécessaire que pour les changements de planning.

**Dernière mise à jour :** 2026-04-06  
**Testé avec :** Aspose.Tasks 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}