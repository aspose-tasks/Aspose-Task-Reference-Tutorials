---
date: 2026-03-21
description: Apprenez à exporter une image et à gérer l'exception BitmapInvalidSizeException
  lors de l'enregistrement d'un projet en tant qu'image dans Aspose.Tasks pour .NET.
  Comprend les étapes pour enregistrer le projet en tant qu'image et exporter le projet
  au format PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Comment exporter une image et gérer l'exception de taille invalide
url: /fr/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment exporter une image – Gestion de l'exception de taille invalide du Bitmap dans Aspose.Tasks

Dans ce tutoriel, vous apprendrez **comment exporter une image** à partir d’un fichier Microsoft Project en utilisant Aspose.Tasks pour .NET et, surtout, comment intercepter l’`BitmapInvalidSizeException` qui peut survenir pendant le processus. Exporter un projet sous forme d’image est une exigence courante pour les tableaux de bord de reporting, la documentation ou simplement le partage d’une capture visuelle d’un planning. À la fin de ce guide, vous serez capable de **sauvegarder le projet en tant qu’image** de manière fiable et même **exporter le projet au format PNG** sans plantages inattendus.

## Réponses rapides
- **Quelle exception peut survenir lors de l’exportation d’une image ?** `BitmapInvalidSizeException`  
- **Quel format est utilisé dans l’exemple ?** PNG (`SaveFileFormat.Png`)  
- **Ai‑je besoin d’une licence spéciale ?** Une licence valide d’Aspose.Tasks est requise pour une utilisation en production.  
- **Puis‑je modifier l’échelle de temps ?** Oui – vous pouvez définir l’unité de l’échelle de temps (minutes, heures, jours, etc.).  
- **Le code est‑il compatible avec .NET Core ?** Absolument – la même API fonctionne sur .NET Framework et .NET Core.

## Qu’est‑ce que l’`BitmapInvalidSizeException` ?
`BitmapInvalidSizeException` est levée lorsque les dimensions du bitmap calculées pour l’image sont hors de la plage prise en charge (par ex., largeur ou hauteur égale à zéro ou dépassant les limites internes). Cela se produit généralement lorsque les paramètres d’échelle de temps ou de vue produisent une image trop grande ou trop petite.

## Pourquoi exporter un projet sous forme d’image ?
- **Reporting visuel** – intégrer un diagramme de Gantt dans des PDF, des documents Word ou des pages web.  
- **Partage multiplateforme** – les fichiers PNG peuvent être visualisés sur n’importe quel appareil sans nécessiter Microsoft Project.  
- **Performance** – les images sont légères comparées aux fichiers de projet complets pour des aperçus rapides.

## Prérequis
1. Connaissances de base en C# et développement .NET.  
2. Aspose.Tasks pour .NET installé (package NuGet `Aspose.Tasks`).  
3. Un fichier Microsoft Project d’exemple (par ex., `Blank2010.mpp`).  

## Importer les espaces de noms
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Guide étape par étape

### Étape 1 : Initialiser le projet et choisir une vue
Tout d’abord, créez une instance `Project` et choisissez la vue que vous souhaitez rendre (ici nous utilisons la première vue du diagramme de Gantt).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Étape 2 : Configurer les options d’enregistrement d’image (Exporter le projet au PNG)
Définissez le format d’image souhaité et indiquez à Aspose.Tasks d’utiliser l’échelle de temps définie dans la vue.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Étape 3 : Ajuster l’unité de l’échelle de temps (Contrôler la taille de l’image)
Modifier l’échelle de temps influence les dimensions du bitmap. Dans cet exemple, nous utilisons **les minutes** pour garder la taille de l’image gérable.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Étape 4 : Tenter de sauvegarder le projet en tant qu’image
Cette ligne exécute réellement l’opération **sauvegarder le projet en tant qu’image**.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Étape 5 : Capturer et gérer l’`BitmapInvalidSizeException`
Enveloppez l’appel de sauvegarde dans un bloc `try / catch` afin que votre application puisse réagir proprement si la taille du bitmap est invalide.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| Exception toujours levée après ajustement de l’échelle de temps | L’échelle de temps génère toujours un bitmap trop grand | Réduisez `view.MiddleTimescaleTier.Count` ou passez à une unité d’échelle plus grossière (`TimescaleUnit`, par ex., Heures). |
| Le fichier de sortie est vide | Chemin de fichier incorrect ou permissions d’écriture manquantes | Vérifiez que `DataDir` pointe vers un dossier accessible en écriture et que le nom de fichier se termine par `.png` si vous changez le format. |
| Qualité de l’image médiocre | DPI par défaut peut être faible | Définissez `options.DpiX` et `options.DpiY` à des valeurs plus élevées (par ex., 300). |

## Foire aux questions

**Q : Qu’est‑ce qui provoque l’`BitmapInvalidSizeException` dans Aspose.Tasks ?**  
R : Elle se produit lorsque les dimensions du bitmap calculées sont invalides – généralement parce que l’échelle de temps crée une image trop grande ou d’une largeur/hauteur nulle.

**Q : Puis‑je personnaliser l’échelle de temps lors de l’exportation d’une image ?**  
R : Oui. Vous pouvez modifier `view.MiddleTimescaleTier.Unit` et `Count` selon vos besoins, comme montré dans le tutoriel.

**Q : Aspose.Tasks prend‑il en charge d’autres formats d’image que le PNG ?**  
R : Absolument. `SaveFileFormat` comprend également JPEG, BMP, GIF et TIFF. Il suffit de changer la valeur de l’énumération dans `ImageSaveOptions`.

**Q : Une licence est‑elle requise pour exporter des images en environnement de production ?**  
R : Oui. Bien que la bibliothèque fonctionne en mode d’évaluation, une licence commerciale supprime les limitations d’évaluation et offre un support complet.

**Q : Comment améliorer la qualité du PNG exporté ?**  
R : Augmentez les paramètres DPI (`options.DpiX` et `options.DpiY`) ou ajustez l’échelle de temps de la vue pour produire un bitmap plus grand.

## Conclusion
En suivant les étapes ci‑dessus, vous savez maintenant **comment exporter une image** à partir d’un fichier Project, comment **sauvegarder le projet en tant qu’image**, et comment gérer proprement l’`BitmapInvalidSizeException`. Ces techniques renforcent vos pipelines de reporting et garantissent que les exportations visuelles fonctionnent de manière fiable quel que soit la taille du projet ou l’échelle de temps.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-21  
**Testé avec :** Aspose.Tasks 24.12 pour .NET  
**Auteur :** Aspose  

---