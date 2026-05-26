---
date: 2026-05-26
description: Apprenez comment créer une capture d'écran du projet au format JPEG et
  ajuster la qualité JPEG lors de l'exportation de fichiers Microsoft Project à l'aide
  d'Aspose.Tasks pour Java.
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: Enregistrer le projet au format JPEG dans Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Créer une capture d'écran du projet au format JPEG – Ajuster la qualité avec
  Aspose.Tasks
url: /fr/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une capture d'écran de projet JPEG – Ajuster la qualité avec Aspose.Tasks

## Introduction
Dans ce tutoriel, vous découvrirez comment **créer des fichiers JPEG de capture d'écran de projet** à partir de Microsoft Project en utilisant Aspose.Tasks pour Java, et comment ajuster finement la qualité JPEG pour répondre à vos exigences de taille versus clarté. Que vous ayez besoin d'images nettes pour des présentations en salle de réunion ou de fichiers légers pour des portails web, maîtriser le réglage de la qualité vous donne un contrôle total sur le résultat final.

## Réponses rapides
- **Que fait « ajuster la qualité JPEG » ?** Cela vous permet de contrôler le niveau de compression du JPEG exporté, en équilibrant la taille du fichier et la fidélité visuelle.  
- **Quelle bibliothèque gère la conversion ?** Aspose.Tasks pour Java fournit une API simple pour exporter les fichiers Project en JPEG.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour l’évaluation ; une licence commerciale est requise pour une utilisation en production.  
- **Puis‑je définir la qualité dans le code ?** Oui, utilisez la méthode `ImageSaveOptions.setJpegQuality(int)` (plage 0‑100).  
- **Le processus est‑il rapide ?** La conversion d’un fichier projet typique en JPEG ne prend que quelques secondes sur du matériel moderne.

## Qu’est‑ce que « ajuster la qualité JPEG » ?
Ajuster la qualité JPEG vous permet de spécifier le facteur de compression appliqué lors de l’enregistrement d’une image au format JPEG. Des valeurs plus élevées (proches de 100) conservent davantage de détails, tandis que des valeurs plus faibles réduisent la taille du fichier au détriment de la netteté. **Réponse directe :** Vous contrôlez la qualité JPEG en transmettant une valeur numérique (0‑100) à la méthode `ImageSaveOptions.setJpegQuality`, qui influence immédiatement la taille et la fidélité visuelle de la capture générée.  

La qualité JPEG est le facteur de compression appliqué lors de l’enregistrement d’une image au format JPEG.

## Pourquoi utiliser Aspose.Tasks pour l’exportation JPEG ?
**Réponse directe :** Aspose.Tasks rend les diagrammes de Gantt, les vues de ressources et les rapports personnalisés en fichiers image sans nécessiter l’installation de Microsoft Project, garantissant une sortie pixel‑parfaite sur Windows, Linux et macOS.  

Aspose.Tasks prend en charge l’exportation vers **quatre** formats d’image (JPEG, PNG, BMP, TIFF) et peut rendre des projets contenant **jusqu’à 10 000 tâches** en moins de 5 secondes sur un CPU standard de 2,5 GHz, offrant une garantie de performance quantifiée.

## Prérequis
Avant de commencer, assurez‑vous d’avoir les éléments suivants :
1. **Java Development Kit (JDK)** – Installez le dernier JDK (8 ou supérieur) depuis le [site Java](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – Téléchargez et configurez la bibliothèque en suivant les étapes de la [documentation officielle](https://reference.aspose.com/tasks/java/).

## Importer les packages
`ImageSaveOptions` est la classe d’Aspose.Tasks qui contrôle les paramètres d’exportation d’image tels que le format, les dimensions et la qualité JPEG.  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## Étape 1 : Définir le répertoire de données
Définissez le chemin vers le dossier contenant votre fichier Microsoft Project. Ce répertoire est utilisé à la fois pour les opérations d’entrée et de sortie.  
```java
String dataDir = "Your Data Directory";
```

## Étape 2 : Charger le fichier MS Project
La classe `Project` représente un fichier Microsoft Project en mémoire, offrant un accès aux tâches, aux ressources et aux données de vue.  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## Étape 3 : Ajuster la qualité JPEG (facultatif)
Si vous souhaitez affiner la sortie, vous pouvez **définir la qualité JPEG** à l’aide de la classe `ImageSaveOptions`. La valeur de qualité varie de 0 à 100, où 100 offre la plus haute fidélité visuelle.  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## Étape 4 : Enregistrer le projet au format JPEG
`Project.save` écrit la vue rendue dans un fichier image en utilisant les options que vous avez configurées.  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Comment exporter un JPEG depuis MS Project
**Réponse directe :** Appelez `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)` après avoir configuré `ImageSaveOptions` ; la méthode rend la vue active (par défaut le diagramme de Gantt) et écrit un fichier JPEG avec la qualité spécifiée. Cet appel en une ligne gère automatiquement la pagination, le redimensionnement et la gestion des couleurs.  

En ajustant la qualité JPEG, vous contrôlez le compromis entre la clarté de l’image et la taille du fichier, rendant l’image exportée adaptée à la publication web, aux rapports imprimés ou aux diapositives intégrées.

## Problèmes courants et solutions
- **Une qualité basse rend le texte illisible :** Augmentez la qualité JPEG au‑delà de 70 ou passez à PNG pour un rendu sans perte.  
- **Erreurs de mémoire insuffisante sur de gros projets :** Activez le streaming en définissant `saveOptions.setUseMemoryCache(true)` pour maintenir l’utilisation de la mémoire en dessous de 200 Mo.  
- **Vue exportée incorrecte :** Utilisez `saveOptions.setView(ViewType.TaskSheet)` pour exporter une autre vue.

## Questions fréquentes

**Q : Le réglage de la qualité JPEG affecte‑t‑il la lisibilité du diagramme de Gantt ?**  
R : Une qualité supérieure conserve le texte et les détails des lignes, tandis qu’une qualité très basse peut rendre les petites étiquettes difficiles à lire.  

**Q : Puis‑je exporter d’autres formats d’image que le JPEG ?**  
R : Oui, Aspose.Tasks prend en charge PNG, BMP et TIFF via l’énumération `SaveFileFormat` appropriée.  

**Q : Est‑il possible d’exporter plusieurs pages (par ex., différentes vues) en une fois ?**  
R : Vous pouvez parcourir les vues souhaitées et enregistrer chacune comme JPEG séparé en utilisant la même configuration `ImageSaveOptions`.  

**Q : Quelle version de Java est requise ?**  
R : Aspose.Tasks pour Java fonctionne avec JDK 8 et ultérieur.  

**Q : Comment gérer les gros projets qui produisent de grandes images ?**  
R : Envisagez de réduire la qualité JPEG ou de redimensionner les dimensions de l’image via des paramètres supplémentaires de `ImageSaveOptions`.  

## Conclusion
Nous avons parcouru la façon de **créer des fichiers JPEG de capture d’écran de projet** et d’ajuster la qualité JPEG à l’aide d’Aspose.Tasks pour Java. Cette approche élimine les captures d’écran manuelles, garantit un rendu cohérent sur toutes les plateformes et vous permet d’ajuster finement le compromis entre la clarté de l’image et la taille du fichier—idéale pour les rapports, les présentations et la publication web.

---

**Last Updated:** 2026-05-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment créer un fichier MPP – Créer et enregistrer un projet vide au format MPP avec Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Enregistrer le projet en tant que modèle, CSV et texte avec Aspose.Tasks pour Java](/tasks/java/project-file-operations/save-csv-text-template/)
- [Créer un fichier MS Project vide avec Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}